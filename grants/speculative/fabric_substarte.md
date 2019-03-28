# Substrate network as an ordering service for Hyperledger Fabric
## Project Description
Current Hyperledger Fabric (HLF) architecture relies on Ordering Service to establish the partial network consensus, in other words, to determine the order of transactions and blocks. Ordering Service mechanism has a pluggable nature and now for the production networks it  uses so-called Kafka consensus. It is a service based on Apache Kafka instance - a distributed message queue platform - and it relies on an internal Kafka cluster distribution technique. As a result, Hyperledger Fabric can only tolerate Ordering Service nodes crashes, but it does not provide BFT properties to the consensus, and it is not ideal even for enterprise-grade trusted environments. 

At the moment HLF's development roadmap includes RAFT implementation of the Ordering Service and some notions of BFT-type consensus implementation for later. However, such implementations would still leverage the current code base and they likely would lock-in HLF users with no interoperability whatsoever.

**The goal of our project is to implement a pluggable HLF Ordering Service based on Substrate network**

Enterprise users and consortiums that adopt such Ordering Service would benefit from:

- Truly decentralised Ordering Service with BFT properties.
- Ability to interact with other public and enterprise networks avoiding lock-in in HLF universe (creating similar Substrate-based service for R3 Corda Notary Service is on our road map).
- Ability to join the main Polkadot network through consensus subnetwork, if willing to do so.

### Benefits for the Ecosystem
The Polkadot ecosystem benefits from this project because companies with permissioned or even private blockchain networks would be able to leverage the public Polkadot infrastructure. Such companies will be willing to contribute to Polkadot development and growth in the same way as big enterprises nowadays contribute to many open-source initiatives.

### Technical Approach
As described above we are creating Ordering Service for Hyperledger Fabric. To illustrate what it is and why it’s important we need to make a quick dive into HLF transaction lifeline. To put the transaction in the block, Client Application needs to perform the following actions:

1. Client Application creates a transaction proposal and sends it to Endorsement nodes (organizations representatives in the network).
1. Client Application collects responses from Endorsement nodes and forms a collective package and sends it to the Ordering Service.
1. Ordering Service collects such packages, orders them, creates a block proposal and sends it via commit message to all (not only Endorsement) nodes in the network. 
1. Each node, receiving commit message with the block proposal validates it and, if the block proposal passes validation, appends block to the end of the ledger.

So from the Hyperledger Fabric architecture perspective Ordering Service is responsible for ordering transactions and creating blocks - it receives transactions, forms a block proposal, either by time interval or the number of transactions and sends block proposal to the network. Essentially it means that Ordering Service is responsible for establishing of partial network consensus. In current HLF architecture, all Client Applications that participate in the HLF network (they essentially represent organisations participating in the network) share a centralised Ordering Service and send transaction proposals to it.

**We propose to create the implementation for Substrate-based network node that would instantiate a decentralised HLF Ordering Service.**

In our approach, each Client Application has its node in the decentralised Substrate-based Ordering Service network. It sends transaction proposals to its “own” Ordering Service node. All nodes in the decentralised Ordering Service network would participate in reaching consensus on transactions order. Because each network participant has its representative in the consensus mechanism, it becomes decentralised and acquires desirable BFT properties. 

Commit messages with block proposals will be delivered to Client Application from its own Ordering Service node. Also, because transactions ordering is going to be determined upon Substrate-based network finality, each decentralised Ordering Service node will transmit the same data to its owning Organisation peers.

Pluggable nature of the Ordering service makes it possible to avoid any modifications of current Hyperledger Fabric codebase. In other words, our approach does not require companies to switch to our code branch from the current HLF upstream.

### Motivation
Russian regional market specifics and QBT positioning make us part of enterprise blockchain initiatives. Since 2016 QBT is bringing decentralization ideas to the field. Despite the current crypto-anarchist ideological misfit, enterprises still want to evolve and be a part of the movement. As a result, private and permissioned networks brought to life - usually through platforms like Hyperledger and Corda - that were purposely built to create such networks. 

After several years of studying and using those platforms, we discovered some cut corners in modules responsible for consensus. We decided to try to fix it since the decentralised consensus is an essential piece that blockchain networks rely on from conceptual perspective. We are starting with Hyperledger Fabric since we are witnessing it’s getting significant traction and has broader adoption in a private/permissioned platforms market. However, we are not dismissing Corda as such and plan to create a version of Substrate-based decentralised consensus implementation for that platform too.

## Team Website
https://qiwi.tech

## Legal Structure
Qiwi Blockchain Technologies is the LLC Incorporated in Russia. Qiwi Blockchain Technologies is a wholly owned subsidiary of QIWI (`NASDAQ:QIWI`).


