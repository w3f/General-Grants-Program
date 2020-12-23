# General Grant Proposal

* **Project:** Hashgraph Consensus Pallet

## Project Overview :page_facing_up: 
We propose the creation of a Proof of Concept Pallet to allow Substrate blockchains to utilize Hedera’s DAG-based consensus for finality. 

Hedera is a public distributed ledger network based on [Hashgraph](https://www.swirlds.com/downloads/SWIRLDS-TR-2016-01.pdf), a directed acyclic graph (DAG) consensus mechanism. This consensus mechanism can be externally utilized through the [Hedera Consensus Service (HCS)](https://hedera.com/consensus-service), Hedera’s primary platform offering that provides fairly-ordered, asynchronous transaction finality. HCS can be used as a general-purpose transaction log that is intended to allow permissioned blockchain/DLT networks to utilize Hedera's consensus for finality.

Our team consists of Hedera developers that see Substrate as the best fit for providing greater functionality on HCS through its modular, flexible and performant blockchain architecture. Hedera’s enterprise customers can use Substrate to build permissioned blockchain networks that achieve public finality using our proposed pallet and configuration. 

We see this project as valuable to both the Hedera and Polkadot ecosystems as it combines the best of both platforms into an open-source solution that makes permissioned blockchain networks more resilient. Our research will also help pave the way for greater interoperability between Polkadot, Hedera and other DAG-based networks.

### Project Details 
Our project will integrate a typical permissioned Substrate network running Aura with the Hedera network through HCS. To achieve this, we will build a finality gadget pallet that borrows from GRANDPA but uses HCS for recording proofs of finality on Hedera. We will also build Off-chain workers to facilitate a connection between a Substrate node’s runtime and the Hedera public network. 

#### High-level Architecture

IMAGE HERE

The diagram above shows how the Hedera Finality Pallet will interact with the HCS Offchain Workers. 

The Hedera Finality Pallet will finalize blocks in a similar manner to GRANDPA but will record the finalizing block message as an HCS transaction. In its simplest form, this will act as a block anchoring mechanism so that the permissioned network can gain some of the security from Hedera’s public network. However, we intend to further research the capabilities of HCS messaging to determine if it can play a larger role in GRANDPA gossip between nodes as further detailed in 6.3 of the [Polkadot Host Spec](https://github.com/w3f/polkadot-spec/releases/tag/v0.0.5).

To send HCS transactions, the Offchain Workers will require a user to provide configuration details for connecting to a remote Mainnet node. For querying Hedera, a separate mirror node is used, which can be hosted locally, but for our PoC, we’ll be using a remote node service for the sake of simplicity. We may also run external components locally to facilitate the connection; although we aim to contain as much as possible within the Offchain Worker for greater consistency between nodes.

Once both the Pallet and Offchain workers are complete, we will create a version of the [substrate-node-template](https://github.com/substrate-developer-hub/substrate-node-template) to demonstrate how a permissioned Substrate network can be set up using HCS for finality by anyone on their local computer. 

### Ecosystem Fit 
#### Why Hedera?
Hedera is unique in that it uses a DAG-based network that is governed by an enterprise council of international companies such as IBM, Boeing and LG. While Polkadot itself is best suited for interoperability between most common blockchains, Hedera is uniquely suited for enterprises that are attracted to its familiar governance and legal structure. For this reason, we believe many enterprises will favor Hedera for public finality while still needing the functionality that Substrate offers. The 20 existing [Members](https://hedera.com/council) on Hedera’s council shows how much traction they’ve already received.

#### Value for Polkadot Ecosystem
Long-term, we believe this project will provide several valuable contributions to the Polkadot ecosystem both in terms of research and an expansion of enterprise usage.

Our PoC will provide valuable research around the application of DAG-based consensus mechanisms on Substrate that can be utilized for future work on the topic that could apply to other implementations beyond Hedera. Existing work already exists in combined DAG-based mechanisms with existing blockchain structures, such as [Babble](https://docs.babble.io/en/latest/blockchain.html) and [Solana](https://solana.com/solana-whitepaper.pdf), so we feel there is a great deal of promise in pursuing this subject for research purposes alone.

Most importantly, we see an integration with Hedera as the first step towards potentially connecting both public networks through a bridge or parachain implementation. Hedera is making strong progress in getting enterprise companies to invest in distributed ledger technology within an ecosystem that they feel comfortable with. We believe there will be immense value in connecting Hedera with Polkadot so that enterprise networks are able to communicate with other blockchains. Our PoC is the first step towards making a connection between Polkadot and Hedera possible. We also believe that our work could be extended to connect to other DAG-based networks. 

IMAGE HERE
Polkadot-Hedera integration concept, modified from Polkadot slides

We must acknowledge one caveat with Hedera in that not all of the network code is open-source. Much of their high-level systems are open-source and even the base code is publicly shared but the Hashgraph protocol implementation itself is a closed license controlled by the Hedera governing Council. Despite this, we feel that the value Hedera provides in greater enterprise traction is worth this trade-off. We also think that other open-source DAG implementations would find value in the work we produce for creating integrations to Polkadot.

## Team :busts_in_silhouette:

### Team members
* Michael Lewellen (Team Leader)
    * CEO of Tarski Technologies, LLC
    * GitHub: https://github.com/cylon56
    * LinkedIn: https://www.linkedin.com/in/michael-lewellen/
    * Currently enrolled in the Substrate Runtime Dev Academy
* Craig Drabik
    * Technical Lead at TxMQ. Inc.
    * GitHub: https://github.com/craigdrabiktxmq
    * LinkedIn: https://www.linkedin.com/in/craigdrabik/
* Rob Kainz
    * CTO at Ledgerama, LLC
    * GitLab: https://gitlab.com/robkainz
    * GitHub: https://github.com/robkainz
    * LinkedIn: https://www.linkedin.com/in/robertkainz/
    * Web: http://robertkainz.com
* Roland Ringgenberg
    * Digital Architect
    * GitHub: https://github.com/ringgi
    * LinkedIn: https://www.linkedin.com/in/rolandringgenberg/
    
We expect our team to collectively work an equivalent of 2 FTE

### Legal Structure 
The grant will be accepted by Tarski Technologies, LLC who will coordinate and subcontract with other partners. All grant work will be completed and delivered as a single team with grant money allocated accordingly.

Tarski Technologies, LLC (Accepting Grant): http://tarski.tech/

Grant Partners:
* TxMQ, Inc: https://www.txmq.com/
* Ledgerama, LLC: https://ledgerama.com/
* Roland Ringgenberg Technologies GmbH: https://www.rolandringgenberg.tech/

### Team's experience
Our team is composed of developers that work on Hedera Hashgraph in various capacities including wallet software and runtime frameworks. Our members bring a mix of experience developing enterprise systems and building blockchain applications on Ethereum (Mainnet and Permissioned), HL Fabric, and Hedera.

#### Michael Lewellen
Michael is CEO and co-founder of Tarski Technologies, a Dallas-based product design & development studio with a specialty in blockchain technology. He holds +8 years of blockchain experience as a blockchain software architect & consultant working with Ethereum for both mainnet and permissioned use-cases. Outside of consulting, Michael teaches a blockchain course at UT Dallas and is a board member for the Texas Blockchain Council, a public policy group that educates lawmakers on blockchain technology. 

#### Craig Drabik
Craig is the practice manager for the Disruptive Technologies Group at TxMQ.  DTG develops business solutions for customers using blockchain and distributed ledger technology, and was the first organization to deliver a production application using Swirlds Hashgraph technology.  Craig is the architect and lead developer of the [Aviator Core Framework](http://aviatordlt.com/index.html), which makes it easy for developers to implement applications on Swirlds Hashgraph and Hedera Consensus Services.  Craig has nearly 25 years of experience in the IT industry, with a skill set encompassing modern web and mobile design and development, business case development, and software project management in addition to blockchain and DLT development.

#### Rob Kainz
Rob is the CTO, architect, lead developer and co-founder for Ledgerama LLC, which develops business solutions for Distributed Ledger Technologies, focusing on Hedera Hashgraph. Rob currently develops Wallawallet, a mobile wallet for Hedera's HBAR cryptocurrency currently available on the Apple App Store and Google Play Store. Rob has over 20 years software design and development experience and has worked on various enterprise applications at companies including IBM, Tivoli, USPS and Railinc. 

#### Roland Ringgenberg
Roland is an independent Digital Architect programming the web for over 2 decades with a strong focus on digital business creation, continuous innovation and cloud native delivery of digital business platforms and ecosystems. After starting his career in the 90es in the music industry he became a Web1 pioneer, introducing the first e-commerce and digital marketplaces in Switzerland, created several startups, became a senior consultant for RIAs in the growth years of Web2 where he implemented digital platforms and apps for major brands, the financial industry, telcos and governments, then joined Swisscom to help develop the Swisscom Cloud, PaaS and XaaS marketplaces. Today he runs his Digital Business Foundry focusing on the Web3 to build a free, fair and trustful digital society. He is a Hedera MVP, Leanstack Lean Startup coach and holds degrees in Higher Informatics from KU Leuven, Belgium, Business Innovation from BFH Bern, Switzerland, as well certificates in Digital Business Strategy from MIT Sloan and Entrepreneurship from Babson, Boston, US. 

## Development Roadmap :nut_and_bolt: 

### Overview
* **Total Estimated Duration:** 15 weeks
* **Total Cost:** $72,600
* **Full-time equivalent (FTE):** 2
* **Cost per day:** $960

### Milestone 1 — Offchain Worker Integration 
* **Estimated Duration:** 6 weeks
* **FTE:**  2
* **Costs:** $28,800

In this milestone, we will provide functionality for a Substrate pallet to communicate with the Hedera network using an Off Chain worker.

Note: The Offchain Worker for this milestone could also be made more generic for external block anchoring on other public networks. We’re open to feedback on doing extra work to make this a more common interface.

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic guide that explains how a user would set up and configure the integration with Hedera Consensus Service, including how to supply your keys, and account ID to the relevant components.  We will also provide an architectural diagram and documentation of the architecture. |
| 0c. | Testing Guide | The code will achieve 90% or better unit-test coverage (e.g. 90%) to ensure functionality and robustness. A guide to running the test suite will be included in the documentation. | 
| 1. | Substrate module: Off-Chain Worker | We will create an off-chain worker module that integrates a Substrate node with the Hedera Consensus Service.  The worker will accept a block or block hash, submit it through HCS and await the result.  Assuming a successful result, the worker will store the Hedera transaction ID associated with the submission, which can later be used to validate the transaction. |  
| 2. | Off-Chain Worker Test Harness | We’ll build a fummy pallet, Rust test harness, or queue-based testing mechanism to perform isolated testing on the off-chain worker and HCS integration components.This will prepare us for integration in milestone 2. |  
| 3. | Source code with Docker files | We will provide a Github repo with a dockerfile to build, test, and run a Substrate node that demonstrates the dummy pallet can communicate with Hedera via the Offchain Worker. |

### Milestone 2 — Hedera Finality Pallet
* **Estimated Duration:** 6 weeks
* **FTE:**  2
* **Costs:** $28,800

In this milestone, we build the pallet that extends GRANDPA finality to use HCS for anchoring finalizing block hashes and communicating them to other nodes.

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic guide that explains how our pallet extends GRANDPA finality for using HCS. |
| 0c. | Testing Guide | 90% unit testing for the Finality Pallet and integration tests with the Offchain Worker. | 
| 1. | Substrate Module: Finality Pallet | We’ll create a stand-alone pallet module that extends GRANDPA finality for pushing block finalization messages to Hedera. We’ll build this starting with the dummy pallet that is integrated with the Offchain Worker component from the 1st milestone. |  
| 2. | Source code with Docker files | We will provide a Github repo with a dockerfile extending from milestone 1 that demonstrates the Finality pallet can communicate with Hedera via the Offchain Worker. |

### Milestone 3 — Hedera Node Template Example
* **Estimated Duration:** 3 weeks
* **FTE:**  1
* **Costs:** $7000

We’ll demonstrate the first two milestones are successful by providing a node-template example and tutorial for running a permissioned substrate network that uses Hedera for finality. We'll also provide a report for the feasibility of future work on DAG-based consensus mechanisms.

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Tutorial Docs | We will provide documentation that instructs a user how to set up a multi-node permissioned Substrate network that uses Hedera from scratch similar to this [tutorial](https://substrate.dev/docs/en/tutorials/build-permission-network/). |
| 0c. | Testing (if needed) | Additional tests that may not be covered in first two milestones | 
| 1. | Source code with Docker files | We will provide a Github repo with a dockerfile extending from milestone 1 that demonstrates the Finality pallet can communicate with Hedera via the Offchain Worker. |
| 2. | Future Work Findings | We will provide a list of enhancements needed to make our work production-ready and determine whether future work mentioned in this grant is still viable. |

### Community engagement

We intend to engage with Substrate developers to get feedback on our implementation, especially for consensus research. On completion, we will publish an article that explains the goals of the project along with the tutorial for how to use the template example.

We will also be encouraging the Hedera team and community to explore our implementation and learn about using Substrate.

## Future Plans
The focus of this grant is to prove the viability of using DAG-based consensus mechanisms with Substrate in a limited capacity. Long-term, we want to pursue more integrations with the Hedera platform as well as extend our components for more generic uses as they become apparent.

Future work we’re considering includes (in order of priority):
1. **Transaction Ordering with HCS** - Explore the viability of using HCS to asynchronously order and confirm individual transactions for higher throughput. This idea could be very challenging with Substrate’s current architecture and we intend to learn more about its viability in this initial grant.
2. **Block Anchoring Pallet** - Our initial work in this grant focuses on publishing finalized blocks to the Hedera network. This could be extended into a generic set of components that make it easy to do block anchoring on any external public blockchain network. Block Anchoring provides an easy first step for permissioned Substrate networks which could later result in more connections to Polkadot and its parachains.
3. **Hedera Relay Chain** - A Relay Chain network on Hedera that allows multiple permissioned Substrate networks using HCS to be interoperable with each other. 
4. **Polkadot Bridge to Hedera Relay Chain** - With a compatible Relay Chain built on Hedera, we can build a bridge to the Polkadot Relay Chain to allow the Hedera network to have an interoperable connection with other Polkadot chains.
5. **Integrate other Consensus Mechanisms** - The work on this grant may provide ideas that lead to other DAG-like consensus mechanisms being integrated into Substrate such as Solana’s Proof of History mechanism.

