# Simplex Protocol

**Project : Simplex Protocol - DEX Pallet**

## Project Overview

**Overview**

Simplex Protocol is building a decentralized protocol on a dedicated trading chain built on polkadot. It will enable deep liquidity starting with support for the exchange of tokens on Simplex Chain, all parachains and ethereum. It then expands on this with support for additional blockchains.  

Our Decentralized EXchange (DEX) uses a dynamic bonding curve supports liquidity pools for unpegged tokens like ETH,DOT, LINK, ACA etc as well as stable coin pools offering low slippage (e.g. DAI,USDT) and moving forward stable coins with different pegs (e.g. smpUSD, smpCNY).

**Deployment**

This phase of the project will be built and deployed on a standalone chain [Simplex Protocol Auriga](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fsimplexprotocol.auriga.dev#/explorer). Subsequent Phases involve deploying as a parachain with the initial target of Rococco.

**Polkadot Ecosystem Benefits**

This protocol lays the foundation for asset exchange, stable coins and advanced aggregation. This will attract the decentralized finance community, provide more liquidity and drive adoption for polkadot.

**Why are we creating this project**

This project provides a foundational layer for the Simplex Protocol.

Our team consists of founders, researchers, builders and strategist for blockchain and decentralized finance. We have built a layer 1 blockchain at Harmony (public blockchain with sharding and open staking). We have chosen to build this project on Polkadot because Substrate allows us to focus on the Protocol and business logic and also we feel the Partners in the ecosystem are laying the foundation for interoperable decentralization and we want to be part of this community.

### Project Details

Please see [this two minute introductory video](https://www.youtube.com/watch?v=9hkUvW5hNOU)  for an overview of the Simplex Protocol vision.

Below are the high level github repositories for the Simplex Protocol.

- Simplex Chain (based of substrate node template)
- Simplex DApp  react based frontend
- Simplex Explorer: forked from polkadot-js/apps
- Simplex js: fork of polkadot.js
- Simplex faucet-bot : faucet functionality

## Ecosystem Fit

For the DEX and bridging phase of Simplex Protocol similar projects include Acala, Polkaswap, Reef and snowfork. 
From our review of the other protocols we are the only protocol to offer multi-asset pools, optimized stable coin support, dynamic bonding curves adjustable transaction fees and limit orders.
We combine this with bridging capabilities for multi-platform support, combinatorial staking for better rewards and synthetic asset support to offer a complete soluiton.

This application is specific to the DEX Pallet and lays the foundation for the larger vision which can be seen in our [draft white paper](https://docsend.com/view/f3ts75wer8yq7ii3). 

### DEX Evolution

| Protocol | DEX | Reward Token | Multi Asset Pools | Optomized StableCoin Support | Dynamic Bonding Curves | Limit Orders | Multiple Platform Support | Dedicated Trading Chain | Synthetic Assets |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-:|
| Simplex | YES | YES | YES | YES | YES | YES | YES | YES | YES |
| Uniswap | YES | YES | NO | NO | NO | NO | NO | NO | NO |
| Balancer | YES | YES | YES | NO | NO | NO | NO | NO | NO |
| Curve | YES | YES | YES | YES | NO | NO | NO | NO | NO |
| Acala | YES | YES | NO | NO | NO | NO | NO | YES | YES |
| Reef | YES | YES | NO | NO | NO | NO | YES | TBD | NO |

The following protocols offer specific functionality and are often leaders in their respective areas.  The points below walk through a chronological evolution of DEX and cross-chain capabilities.

- Decentralized Exchanges leader Uniswap introduced a simple bonding curve supporting two token liquidity pool.
- It recently introduced it’s UNI token which is now table stakes for all Decentralized EXchanges, Simplex Protocol combinatorial staking extends this combining trading, protocol and stability fees.
- Multi Asset Pools were introduced by Balancer and adopted by Curve who introduced the first bonding curve to support stable coins.
- Simplex adds to this with our dynamic bonding curves which supports multi asset pools and stable coins as well as regular tokens.
- Our Liquidity Providers can set the transaction fees when creating a Liquidity Pool similar to Balancer and Curve.
- We also introduce limit orders powered by our unique off-chain worker capabilities.
- Polkadot and Ethereum are supported initially with more platforms to come powered by our integrated bridging technology.
- Acala and Reef are also building on Polkadot which provides the ability to create dedicated trading chains.
- Maker introduced collateralized stable coins also known as synthetic assets, Acala has replicated this on Polkadot and Simplex is looking to extend this with collateralized assets using DOT, ETH and eventually Simplex’s own SMP Token.

## Team 👥

### Team members

- Chao Ma: Simplex Protocol Co-founder
- Minh Doan: Simplex Protocol Co-founder
- John Whitton: Simplex Protocol Co-founder

### Team Website

- [https://simplexprotocol.com](https://simplexprotocol.com)

### Legal Structure

None at this time. 

### Team's experience

The team all have experience working on the Harmony Protocol as founders, researchers, and ecosystem architects. Chao Ma led the core protocol development, Minh Doan was a Founder and core Protocol Developer/full stack engineer and John Whitton focused on Developer Tools and building the Ecosystem

Relevant Contributions are 

- Chao Ma: Chao has strong research experience in mathematics and has published 6 papers with 180 citations. Chao has previously  worked in Artificial Intelligence and the blockchain industry. He has  worked on various components of a layer 1 protocol such as view change in consensus, state syncing, cross-shard transactions and open staking. Currently, his main areas of interest are blockchain, cryptography and zero knowledge proofs.
- Minh Doan: Minh has strong engineering experience, with over 20 years of programming. Prior to co-founding Simplex Protocol, Minh prototyped 4 projects nimspace.com, remotiveworks.com, [screentor.com](http://screentor.com) and [codelight.ai](http://codelight.ai) in 4 months. Minh was a co-founder of [Harmony](http://harmony.one) where his tasks included designing, building and deploying blockchain data structures, consensus, network deployment of 10k nodes, blockchain explorer, SDK, dapp development and a  staking dashboard. Minh worked at several startups and at Google as a technical lead. Minh came to the US to pursue his Ph.D. in Computer Science.  Minh is also a competitive programming winner and  medalists in several national programming contests (USACO Open Winner 2001).
- John Whitton : John's originally met Gavin Wood in 2016 and worked briefly with Tomasz Drwięga on Parity before taking a role as CTO of a small Blockchain Startup based on Ethereum which then moved to Hyperledger. He did further [research](https://github.com/johnwhitton/blockchain-eval/blob/master/substrate.md) into Polkadot and Substrate in 2019 and did strategy work on smart contract protocols and digital assets in 2019 including working on Cowri,a stablecoin exchange protocol, before taking a role with Harmony as an Ecosystem Architect with a focus on Developer tooling and Ecosystem growth. His technical Portfolio is [here](https://johnwhitton.dev/docs/docs/learn/portfolio/) and more information can be found on [johnwhitton.dev](https://johnwhitton.dev/).

### Team Code Repos

- [https://github.com/simplexprotocol](https://github.com/simplexprotocol)
- [https://github.com/chaosma](https://github.com/chaosma)
- [https://github.com/johnwhitton](https://github.com/johnwhitton)
- [https://github.com/daywednes](https://github.com/daywednes)

### Team LinkedIn Profiles

- [https://www.linkedin.com/mc8305/](https://www.linkedin.com/in/mc8305/)
- [https://www.linkedin.com/in/daywednes/](https://www.linkedin.com/in/daywednes/)
- [https://www.linkedin.com/in/johnwhitton/](https://www.linkedin.com/in/johnwhitton/)

## Development Roadmap

In this phase we plan to develop initial decentralized exchange Pallet for the Simplex Protocol. 

Please see here for [Simplex Protocol Dynamic Bonding Curve definition](https://www.notion.so/Simplex-Protocol-Bonding-Curve-b67269f453ec427488e23e5a368eaa9d).

### Milestone 1: Framework design and minimal DEX Pallets 

* Estimated Duration: 1 month
* FTE: 1.5
* Costs: $10,000

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a.	| License	| GNU GPL v3 |
| 0b.	| Documentation	| We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how to create a liquidity pool and provision funds to it. |
| 0c.	| Testing Guide	| The code will have proper unit-test coverage (e.g. 90%) to ensure functionality and robustness. In the guide we will describe how to run these tests. |
| 1. | Pallet: Simplified Bonding Curve	| We will create a Pallet that will implement simplified bounding curves. |
| 2. | Pallet: Liquidity Provisioning	| We will create a Pallet that will implement Liquidity Pool Provisioning. |
| 3. | Substrate chain	| We will Host this on our [Auriga Standalone Network](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fsimplexprotocol.auriga.dev#/explorer) |
| 4. | Docker	| We will provide a dockerfile to demonstrate the full functionality of our chain |

### Milestone 2: Full version of SMP model 

* Estimated Duration: 1 month
* FTE: 1.5
* Costs: $10,000


| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a.	| License	| GNU GPL v3 |
| 0b.	| Documentation	| We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how to create a liquidity pool and provision funds to it. | 
| 0c.	| Testing Guide	| The code will have proper unit-test coverage (e.g. 90%) to ensure functionality and robustness. In the guide we will describe how to run these tests. |
| 1. | Pallet: SMP Bonding Curve | We will create enhance the simplified bonding curve created in Phase 1 to the SMP dynamic bonding curve. |
| 2. | Pallet: SWAP Functionality | We will create a Pallet that will implement SWAP functionality. |
| 3. | Pallet: Basic Reward Functionality | We will create a Pallet that will implementBasic Reward Functionality. |
| 4. | Substrate chain | We will Host this on our [Auriga Standalone Network](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fsimplexprotocol.auriga.dev#/explorer) |
| 5. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Milestone 3: Simplex DApp on Test Network 

* Estimated Duration: 1 month
* FTE: 1.5
* Costs: $10,000


| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a.	| License	| GNU GPL v3 |
| 0b.	| Documentation	| We will provide both inline documentation of the code and a basic tutorial that explains how a user can deploy the Simplex Protocol DApp and the polakdot-js app forked by Simplex Protocol with DEX Capabilities. | 
| 0c.	| Testing Guide	| The code will have proper unit-test coverage (e.g. 90%) to ensure functionality and robustness. In the guide we will describe how to run these tests. |
| 1. | Polkadot-js app DEX Capabilities | We will fork polkadot-js app and provide dex functionality | 
| 2. | Simplex Protocol DApp | We will build Simplex Protocol DApp with DEX Functionality |
| 3. | Applications Deployed and Hosted on Auriga | We will create a Pallet that will implementBasic Reward Functionality. |
| 4. | Substrate chain | We will Host this on our [Auriga Standalone Network](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fsimplexprotocol.auriga.dev#/explorer) |
| 5. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |
| 6. | Community Education | We will publish Medium Articles in English Chinese and Vietnamese and also posts on twitter. Explaining the DEX Functionality. |

## Future plans

We plan to make our chain one of the parachain in polkadot ecosystem. Thus, there are still a lot of work to be done. Here are a few of them:

1. Implement SMP Incentivization Functionality
2. Bridging Functionality (XCMP Parachain Integration and Ethereum snowfork like integration)
3. Application Functionality (Simplex Dapp, polkadot-js apps, wallet)
4. Parachain Functionality (Launching on Roccoco initially)
5. Collateralized StableCoins Support
6. Governance model using SMP

## Additional Information

Work done so far has included research and prototyping.

No other teams have contributed to the project.

This is our first grant application. 
