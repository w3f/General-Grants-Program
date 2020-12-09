# General Grant Proposal

* **ever.Finance:** ConsenStorage

## Project Overview :page_facing_up:

ConsenStorage is an incentive consensus protocol for file storage. We have improved a storage-based mining mechanism to provide a large-scale permanent file storage service using Polkadot blockchain technology.

### Overview

Please provide the following:
  * A brief description of the project.
  * An indication of how you will integrate this project into Substrate / Polkadot / Kusama.
  * An indication of why your team is interested in creating this project.

### Project Details 
We expect the teams to already have a solid idea about the project's expected final state.

Therefore, we ask the teams to submit (where relevant):
* Mockups/designs of any UI components
* API specifications of the core functionality
* An overview of the technology stack to be used
* Documentation of core components, protocols, architecture etc. to be deployed
* PoC/MVP or other relevant prior work or research on the topic

#### The Recall Block
In blockchain data structure each block is linked to two prior blocks: the previous block in the ‘chain’, and a block from the previous history of the blockchain. Consequently, the blockchain data structure is not strictly a chain but it is a slightly more complex graph structure.

The recall block is selected based on a hash of the previous block. This results in a deterministic but unpredictable choice of block from the chain’s history.

In order to mine or verify a new block, a node must have that block’s recall block. Demonstrating proof that the miner has access to the recall block is part of block construction. The entire recall block data is included in the material to be hashed for input to the consensus.

The algorithm incentivises storage as miners need access to random blocks from the blockchain’s history in order to mine new blocks and receive mining rewards. And the algorithm also incentives miners to store rare blocks more than it incentivizes them to store well-replicated blocks. This is because when a rare block is chosen, miners can mine new blocks with less competition.

### Ecosystem Fit 
Arweave is a data perpetual blockchain that uses POW for storage and mining. We improved the use of Polkadot's POS algorithm for file storage.

## Team :busts_in_silhouette:

### Team members
* Wei Xiong
* Guanghua Guo

### Team Website	
* https://ever.finance

### Legal Structure 
Shared privately via the Google Form used for your application.

### Team's experience
* Wei Xiong: Founder of everFinance. Former imToken Tokenlon(DEX) core developer. Five years of banking software development experience.
* Guanghua Guo: The development leader of ChainX, the original development leader of Bytom.

### Team Code Repos
* https://github.com/everFinance/consen-storage

### Team LinkedIn Profiles
* https://www.linkedin.com/in/%E7%82%9C-%E7%86%8A-675a9a33/
* https://www.linkedin.com/in/%E5%85%89%E5%8D%8E-%E9%83%AD-964b199a/

## Development Roadmap :nut_and_bolt: 

This section should break out the development roadmap into a number of milestones. Since the milestones will appear in the grant contract, it helps to describe the functionality we should expect, plus how we can check that such functionality exists in the product. Whenever milestones are delivered, we refer to the contract to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions it should be clear how the project is related to Substrate and/or Polkadot. We recommend that the scope of the work can fit within a 3 month period and that teams structure their roadmap as 1 month = 1 milestone. 

For each milestone:
* Please be sure to include a specification of the software. The level of detail must be enough so that we are able to verify that the software meets the specification.
* Please include total amount of funding requested per milestone.
* Please note that we require documentation (e.g. tutorials, API specifications, architecture details) in each milestone. This ensures that the code can be widely used by the community.
* Please provide a test suite, comprising unit and integration tests, along with a guide on how to run these.
* Please commit to providing a dockerfiles for the delivery of your project. 
* Please indicate the milestone duration, as well as number of Full-Time Employees working on each milestone, and include the number of days along with their cost per day.

### Overview
* **Total Estimated Duration:** Duration of the whole project
* **Full-time equivalent (FTE):**  Workload of an employed person ([see](https://en.wikipedia.org/wiki/Full-time_equivalent)) 
* **Total Costs:** Amount of Payment for the whole project. The total amount of funding needs to be below $100k.

### Milestone 1 — Implement storage consensus Modules 
* **Estimated Duration:** 2 month
* **FTE:**  1
* **Costs:** $30,000

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 / MIT / Unlicense |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works. |
| 0c. | Testing Guide | The code will have proper unit-test coverage (e.g. 90%) to ensure functionality and robustness. In the guide we will describe how to run these tests | 
| 1. | Substrate module: Consensus | We will create a Substrate module that will do two things. 1. Link to follow polkadot consensus. 2. Provide a trait for the incentive module, and provide incentive entry for the incentive node and storage account |  
| 2. | Substrate module: Incentive | We will create a Substrate module that will do two things. 1. Token issuance and management (how to manage if dot is used, how to issue if additional token is used). 2. Realize the incentive trait of consensus module.|   
| 3. | Substrate chain | Modules Consensus & Incentive of our parachain will interact in such a way spown new block by a hybrid consensus (follow polkadot consensus and storage consensus) |  
| 5. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Milestone 2 Example — Additional features
...

### Community engagement

We have published some articles on medium: https://medium.com/everfinance. 

## Future Plans
* Implements storage transaction modules
* Develop applications based on the storage computing paradigm

## Additional Information :heavy_plus_sign: 

* What work has been done so far?
We will finish the consensus algorithm in the 2021Q1 and further advance the development of the storage chain.

* Are there are any teams who have already contributed (financially) to the project?
No.

* Have you applied for other grants so far?
No.
