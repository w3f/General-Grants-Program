# General Grant Proposal

* **Project:** Seor Network

## Project Overview :page_facing_up: 

### Overview

With the rapid development of public chain technology and ecology, more and more developers, technical communities and companies have begun to pay attention to entering the blockchain field, and try to gain their business through blockchain technology.
However, due to the relatively high technical threshold in the blockchain field, it is difficult for these groups to quickly and truly use blockchain technology to benefit their businesses.

In order to lower the technical threshold and allow more people to participate in the blockchain field, we proposed a low-code multi-chain smart contract development platform.
It is a platform that supports one-click parameterized deployment of standard smart contracts to different target public chains in a code-free manner.

### Project Details 

####Architecture

The platform includes standard contract sets, on-chain deployers, multi-chain DApp, multi-chain SDK, platform open protocol, etc. The outline of the system architecture is shown below:  

![](https://seor.io/static/arch/overview.jpeg)  
  
  

* **Standard contract set:**  
A set of pre-defined parameterized standard contracts on the platform. It is implemented in different techniques such as Solidity, ink!, Python to support different public chain technology stacks.  

* **Smart contract deployer:**  
A set of smart contracts that do not belong to different public chains, but the centralized contracts of standard contracts will be deployed on different target chains through the deployer.  

* **Multi-chain DApp:**  
The platform carries all interactions and supports multiple public chains. Users can configure parameters, one-click deployment, and contract interaction through DApp.  

* **Multi-chain SDK:**  
A front-end library that supports the platform's interaction with different public chains, bridges the technical differences of different public chains, provides a unified interaction interface, and allows DApps to switch between different public chains for interaction at any time without recoding.  

* **Open platform:**  
Through standard protocols, other developers are allowed to access the platform, providing more users with multi-chain codeless access capabilities.  

####Advantages 

* Blockchain and smart contract technology can be used without contract coding, which reduces the threshold for using blockchain technology.  

* Hold a variety of blockchain technology architectures, without worrying about the underlying implementation, so that users of blockchain technology can focus on the business level.  

* Unify the blockchain access interface, smooth out the technical differences of heterogeneous block links, and implement a set of codes to access public chain systems with different technical architectures.  

####Overall plan

We expect to implement a codeless smart contract platform that can support multiple chains through four phases.  
* Implement some popular standard parameterized multi-chain contracts, such as ERC20, ERC721, etc. At the same time complete the basic contract deployer, multi-chain support SDK and a multi-chain DApp that allows users to operate.  

* Add some standard parameterized contracts for complex businesses to the contract set, such as DEX business and liquid mining business. At the same time upgrade the supporting SDK and DApp.  

* Carry out business integration within the contract collection to enable some composite businesses to form a more complete business flow, such as one-click completion: ERC20 Token issuance + Token sales + DEX listing + liquidity mining mine. And upgrade the contract deployer, multi-chain DApp and other infrastructure.  

* Support more parallel chains and public chains that support smart contracts, upgrade SDK and DApp, and propose a complete standard access protocol to implement an open platform.

Implementation content of this grant application:
We will use this grant to advance the development of the first and second phases. For details, please refer to the milestone section.

### Ecosystem Fit 
No

## Team :busts_in_silhouette:

### Team members
* Winnie Wen - team leader
* Yingxuan Li - full-stack engineer
* Huaiyu Wang - full-stack engineer

### Team Website	
* https://www.seor.io

### Legal Structure 
* Name: SEALSC FOUNDATION LIMITED
* Address: 2 VENTURE DRIVE, #11-31, VISION EXCHANGE, SINGAPORE 608526
* UEN: 201931689N

### Team's experience
Our team is made up of leaders, core development engineers, and community developers of leading blockchain enterprise and projects Onchain, Ontology, TRON, and Bitkeep. We have rich technical accumulation and in-depth understanding in the blockchain field. We are working on blockchain's standardize and protocolize, and will provide a complete infrastructure solution to enable blockchains to powered various fields.
### Team Code Repos
https://github.com/SealSC

## Development Roadmap :nut_and_bolt: 

### Overview
* **Total Estimated Duration:** 95 days
* **Full-time equivalent (FTE):**  3
* **Total Costs:** $12500

### Milestone 1 — Standard contract parameterization 
* **Estimated Duration:** 5 days
* **FTE:**  1
* **Costs:** $500

Using Solidity language to complete the contract parameterization of the two standards of ERC20 and ERC721, and support the configuration of parameters such as the number of issuances, types, additional issuance and destruction support.

### Milestone 2 — Implement a multi-chain contract deployment platform  
* **Estimated Duration:** 5 days
* **FTE:**  1.5
* **Costs:** $500

A codeless contract deployment platform that supports multiple chains, supports the codeless deployment of ERC20 and ERC721 standard contracts that have been implemented in the first phase and the realization of front-end interaction.

### Milestone 3 — Parameterization and codeless deployment of the Uniswap protocol  
* **Estimated Duration:** 10 days
* **FTE:**  2
* **Costs:** $1500

Use the Solidity language to complete the parameterized transformation of the Uniswap agreement contract implementation, and add the code-free deployment of the contract and the implementation of the front-end interaction on the front end.

### Milestone 4 — Parameterization and codeless deployment of ERC20 Token liquidity mining contract  
* **Estimated Duration:** 10 days
* **FTE:**  2
* **Costs:** $1500

### Milestone 5 — Use ink! to develop standard contract parameterization    
* **Estimated Duration:** 10 days
* **FTE:**  2
* **Costs:** $1500

Use ink! to complete the contract parameterization of ERC20 and ERC721 standards, and support the configuration of parameters such as the number of issuance, types, additional issuance and destruction support.

### Milestone 6 — Implement codeless deployment of ink! contracts
* **Estimated Duration:** 10 days
* **FTE:**  2
* **Costs:** $1500

Upgrade platform to support ink! contract deployment without code.

### Milestone 7 — Use ink! to implement parameterized Uniswap protocol
* **Estimated Duration:** 20 days
* **FTE:**  3
* **Costs:** $2500

Implement the parameterized Uniswap protocol in phase-3 through ink!.

### Milestone 8 — ink! version Uniswap protocol codeless deployment
* **Estimated Duration:** 5 days
* **FTE:**  1
* **Costs:** $500

Implement the parameterized Uniswap protocol in phase-3 through ink!.

### Milestone 8 — Ink! implemented parameterized ERC20 Token liquidity mining protocol
* **Estimated Duration:** 20 days
* **FTE:**  3
* **Costs:** $2500

Use ink! to implement the liquidity mining protocol of ERC20 Token in phase-4, and open the code-free deployment and corresponding interactive capabilities of the protocol in the platform.

## Future Plans
* An open platform that allows third-party developers to access and build codeless DApps.
* Implement a complete set of DApp interactive protocols compatible with heterogeneous chains.
