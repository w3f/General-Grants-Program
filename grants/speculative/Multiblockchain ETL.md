# Multiblockchain ETL
## Project Description
Taken to the extreme, we envision interoperability-first blockchain data warehouse across all the blockchains we validate, complete with event subscriptions and useful aggregate functions. With it people have easier time building wallets, dashboards, explorers and apps that interact with multiple blockchains connected through interchain communication protocols. In the interconnected blockchain network applications will need to be able to follow events across chains. Imagine, for example, moving a chain A asset through bridge B to parachain X to open a CDP, then using received stablecoin to long a synthetic asset from parachain D on a margin trade chain E. The closest analog to what we want to eventually make is dfuse, but for the forest of blockchains.

Main points:
- many blockchains lack good public and/or ready-made private APIs to build apps on
- with interblockchain communication proliferation, a walled garden-like APIs won't cut it: good apps will require a single request to analyze multiple blockchains (simplest example is a wallet querying multiple balances but it's going to be much more complex than that eventually)
- multi-network validators are uniquely positioned to implement such an API: on one hand, they already bear a good part of blockchain API costs: node management. On the other, they are already trusted to validate blockchain network and have their skin in the game, making them more trustworthy as a source of blockchain data

That’s a long way into the future: for a first step, we can make an adaptable ETL solution for both Polkadot and Filecoin + GraphQL API for the collected data. It is a comparatively small deliverable that still makes us closer to our grand vision and can be continued with data enrichment pipelines and ETL and APIs for notable applications and additional blockchains.

NB: This is a proposal for combined grant initiative for both Web3 Foundation and Filecoin. [Here](https://github.com/filecoin-project/devgrants/pull/122/)'s corresponding proposal for Filecoin.

## Team members
P2P Validator - Secure Non-Custodial Staking service. We’re making an effort to help the networks we’re validating. We’ve got a decent developers team, including blockchain development, and a sizeable stake in the network itself. Our interests are very aligned with Polkadot’s success. Our team for that particular proposal:

Team leader:
- Vasiliy Shapovalov, 11 years in software development. Mostly infosec-related projects, including compiler engineering, network security, formal verification.
Team members:
- Andrey Zavgorodniy: senior blockchain developer. Ex-SONM, Ex-Lazada.
- Michael Mozhaev: golang developer
- Pavel Klyibik: golang/c++ developer
- Mikhail Semenkin: solidity & full stack NodeJS developer
- Vladimir Matveev: devops engineer

## Team Website	
- https://p2p.org

## Legal Structure 
Provided seprately.

## Team's experience

## Team's experience
Blockchain team received Interchain Foundation funding for Arcade - Tendermint hack with built-in BLS random beacon. A few of the most interesting files to check out:
- https://github.com/corestario/tendermint/blob/develop/docs/arcade/arcade.md
- https://github.com/corestario/dkglib/blob/master/lib/dealer/dkg_dealer.go
- https://github.com/corestario/tendermint/blob/develop/node/bls/bls_node.go

We've developed ETL pipeline and an API for Cosmos data, it's closed source so far but you can see how it works on our website.

The cool thing about our pipeline is that we extract data paid rewards on delegation and redelegation that no single block explorer so far can show (you can see the examples in our article) and we can work with all three upgrades of Cosmos Hub at once.

We've developed [an API for Cosmos staking referral program](https://docs.defiapi.com/cosmos-staking-api/), where you can check out our documentation-fu:

## Team Code Repos
Most interesting public repos are:
- https://github.com/corestario/dkglib
- https://github.com/corestario/tendermint
- https://github.com/corestario/randapp

## Team LinkedIn Profiles
- Vasiliy Shapovalov https://www.linkedin.com/in/vasiliy-shapovalov-91716491/

## Team Github Profiles
- Vasiliy Shapovalov https://github.com/vshvsh
- Andrey Zavgorodniy https://github.com/oopcode
- Michael Mozhaev http://github.com/programmer10110
- Pavel Klyibik https://github.com/PashaKlybik
- Mikhail Semenkin https://github.com/krogla
- Vladimir Matveev https://github.com/ponchik69

## Development Roadmap
Before the development starts we need to take the big decision of what stack to use. Main options are industry standards (Apache Spark/Beam pipelines). 
We provide estimations privately. 

### Milestone 1 — ETL Stack and Architecture Drafts — 2 weeks
- We will explore and compare options to make the extensible and easy to use Extraction toolkit for Substrate-based blockchains. We'll compare industrial standard stacks (e.g. Apache Spark, Apache Beam) and successful related blockchain-specific projects (e.g. EthereumETL, VulcanizeDB, Graph Protocol)
- We will reach out to experts in the field, including Graph Protocol team, to ensure that the architecture allows for reusable code and logic.
- We will deliver a specification for stack and architecture we will use
### Milestone 2 — GraphQL API over built-in Filecoin Lotus node ETL — 2 weeks (in parallel with architecture drafts)
- We will develop GraphQL API endpoint over built-in Lotus node ETL based on Hasura
- We will provide deployment scripts, documentation and tutorials on configuring and running GraphQL endpoint
### Milestone 3 — Extraction and Load framework — 1 month
- We will develop the framework to extract and store raw tx/block data from Polkadot Relay chain and Filecoin, suitable both for blockchains with finality gadgets and reorganizable chains
- We will develop a reference implementation of the said pipeline for Filecoin and Polkadot 
- We will provide documentation and tutorials on running the extraction pipelines and making a custom extraction pipeline
### Milestone 4 — Enrichment, API endpoints, Documentation — 1 month
- We will create enrichment transformations for the blockchain chain data, including specialized structured data warehouses for transfers, staking, governance on Polkadot and actors and messages on Filecoin
- We will create a GraphQL API over raw and enriched data extracted from the chain
- We will provide documentation and tutorials on running the pipelines we made, hosting an API, using the API and developing your own pipelines and APIs for other blockchains.
- We will provide a docker-compose setup for easy deployment of the ETL and API solution
### Milestone 5 — Miner’s Dashboard for Filecoin — 1 month
- We will create a dashboard that tracks filecoin miner’s activity and historical data using the GraphQL API we made and prometheus exporter
- We will provide documentation and tutorials on running the dashboard 

## Future Plans
Our future plans are to build ETL pipelines for the most notable parachains and bridged chains, and develop an API gateway to make possible to make multichain data requests.
## Additional Information
### What work has been done so far?
We made a ETL pipeline for Cosmos-based networks for our internal use and integrated it in the our dashboard. Most of this code is not going to be used for the proposed project - we're unhappy with our current data gathering solution,  and transformations are obviously blockchain-specific.
### Are there are any teams who have already contributed (financially) to the project?
So far we're fully self-funded.
### Have you applied for other grants so far?
Part of the team had delivered Arcade (see above). We are working on NuCypher grant for monitoring and alerting solution right now.

We have made some grant applications to other blockchain foundations and teams that are under review or waiting for more auspicious moment to be discussed.
### Are there any other projects similar to yours? If so, how is your project different? 
There is a plethora of Ethereum-related projects that have some similarity to what we want to do. Some of them are open-source, and the Graph Protocol in particular has a token model attached. The end product we're going for is a mix of Dune (for a lot of ad-hoc application-specific transformations, and eventual business model) and Graph Protocol (for open source code, ad-hoc transformation building and GraphQL API on top).
- EthereumETL
- VulcanizeDB
- Graph Protocol
- dfuse
- Dune Analytics
- Anyblock Analytics
## License
We will use open source license for all the code in the scope. We'll use Apache 2.0.
