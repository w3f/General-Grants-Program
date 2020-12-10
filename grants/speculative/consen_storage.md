# General Grant Proposal

* **ever.Finance:** ConsenStorage

## Project Overview :page_facing_up:

ConsenStorage is an incentive consensus protocol for file storage. We have improved a storage-based mining mechanism to provide a large-scale permanent file storage service using Polkadot blockchain technology.

### Overview

* Distributed storage to ensure data availability.
* A deterministic and traceable storage that can be used for decentralized applications.
* Use Substrate to add the block generation algorithm of the storage mode to the consensus module.

### Project Details 

In order to build a storage blockchain platform, we used the following key technologies.

* The Recall Block
* Permanent storage price
* Storage and Bandwidth incentive

#### The Recall Block
In blockchain data structure each block is linked to two prior blocks: the previous block in the ‘chain’, and a block from the previous history of the blockchain. Consequently, the blockchain data structure is not strictly a chain but it is a slightly more complex graph structure.

The recall block is selected based on a hash of the previous block. This results in a deterministic but unpredictable choice of block from the chain’s history.

In order to mine or verify a new block, a node must have that block’s recall block. Demonstrating proof that the miner has access to the recall block is part of block construction. The entire recall block data is included in the material to be hashed for input to the consensus.

The algorithm incentivises storage as miners need access to random blocks from the blockchain’s history in order to mine new blocks and receive mining rewards. And the algorithm also incentives miners to store rare blocks more than it incentivizes them to store well-replicated blocks. This is because when a rare block is chosen, miners can mine new blocks with less competition.

#### Permanent storage price

Statistics show that the storage cost is decreasing at a staggering rate every year. The average storage cost decreases by 30.57% per gigabyte every year. As time goes by, the cost will converge to a constant, which is considered as the permanent storage cost. We will price storage based on the converged constant to stabilize storage costs.

#### Storage and Bandwidth incentive

##### Storage

Create a storage fund to ensure the profitability of mining. The storage fund is used to ensure that future transaction fees are not enough to cover the cost of miners and subsidize miners. When a new block is mined, a part of the transaction fee of the new block will be paid to the miner, and another part of the fee will be deposited into the storage fund.

Use permanent storage price as the base of transaction costs.

Polkdadot parachain supports up to 10 nodes, so user payment fee = (10 * permanent storage cost) * instant constant. If there is only one node currently, 1/10 of the fee will be paid to the node at a certain discount, and remaining fee will be deposited into the stroage fund.

In the case of insufficient funds, the instant constant of the fee can also be adjusted to increase the user's payment fee to offset the operating cost of the entire network.

##### Bandwidth

Users requesting data from nodes need to use purchased bandwidth credits, which are digital credits calculated in bytes. The tokens consumed by the user at the time of purchase will be deposited into the fund.

When a user requests data from a node, a message signature is required. This signature is like a check. The node can use the signature to redeem the token paid by the user.

Insufficient user bandwidth points, the node can reject the response data.

If the node data response is not timely or the response is wrong, the user can replace other high-quality nodes for data request.

### Ecosystem Fit 
Arweave is a data perpetual blockchain that uses POW for storage and mining. We improved the use of Polkadot's POS algorithm for file storage, and, increased bandwidth incentives to make the entire economic model more complete.

## Team :busts_in_silhouette:

### Team members
* Wei Xiong
* Guanghua Guo

### Team Website	
* https://ever.finance

### Team Mail

* dev@ever.finance

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

### Implement storage consensus Modules 
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
