# Concerto DAO

## Project Description

### Abstract

Concerto, a Decentralised Autonomous Organisation (DAO), works on top of Polkadot, Bulletproof, and Game Theory. It is not only a trendy technology of Utopia but is also tailored for the real world. Furthermore, a series of problems related to profitability, decentralisation and secrecy that lead to the failure of other DAOs can be solved here. Based on three core principles: profit first, decentralisation, and secrecy, Concerto can successfully strip information asymmetry off individual investment behaviour with the help of game theory and zero-knowledge technology. Owing to the secret and verifiable information on Concerto, investors might gain profit easier than in other classic DAOs with traditional methods.

Concerto DAO will run on Polkadot. The reason for this choice is to widen the range within which the investment can be targeted. Thanks to cross-chain technology, Concerto can theoretically touch any crypto assets in the blockchain world, and makes it possible to directly perform on-chain asset management.

### Whitepaper

https://concertodao.com/Concerto_Whitepaper.pdf

## Team members
* Elder K
* Dr. Moo
* L. Er.
* Neil Sanchez

## Team Website
* https://www.concertodao.com

## Legal Structure
N/A (It's initiated by an anonymous team and will be run in the form of DAO.)

## Team's experience
L. Er., a crypto investor，managing partner of a major token fund. Average investment return of 30X+ during the past 3 years. Tired of centralised way of investment, sick of stupid decision making, and bored of lame funny projects. Try to find a new way of supporting new promising projects without inside information and  monopoly.

Dr. Moo, early investor and adopter of Bitcoin, freelance programmer and miner, has participated in the crowd funding of Ethereum and The DAO.

Neil Sanchez, smart contract developer and community leader, has been an active maintainer of several Dapp projects for years and now is focusing on DeFi.

Elder K, Blockchain Scientist, Rust Developer, Rust-Ethereum(Parity) Contributor, expert in cryptography, has more than eight years experience of Blockchain based software development.

## Team Code Repos
* https://github.com/ConcertoDAO/Whitepaper
* https://github.com/ConcertoDAO/website

## Team LinkedIn Profiles
N/A

## Development Roadmap

### Milestone 1 — Implement Smart Contracts — 1 month — $10,000
* ZKP implementation in Rust with basic Pederson Commitment and Crypto Toolsets and its `ink!` contract API (Apache 2.0 license).
* Testable economic model, Data back testing for our Whitepaper (in Python).
* Vault Contract based on `ink!` DSL for ZKP based Concerto Token Distribution Phase.
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

### Milestone 2 — Additional features — 1 month — $10,000
* Implement Bulletproof NIZK based on our ZKP system.
* Voting / Proposal Smart contracts which are based on Range Proof.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

### Milestone 3 — Additional features — 1 month — $10,000
* Full feature version of Concerto DAO, including Vault, Voting, Proposal and Liquidation Smart Contract.
* Formal verification for Contracts (with Coq).

## Future Plans
* The long-term vision of Concerto DAO is to become a DeFi infrastructure in the Polkadot network. Starting as a DAO-based investment fund, it will gradually expand its business to areas such as lending and insurance.

## Additional Information
When raising DOT for Concerto investment fund, we need to implement a fundraising smart contract to make sure the process is transparent and safe. However, smart contracts are not supported on Polkadot relay chain and the promising parachains such as Edgeware have not been connected to the relay chain so contracts on them cannot interact with DOT assets. Therefore we have to do this in a semi-centralised way. If it's possible, we'd like to have w3f members to hold some of the multi-sig keys for the fund. When everything is ready, we'll migrate the funds to a smart contract on the Polkadot ecosystem.
