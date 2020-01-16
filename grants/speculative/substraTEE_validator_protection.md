# SubstraTEE Validator Protection

## Project Description

We suggest a solution for validator key management that protects the validator against attacks who try to cause slashable behaviour.

### Problem statement

Polkadot nominated proof-of-stake (NPoS) validators sign various messages with hot keys, the session keys. These messages can be related to consensus, such as GRANDPA finality votes or block authoring. These keys do not allow the transfer of any funds, but if the key is compromised, an attacker could hurt the validator by committing slashable behavior.
A second issue arises when the validator introduces redundancy in order to achieve high availability. The validator could run several validator nodes (all using the same session keys). This, however, could cause accidental double signing of two different block proposals, which would be punished by slashing.
Further, the session keys are not all necessarily of the same type. For example, one Substrate-based chain could have a set of session keys that includes sr25519, ed25519, BLS12-381, or anything that has a verification implementation. Not all hardware security modules (HSM) support such a variety of keys.

### History

SCS has developed SubstraTEE based on Intel SGX technology with a grant from the web3 foundation. After fulfilling that grant with the delivery of M4, SCS continued the development on its own and has reached M5, adding a private token transfer implementation that allows to instantiate a pallet-balances module within an enclave. A pending grant proposal shall allow SubstraTEE to perform light client verifications inside the enclave to allow trustless reading of chain state from the enclave state transition function (STF) and verifying inclusion proofs for arbitrary extrinsics.

### Technical Concept

We strongly discourage simple remote signing schemes because they do not provide additional security under our problem statement. Just protecting the key from leaking doesn’t protect from slashing if an attacker manages to have fake blocks signed by the remote signer. Instead, we must make sure that 
the private session key can never leak
only legit payloads can be signed with the session key.
the signer is highly available
The first requirement can be approached with HSM remote signing solutions. The third one can be achieved by a N-of-M multisig scheme with redundant remote signers. 

The second requirement is more challenging. In the case of validators, a “legit” payload is
A valid block consisting of valid extrinsics and intrinsics
At a certain block height, only one block may ever be signed (not to be slashed for double signing)
The remote signer must therefore be aware of the most recent block header and must keep track of blocks it has signed (Special attention has to be paid to replay attacks).
In order to verify block contents, the remote signer must be able to execute the block, which means it needs access to the most recent state and to the runtime code (wasm).

These requirements actually align pretty well with the requirements to relay-chain validators’ verification of parachain blocks. Collators supply to validators the next block to be finalized along with the currently active runtime wasm and the fraction of chain state that is necessary to execute the block.

We now elaborate how we could implement such a scheme within SGX enclaves. This way, session keys could be isolated within SGX and we could make sure only legit blocks are signed exactly once.

To keep this proposal within reasonable financial limits, we will stage the development. The above described full-blown solution is beyond the limits of a single proposal.
### Stage 1: Simple Remote Signer
The first stage only protects against leaking the session key under the guarantees of Intel SGX. It does not protect against slashable behaviour.


The validator sends the next block to the signer which launches the enclave in custody of the session key which signs anything it is being sent and returns it to the validator. The signer API supports at least the following calls:
```
get_public_key()
sign(payload)
```

For this we don’t necessarily need to build on substraTEE, as no remote attestation and no chain interaction is needed (assuming the SGX machine is in possession of the validator operator). This first stage serves to define and test the API between parity substrate and the remote signer. To date, substrate does not support remote signing, so it is an integral part of this proposal to negotiate such an API with parity devs.

As a first step, ed25519 keys will be supported.

#### Benefit for validators

At this stage the signer is just a “poor-man’s HSM”. No real mitigation of the risk to get slashed.

### Stage 2: Double Signing Protection

Next, we use substraTEE’s light client functionality (to be developed with a pending grant proposal) to make sure the payload to be signed is a block linking to the tip of the chain. Moreover, we keep track of all blocks that have been signed by the enclave.

Replay protection will be implemented based on the ROTE protocol. This protocol leverages a distributed set of SGX machines. As long as at least one enclave is online that hasn’t suffered a rollback, the integrity of each enclave is guaranteed.

