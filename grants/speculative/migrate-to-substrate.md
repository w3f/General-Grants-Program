# Migrate to Substrate

## Project Description

If you have an existing group of token holders that you want to migrate to a
Substrate based blockchain, you'll most likely run into the situation that the
old and the new address system are incompatible.

Since Substrate addresses are encoded pubkeys, this happens when some of the
token holders are identified by an `address = derive(pubkey)` with unknown
`pubkey` only or when users' keypairs change.

The Shift team faces this challenge when migrating from a legacy
[Lisk](https://lisk.io/)-based blockchain to Polkadot. To make a migration to
Substrate possible, we propose a way to transfer the old tokens to the new
system in a secure and convenient way.

The same problem exists when you want to perform an airdrop over a different
crypto ecosystem or when switching from one signature algorithm to another. We
intend to solve the primary problem in a sufficiently general fashion to cover
those use cases as well.

## Team Members

The following people from the Shift team will be involved in this project:

- **Simon Warta**: Software Engineer, Lead developer for this project
- **Ralf S**: Software Engineer, Co-founder Shift
- **Heisenberg**: Conceptual Engineer

## Team Website

- Main website: https://www.shiftproject.com
- Twitter: https://twitter.com/ShiftNrg
- Migration to Polkadot / Substrate Summary: https://www.shiftproject.com/news/6
- AngelList: https://angel.co/company/shiftproject

## Legal Structure

A private company registered in the Netherlands. Details will be provided
privately to the Web3 foundation.

## Team's Experience

- **Simon Warta**
  ([Github](https://github.com/webmaster128/)/[Twitter](https://twitter.com/simon_warta)/[Medium](https://medium.com/@simonwarta)):
  Focused on client-side cryptography; Lead developer of the multi-blockchain
  library [IOV Core](https://github.com/iov-one/iov-core). Developed a
  [C++ re-implementation of the Lisk blockchain](https://github.com/webmaster128/snapshot-validator)
  to verify state dumps; Implemented Lisk key and address derivation in
  Rust/OpenCL for
  [a GPU powered vanity address generator](https://github.com/webmaster128/lisk-vanity);
  Found and responsibly disclosed a
  [critical transaction malleability bug](https://medium.com/@simonwarta/burntx-how-to-burn-tokens-in-lisk-1-1-1-b0830d7eed9d)
  in Lisk and its forks. Writes Rust
  [CosmWasm](https://blog.cosmos.network/announcing-the-launch-of-cosmwasm-cc426ab88e12)
  smart contracts in Rust for fun. Ran a few Substrate testnets
  [in the early days](https://github.com/paritytech/substrate/issues?utf8=%E2%9C%93&q=author%3Awebmaster128).
- **Ralf S**: Comes from a computer science background and has been working as a
  sole proprietorship doing development for the past 15 years. He has had
  professional soccer teams as clients through their use of his
  score/registration software, such as AZ, Heerenveen and Sparta. He was also
  responsible for interconnectivity between the APIs of online job boards like
  Monsterboard and Stepstone. For the last four years Ralf has been heavily
  involved in the decentralized aspect of blockchain and working on the
  implementation of blockchain to the hosting industry. He connected the
  original Shift blockchain to ZeroNet and later to IPFS. He maintained Shift as
  a fork of the Lisk codebase and added the application specific storage
  functionality.
- **Heisenberg**: Almost finished with Bachelor Degree in Chemistry and Chemical
  Engineering; Experienced in understanding/comprehending complex, technical
  subject matter; Experienced in pre-designing technical systems.

## Team Code Repos

- https://github.com/shiftproject

## Development Roadmap

This project consists of two main components: the blockchain module and a web
application that submits transactions on behalf of the user. A rudimentary
standalone user interface that demonstrates the usage of those two components
will be provided as an example.

All software of this project is going to be released under Apache 2.0.
Documentation is going to be released under CC-BY-4.0.

### Milestone 1

- Product: The Shift specific Substrate blockchain module that implements a
  token claim transaction with a hardcoded verification algorithm that can be
  initialized with a list of tokens and holders. Command line tools to perform
  claims.
- Documentation: A tutorial and docker images will be provided that allow
  testing token claims using real world data from Shift Testnet.
- Estimated time: 1 month
- Required funding: \$10,000 (50 % in EUR, 50 % in DOT)

### Milestone 2

- Product: A Shift specific implementation of a web application that takes proof
  of ownership messages via a REST API, checks their validity and sends them
  wrapped in claim transactions to an external blockchain node. A Shift specific
  standalone user interface that demonstrates the usage of the web application.
- Documentation: A tutorial and docker images that include the blockchain node,
  the web service and a local UI for browsers.
- Estimated time: 1 month
- Required funding: \$10,000 (50 % in EUR, 50 % in DOT)

### Milestone 3

- Product: A generalization of the products from milestone 1 and 2 in a way that
  the user can plugin their specific verification algorithm. Implementation of a
  migration ending transaction with plugable logic (e.g. burn or transfer to
  charity).
- Documentation: A tutorial and docker images. To demonstrate how this
  generalization can be used, a Substrate based demo chain is created that
  airdrops demo tokens over ATOM holders (the staking token of Cosmos Hub; using
  secp256k1 keypairs, BIP44 derivation and bech32 encoded addresses to show the
  flexibility).
- Estimated time: 1 month
- Required funding: \$10,000 (50 % in EUR, 50 % in DOT)

## Additional Information

### Work done so far

There is a work in progress
[technical project description](https://github.com/shiftproject/migrate-to-substrate/blob/master/README.md)
that explains the motivation as well as the feasibility of the implementation.

### Out of scope

- Support for funds that are stored in more complex structures like multisig
  accounts or smart contracts
- Support for hardware wallets
- Partial claims of the available tokens
- Production quality user interfaces
- Pre-genesis migration tooling

### Similar projects

#### Polkadot Claims

The right to receive DOTs or KSMs (the Kusama testing DOTs) is granted by
participating in the Polkadot ICO that was done on Ethereum.

For pre-genesis DOT claims, there is an
[Ethereum smart contract](https://github.com/w3f/polkadot-claims) you interact
with to publish your Polkadot address with a proof of ownership. This works well
because the source system (Ethereum) is a smart contracting platform. In
contrast to Polkadot Claims, this grant application does not require the source
system to perform custom operations for the claim. It could even be a chain that
stopped at the point of the migration.

For post-genesis claims, there is the
[Claims runtime module](https://github.com/paritytech/polkadot/blob/v0.7.10/runtime/src/claims.rs#L17),
which is very similar to what this grant application wants to achieve. The main
difference is that the source system is fixed to Ethereum and cannot easily be
adjusted. We propose a migration tool whereby the account balances in the target
system can be imported from all types of data sets (typically blockchain state
dumps) and the verification algorithm is injected.

Polkadot's Claims runtime module relies on unsigned transactions that don't pay
fees, which is a simple solution for the chicken-egg problem. However, it might
create a potential for spam, which needs to be carefully analyzed.

In conclusion, the Ethereum smart contract and the Claims runtime module are
specific tools, while Migrate to Substrate is highly customizable.
