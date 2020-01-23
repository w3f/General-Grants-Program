# DPOS Oracle

## Project Description

DPOS Oracle is a decentralized oracle managed by the community in a DPOS-like fashion. 

The solution will represent a framework for creating and using such oracles. The core of the solution will be reusable and flexibly configurable code in the form of several SRML modules. Extensible oracle node code and Polkadot-js-based management interface will also be delivered. 

The suggested solution will operate as follows: there’s an onchain community voting for oracle node candidates with the help of some token. After voting, those tokens are blocked for at least one oracle operation cycle. At the beginning of the next cycle, several candidates, collected the majority of votes, are appointed active oracle nodes. From this moment and further on, they must deliver data to the blockchain at certain intervals. Upon receiving some data from active nodes, the blockchain averages them following the predefined rules (e.g. the median value) and makes them available to other SRML modules.

Key benefits:

* The solution allows to **lift one of the main blockchain limitations** - inability to receive real-world data
* **There’s no single point of failure**, solution reliability depends on the community that is incentivized to build a secure infrastructure for the project.
* The solution is **time and resource-savvy** for Polkadot ecosystem projects
  - Easily configurable open source framework
  - Management interface as a Polkadot-js part
  - Configurable offchain oracle node allowing to provide data straight away, without extra software development


## Team members

* Team leader - Alexey Makeev (CTO, Architect)
* Sergey Prilutskiy (CRO, DevOps, Fullstack Developer)
* Mikhail Gorbachev (Rust Developer)
* Sergey Govyazin (JS Developer)


## Team Website	

* https://mixbytes.io

## Legal Structure 

Russian LLC

## Team's experience

* Alexey: 3 years of blockchain experience, 1 year of Polkadot development experience. Experience in architecting and developing a blockchain finality gadget and smart contract systems. 7+ years of experience in the Internet search engine project (5  as a Team Lead). 
* Sergey: 4 years of blockchain experience, 1 year of Polkadot development experience. Experience in architecting and developing smart contract systems. 9 years of experience in web portal development and working with antispam software development teams (7 years as a Team Lead).
* Mikhail: 3 years of blockchain experience, 6 months of Polkadot experience. 4 years of C++\Rust development in system programming. Previously was engaged into fintech and dynamic disassembling.
* Sergey Govyazin: 2 years of blockchain experience, 1 year of Polkadot experience. Deep understanding and expertise of JS-development, good knowledge of C++\Rust.

## Team Code Repos

* [https://github.com/mixbytes](https://github.com/mixbytes)
* [PoC of table-score and oracle-dpos modules](https://github.com/mixbytes/substrate-dpos-oracle)
* [Substrate module simple oracle](https://github.com/mixbytes/substrate-module-oracle)
* [Substrate module multisig](https://github.com/mixbytes/substrate-module-multisig)

## Team LinkedIn Profiles

* [Alexey Makeyev](https://www.linkedin.com/in/aleksey-makeyev-98471884/)
* [Sergey Prilutskiy](https://www.linkedin.com/in/sergey-prilutskiy-2a619951/)
* [Mikhail Gorbachev](https://www.linkedin.com/in/sadsnake/)

## Intended language of development

* Rust
* Javascript

## Development Roadmap

* Start: immediately after grant receipt.
* 1-3 weeks:
  - a 'table-score' SRML module. The module allows to rank sets with the help of voting with assets (tokens). The module will support several independent sets of this kind called table-scores.
    * The module can create table-scores
    * The module can select a subset of power N from a set
    * Set consists of parameterizable values (`AccountId` in our case).
    * Selection is made by voting with a parameterizable asset (an asset (i.e. a token) is created via SRML module "assets").
  - Realization of the 'table-score' (voting) js app using [polkadot-js](https://github.com/polkadot-js).
  - We will deliver a working module for managing entities in the DPoS style along with a js app. Additionally, we’ll deliver a simple tutorial on using `table-score` as a standalone module.

* 4-6 weeks:
  - an 'oracle-dpos' SRML module. The module will:
    * Create an oracle (along with selecting (creating) a target asset and building an oracle table score).
    * Store values from the source accounts selected in the 'table-score' module
    * Calculate and publish some value
    * Optionally, reward source accounts.
  - Realization of an oracle app using [polkadot-js-apps](https://github.com/polkadot-js/apps).
  - We will deliver a working oracle module along with an app, which shows the current state of the oracle. Additionally, we’ll deliver a tutorial on using the oracle’s on-chain and js parts.

* 7-10 weeks: an off-chain oracle part and testing
  - Implement an offchain oracle part using [rust-api](https://github.com/scs/substrate-api-client). The part will:
    * Monitor its status in relation to other candidates
    * Collect the data required for external assets via json RPC (if needed)
    * Extract json data via preconfigured search request clauses
    * Alternatively, execute data collection custom code
    * Send the data to the oracle blockchain part
  - Realization of reparametrization app using voting and [polkadot-js-apps](https://github.com/polkadot-js/apps).
  - We will deliver a well-documented solution containing on-chain, off-chain and GUI parts along with a demonstration scenario that is easy to run using [MixBytes Tank](https://github.com/mixbytes/tank).

We are planning to further develop the project under Apache 2 license. 

We will provide after-delivery support, consult the teams on any issues that may potentially arise and fix the bugs and errors on the way. 

## Additional Information

### What work has been done so far?
* [PoC of table-score and oracle-dpos modules](https://github.com/mixbytes/substrate-dpos-oracle)

### Have you applied for other grants so far?
* https://github.com/w3f/Web3-collaboration/blob/master/grants/speculative/MixBytes_Tank.md
* C++ PRE implementation

### Are there any other projects similar to yours?
Not that we are aware of
