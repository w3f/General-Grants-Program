# SubstraTEE for Scalability

A 2nd-layer protocol for substrate chains

## Project Overview

### Summary

SubstraTEE today provides a framework enabling confidentiality for substrate blockchains by leveraging Trusted Execution Environments (TEEs). The current version uses indirect invocation: All confidential transactions need to pass through the blockchain as a proxy to substraTEE workers in end-to-end encrypted form. This is necessary to get consensus on the ordering of transactions.

We now propose to improve scalability by orders of magnitude without compromising on confidentiality. We suggest a direct invocation architecture, such that individual transactions are directly sent to and processed by workers without touching the underlying layer one blockchain. Layer one will only be used as a registry of remote-attested TEEs and to provide finality to 2nd layer blocks.

SubstaTEE v0.6.5 already supports sharding of confidential state. Each shard has to be maintained by multiple workers to ensure redundancy. We now propose that each shard maintains its own asynchronous 2nd layer blockchain, a pruned sidechain with sub-second block times, validated by fully trusted TEEs.

![scaling layers](https://raw.githubusercontent.com/scs/substraTEE-book/master/src/fig/scaling-layers.svg)

### Benefit for Ecosystem

With this proposal, the Polkadot ecosystem gets a highly scalable 2nd layer for any substrate-based chain, parachain or parathread building on the SubstraTEE framework.

As known from previous versions of SubstraTEE, the 2nd layer is compatible with substrate pallets. Custom pallets written for layer one can simply be instantiated on the second layer - while still being able to trustlessly interact with layer one.

#### Encointer 

[Encointer](https://encointer.org), the first live use case of SubstraTEE, would benefit directly from this work in the following ways:

  * **scale to thousands of communities horizontally**, unaffected by the number of tx per community
  * **tx fees in relation to purchasing-power**: Encointer uses one shard per community currency. Today we need to charge tx fees on layer one which is not inclusive because of very different purchasing power among users globally. This proposal would allow encointer to charge tx fees in local currency per shard - thereby adjusting fees to local purchasing power.

#### Parathreading: Accessibility for low-capitalized projects

Becoming a parachain requires locking significant amounts of capital. With direct invocation, SubstraTEE can contribute an entirely new way to join the polkadot network. The SubstraTEE-node maintaining the worker registry would only need block updates if new workers want to join or if sidechains require finality. Parathread economics are perfectly suited for this because newly joining workers could spend DOTs on the relay chain in order to accelerate the next block for the SubstraTEE parathread. Or a user who awaits finality can also contribute DOTs in order to accelerate finality. Meanwhile, the Sidechains can produce blocks at a much higher frequency.

### History

SCS has developed SubstraTEE based on Intel SGX technology with a grant from the web3 foundation. After fulfilling the first grant with the delivery of M4, SCS continued the development on its own reaching M5, adding a private token transfer implementation that allows to instantiate pallet modules within an enclave. A further grant from w3f has been delivered and accepted (M6 & M7) enabling SubstraTEE to perform light client verifications inside the enclave to allow trustless reading of chain state from the enclave state transition function (STF) and verifying inclusion proofs for arbitrary extrinsics. The Encointer project has contributed the sharding feature.

## Technical Concept

Our proposal is a 2nd layer asynchronous sidechain that is validated by TEEs. Because we trust in the integrity of TEEs to execute the correct code, there is no need for a BFT consensus algorithm. However, we need multiple TEEs per sidechain in order to achieve both liveness and availability.

### Trusted Validator Coordination

![block production](https://raw.githubusercontent.com/scs/substraTEE-book/master/src/fig/sidechain-block-production.svg)

The sidechain validators produce blocks in round-robin order with a target block time T and broadcast them to the other validators. Should a validator fail to broadcast a block (or the block doesn’t reach the next validator) that validator is skipped after waiting for t = T*2^k where k is the number of missed blocks.
The target block time can be adaptive in the future. The larger the shard state grows, the longer block production will take because the entire state will have to be decrypted from disk into memory and back.

### Finality

Sidechain blocks are produced asynchronously to layer one at a higher block rate. Despite the TEEs’ integrity guarantees these blocks are not final because forks on the sidechain can happen. Every sidechain block hash is anchored to the layer one blockchain and gets finalized on layer one with the block that includes its anchoring extrinsic.

### Block Production

![sequence diagram](https://raw.githubusercontent.com/scs/substraTEE-book/master/src/fig/sidechain-sequence.svg)

Each SubstraTEE-worker (validator) maintains its transaction pool and provides an RPC interface for users to submit and watch their extrinsics targeted to a 2nd layer shard.

The block production logic is pretty similar to substrate but there are no block proposals. Blocks are directly imported and applied to the state because we trust the validators integrity. 
Upon its turn to produce a block, a validator forwards all ready transactions from the pool into the enclave. There is no block size limit as the chain can be pruned. There is, however, a block execution time limit. The enclave now loads the latest state, decrypts it and applies the STF on it for every extrinsic until either there are no extrinsics left or the execution time limit has been reached. 
The block is then broadcast to all other validators who apply all the changes to the state and prune their transaction pool.
During idle time, the enclave validates incoming transactions in batches (validate signature, nonce and ability to pay fees).  

## Detailed Tasks

### RPC interface for SubstraTEE worker

Currently (v0.6.5) the worker has a simplistic websocket interface to query confidential state with authentication. For direct invocation we would refactor this interface to use json-rpc in similar fashion like substrate does and we’d use familiar naming where it makes sense. The most important calls would be:

  * `author_submitAndWatchExtrinsic`
  * `author_submitExtrinsic`
  * `author_pendingExtrinsics`
  * `chain_subscribeAllHeads`
  * `rpc_methods`
  * `state_getMetadata`
  * `state_getRuntimeVersion`
  * `state_get` custom getter for either public data (permissionless) or private data (authenticated, only over wss://)
  * `system_health`
  * `system_name`
  * `system_version`

### Transaction Pool

This will mainly be code reuse from substrate. However, the definition of `TransactionStatus` would not include `Finalized` because finality will be provided on layer one. The finality status could in theory be provided by tracking the status of the confirmation on layer one. However, this shall be left for future work.
In a first iteration, there will be no gossiping of validated extrinsics among txpools. As sidechains are expected to be maintained by a handful of workers only, this will not be an issue for confirmation time.

### Batch Validation

Substrate validates the signature, the nonce and the ability to pay fees for every extrinsic before including it in a block proposal or even broadcasting it to other nodes.
SubstraTEE shall do the same. For performance reasons, this shall be done in batches because the task of validation (nonce and fee) requires the entire encrypted state to be loaded and decrypted in the enclave. As workers produce blocks in round-robin fashion, idle time is plannable and can be used for validation of extrinsics.

### Block Production

v0.6.5 processes all calls in a layer one block as a batch but confirms them separately. With our current proposal we suggest producing blocks at sub-second intervals and confirming block hashes only by sending one extrinsic per block to layer one .
We propose a simplified block format as we don’t need any light client proof capability (the signature of the block-producing enclave(s) is sufficient in our trust model)

|Field | Type | Comment |
|----|----|----|
|BlockNumber | u64 |  |
|ParentHash  | H256 |  |
|Timestamp  | i64
|LayerOneHead | H256 | needed because extrinsics can depend on layer one state |
| ShardIdentifier| H256 | |
| BlockAuthor | AccountId | must be registered on layer one as an enclave for the respective shard
| ExtrinsicHashes | Vec<H256>
| StateHashApriori | H256
| StateHashAposteriori | H256
| StateUpdate | encrypted vec of key-value pairs to update |
| BlockAuthorSignature | Signature

### Block Broadcasting and Inclusion

Our proposed sidechains are similar to PoA substrate chains. Authorities are well-known (registered and remote-attested enclaves on layer one). Unlike PoA, however, blocks do not need to be proposed and agreed upon by consensus. Workers trust each other because they have mutually remote-attested their SGX properties at one point (or regularly).
The block producer just broadcasts a new block to its peer when it is its turn. The others validate block consistency only and apply all the changes to their state without re-executing the included extrinsics.
In addition to this, the block production order of workers must be enforced on layer one where finality is reached. Workers have to adjust to the outcome if they happen to end up on an abandoned fork.

If the blockchain is pruned we need an onboarding mechanism for newly joining workers. Unlike the current implementation of SubstraTEE, the new worker can’t sync its shards on its own from genesis. We suggest pushing state snapshots to IPFS regularly so newly joining workers can sync quickly. Alternatively, existing workers could provide state snapshots on request directly to the newcomers over a bilateral communication channel.
These snapshots can also be used to roll back in the case of forks on the sidechain.

### Benchmark

We claim to provide a solution to dramatically improve the scalability of blockchains in both tps and confirmation time latency. A benchmark will be taken out in order to prove this claim and quantify the limits of the implementation. 
We would expect the single-shard performance to be in the order of substrate’s tps throughput but with much lower confirmation times. It is further expected that horizontally scaling to multiple independent shards will be approximately linear until the block confirmations by themselves congest layer one. Empirically quantifying the amount of shards that can be served by a single polkadot parachain would be too much effort and is out of scope. Instead, we will provide a theoretical estimate of total tps based on the number and complexity of layer one extrinsics.

#### single-shard performance

  * 3 workers on 3 Intel SGX machines in at least two different locations.
  * layer one is a local testnet (not relevant for this test)
  * send extrinsics (balance transfers) to all three workers at increasing frequency. monitor txpool and confirmation time ( `Ready`, `InBlock` ).
    * No state queries
    * No dependency on layer one state
  * Repeat and add state queries (`TrustedGetter`) after each `InBlock` over RPC.

## Ecosystem Fit

Another similar project in the web3 ecosystem is Phala which also works with Intel SGX to provide confidentiality. While Phala currently puts a focus on providing solutions for specific use cases, SubstraTEE is a generic framework, maximizing compatibility with substrate pallets.

To our best knowledge, Our proposal is not covered by any other project.

* Alain Brenzikofer: @brenzi on github, Department Head, Developer
* Marcel Frei: @electronix on github, Project Manager for substraTEE, Developer
* Sabine Proll: @sabinep, Developer
* Juraj Skripsky: @jskripsky on github, Rust-Guru, Reviewer

## Team Website

* https://www.scs.ch/en/about-scs/departments/decentralized-systems/

## Legal Structure

Swiss AG

## Team's experience

As an engineering services company SCS AG has more than 25 years of experience in the fields of electronics, software and system design. Profound know-how, solid methodological competence as well as efficient project management are the foundation of our success.

Most programming experience in the following languages: C/C++, C#, Java, Python and VHDL.

Alain Brenzikofer follows Blockchain developments since 2011. He works for SCS since 2012 where he started working on blockchain projects in 2016 and was appointed to lead a new department for "decentralized systems" in summer 2018. As a private initiative, he designed a new cryptocurrency ecosystem [encointer - An Ecological, Egalitarian and Private Cryptocurrency and Self-Sovereign Identity System](https://encointer.org) . A project he currently intends to realize based on Substrate (including this privacy extension).

Our team is part of the [Quartierstrom project](https://quartier-strom.ch), implementing and currently field-testing a decentralized P2P energy market in Switzerland together with ETHZ, Bosch IoT Lab, HSLU and others.
SCS is in charge of the development of a dynamic grid usage-tariff smart contract as well as privacy-by-design concepts for the decentralized energy auction, thereby investigating and evaluating Zero-Knowledge Proofs, Linkable Ring Signatures, Multi-Party Computation as well as Trusted Execution Environments.

Moreover, we've developed a PoC for Electric Vehicle charging process on blockchain based on Parity Ethereum: https://youtu.be/xJUKNlV79pg

For trusted sensor oracles, Alain wrote a [whitepaper on decentralized trusted timestmping](https://www.scs.ch/wp-content/uploads/2017/01/trusted-sensor-whitepaper.pdf).

Alain, Marcel and Christian are the core devlopers for substraTEE.

A few further blockchain projects are subject to NDAs.

## Team Code Repos

* https://github.com/scs/substraTEE
* https://github.com/scs
* https://github.com/brenzi
* https://github.com/encointer

## Team LinkedIn Profiles

(Not all on LinkedIn)

https://www.linkedin.com/in/alain-brenzikofer-9a4480165/

https://www.linkedin.com/in/juraj-skripsky-4338a217/

https://www.linkedin.com/in/sabine-proll-5a7118153/

## Development Roadmap

### Milestone M8.1: Accept extrinsics directly over RPC

  * Implement RPC interface replacing the current websocket worker-api
  * Implement tx pool based on substrate’s
  * Implement batch validation of direct invocation extrinsics.

For test purposes, direct invocation extrinsics will be applied to the STF state.

Acceptance:
  * demonstrate the private-tx example as used for M5 but replace indirect invocation (via chain) with direct invocation (via worker RPC). Demonstration runs in docker.

### Milestone M8.2: Single Worker Block Production

  * refactor execution sequence as specified above
  * implement new Block type
  * implement journaling of state updates (similar to substrate) and generate a diff per block that can be applied by other workers (StateUpdate)
  * implement execution time limit
  * send block confirmations to layer one

Acceptance:
  * run same test as M8.1 and verify that blocks are produced and confirmed on layer one

### Milestone M8.3: Multi-Worker Setup

  * improve SubstraTEE-node enclave registry to simplify shard authority set lookup
  * implement block broadcast logic
  * implement pruning and snapshotting that will allow new workers to join in.
  * implement layer one pallet that enforces block production rules
  * implement test setup where workers join and go offline
  * Tutorial how to use the new SubstraTEE-framework to boost scalability for a simple use case (shielding-unshielding tx shown in M6. But now with high tps and low latency

Acceptance

  * Demonstrate multi-worker docker setup. Run same test as for M8.1 several times, after each mutation of worker sets. Verify correct balance movements of tester account.
  * Tutorial run-through by web3

### Milestone M8.4: Benchmark
  * Assess tps and confirmation time latency for single shards as defined above. 

Acceptance

  * upon delivery of benchmark report

## Timeline

  * T0: project start (upon agreement)
  * M8.1: T0+4 weeks
  * M8.2: T0+7 weeks
  * M8.3: T0+12 weeks
  * M8.4: T0+15 weeks

## Future Plans

SCS *department decentralized systems* has been working with the web3 ecosystem since *wave1* and continues to apply the technology for its engineering services for the industry. The goal is to finance ongoing maintenance of SubstraTEE either through individual projects or through running SubstraTEE as a platform as a Polkadot parachain in the near future. In the latter case, such a platform could be maintained with *Treasury* funds, given the interest from the community.

As SubstraTEE is a prominent building block of Encointer, the synergy continues to flourish.
