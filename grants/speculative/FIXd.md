# FIXd

The Decentralized Financial Information Exchange (FIXd) is an immutable, permissionless, open source orderbook and high performance matching engine system for peer-to-peer trading applications. 

## Project Description

For projects facilitating inter-chain (Bitcoin <--> Ethereum) or intra-chain (ERC20 <--> ERC20) exchange of cryptoassets using Hashed Time-Locked Contracts (HTLCs) or similar mechanisms to ensure atomicity of swaps, the settlement process might be the simplest part of the project. This is due to many recent research and practical advances in protocols to accomplish reliable trades with HTLCs. Moreover, many projects already offer on-chain settlement in a production environment.

However, it turns out that a significant part of the peer-to-peer trading problem exists *before* on-chain settlement begins. These are the steps in the peer-to-peer trading process that every peer-to-peer trading application developer still struggles with:  

1. Discovering a trading counterparty
2. Negotiating the terms of your contract
3. Persisting and making immutable the terms of the agreement *without the involvement of any third-party operated infrastructure*

FIXd provides a decentralized solution to steps 1-3 above; it replaces the dedicated and centralized server that application developers typically need to operate in order to help users easily communicate their intentions and commit to a trade.

In summary, FIXd has the following high-level characteristics:

* Permissionless blockchain and P2P network
* Provides similar features of a distributed database, with ACID properties
* Fast lookup and response times
* Uptime exceeding current financial industry expectations
* Pseudonymous network by default (stronger privacy protections are planned for the future)
* Free and Open Source Software (Apache 2.0)
* Built-in matching engine, with support for limit, partial, and stop-loss orders (additional and more advanced options are planned for the future)
* Well-defined interfaces, i.e. the interfaces which settlement engines/applications for multiple chains will rely on 

In addition to making DeFi application developers and traders happy, FIXd also satisfies financial regulators: what regulators are most interested in is preventing a third party from modifying or faking the orderbook history, or otherwise affecting the outcome of future trades. FIXd is an open system that makes auditing scriptable, so regulators can perform the same audit checks and policy enforcement without an army of people.

FIXd lets p2p trading application developers focus on publishing great trading applications, rather than operating infrastructure and worrying about compliance.

Last but not least, FIXd plays a great role in the Web3 ecosystem:

* Uses substrate as the underlying technology
* Uses libp2p as the enabler for securely relaying messages
* Community-centered project, enabling trading applications

## Team Details

### Websites

* https://sibex.io
* https://docs.sibex.io
* https://trade.sibex.io
* https://gitlab.com/sibex

### Members

* Dr. Guilherme Sperb Machado
* Justin Smith
* Robert Balas
* Sergiu Falcusan
* Alin Turbut
* Cristian Ilca

### Team's Experience

Our team was the first to deploy Atomic Cross-Chain Swaps via HTLCs in a B2B environment, and we shipped our first peer-to-peer trading products in less than 6 months. Together we have decades of combined experience building applications for Bitcoin, Ethereum, Neo, Aion, Zcash, and Monero. We also have more than 30 years of combined experience in delivering software projects.

