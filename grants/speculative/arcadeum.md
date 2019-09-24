# Arcadeum Game Channels

## Project Description

State channels are a well-known layer-2 construction in the blockchain space for increasing the scalability of existing blockchains, the core idea being to conduct as much computation off-chain, and only resorting to on-chain transactions in the event of a dispute.
Arcadeum game channels are an engineering effort by the Horizon Blockchain Games team to create a library for traditional game developers to create provably-fair blockchain games without the deep requisite knowledge that's normally needed to build dapps.
Arcadeum game channels are state channels applied specifically to two-player adversarial turn-based games.
As game channels are geared specifically towards games, we also aim to provide useful primitives and extensions to that end as well.

Gaming itself is a multi-billion dollar industry [1] and one of the most natural applications of blockchain tech.
In the case of Polkadot, being able to declare that it can support such an extremely common and high-demand use case with relative ease is great validation for its ecosystem as a whole.
Horizon is currently invested in undertaking this work as we believe developers using our work gain the most benefit when they can choose the technology that suits them most appropriately, such as Substrate.

[1] https://newzoo.com/insights/articles/the-global-games-market-will-generate-152-1-billion-in-2019-as-the-u-s-overtakes-china-as-the-biggest-market


## Design

Games can be modelled mathematically as deterministic finite-state machines (FSMs).
Our design transforms those FSMs into new ones satisfying several useful properties for blockchain games:
1. (replication) States are always serializable regardless of their serializability in the original FSM
2. (non-repudiation) States cannot be constructed without the cooperation of all participants
3. (pruning) States can omit most of the history of a given match, leading to reductions in storage and computational resources
4. (batching) At most one signature verification is needed per participant to verify a state
5. (delegation) States can also be signed with other keys certified by a participant

Provably fair random number generation is built upon this foundation and is completely transparent to game developers.
The developer only needs to make a call to `context.random().await` to obtain a `rand::Rng` object.
This is Rust's async-await syntax which we adopt for developer convenience.

States in the transformed FSMs can be interpreted as proofs of game states signed by the participants, while transitions between game states can be interpreted as signed diffs on those proofs.
Proofs have the replication property since they always encode as a serializable game state with some number of transitions, possibly none.

The Arcadeum game channel library is written in Rust, includes JavaScript bindings, and targets WASM environments like modern Web browsers and blockchains like Substrate or Ethereum 2.0.
This library is already in use by the trading card game at www.SkyWeaver.net.


## Team members

* William Hua (Lead Applicant)
* https://horizongames.net


## Team Website

* https://horizongames.net


## Legal Structure

Horizon Blockchain Games Inc.


## Team's experience

The Horizon team has been active in blockchain for the past two years.
Some of our most visible work includes our collaboration on the ERC-1155 multi-token standard, the ERC-20 meta-transaction wrapper, and an early state channel PoC for Ethereum which was the precursor to this new improved design of Arcadeum game channels.

William Hua is Chief Scientist at Horizon.
He has almost a decade of experience working in software development.


## Team Code Repos

* https://github.com/arcadeum
* https://github.com/horizon-games


## Team LinkedIn Profiles

* https://www.linkedin.com/in/william-hua-72786851/
* https://www.linkedin.com/company/horizon-blockchain-games


## Development Roadmap

### Objective - Substrate module generator for game channels - ~1 week

* Create a basic Rust framework for deploying Arcadeum game state verifiers on a Substrate chain
  * Features:
    * Transparent commit-reveal scheme for trustless randomness in 2-player adversarial games with a focus on seamless integration for developers -- a random number generator is obtainable via a single simple async call
    * Ephemeral key awareness -- per-match ephemeral keys are automatically handled by the framework
    * Abbreviated proofs -- verifying the result of a match doesn't require a complete history of player actions, which can be expensive in terms of data and computation
    * Minimal signature verification -- at most one signature verification per player is required versus the naive approach of one signature verification per action
* Document the developer API of the framework
* Produce basic game demos using the framework showcasing the above features
* Deliverables:
  * Basic example games showcasing the listed features that can compile down into Substrate modules, each with storage to record match results and a proving function
  * Sample proofs that can be submitted as extrinsics to validate the correctness of the verifiers
  * API documentation of the Rust library


## Additional Information

Several months worth of engineering effort have already been invested into the Arcadeum game channel work as outlined in the roadmap.
The scope of this proposal covers our work on game channels and the work of integrating it into a framework for building Substrate modules that can verify match proofs.
We are currently already aware of certain technical challenges that exist in front of us to complete the objective.
We intend to continue long-term development on this work because of its position as a core piece of infrastructure in SkyWeaver, and in any potential future projects we undertake.
Horizon is currently backed by investor capital.
