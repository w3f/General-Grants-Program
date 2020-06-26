# PostgreSQL Indexer and Consensus Ensurer

## Project Description

### A brief description of the project.

Indexer analyses metadata and produces database schema from it, then it scans blocks, extracts data from transactions and saves it to database tables.

CE ensures that the node a dApp communicates to entered consensus with the rest of the network.

### An indication of why this project is good for the ecosystem.

Indexer will enable creating applications with high performance requirements.

CE will add missing layer of security that is assumed to be present in any blockchain network.

### An indication of how you will integrate this project into Substrate / Polkadot.

Indexer interacts with Substrate/Polkadot via RPC interface, and CE acts as a transparent layer for a client API (so that dApps will not need to change), but the set of nodes to interact with will be managed by CE instead of application maintainers.

### An indication of why your team is interested in creating this project.

Currently available solution from Polkascan serves its needs well. We would like to expand capabilities of indexers and create a flexible indexer that is less dependent on concrete runtime configuration and opens capabilities to many high performance dApps including ones that require their own runtime modules and new transaction types.

CE is a very needed (and missing) part for any blockchain. Operating with preset hardcoded node is an obvious vulnerability for a dApp because this single node may be attacked. We are interested in improving network security so, this problem is of our interest as well. 

## Team members
* Alexander Mitrovich
* Greg Zaytsev
* Maksim Styrgin

## Team Website	
* http://usetech.com/blockchain.html

## Legal Structure 
These details will be shared privately via our Google Form.

## Team's experience
Our team members each have more then 15 years of IT experience in managing projects and writing software for product companies and large enterprises alike. We created the Blockchain practice in 2016 and have done dozens of projects for clients across the globe on variety of blochchains, mostly on Ethereum.

## Team Code Repos
* https://github.com/usetech-llc/

## Team LinkedIn Profiles
* https://www.linkedin.com/in/alexandermitrovich/
* https://www.linkedin.com/comm/in/gregory-zaitsev-95ba633

## Development Roadmap
Project roadmap and financial plan will be shared privately via Google Form.
Our areas of interest in Polkadot and Substrate are around:

* Decentralized Non-Fungible Token Exchange
* Enterprise applications
* Bridges

## Additional Information
C++ and C# APIs are delivered. Source code and documentation are available at these public repositories: 
* https://github.com/usetech-llc/polkadot_api_cpp
* https://github.com/usetech-llc/polkadot_api_dotnet
* sr25519 porting to C is implemented, available here:
* https://github.com/usetech-llc/sr25519
* We have already completed most of the development for the Indexer, to insure we undestand the limits of the possible implementation
