# Paraswap

## Description

Paraswap is a Substrate pallet that implements the constant product market maker model ([XYK model](https://github.com/runtimeverification/verified-smart-contracts/blob/uniswap/uniswap/x-y-k.pdf)) for automated market makers (AMM).
Pallet will allow other parachains to include AMM features, that will provide decentralized exchange of tokens.

Exchange of assets is one of the fundamental operations in crypto ecosystems and provides liquidity for endless blockchain usecases.
We choose peer-to-contract exchanging as it proved popular in Ethereum DeFi ecosystem and it can serve as a [Price oracle](https://web.stanford.edu/~guillean/papers/uniswap_analysis.pdf) service for the Polkadot ecosystem.
When demand will be validated, we will consider other AMM models in the future.

We will develop a pallet that implements XYK model to allow:

1. Internal Parachain swapping through Assets pallet
2. External swapping between two other parachains (through XCMP)

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

**Phase 1 - the first ½ of funding - week 2-4:**
  
  (with respective documentation)
  License: Apache 2.0

  TBD

 **Phase 2 - the second ½ of funding - week 4-10:**
  
  (with respective documentation)
  License: Apache 2.0
  
  TBD

## Future Plans

We plan to develop fully functional AMM parachain, once we develop the pallet foundations for it.
Product-wise it can develop in two directions:
  1. run multiple AMM models simultaneously (peer-to-contracts)
  2. aggregating the ecosystem liquidity, by load balancing different liquidity demands towards one liquidity pool.

## Additional Information

We're behind the [Polkalert](https://www.polkalert.com) (Substrate node monitoring tool)
and [API explorer](https://apiexplorer.polkalert.com/) (Substrate chain API inspection tool).

We have a running PoC of XYK pallet on a remote Subtrate node (to be provided) 
