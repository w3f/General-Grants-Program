# substraTEE-ink-contracts

## Project Description

This application is a follow-up to our [grant for developing substraTEE](https://github.com/w3f/Web3-collaboration/pull/66). [substraTEE](https://github.com/scs/substraTEE) is an off-chain-worker system that interacts with a substrate chain and executes calls to a state-transition-function inside an Intel SGX enclave in order to provide integrity and confidentiality within the guarantees of Intel.

During the implementation of our *wasm-stf-within-sgx-enclave* feature we realized the potential to support [ink contracts for our SGX off-chain worker](https://github.com/scs/substraTEE-worker/issues/15). We consider this feature a suggested change request. It exceeds our budget for the current grant.

The feasibility is already shown in [our PoC](https://github.com/scs/substraTEE-worker/tree/brenzi-contract-modular), where we instantiate a substrate runtime with srml-contract module in our SGX enclave and call the [flipper contract](https://github.com/paritytech/ink/wiki/Writing-Your-First-Contract). This PoC, however, is a quick hack without all the needed functionality and can't be released as such.

Benefit for ecosystem:

* Portability: Developers can develop ink contracts and at a later stage decide to run them *confidentially* in a substraTEE-worker without modifying the contract (if they do not need to access the state of the chain).
* Scalability: Because substraTEE-worker contracts can be called off-chain, the tx throughput is expected to increase by orders of magnitude compared to on-chain contracts (no benchamrks or analyses have been taken out so far). On-chain anchors aggregating many contract call receipts will be submitted as extrinsics to substrate.

Our team is interested in continuing the development of substraTEE because we see interest in the community for substraTEE's value proposition. Moreover, it accelerates Alain Brenzikofer's private not-for-profit cryptocurrency&DID project [encointer.org](https://encointer.org).

## Team members

* Alain Brenzikofer: @brenzi on github, Department Head, Developer
* Marcel Frei: @electronix on github, Project Manager for substraTEE, Developer
* Christian Langenbacher: @clang on github, Developer
* Sabine Proll: @sabinep, Developer
* Juraj Skripsky: @jskripsky on github, Rust-Guru, Reviewer

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

https://www.linkedin.com/in/christian-langenbacher-baa629182/

https://www.linkedin.com/in/juraj-skripsky-4338a217/

https://www.linkedin.com/in/sabine-proll-5a7118153/

## Development Roadmap

We intend to base this work package on [our PoC](https://github.com/scs/substraTEE-worker/tree/brenzi-contract-modular) which is partially documented in [this issue](https://github.com/scs/substraTEE-worker/issues/15).

What needs to be done:

* refactor the dirty-hack PoC code
* write unit tests
* graceful error handling
* parse ink ABI definitions
* persist Externalities (state)
* finish our [PR to substrate](https://github.com/brenzi/substrate/tree/brenzi-contract-replace-sr-io) which allows to instantiate a runtime within Intel SGX enclave
  * cleaning code
  * implementing child_storage in sr-io

As neither substrate nor ink are stable, we'll have to base our work on a recent commit and we might deliver based on selected upstream commits. Ongoing integration work is not part of the requested budget.

### Timeline

(continuing Milestone numbering since substraTEE grant (M1-M4))

- T0: Project start: favorably mid July 2019
- M5: T0 + 3 weeks (subject to holiday plans, TBD when we know the start date)
