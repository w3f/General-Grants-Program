# Ultrain Polkadot Bridge
## Project Description
In this project, we will deploy a Polkadot-Ultrain bridge to connect Polkadot and Ultrain together.
By the bridge, User can
* Interact with the applications on the Polkadot ecosystem.
* Relay Ultrain transaction to compatible Polkadot Parachain
* Swap UGAS between Ultrain and Polkadot.

Ultrain is a public chain base on R-POS, a new consensus mechanism which was defined as a random trusted consensus framework. 
ECC, ED25519 and BLS was used for signature and verification in R-POS. By VRF, it choose one committee member randomly to generate block in every round.
Signature aggregation is record in block header which can be used to verify the block heads. Transaction merkle root recorded in block head which can be used 
to validate whether the specified transaction has been finalized.

This project would give an example how to bridge Polkadot and a POS chain.

This project has 3 custom modules
* Polkadot-Ultrain-Bridge
* Substrate Parachain
* Ultrain Bank module

### Polkadot-Ultrain-Bridge
A substrate module, It works as a light client of Ultrain.
*   It can verify and store Ultrain block head.
*   Accept and verify Ultrain transaction.
*   Create a token PolkaUGAS in Polkadot
*   Relay Ultrain transaction to compatible Polkadot contract

### Substrate Parachain
A Polkadot Parachain maintain the genesis block info and committee members of Ultrain.

### Ultrain Bank module
A smart contract in Ultrain.

* The bank would lock collateral to Polkadot.
* The bank pooling the Polkadot-Ultrain bridge status and release UGAS to user when needed.
* The bank can get back collateral from Polkadot after release UGAS.

### Request PolkaUGAS
![Request PolkaUGAS](https://raw.githubusercontent.com/ultrain-os/Web3-collaboration/master/grants/request_polkaugas.jpg)
*   The Bank need to lock collateral at Polkadot Bridge.
*   The user pays UGAS to Bank
*   The user post a transaction on the bridge that include the proof of lock UGAS transaction .
*   The Bridge parse and verify the UGAS lock transaction
*   After verification, bridge issue PolkaUGAS to specified account.

### Redeem UGAS
![Redeem UGAS](https://raw.githubusercontent.com/ultrain-os/Web3-collaboration/master/grants/redeem_ugas.jpg)

* the user burn PolkaUGAS in Parachain
* Bank in Ultrain pooling the burn information
* Bank in Ultrain release UGAS to specified user
* Bank in Ultrain provide proof to bridge
* Bridge verify release proof
* Unlock collateral to Bank in Ultrain

## Team members
Name of team leader:

Yufeng Shen, Chief Architect

Name of team member:

Yu Su,
Zhongwei Zhang,
Xiaojian Chen,
Huichao Yan

## Team Website	
* https://ultrain.io/team 

## Legal Structure 
ULTRAIN FOUNDATION LTD,
9 TEMASEK BOULEVARD #04-02,
SUNTEC TOWER TWO,
Singapore 038989

## Team's experience
**Yufeng Shen** 
* Chief Architect
* Graduated with MS in Computer Science from Alberta University, Yufeng was a Senior Software Engineer at Google Chrome OS team, then a Senior Technical Expert at Alibaba Cloud OS team. As the Chief Architect, he leads the design and implementation of the core parts of Ultrain.

* Experiences:
    Senior Technical Expert, Alibaba Cloud OS
    Senior Software Engineer, Google*

**Yu Su**
* Technical Expert
* Former Employer: Nokia
* Experience: > 10 years
* Previously worked with Nokia, where he was responsible for platform maintenance and optimization, including cRNC, mcRNC and MGW

**Zhongwei Zhang**
* Technical Expert
* Former Employer: Ericsson; ZTE
* Experience: > 11 years
* Senior Development Engineer at L.M.ERICSSON for 9 years, where he focused on WCDMA/LTE optimization, as well as oversight of Linux platform development. Spent 2 year with ZTE

**Huichao Yan** 
* Technical Expert
* Former Employer: Quanmin.tv
* Experience: >10 years
* Worked as C++ and Lua development engineer with multiple technology companies, including 10jqka and Quanmin.

**Xiaojian Chen**
* Technical Expert
* Former Employer: Alibaba
* Experience: > 8 years
* Former core architect for taobao.com at Alibaba, and was in charge of the system stability during 11.11


## Team Code Repos
https://github.com/ultrain-os

## Team LinkedIn Profiles
* https://www.linkedin.com/in/yufeng-shen-803a2b11/ <Yufeng Shen>
* https://www.linkedin.com/in/yu-su-9067275b/ <Yu Su>
* https://www.linkedin.com/in/zhongwei-zhang-aa9645133/ <Zhongwei Zhang>
* https://www.linkedin.com/in/huichao-yan-16614216b/ <Huichao Yan>
* https://www.linkedin.com/in/xiaojian-chen-a432a7190/ <Xiaojian Chen>
 

## Development Roadmap
### Milestone 1： 6 Weeks

* Develop the substrate module as Ultrain interface, and this module will enable the functions below:
    * Receive, verify and maintain the most recent N block heads of Ultrain chain, and become the light client end of Ultrain.
    * Receive merkle proof，and validate whether a certain transaction has been confirmed at a required block height
    * Issue UGAS in Polka format, which is UGAS' reflection in Polkadot; 
    * Function Test 

### Milestone 2: 4 Weeks

* Build the Parachain for Polkadot, which maintains the genesis block info and committee members of Ultrain.
    * Function Test 

* Documentation:
    * Function specification

### Milestone 3：4 Weeks

* Realize Bank component on Ultrain’s chain, which has the functions below:
    * Receive users' UGAS and lockup 
    * Submit transaction data and merkle proof to Polkadot-Ultrain-Bridge 
    * Release UGAS to user in Ultrain when he burn PolkaUGAS in Polkadot Parachain.
    * Integration test and deliver.

* Documentation
    * Function specification



### Further plan
* In further plan, it can bridge more POS chain, which has compatible transaction format.

We will assign 5 experts to finish the Polkadot-Ultrain-Bridge in 3 month.


## Additional Information

* What work has been done so far?
   * High level design
* Are there are any teams who have already contributed (financially) to the project?
   * None
* Have you applied for other grants so far?
   * No
* Are there any other projects similar to yours? 
   * There are already some Polkadot bridges work, like Paritytech/parity-bridge. 
* How is your project different?
   * Paritytech/parity-bridge bridges between any two ethereum-based networks.
   Polkadot-Ultrain-Bridge is a light weight bridge, bridge Ultrain-based network.
