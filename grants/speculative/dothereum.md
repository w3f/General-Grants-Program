# Dothereum

![Dothereum](https://i.imgur.com/H2LTIW4.png)

**Dothereum** - the _Ethereum_ for _Polkadot_.

### Project Description
* Polkadot is not a competition to Ethereum, but rather compliments and helps scale the next generation of decentralized applications. **Dothereum** will be the parachain that bridges Ethereum to the Polkadot ecosystem. 
* Our team is a group of core Ethereum and Polkadot developers, contributing to core infrastructure for years now. We are excited to see this project evolve.
* We plan to have a testnet for our parachain that can clone the state of Ethereum block for block.
* Once launched, Dothereum will be the first parachain entirely written in Go. This should encourage lowering the entry barrier for developers attracted by Polkadot.

### Team members
* We plan to allocate at least three engineers to work on Dothereum initially. More details are available on request.

### Team Website
* [WIP] https://dothereum.net

### Legal Structure
* The Dothereum venture is currently in concept and seed stage. No investments have been secured so far. 
* This project is a joint venture between two incorporated companies. More details are available on request.

### Team Code Repository
* https://github.com/dothereum

### The intended language of development
* Golang, Wasm

### Scope and Roadmap
* We will require six months to kick-off this project. This involves but is not limited to:
    * Sorting out a legal framework for running parachain(s) with native tokens, i.e., a Dothereum Foundation
    * Bootstrapping a community around the idea of a next-generation smart-contract platform built on a modern technology stack 
    * Creating a proof-of-concept Dothereum testnet that allows for accessing the Ethereum state on request, block for block 
* Dothereum Project Components:
    1. Create a generic Go-based testnet for Dothereum to allow users running nodes and joining the network
    2. Develop and deploy generalized parachain bridge module for Go to access Ethereum state on request, block for block
    3. Implement a state-rent mechanism that enables developers to import, rent, and access state from the Ethereum blockchain on Dothereum
    4. Enable Wasm smart-contract support with EVM backwards-compatibility

* Outlook beyond the testnet
    1. Deploying generic parachain bridges to enable legacy Ethereum developers to migrate tokens, contracts, and state
    2. Storing the pruned Ethereum state and making it available for the entire Polkadot ecosystem, i.e., to work with Edgeware contracts 
    3. Optionally, working on tooling to enable developers to build generalized smart-contracts that maintain EVM compatibility to eventually provide a two-way state bridge with Ethereum
    4. Advocating in the Polkadot community to accept Dothereum as one of the parachains included in genesis
    5. Considering a fair allocation of the native Dothereum $XTH tokens, i.e., by allocating them to $ETH and $DOT holders, or exploring other options such as lock-drops, work-drops, dex-drops 

* Further roadmap milestones will include:
    * Providing Ethereum developers with a reliable scalability solution and migration paths for moving to Polkadot
    * Implement a _Dothereum_ testnet upon Polkadot genesis that allows for accessing the Ethereum state on request, block for block 
    * Optionally, allow for the generalized parachain bridge to be two-directional, enabling smart contracts to be written in native programming languages which get interpreted to EVM bytecode.
    * See also: https://medium.com/@dothereum/the-dothereum-parachain-7fd056c1107d

* Ideally, we can receive part of the required funding as an initial _seed_ of $USD 100_000.00 (2%) at the beginning of the project.
* We would be willing to consider additional funding in $DOT tokens, up to $USD 500_000.00 (10%), upon successful completion of seed phase and the actual launch of the Polkadot network with a Dothereum parachain. 
* The rest of the required mid- and long-term funding shall be provided via interested VCs and a sustainable developer-token distribution strategy.
* For the Polkadot genesis, a token-distribution model for $XTH has to be mapped out. It should be opt-in and reach a broad range of interested stakeholders (ex-miners, private/corporate investors, traders, developers), e.g., lock-drops, work-drops, dex-drops.
* Alternatively, we are thinking to allow for an even distribution of tokens between $DOT and $ETH holders respectively, with additional tokens allocated for fundraising and the team. More research is necessary, we do believe however, that $DOT and $ETH holders will be required to signal commitment to recieve $XTH with an equal amount to be able to be distibuted between the two.
* All strategical and technical advisory is welcome and appreciated.
* We are open to venture capital financing.

![the smart-contract parachain](https://i.imgur.com/SCOHRkD.jpg)