The team has a proven track record of developing open source projects, as well as working at large corporations. Moreover, members are integrated on the Blockchain ecosystem by attending and speaking on multiple venues/conferences, such as [ETH Devcon](https://devcon.org), [NEO Devcon](https://devcon.neo.org), [Zcon](https://www.zfnd.org/zcon/), [Crypto Valley Conference](https://www.cryptovalleyconference.com), and others.

One of the members, Dr. Guilherme Sperb Machado, has also vast academic experience -- where he holds a Guest Researcher position at the University of Zurich, Switzerland. In the past, he co-authored papers in the area of peer-to-peer systems and, more recently, published the paper entitled "Rational Exchange: Incentives in Atomic Cross Chain Swaps" at the IEEE ICBC 2020 conference.

In summary: our team consists of individuals with industry and academic background, not only fine designing and architecting solutions but also materializing them into usable, solid, and scalable products.

### Team Code Repositories

* Dr. Guilherme Sperb Machado
  - https://github.com/gsmachado | https://gitlab.com/gsmachado
  - https://github.com/neow3j
  - https://github.com/axlabs
* Justin Smith
  - https://gitlab.com/sibex
  - https://gitlab.com/rusticbison/xwallet
* Robert Balas
  - https://github.com/aionnetwork/aion
* Sergiu Falcusan
  - https://github.com/aionnetwork/aion
  - https://stackoverflow.com/users/1696716/smotru
* Alin Turbut
  - https://github.com/aionnetwork/aion_pool2
  - https://stackoverflow.com/users/2424320/turbut-alin
* Cristian Ilca
  - https://github.com/aionnetwork/Desktop-Wallet/graphs/contributors

### Team Profiles

* Dr. Guilherme Sperb Machado
  - https://machados.org/gsm
* Justin Smith
  - https://jsmith.site

## Legal Structure

Please see Google Form.

## Development Roadmap

### Milestone 1 - 5 month

FTE (Full-time Equivalent):
  * Senior SWE (Software Engineer): 2 FTE

Activities:
* Build a blockchain-based OrderBook with substrate (FIXd daemon)
* Evaluate which consensus mechanism available on substrate is the most suitable to this use case (i.e., Aura, Aurand, BABE, Grandpa), or if adaptions to an existing mechanism are required
* Validation should be performed via a quorum of validator nodes
* Every transaction represents an order action to the orderbook (e.g., creating an order, canceling an order, etc), including a fee
* Evaluate and implement a fee mode, as well as a payment scheme (e.g., fees could also be paid with BTC, ETH, or USDT)
* Fees are paid to a randomly chosen validator node to validate each transaction
* Zero fee transactions are ignored, higher fee transactions are prioritized
* The FIXd daemon focuses on the orderbook; thus, the settlement part (HTLCs) should happen outside of the FIXd daemon, possibly using substrate's off-chain workers feature
* Well-defined interfaces to external settlement components
* Document architectural decisions, network principles, parameters, and daemon's modules

### Milestone 2 - 3 months

FTE (Full-time Equivalent):
  * Senior SWE: 2 FTE

Activities:
* Build the matching engine (part of the "chain specification")
  * Limit orders support
  * Partial orders support
* API v1: JSON-RPC and Websocket interfaces
* API v1: Documentation of JSON-RPC and Websocket interfaces
* Website with an introduction to FIXd, code examples, API documentation
* Docker testnet (docker-compose) to demonstrate the project's functionality

## Future Plans

* Legacy financial organizations use a protocol specification to exchange messages with each other called [FIX](https://www.fixtrading.org/standards/). Originally written in 1992, FIX is simply a standardized messaging system, and does not prevent the corruption and cheating that is so common behind closed doors in global financial markets. We would like to see the FIXd project to evolve into a global Financial Information eXchange protocol that enforces good behavior, rather than suggests it. The FIXd protocol should be governed and maintained by the community of developers and organizations who are building peer-to-peer trading and finance applications, rather than legacy financial organizations.
* Implement a FIX gateway interface, which would bridge the old world ([FIX standard](https://www.fixtrading.org/standards/)) to the FIXd project's interfaces; this way, legacy trading systems could have a smoother integration to the new world of asset trading FIXd aims to provide.
* Support for additional, more complex order types, such as "iceberg" orders.
* Support for additional crypto-currencies.
* Provide better privacy guarantees (e.g., use ZK techniques).
* Optimizations: tweaking the incentive mechanism, investigating edge cases and in general improving the reliability of the system.
* Parameterize the system; meaning to build it more generically so that it can be more easily forked.

## Additional Information

* SIBEX AG has already developed a simple prototype peer-to-peer network and messaging system which can be the basis of FIXd (using libp2p)
* SIBEX AG has started to port its current production relay's capabilities to the prototype
* SIBEX AG is willing to adapt its own current proprietary settlement protocol (based on HTLCs) to be plugged to the FIXd project
* SIBEX AG will provide a complementary source of funding for this project. Web3 grant funding triggers Apache 2.0 licensing and immediate public access to the project repository.
* SIBEX AG will provide management support for the project.  
  