#### Benefit for validators
For high-availability setups with redundant validator machines, a single remote signer can protect against double-signing. However, if the signer goes offline, the redundancy of validator nodes is futile.

### Stage 3: Block Execution

*This stage is out of scope for this proposal.*

The signer runs a native- and/or wasm executor inside the enclave which can execute the block to be signed. In addition to the features of Stage 2, the block will only be signed if the block executes correctly based on a provided state (verified by the light client inside the enclave).

At this stage it becomes questionable if the signer should really be a separate unit doubling a lot of the essential node logic. An alternative could be to isolate the node’s entire executor into SGX. This however would mean a very deep integration of SGX into substrate.

## Team members
* Alain Brenzikofer: @brenzi on github, Department Head, Developer
* Marcel Frei: @electronix on github, Project Manager for substraTEE, Developer
* Christian Langenbacher: @clangenb on github, Developer

## Team Website	
* https://www.scs.ch/en/about-scs/departments/decentralized-systems/


## Legal Structure 

Swiss AG

## Team's experience

As an engineering services company SCS AG has more than 25 years of experience in the fields of electronics, software and system design. Profound know-how, solid methodological competence as well as efficient project management are the foundation of our success.

Most programming experience in the following languages: C/C++, C#, Java, Python and VHDL.

Alain Brenzikofer follows Blockchain developments since 2011. He works for SCS since 2012 where he started working on blockchain projects in 2016 and was appointed to lead a new department for "Decentralized Systems" in summer 2018. As a private initiative, he designed a new cryptocurrency ecosystem [encointer - An Ecological, Egalitarian and Private Cryptocurrency and Self-Sovereign Identity System](https://encointer.org) . A project he currently intends to realize based on Substrate (including this privacy extension).

Our team is part of the [Quartierstrom project](https://quartier-strom.ch), implementing and currently field-testing a decentralized P2P energy market in Switzerland together with ETHZ, Bosch IoT Lab, HSLU and others.
SCS is in charge of the development of a dynamic grid usage-tariff smart contract as well as privacy-by-design concepts for the decentralized energy auction, thereby investigating and evaluating Zero-Knowledge Proofs, Linkable Ring Signatures, Multi-Party Computation as well as Trusted Execution Environments.

Moreover, we've developed a PoC for Electric Vehicle charging process on blockchain based on Parity Ethereum: https://youtu.be/xJUKNlV79pg

For trusted sensor oracles, Alain wrote a [whitepaper on decentralized trusted timestamping](https://www.scs.ch/wp-content/uploads/2017/01/trusted-sensor-whitepaper.pdf).

Alain, Marcel and Christian are the core developers for substraTEE.

A few further blockchain projects are subject to NDAs.

## Team Code Repos

* https://github.com/scs/substraTEE
* https://github.com/scs/substraTEE-worker
* https://github.com/scs/substraTEE-node
* https://github.com/scs/substrate-api-client
* https://github.com/scs
* https://github.com/brenzi
* https://github.com/encointer

## Team LinkedIn Profiles

https://www.linkedin.com/in/alain-brenzikofer-9a4480165/

https://www.linkedin.com/in/christian-langenbacher-baa629182/


## Development Roadmap

### M1: Demonstrate Stage1
1. Run a dockerized testchain based on substrate nodes (with support of remote signing)
1. Run a remote signer for every validator inside its own docker container (SGX in SW mode, no specific HW needed)
1. Show that block production works
1. Provide a tutorial on how to set up remote signing with real SGX HW for polkadot NPOS validators.

### M2: Demonstrate Stage2
1. Run dockerized testchain based on substrate nodes (with support of remote signing)
1. Run a redundant set of remote signers inside their docker container (SGX in SW mode, no specific HW needed)
1. show that block production works
1. attack 1: Try to get a block signed that links to the 10th most recent block. Show that it isn’t signed by the signer
1. attack 2: Try to get a block signed that links to the most recent block after a block for this block height has already been signed. Show that it isn’t signed by the signer
1. attack 3: Re-iterate attack 2 with a rollback: Roll back the state of one enclave to the state prior to signing the most recent block and show that no block will be signed by that enclave for the current block height.
