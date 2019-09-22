# Polkaeos

## Project Description

Polkaeos is a polkadot-EOSIO cross-chain bridge implementation with no loss of trust, the goal is to implement this:

- A bridge between polkadot and chain based on EOSIO.
- State Mapping Between Polkadot and EOSIO, especially for Token in both side.
- Zero Trust Loss, the bridge can be trust with any addon hypothesis and premises.

By Polkaeos, we also can make a EOSIO based chain as a sub chain for polkadot parallel chain.

At present, EOSIO is one of the main technologies of block chain, so it is of great value to build a cross-chain bridge between Polkadot and EOSIO.

In order to run DAPP with high performance and low latency, EOSIO has made a lot of design choices. On the one hand, this makes EOSIO landing quickly, but on the other hand, it also brings a great degree of centralization problems.
At the same time, the features of EOSIO make it very difficult to cross-chain with it: EOSIO node deployment is expensive, Comparing with other public chains, the computing in EOSIO is very large.
All of this will make a bridge just designed like polkadot-ETH cannot do work well in polkadot-EOSIO.

So polkaeos achieves a cross-chain Bridge Based on the features and functions of Polkadot and EOSIO, polkaeos will be designed decentralized as much as possible to make it can used for more applications.

The details design for polkaeos is here: [Polkaeos](https://github.com/polkaeos/polkaeos/blob/demo/desgin.md)

At the first, the polkaeos wants to be used as to make EOSIO more decentralized, use a blockchain is a good way to achieve it, so there is a desgin to polkaeos, which is also a bridge in polkadot.

This is an open source project under Apache License 2.0. All the defined milestones will be available to the open source community.

## Team members

* Fan Yang: Developer for the polkaeos.

## Team Website

* https://github.com/polkaeos/polkaeos

## Team's experience

* Fan Yang: As core developer to eosforce, which is a EOSIO fork chain with lots of changes, 8 years coding experience.

Projects help to the development of polkaeos by Fan Yang:

- [eosforce](https://github.com/eosforce/eosforce) : A EOS Fork chain with different governance concepts and more decentralized than eosio.
- [codex.relay](https://github.com/codexnetwork/codex.relay): A Relay Chain based on EOSIO, high performance cross-chain relay services to other chains.
- [eos-light-node](https://github.com/fanyang1988/eos-light-node): A Test EOSIO light node implementation.

## Team Code Repos

* https://github.com/polkaeos/polkaeos

## Team LinkedIn Profiles

* Fan Yang: https://www.linkedin.com/in/yang-fan-460175132/

## Development Roadmap

As Design in [Polkaeos](https://github.com/polkaeos/polkaeos/blob/demo/desgin.md), polkaeos is has 4 parts works to do:

- polkaeos chain base implementation.
- eosio light node implementation for polkaeos.
- contacts to help Cross-chain in EOSIO.
- state transfer worker node.

In Early Version of polkaeos, we just support basic value state mapping and token mapping between polkaeos and EOSIO.

### Milestone

In Planning, all of work for polkaeos is need 4 months, and $30k grants to make we can full-time development the polkaeos.

In Developping, there may be more developers for polkaeos to make it finished more quickly.

- M1 - 3 week: Polkaeos chain base implementation
  - Design a Abstract blockchain Architecture for verify ordered extrinsics hold by each nodes.
  - Implement the blockchain based on Substrate, which can verify the ordered extrinsics hold by each nodes, in next Milestone, the extrinsics will be Blocks Header and Key Action from eosio.
  - After this Milestone, we can get a chain which can verify sequence extrinsics got in offchain by each nodes, this chain can also used to implement other bridges which all node in bridge is also a node in other chain.
  - $5,500

- M2 - 5 weeks: EOSIO light node implementation for polkaeos.
  - Implement EOSIO base data structure and it's serialization library by rust.
  - Implement EOSIO P2P protocol for polkaeos.
  - Verify the EOSIO block header in polkaeos offchain.
  - Make a EOSIO Data Storage for polkaeos.
  - After this Milestone, a node in polkaeos also a node in eosio, the polkaeos can sync blocks and be a light node in EOSIO network to verify the block it got.
  - $9,500

- M3 - 2 weeks: Implement EOSIO to Polkaeos State Mapping
  - Implement contacts to in EOSIO, which make a assert to state in EOSIO RAM.
  - Make handler in polkaeos for cross-chain actions.
  - Verify the EOSIO block Datas by chain implement in M1.
  - After this Milestone, polkaeos can mapping state from EOSIO, that mean EOS can be transfer into polkaeos chain.
  - $3,500

- M4 - 2 weeks: Implement Polkaeos to EOSIO State Mapping
  - Implement Polkaeos state mapping proof.
  - Implement miners(or transfer workers) push contract in EOSIO.
  - Implement the verify to the miners, include the miner fisherman.
  - Implement the miners registry process in both polkaeos and EOSIO.
  - After this Milestone, use tools (like substrate-ui) can complete transfer state form polkaeos to EOSIO by hand)
  - $3,500

- M5 - 3 weeks: Tools and Documentations
  - Implement the node for miners, which can do transfer work automatically.
  - Some API for polkaeos to get chain state.
  - Documentations for polkaeos.
  - After this Milestone a miner node can be used by miner which transfer state to EOSIO and check other miner automatically. also there will be some api to help user get chain sync state by polkaeos, then we will complate all documentations need by startup testnet.  
  - $5,500

- M6 - 1 weeks: Startup polkaeos testnet
  - Launch a polkaeos testnet
  - After this Milestone, we will make polkaeos testnet ready, start a testnet between Kusama and ENU( which is same with EOS, but more cheap, if ENU cannot work, the testnet will between a EOSIO testnet )
  - $2,000

All the deliveriables for each milestone will be published in the open source repositories.

### Long-term Plan

Polkaeos make a trusted bridge between EOSIO and polkadot parachain, it need much more works to do:

- Support More Type of Status to Mapping between Polkaeos and EOSIO, not just some token and number.
- EOSIO Block Cropping, by the new version of EOSIO, we can skip some block check safety.
- JS API for Polkaeos, and also for EOSIO, this can make use bridge more easy.
- Support EOS-VM in polkaeos, EOS-VM is in developing by Block.One, it may be a useful VM for block chain, in polkaeos, we will implemented lots of support for EOSIO, support EOS-VM will easily.
- By EOS-VM, polkaeos can support EOSIO contracts, but as a more decentralized blockchain, there will be a lots of limit to be add for polkaeos.
- Subchain based on EOSIO for polkaeos, it will be changed from EOSIO, so cross-chain with it will cost much less than EOSIO.
- Support Chains based on EOSIO, like EOSForce(EOSC), BOSCore, ENU ...

The plans will be some independent project, and we will implement this by polkaeos.

## Additional Information

* What work has been done so far?
  * There is a [Design Document](https://github.com/polkaeos/polkaeos/blob/demo/desgin.md) and a Demo for polkaeos, and the demo is just for test if the substrate can hold the eosio blocks.

* Are there are any teams who have already contributed (financially) to the project?
  * No.

* Have you applied for other grants so far?
  * No.

* Are there any other projects similar to yours?
  * There may be lots of bridge between EOSIO and polkadot, but we don't know right now.

* How is your project different?
  * polkaeos is a more decentralized implementation even loss some functionality for it, to achieve it polkaeos have quite different from other bridges desgin, so that it will can be trusted by users form both polkaeos and EOSIO, it is key to work well.