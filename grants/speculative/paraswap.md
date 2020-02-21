# Paraswap

## Description

Paraswap is a Substrate based parachain that implements the pallets for the constant product market maker model ([XYK model](https://github.com/runtimeverification/verified-smart-contracts/blob/uniswap/uniswap/x-y-k.pdf)) for automated market makers (AMM).
Open sourced pallet will allow other parachains to include AMM features, that will provide decentralized exchange of tokens.

Exchange of assets is one of the fundamental operations in crypto ecosystems and provides liquidity for endless blockchain usecases.
We choose peer-to-contract exchanging as it proved popular in Ethereum DeFi ecosystem and it can serve as a [Price oracle](https://web.stanford.edu/~guillean/papers/uniswap_analysis.pdf) service for the Polkadot ecosystem.
When demand will be validated, we will consider other AMM models in the future.

We are interested in this project because we have a passion in DeFi, we love the orderbooks and we have a great team fit for this implementation.

## Team members
* Name of team leader

    __Peter Kris__
    
* Names of team members

    __Gleb Urvanov__
    - Architect, Rust engineer, Backend developer
    - PhD dropout from Nuclear university Moscow - track record of mobile OS engineering, machine learning, smart contracts. Has been tinkering with derivatives on Ethereum early on and likes to get hands-on in mathematics of it.
    
    __Jakub Panik__
    - full stack developer, DevOps, Substrate/Polkadot JS API explorer
    - Jakub opened up many issues on the Polkadot JS or even suggested improvement for [1.0.1 version](https://github.com/polkadot-js/api/releases/tag/v1.0.1)
    
    __Stanislav Vozarik__
    - Rust developer
    - previously progamming automated trading strategies in C++, exploiting orderbooks on traditional derivates exchanges
    - Economics graduate with passion in option pricing and formalizing derivates in general
    
    __Jakub Gregus__
    - product consultant
    - blockchain and DeFi researcher with bold opinions on management of liquidity pools and aggregating them
    - Zee Prime Capital partner
    
    __Peter Kris__
    - project / product management
    - generalist, full stack dev, leader of Block Unison, passionate about DeFi

## Team Website	

[https://www.blockunison.com](https://www.blockunison.com)

## Legal Structure 
Block Unison LTD, based in Southampton, England

## Team's experience
Block Unison is a company of active engineers since the beginning of Ethereum.
With the help of [Zee Prime Capital](https://zeeprime.capital/), we're behind the [Polkalert](https://www.polkalert.com) (Substrate node monitoring tool)
and [API explorer](https://apiexplorer.polkalert.com/) (Substrate chain API inspection tool).
In the past, we've engineered many small Solidity solutions up to high-budget projects that required significant scaling of blockchain operations.
We're gathering blockchain talent across SK/CZ/UK/RU markets, have been involved in core community since the early Bitcoin days, organising events, doing workshops (Rust workshop the last time).

## Team Code Repos
[https://github.com/gleb-urvanov](https://github.com/gleb-urvanov)

[https://github.com/jak-pan](https://github.com/jak-pan)

[https://github.com/PetoU](https://github.com/PetoU)

## Team LinkedIn Profiles
- [https://www.linkedin.com/in/gleb-urvanov/](https://www.linkedin.com/in/gleb-urvanov/)
- [https://www.linkedin.com/in/peter-kris-a7274054/](https://www.linkedin.com/in/peter-kris-a7274054/)
- [https://www.linkedin.com/in/jakub-gregus-3025018a/](https://www.linkedin.com/in/jakub-gregus-3025018a/)
- [https://www.linkedin.com/in/jakubpanik/](https://www.linkedin.com/in/jakubpanik/)

## Development Roadmap

**First milestone: Core functionality**

Time estimation: week 1-4
(with respective documentation)

1. Automated Market Making exchange, allowing instantaneous trade between different assets. Technical implementation: the solution will be provided in form of open source Substrate pallet, operating with Generic Assets (by Substrate) and thus reusable by any other substrate-based blockchain supporting the pallet.  

The exchange pallet will include following functionality:  
    - create pool  
    - mint/burn liquidity  
    - swap assets  
    - read-only RPC methods to calculate swap price  

2. Bridge for Ethereum ERC-20 compatible tokens to their representations on our blockchain.
Bridge functionality should be provided in a permissionless way. The solution will include a Substrate pallet on our blockchain side, and Ethereum solidity smart contract on Ethereum side. Assets sent to the pallet or contract will be locked in the transfer pool, and will become accessible on the other side of the bridge correspondingly.
Technical implementation: we are considering Parity Bridge (https://github.com/paritytech/parity-bridge) or a custom implementation. There is a possibility to choose another bridge implementation if found suitable.

3. Tests. The code provided in form of Substrate pallets will be covered by tests sufficient to control correctness of the code behavior and to cover corner cases.

Technical implementation: tests for pallets in Rust language.

4. UI. It is suggested to implement the UI for the system in form of plugin for Polkadot Apps. This will allow us to avoid the necessity to implement our own substrate wallet app, while having a convenience from standard chain utilities in the same app. The alternative of having our own web application is also considered.

Technical implementation:  
    - frontend application in typescript. 
    - UI features for the milestone:
    - Create an asset
    - See asset balance using AssetId
    - Transfer Asset
    - Create Pool
    - Mint liquidity
    - Burn liquidity
    - Swap assets
    - View pool by asset id pair

**Second milestone: Advanced functionality**

Time estimation: week 4-8
(with respective documentation)

1.  Native blockchain asset (currency) will be introduced, and holding or using the native asset will alter (reduce) exchange fees.

Technical implementation: Generic Asset pallet by Substrate.

2. Consensus. The first consensus mechanism will be added to the network.

Technical implementation: Aura pallet by Substrate.

3. Staking. To reduce overcollateralization, provide additional benefits for validators and to increase validor’s responsibility, the staking will be implemented in form of liquidity provisioning (market making) to exchange pairs between the native asset and the asset chosen by validator. Using validator’s stake for market making will increase exchange capitalization.
Technical implementation will include implementation of the custom staking pallet.

4. Liquidity pool. The pool, containing assets locked by staking or liquidity provisioning, should be inaccessible by any parties excluding corresponding blockchain frame pallets. 

Technical implementation: while in Ethereum network every smart contract has an address suitable for that purpose, the implementation using substrate framework is to be defined.

**Third milestone: Testnet launch**

Time estimation: week 8-12

1. The primary goal of the launch of functional and publicly available testnet, bridging our blockchain with chosen Ethereum testnet (Ropsten and Goerly are considered). All the functions of first and second milestones will be accessible by testnet users.

2. Documentation covering running a testnet node, validating or using the blockchain will be provided.

3. UI functionality will be extended during the third milestone implementation. 
Technical implementation of the application will require a backend application. NodeJS and Typescript language are chosen for the backend implementation.
New features will be:  
    - Add asset metadata like Name, Decimals, etc
    - Parse asset meta from ethereum network (if asset is bridged)
    - Search Pools by asset id or asset name/ticker
    - Bridge asset to/from ETH address
    - Asset exchange/transaction history
    - Account asset balance history
    - Account value estimation (in given asset)

**Extra: XCMP protocol support**

1. The next goal to implement after reaching the milestones above and essential for the project is interoperability between substrate-based chains supporting XCMP protocol and generic assets.


## Future Plans

We plan to develop a fully functional AMM parachain, once we develop all the pallets needed and go through testnet phase.
Product-wise it can develop in two directions:
  1. run multiple AMM models simultaneously (peer-to-contracts)
  2. aggregating the ecosystem liquidity, by load balancing different liquidity demands towards one liquidity pool. (The first phase is aggregating staking and liquidity provisioning pool)

## Additional Information

We're behind the [Polkalert](https://www.polkalert.com) (Substrate node monitoring tool)
and [API explorer](https://apiexplorer.polkalert.com/) (Substrate chain API inspection tool).

We have a running PoC of XYK pallet on a remote Subtrate node
[Github repo of PoC](https://github.com/gleb-urvanov/substrate-xyk) 
