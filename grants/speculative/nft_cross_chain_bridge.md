# NFT Cross-chain Brige

## Project Description
The XClaim framework provides a general method for how to build a token bridge between two blockchain network, one of the two blockchain required to support smart contract and chainRelay.

But it made some assumptions to the token, which should have price feed provided by Oracles and should have good liquidation to prevent price violation.

When we were trying to apply this framework to non-fungible token, we found some new challenges, including:

* It is hard to find a price feed using Oracles, because there is not no such liquidation exchanges for NFTs.
* NFT price varies for different holders in the market, so it is hard for requiring the *Vault* to providing sufficient collateral.

To resolve these two issues, Darwinia have two proposals for the solution:
* Introducing Harberger Tax mechanism from radical market, to provide a rational price finding method for NFTs.
* Give more assumption about the blockchain networks, that the two networks should both support smart contract and chainRelay. In this way, the vault and iSC can verify with each other, and eliminate the requirement of sufficient collateral. At the same time, it also increase the capital efficiency for *Vault* to involve and contribute.

By the way, Darwinia network already listed on Polkadot wiki in community section https://wiki.polkadot.network/en/latest/polkadot/build/examples/

## Team members
* Alex Chien

* Denny Wang


## Team Website	
https://www.itering.com

https://darwinia.network/


## Team's experience
Core team of Darwinia Network is from Itering Tech Co., Ltd. 

Itering has a complete and professional team from technology to operation. The technical department has many senior experts engaged in the development and technical research of blockchain field, and has rich experience in consulting and development on blockchain technology such as public chain technology, Ethereum and smart contract.

* Alex Chien

Excellent technical expert in blockchain, full stack engineer, has been involved in the technical work of bitcoin and blockchain since 2011, and has participated in the technology development of several open source projects, especially in graphene technology and EVM smart contract technology. Very rich development experience.

* Denny Wang	

Excellent technical expert in blockchain, core developer of BitShares 1.0, intelligent contract security expert. Now he is mainly engaged in Ethereum's Layer2 network and Polkadot cross-chain related research. He has served as technical leader in several blockchain technology companies.

## Team Code Repos
* https://github.com/darwinia-network
* https://github.com/evolutionlandorg
* https://github.com/itering

## Team LinkedIn Profiles
* https://www.linkedin.com/in/alex-chien-46448216/
* https://www.linkedin.com/in/denny-wang/

## Development Roadmap

### The specifications of the project including:

There are some new challenges and different concern when providing a cross-chain solution for NFT compared to XClaim's framework. It will meet the following requirements:

* Safety
* Liveness
* Consistency
* Redeemability

It can also been split into three parts:

- With the basis design of XClaim, replace price finding module from oracle's price feed to "Harberger Tax" Model

    - The price finding mechanism for *Vault* to determine how much collateral are required.
        * NFT holders evaluate a price and pay a cross-chain fee to the NFT mortgagor (Vault)
        * When the redemption is initiated, if the lock Vault does not release the NFT, its collateral will be fined and compensated to the NFT holder.
    - Mitigating Exchange Rate Fluctuations and price extreme devaluation
        * After the NFT holder changes, a new evaluation price can be initiated to remind the Vault to make up the collateral.
        * If the Vault collateral is seriously insufficient, the NFT will be forcibly redeemed by the issue contract to the account designated by the holder.
    - The specification is in the middle of [drafting](https://github.com/darwinia-network/rfcs/blob/master/paper/XClaim_Based_NFT_Bridge_Protocol_CN.md) (English version is TBD)

- Removing the requirement of Vault's Collateral by introducing two chainRelay(one for each blockchain) in the design
    - Introduce the two chainRelay model to build a trustless solution for the crosschain solution
        * ChainRelay can maker *Vault* work as wish, it can only follow the instruction on another chain to redeem to specific account, and avoid cases of malicious and attack. 
    - The comparison between two chainRelay design and XClaim's design.
        * Require the assumption that both blockchain support smart contract and chainRelay.
        * Benchmark and estimation about the cost and performance of the chainRelay on major blockchains (Ethereum etc.).
        * The disadvantage of the XClaim's model: Very low efficiency of funds from rational economic analytics, which will make the adoption being very hard.
        * Details Diagram and algorithm about the design. 
        
- NFT Standards on Polkadot, and the design on normalization process for bridged tokens to resolve indentifiability and resolution issues.

Currently we are still drafting the specification. We will focus on the scope of resolving challenge problems about how to do cross-chain non-fungible token inter-operations.

### Milestones

- M1 (3 weeks):Full specification on cross-chain bridge for NFT.
    - Deliverables
        - A description of the functionality and requirements of NFT bridge design.
        - A full written specification of the NFT bridge design. The specification should be detailed
          enough such that a competent team could implement the bridge.
        - A security analysis to explain how the specification corresponds to the stated
          requirements.

- M2 (3 weeks): Produce a minimal PoC (On Ethereum testnet and Darwinia testnet). 
    - Features and functions
        - ChainRelay PoCs on Ethereum and Tron testnet.
        - Minimal Poc of Vault and Issuing smart contract.
    - Deliverables
        - Docker container running a substrate node with NFT bridge runtime included, can connect to testnet and syncing blocks.
        - Finish a NFT cross-chain issue and redeem actions according to protocol.

- M3 (6 weeks): Full Implementation. 
    - Deliverables
        - A fully working software implementation of the NFT bridge specification.
            * Our acceptance tests should mostly consist of sending messages and/or
              value through the bridge while preserving trust model constraints.
        - Complete documentation
        - A demonstration that security was considered throughout the entire project lifecycle and evidence that the implementation has no known security flaws.
        - Open source and be licensed using Apache 2.0 (preferred) or the GNU GPL v3 license.
 
After that, there could more testnet for testing and security auditing and preparing for the mainnet launch at Q4 2019 or Q1 2020. 

For M1 milestone, we are willing to request $5K. For M2 milestone, we are willing to request $10K. For M3 milestone, we are willing to request $15K.
We are ok to accept DOTs as payments, all in DOTs is good.

## Additional Information
**Tech & Ecosystem**

Darwinia Network is committed to being a parachain for Polkadot, which we are preparing for both Tech and Ecosystem.
You can check our github and homepage for tech detail

**Home**: https://darwinia.network/

**GitHub**: https://github.com/darwinia-network

Meantime, Darwinia Network design a Staking mode to build ecosystem to bid Polkadot parachain. We look forward to Polkadot’s advising and support.

Community
We host a meetup about blockchain in Nanjing ,China to help build Polkadot community. Here are some photos and reference for the meetup.  We look forward to Polkadot team coming to Nanjing!
Photos for the meetup: https://docs.google.com/document/d/102bC3WZneeKwS2OQl7eJ31D1U--BGyDbfYvflAcbJss/edit?usp=sharing

**News for the meetup:**

https://www.huodongxing.com/event/1496429656800

https://mp.weixin.qq.com/s/9KuIkOt3CY_oKdnBAkaNYA

https://mp.weixin.qq.com/s/xfqTKTUpElOPp1hzwBnukQ

**Is it open source?** 

Our code will be fully open source.

