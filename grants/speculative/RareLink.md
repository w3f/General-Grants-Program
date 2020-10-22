
# General Grant Proposal

* **Project:** RareLink Protocol

## 1. Project Overview :page_facing_up: 

### 1.1 Overview

Existing non-fungible tokens (NFTs) are "static" (e.g., do not interact with data and events outside of the blockchain network) and created by ERC721 standard in Ethereum to represent tokenized ownership of unique assets. Therefore, they are limited to the Ethereum network and isolated from the real world. On the contrary, "dynamic" NFTs can receive data and events from the real world through Oracle service and response to them accordingly, which enables tons of business use cases and becomes the next revolution in the blockchain domain.

RareLink Protocol is a new initiative to create "dynamic" NFTs and provide a two-way token bridge between Ethereum and Polkadot ecosystems, which facilitates the minting, transfer and exchange of dynamic NFTs:

  * creates a minting platform to create dynamic NFTs in both Ethereum and Polkadot network:
     * develop smart contracts in Ethereum network and integrate with Chainlink to create dynamic NFTs in Ethereum network;
     * build NFT pallet using Substrate development and integrate with Chainlink pallet to create dynamic NFTs in Polkadot network;
  * a new token bridge will be created to enables two-way transfer of dynamic NFTs between Ethereum and Polkadot:
     * existing token bridge projects cannot transfer *dynamic events* across the network to update transferred dyanmic NFTs;
     * new token bridge will focus on the transfer of dynamic NFTs and aim to preseve their dynamic behavior across networks.  
     
The team behind RareLink Protocol are early adoptors and developers of blockchain technology including Ethereum and Polkadot. We are proficient in mechanism design and blockchain development. In particular, our team believe NFTs will revolutionzie many industries (e.g., retail, real estate, advertising, etc.) in the near future. Moreover, "dynamic" NFT enables unique tokens in blockchain network to interact with data in the real world, which will make more business use cases possible and more efficient. Our team believe in this vision so we look forward to working on RareLink Protocol and make it happen. 

### 1.2 Project Details 
We expect the teams to already have a solid idea about the project's expected final state.

Therefore, we ask the teams to submit (where relevant):
* Mockups/designs of any UI components
* API specifications of the core functionality
* An overview of the technology stack to be used
* Documentation of core components, protocols, architecture etc. to be deployed
* PoC/MVP or other relevant prior work or research on the topic

### 1.3 Ecosystem Fit 
Are there any other projects similar to yours? If so, how is your project different?

## 2. Team :busts_in_silhouette:

### 2.1 Team members
* Moke: early adoptor and investor in blockchain domain. He served as advisors in many blockchain projects. He is active community member of polkadot since 2017 and helped many projects get launched in Polkadot ecosystem. Moke had hosted many technical meetups and summits about Polkadot technology this year.

* Fancy: He received his PhD degree from UCLA and had many years industrial experience of software development. He loves to learn new technology and became interested in blockchain technology. Moreover, he joined a blockchain startup as a founding member and helped launch new blockchain network service successfully. He had acquired rich experience of blockchain development in the past few years.

* Han: 


* Heng: He serves as the Chinese community manager in RareLink. Heng had many years experience of financial service and community building. He had joined Ethereum community back in 2015 and actively helped people join the community. Lately, he supports the Polkadot community in China and hosted many technical events.



### 2.2 Team Website	
* http://rarelink.network/

### 2.3 Legal Structure 
* details will be shared privately via the Google Form.

### 2.4 Team's experience

Our team had great development experience in blockchain domain.


### 2.5 Team Code Repos
* rarelink-runtime-node: https://github.com/RareLink/rarelink-runtime-node
* rarelink-docs: https://github.com/RareLink/rarelink-docs
* token bridge poc
    * Oracle module: https://github.com/RareLink/tokenbridge
    * Bridge contracts: https://github.com/RareLink/tokenbridge-contracts
    * evm pallet: https://github.com/RareLink/frontier

### 2.6 Team LinkedIn Profiles
* provide upon request

## 3 Development Roadmap :nut_and_bolt: 

This section should break out the development roadmap into a number of milestones. Since the milestones will appear in the grant contract, it helps to describe the functionality we should expect, plus how we can check that such functionality exists in the product. Whenever milestones are delivered, we refer to the contract to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions it should be clear how the project is related to Substrate and/or Polkadot. We recommend that the scope of the work can fit within a 3 month period and that teams structure their roadmap as 1 month = 1 milestone. 

For each milestone:
* Please be sure to include a specification of the software. The level of detail must be enough so that we are able to verify that the software meets the specification.
* Please include total amount of funding requested per milestone.
* Please note that we require documentation (e.g. tutorials, API specifications, architecture details) in each milestone. This ensures that the code can be widely used by the community.
* Please provide a test suite, comprising unit and integration tests, along with a guide on how to run these.
* Please commit to providing a dockerfiles for the delivery of your project. 
* Please indicate the milestone duration, as well as number of Full-Time Employees working on each milestone, and include the number of days along with their cost per day.

### 3.1 Overview
* **Total Estimated Duration:** Duration of the whole project
* **Full-time equivalent (FTE):**  Workload of an employed person ([see](https://en.wikipedia.org/wiki/Full-time_equivalent)) 
* **Total Costs:** Amount of Payment for the whole project. The total amount of funding needs to be below $100k.

### 3.2 Milestone 1 Example — Implement Substrate Modules 
* **Estimated Duration:** 1 month
* **FTE:**  1
* **Costs:** $5,000

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 / MIT / Unlicense |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works. |
| 0c. | Testing Guide | The code will have proper unit-test coverage (e.g. 90%) to ensure functionality and robustness. In the guide we will describe how to run these tests | 
| 1. | Substrate module: X | We will create a Substrate module that will... (Please list the functionality that will be coded for the first milestone) |  
| 2. | Substrate module: Y | We will create a Substrate module that will... |  
| 3. | Substrate module: Z | We will create a Substrate module that will... |  
| 4. | Substrate chain | Modules X, Y & Z of our custom chain will interact in such a way... (Please describe the deliverable here as detailed as possible) |  
| 5. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### 3.3 Milestone 2 Example — Additional features
...

### 3.4 Community engagement

As part of the Program, we require that you produce an article/tutorial and publish it (for example on [Medium](https://medium.com/)). It should explain your work done as part of the grant. 

Normally, we ask you to submit the write-up upon the completion of your grant, although for larger projects it might make sense to publish multiple articles after the completion of different milestones.

## 4. Future Plans
Please include the team's long-term plans and intentions.

## 5. Additional Information :heavy_plus_sign: 
Any additional information that you think is relevant to this application that hasn't already been included.

Possible additional information to include:
* What work has been done so far?
* Are there are any teams who have already contributed (financially) to the project?
* Have you applied for other grants so far?
