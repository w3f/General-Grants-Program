# Stellar Polkadot Bridge

## Project Description
A Stellar Bridge is a trustless cross blockchain framework. The bridge would create assets on Polkadot blockchain that are mapped by equivalent assets on the Stellar Blockchain. This would allow stellar token holders to 
* use their tokens to trade or 
* interact with the applications on the Polkdot ecosystem.

The bridge would ensure decentralized, trustless, transparent and atomic cross blockchain issue and redeems.

The system would comprise of 4 custom modules that would run between the Stellar and Polkdot Blockchain. 
1. Stellar Relay
2. Substrate Parachain
3. Stellar Treasury
4. User Wallet

### Stellar Relay

A Substrate module for PolkaXLM that imports and stores Stellar block headers and exposes end points for Substrate smart contracts to verify transactions.

The main functionality it provides is:
* Verification of a Stellar transaction
* Relay the Stellar transaction to any Polkadot contract
* Storage of Stellar block headers
* Inspection of the latest Stellar block header stored in the contract

### Substrate Parachain

A parachain that maintains all the transactional data and runs the consensus for all Issue and Redeem requests. The nodes get compensated for block generation.

### Stellar Treasury

A Stellar Wallet that acts as treasury for Issue and Redeem requests.

### User Wallet

A Stellar and Polkadot user wallet that maintains the user balance of XLM and Polka XLM.
The Interface triggers Issue and Redeem requests and submits transactions to both blockchains.

The Token issue and redeem flow will be as follows:

## Token Issue

![Token Issue](https://github.com/kimeoapp/Web3-collaboration/blob/master/grants/Issue.png "Token Issue")

1. The user initiates a Stellar transfer to the Treasury from their Stellar wallet.
2. The amount is locked into the Treasury.
3. The Application waits for the transaction confirmation.
4. The Application submits the proof of transaction to the substrate parachain.
5. The Parachain nodes verify the proof via the Stellar Relay and confirms the transaction.
6. The Substrate Parachain module initiates a Token mint on Polkadot.
7. The issued token gets transferred to the Polkadot wallet of the user.
8. The Substrate parachain verifies the issue and adds the transaction to the block.

## Token Redeem

![Token Redeem](https://github.com/kimeoapp/Web3-collaboration/blob/master/grants/Redeem.png "Token Redeem")

1. The user initiates a Polka Stellar burn.
2. The Application waits for the transaction confirmation.
3. The Application submits the proof of transaction to the substrate parachain.
4. The Substrate Parachain verifies the burn.
5. The Substrate Parachain module initiates a Token release on Stellar.
6. The amount is released from the Treasury.
7. The released token gets transferred to the Stellar wallet of the user.
8. The Substrate Parachain verifies the release via the bridge and adds the transaction to the block.

We believe this could be useful to the community as anyone who wants to work with Stellar and Polkadot could use it. 
We are using Stellar in Kimeo (our android app) and are looking to work with Substrate for creating a data layer.

## Team members
* Ajaypal Saggu
* Ankur Grover
* Kamaljeet Singh
* Amardeep Kaur

## Team Website	
* https://kimeoapp.com

## Legal Structure 
Shared in Google Doc.

## Team's experience
We have worked with Major Technology Companies in India and built multiple projects. We have worked with Wipro, Aricent, HCL, DRDO and with Startups in multiple countries. We have founded 4 startups in 4 continents and raised money, got paying customers in those. We have run software development business with clients in US and Europe for last 6 years.

## Team Code Repos
* https://github.com/kimeoapp
* https://github.com/cozmbatman
* https://github.com/ankurgrover

## Team LinkedIn Profiles
* https://www.linkedin.com/ajaypalnitj
* https://www.linkedin.com/groverankur

## Development Roadmap
### Milestone 1: 5 weeks

* Deliverables
  * Stellar relay Substrate module - A Substrate module that acts as an interface with the Stellar blockchain for transaction verification.

* Documentation
  * Functional Specifications
  * Setup Instructions
  * Testing Steps

* Test scripts for deployment and end point testing
  * Successful deployment of Substrate Module
  * Test a success case for a valid transaction ID on Stellar Blockchain from a Polkadot contract.
  * Test a failure case for an invalid transaction ID on Stellar Blockchain from a Polkadot contract

### Milestone 2: 5 weeks
* Deliverables
  * Substrate Parachain - A parachain that maintains all the transactional data and runs the consensus for all Issue and Redeem requests

* Documentation
  * Functional Specifications
  * Setup Instructions
  * Testing Steps

* Test scripts
  * Test successful deployment of a parachain node
  * Verify a Valid transaction by Transaction ID via the Stellar Relay
  * Verify a Valid transaction by Transaction ID via the Stellar Relay
  * Generate a Mint request on Polkadot Contract
  * Verify a token transfer to a Polkadot Wallet
  * Verify a token brun from a Polkadot Wallet
  * Verify a block creation with the custom block structure

### Milestone 3: 6 weeks

* Deliverables
  * Stellar Treasury Contracts - A Stellar Wallet that acts as treasury for Issue and Redeem requests.
  * Android Wallet - A Stellar and Polkadot user wallet that handles Issue and Redeem requests and maintains the user balance of XLM and Polka XLM.

* Documentation
  * Functional Specifications
  * Complete system Setup Instructions
  * Testing Steps

* Test scripts
  * Android wallet installation
  * Test user wallet creation on the Stellar blockchain
  * Test user wallet creation on the Polkadot blockchain
  * Test end to end flow for Token Issue
  * Test end to end flow for Token Redeem

We plan to keep maintaining and updating the repo for next 3 years at least as we are going to use this in our app as well. 

## Additional Information

* What work has been done so far?

We have created the Stellar setup. We have conducted the feasibility study and assessed the possible features of the system. 

* Are there are any teams who have already contributed (financially) to the project?

No

* Have you applied for other grants so far?

No

* Are there any other projects similar to yours? 

There are other bridges but Stellar has a different architecture and consensus which makes it much different than other bridgers like Ethereum and Bitcoin.

* How is your project different?

It is the first Stellar to Polkadot Blockchain bridge.
