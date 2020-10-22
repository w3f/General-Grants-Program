
# General Grant Proposal

* **Project:** RareLink Protocol

## 1. Project Overview :page_facing_up: 

### 1.1 Project Description

Existing non-fungible tokens (NFTs) are "static" (e.g., do not interact with data and events outside of the blockchain network) and created by ERC721 standard in Ethereum to represent tokenized ownership of unique assets. Therefore, they are limited to the Ethereum network and isolated from the real world. On the contrary, "dynamic" NFTs can receive data and events from the real world through Oracle service and response to them accordingly, which enables tons of business use cases and becomes the next revolution in the blockchain domain.

RareLink Protocol is a new initiative to create "dynamic" NFTs and provide a two-way token bridge between Ethereum and Polkadot ecosystems, which facilitates the minting, transfer and exchange of dynamic NFTs:

  * creates a minting platform to create dynamic NFTs in both Ethereum and Polkadot network:
     * develop smart contracts in Ethereum network and integrate with Chainlink to create dynamic NFTs in Ethereum network;
     * build NFT pallet using Substrate development and integrate with Chainlink pallet to create dynamic NFTs in Polkadot network;
  * a new token bridge will be created to enables two-way transfer of dynamic NFTs between Ethereum and Polkadot:
     * existing token bridge projects cannot transfer *dynamic events* across the network to update transferred dyanmic NFTs;
     * new token bridge will focus on the transfer of dynamic NFTs and aim to preseve their dynamic behavior across networks.  
     
The team behind RareLink Protocol are early adoptors and developers of blockchain technology including Ethereum and Polkadot. We are proficient in mechanism design and blockchain development. In particular, our team believe NFTs will revolutionzie many industries (e.g., retail, real estate, advertising, etc.) in the near future. Moreover, "dynamic" NFT enables unique tokens in blockchain network to interact with data in the real world, which will make more business use cases possible and more efficient. Our team believe in this vision so we look forward to working on RareLink Protocol and make it happen. 

### 1.2 Ecosystem Fit 

There are some existing token bridge projects (e.g., POA token bridge, Parity token bridge, and ChainSafe/Centrifuge chainbridge) are implemented to transfer "static" tokens such as ERC20 or ERC721 tokens. However, they are not able to relay dynamic events for dynamic NFTs, therefore, the dynamic NFTs will lose dynamic behavior after cross-chain transfer. In fact, they become "static" NFTs after cross-chain transfer. Therefore, existing bridges are not suitable and a new token bridge is required. 

RareLink Protocol is built to preserve the dynamic behavior of dynamic NFTs across different networks. It aims to close the gap and create a new two-way bridge for dynamic NFT to enable more business use cases in both ecosystems. 


## 2. Team :busts_in_silhouette:

### 2.1 Team members

* Han: full-time developer works on RareLink Protocol.

Our team has a few part-time developers and their information can be provided in private. We can transfer one or more part-time developer into full-time if grant is received.

### 2.2 Team Website	
* http://rarelink.network/

### 2.3 Legal Structure 
* details will be shared privately via the Google Form.

### 2.4 Team's experience

Our team had great development experience in blockchain domain.

1. Full blockchain project delivered from whitepaper to network launch: Solidity, Javascript, REST API;
2. Token bridge developed between Ethereum, POA network and Binance chain. 
3. Integration with Chainlink and Uniswap to create a decentralized exchange.

### 2.5 Team Code Repos
* rarelink-runtime-node: https://github.com/RareLink/rarelink-runtime-node
* rarelink-docs: https://github.com/RareLink/rarelink-docs
* token bridge poc
    * Oracle module: https://github.com/RareLink/tokenbridge
    * Bridge contracts: https://github.com/RareLink/tokenbridge-contracts
    * evm pallet: https://github.com/RareLink/frontier

### 2.6 Team LinkedIn Profiles
* provide in private through Google Form.

## 3 Development Roadmap :nut_and_bolt: 