## Team Experience
A fundamental challenge for any enterprise is matching business problems with technological opportunities, including the new business and operational concepts those technologies make possible. Parts of this challenge are extremely difficult because:

- some business problems have no easy or obvious technical solutions; 
- and some emerging technologies may have far reaching business consequences that are still unclear.

**QIWI BLOCKCHAIN TECHNOLOGIES focuses on this hard niche — a set of technical challenges that, if solved, will be of enormous benefit to operational business efficiency.**

With QBT leading expertise, highly skilled team, and overall flexibility we are uniquely positioned to provide value-add services regarding blockchain platform access, solutions development, and providing ready-made blockchain products.

A few examples of QBT projects include:

### Masterchain
Masterchain is the first Russian national network for exchanging and storing financial data. It allows effecting payment online, promptly actualize the data as well as create financial services. The platform features the following services: a decentralized depository system for invoice accounting, a distributed registry of digital bank guarantees, emission of digital letters of credit, and the Know Your Customer project to prevent fraudulent transactions. Masterchain is a permissioned Ethereum fork with Russian cryptography. The communications between the nodes of the network are based on the modified Ethereum protocol. The platform approved and supported by the Bank of Russia.

*Tech stack*: Ethereum (geth).

*Whitepaper*: http://fintechru.org/documents/Masterchain_whitepaper_v1.1_en.pdf

### Metherscan
Blockchain explorer for MasterChain.

*Tech stack*: Python, Go, PostgreSQL, React

https://metherscan.qdlt.io (`login: qbt; password: qbt`)

### QIWI Distributed Processing
The QDP (QIWI Distributed Processing) platform uses open-source software and is based on distributed ledger technology (blockchain), which significantly enhances its safety and lowers maintenance costs. The platform has already been tested and is ready to be commercialized. QDP will serve as a core of blockchain startups at the interface of real financial institutes and new dynamic business models.

*Tech stack*: Go

*Credentials*: github.com/qiwitech/qdp

## Team Members
QBT team includes 10+ highly skilled architects and developers that can contribute to the proposed project. We are highlighting the experience of team members that form the project core team.

- **Peter Kalambet** (https://github.com/kalambet) - System Architect. Worked in global IT companies on cloud infrastructure projects. 10+ experience in IBM research. 
  - Development of blockchain PoC since 2014.
  - Architecture design and PoC implementation of Blockchain Pilots for Platforms based on Hyperledger Fabric, R3 Corda, Ethereum.
  - Contribution to the Cloud Foundry (source PaaS virtualization engine) and porting Cloud Foundry on POWER architecture.
  - Contribution to the privacy-preserving authentication protocol IBM Identity Mixer.

- **Dmitry Moskowski** (https://github.com/corpix), Golang Developer. Worked as a frontend and backend developer in local companies for 8+ years.
  - Worked with various teams at Yandex for ~4 years, frontend and backend engineering.
  - Implementation of the backend components for A/B testing system at Yandex.
  - Design and implementation of the decentralised RTB metrics collection platform on Kafka and ClickHouse.
  - NixOS enthusiast.

## Intended Language of Development
The Fabric part is going to be implemented using Go since the whole Fabric codebase uses Go. And for the Substrate part Rust is going to be used since other runtimes are still in the early stages of development.

## Development Roadmap
### Phase One
*The content of Phase One is the subject of current grant application.*

Provide general implementation where each Client Application has its own Ordering Service (OS), in contrast with current Hyperledger Fabric architecture which implies a single OS per network. Each of this OS will be a node in the Substrate-based network. Ledger, in this case, will contain only transactions and blocks from the Hyperledger Fabric network.

- Ordering service mock implementation (1w)
- Go Substrate JSON-RPC wrapper (1w)
- Base Substrate runtime and storage for Hyperledger Fabric ledger metadata (1w)
- Implement Hyperledger Fabric block cutter based on Substrate chain finality (3w)
- Finalize initial Substrate-based Ordering Service implementation (2w)
- Service auto-provisioning on network deploy and Substrate runtime one-time configuration based on Hyperledger Fabric Orderer config yaml's (2w)
- Performance and stress testing. Documentation creation. (2w)

### Future Development
- **Phase Two**: add consensus algorithm into Substrate that combines PoA (AuRa) and endorsement policy from Fabric, so OS based on Substrate network will be aware of transaction acceptance policy. It will also require to extend ledger by storing Hyperledger Fabric read-write sets.
- **Phase Three**: Extend Substrate runtime with parsing semantic of Hyperledger Fabric read-write sets, to adopt inter-chain messaging.

We also envision implementing similar project to implement Substrate-based consensus for R3 Corda. 

## Additional Information
### What work has been done so far?
Getting familiar with Substrate's and Hyperledger code base.

### Have you applied for other grants so far?
No.

### Are there any other projects similar to yours?
Not to our knowledge.
