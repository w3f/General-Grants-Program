# Polkadot Overview

## Project Description
We intend to create a validators explorer for Polkadot Network. The main features list:

1. Ability to see the list of active validators, their info (description, website, twitter, commission, etc.) and their statistic (status, uptime, stability info,  etc.)
2. Nominators will be able to see their stake distribution across the validators
3. General network information (number of validators, number of validator candidates, era, latest block, etc.)

We are interested to build a project like this because we are currently running the validation nodes in Tendermint based networks (Cosmos, IRIS, Terra, and Minter) and see the needs from delegators to have the summarized data about validators in one place.

Our main goal is to make the Polkadot Overview app and also to run our validation node in Polkadot.

## Team members
* Tim Kabanov
* Ilya Stepanov
* Dmitriy Petrov

## Team Website	
[https://genesislab.net](https://genesislab.net)

[https://twitter.com/GenesisLab_net](https://twitter.com/GenesisLab_net)

## Team's experience
We are a team of 3 developers focused on blockchain related web services development. We are also running validation nodes in Proof of Stake networks like Cosmos, IRIS, Terra, Minter, and Polkadot (PoC-4 testnet).

For our web applications we are using Laravel (PHP) + VueJS. For our cross-platform desktop applications we are using Electron.

So far we have running validator explorers for Cosmos ([Cosmos Overview](https://cosmos-overview.genesislab.net/)), Minter ([Minter Overview](https://overview.minter.store/)) and other Tendermint based networks. Also, we have the open source [Autodelegation tool](https://github.com/genesis-lab-team/minter-autodelegator) for Minter to give the ability for users to automatically re-delegate their rewards.

## Team Code Repos
* https://github.com/genesis-lab-team
* https://github.com/i7495
* https://github.com/tim-kabanov
* https://github.com/PetrovDw

## Team LinkedIn Profiles
* https://www.linkedin.com/in/tim-kabanov
* https://www.linkedin.com/in/ilya-stepanov-79058038/
* https://www.linkedin.com/in/dmitriy-petrov-b79671187

## Development Roadmap
#### Milestone 1 - Research and backend development - 1 month - 1/3 of DOTs requested
* Setup the Polkadot full node
* Development of the blockchain parsing system to collect all the required information for the application and setup of the database (Mongo DB) to store the blockchain data in it
* Analyze and prepare the data that will be used in frontend of the Polkadot Overview application
* Backend code development to retrieve the data from DB using the Laravel framework

*Milestone 1 result will be delivered as a docker container with MongoDB and backend code in it. You will be able to connect to the MongoDB and check that application collect the data from the blockchain.*

#### Milestone 2 - Frontend development - 1 month - 1/3 of DOTs requested
* Frontend development with the UI to show the collected data to the end users with VueJS

*Milestone 2 result will be delivered as a docker container that will provide the full functional application with the backend and frontend. You will be able to see the running application on your local machine.*

#### Milestone 3 - Feedback collection, application testing and documentation - 1/3 of DOTs requested
* Preparation of the setup instructions and documentation / tutorials that describes application features
* Release Polkadot Overview on [https://polkadot-overview.genesislab.net](https://polkadot-overview.genesislab.net)
* Collect users feedback and feature requests
* Code refactoring, new features implementation based on users feedback, bug fixing
* Upload the application's code to [our GitHub](https://github.com/genesis-lab-team)

*Milestone 3 result will be the publicly available application on [https://polkadot-overview.genesislab.net](https://polkadot-overview.genesislab.net) with the open source code and documentation available for everyone.*

Our long-term plans and intentions after the grant has been awarded is to run the validation node in Polkadot main net and to continue the Polkadot Overview application development based on the features requests.

## Additional Information

**What work has been done so far**

Setup the Polkadot full node. Research for the possible ways to collect the blockchain data.

**Have you applied for other grants so far?**

No