### 3.1 Overview
* **Total Estimated Duration:** 5 months
* **Full-time equivalent (FTE):**  1.5 FTE
* **Total Costs:** 2500 DOT (We accept up to 100% of payment in DOTs that are equivalent to $10000)

### 3.2 Milestone 1 — Create dynamic NFT module in Ethereum and Polkadot
* **Estimated Duration:** 1 month
* **FTE:**  1
* **Costs:** 500 DOTs (equivalent to $2000)

* **Task**:
   * *minting in Ethereum*: 
     * build smart contract to mint ERC721 tokens and integrate with Chainlink to enable dynamic behavior; 
     * users should be able to configure settings and create their own dynamic NFT in Ethereum. 
   * *minting in Substrate*: 
     * build the runtime module using existing NFT pallet and Chainlink pallet on top of Substrate; 
     * allows users to create dynamic NFT on Substrate.
* **Test**
   * deploy the solidity contract to Ethereum public testnet and write test to demonstrate the minting of dynamic NFT.
   * deploy the Runtime module to Substrate testnet and verify the minting of dynamic NFT.
* **Documentation**:
   * document in detail about minting dynamic NFT in both Ethereum and Substrate;
   * a demo will be added to show that merchant can issue dynamic NFTs as admission tickets with expiration date.


### 3.3 Milestone 2 — Implement two-way bridge for dynamic NFT between Ethereum and Polkadot
* **Estimated Duration:** 2 month
* **FTE:**  1
* **Costs:** 1000 DOTs (equivalent to $4000)

* **Task**:
   * bridge contract in Ethereum and Substrate
      * this module allows the dynamic NFTs to be locked/burnt in bridge contract for token transfer;
      * it can mint new tokens upon receiving events from validators to complete the token transfer;
      * it can send/receive update events across the bridge for dynamic NFTs that had been transferred across network;
   * off-chain validator module:
      * the validators are responsible to relay the transfer event (including both token and update event transfer) across the blockchain networks.
* **Test**:
   * deploy token bridge to testnet and run system test:
      * mint, list and burn dynamic NFT in both networks;
      * test the bidirectional transfer of dynamic NFT across the blockchain networks;
      * verify dynamic behavior remains intact after the cross-chain transfer.
   * run load testing: 
      * transfer a large number of dynamic NFTs or update events in the same time to test the stability and capacity limit. 
      * Measure performance of bridge over the time.
* **Documentation**:
  * create the tutorial to walk through the process of transferring dynamic NFTs in both directions;
  * a step-by-step demo will be added to show the complete transfer process.


### 3.4 Milestone 3 — Build frontend for users and SDK for third-party integration 
* **Estimated Duration:** 2 month
* **FTE:**  1
* **Costs:** 1000 DOTs (equivalent to $4000)

* **Task**:
  * Web UI: user should be able to mint, list and transfer their dynamic NFT through the website on specified network.
  * SDK: in order to facilitate the third-party integration, SDK will be built to allow developers to easily invoke APIs to mint, list and transfer dynamic NFTs in their own applications.
* **Test**:
  * run end-to-end test on Web to demonstrate the minting, listing and transfer of dynamic NFTs. 
  * build a test project to integrate SDK and verify its functionality.
* **Documentation**: 
  * add “get-started” tutorial to show end-to-end process of minting and transferring dynamic NFT with Web UI across network. 
  * create document of all externally callable APIs. 
  * create a sample project to demonstrate the way to integrate SDK.

### 3.5 Community engagement

RareLink Protocol has great community support in China and Germany. Our community manager will host technical meetups in different cities to engage more community members. Moreover, many media channels will report RareLink Protocol to their audience. 

## 4. Future Plans

Our long term plan is to onboard more developers to build applications on top of RareLink Protocol, which allows more use cases to be available to users.

## 5. Additional Information :heavy_plus_sign: 

* **What work has been done so far?**


* **Are there are any teams who have already contributed (financially) to the project?**
No

* **Have you applied for other grants so far?**
No

* **Are there any other projects similar to yours?**
To the best of our knowledge, there is no project about dynamic NFT that is similar to our project. Please let us know if there are any.
