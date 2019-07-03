# Darwinia Network

## Project Description
We are building a game parachain (Darwinia Network) for Polkadot. Darwinia Network is an open, cross-chain protocol support games for cross-chain interaction in game logic and game assets. Meantime, we are developing Darwinia AppChain ,Darwinia AppChain is a set of blockchain development kits that can meet the needs of application developers for different blockchain customizations. With Darwinia AppChain ,developers can create blockchain game or dapp quickly and smoothly.

We created a multi-chain game world: Evolution Land, www.evolution.land. We will use Darwinia network for cross-chain operation for Evolution Land. EvolutionLand has been deployed and live on Ethereum and Tron, we are working to extend to EOS and PChain network in next iteration.

* The TRON continent won the $20,000 special prize in the TronAccelerator competition and was invited to attend the niTROn Summit conference.
* Partnership with Imtoken and bihu.com.
* Interstellar asset coding standard enables Cryptokitties to integrate into the Evolution Land to create an open game ecosystem (Kitties become pets in EvolutionLand).

By the way, Darwinia network already listed on Polkadot wiki in community section https://wiki.polkadot.network/en/latest/polkadot/build/examples/

## Team members
* Alex Chien

* Denny Wang


## Team Website	
https://www.itering.com

https://darwinia.network/


## Team's experience
Core team of Darwinia Network is from Itering Tech Co., Ltd. 

Itering has a complete and professional team from technology to operation. The technical department has many senior experts engaged in the development and technical research of blockchain field, and has rich experience in consulting and development on blockchain technology such as public chain technology, Ethereum and smart contract.

* Alex Chien

Excellent technical expert in blockchain, full stack engineer, has been involved in the technical work of bitcoin and blockchain since 2011, and has participated in the technology development of several open source projects, especially in graphene technology and EVM smart contract technology. Very rich development experience.

* Denny Wang	

Excellent technical expert in blockchain, core developer of BitShares 1.0, intelligent contract security expert. Now he is mainly engaged in Ethereum's Layer2 network and Polkadot cross-chain related research. He has served as technical leader in several blockchain technology companies.

## Team Code Repos
* https://github.com/darwinia-network
* https://github.com/evolutionlandorg
* https://github.com/itering

## Team LinkedIn Profiles
* https://www.linkedin.com/in/alex-chien-46448216/
* https://www.linkedin.com/in/denny-wang/

## Development Roadmap

### The specifications of the project including:

- Dual token model design and implementation, the native tokens are RING and KTON.

    - RING token for payment and gas fees, can be locked to issue KTON
    - KTON can only be created by locking RING, the amount issued depends on how long the RING will be locked.
    - The draft of the specification is now located in RFC-0007 (English version is TBD)

- The staking allocation in the solo model.
    - Withdraw income support to KTON Token before transferring
    - Support Treasury runtime within the staking
    - Normal staking using locked KTON as voting tickets, and income are paid in RING

- Migrating current contract runtime, and support paying gas fee using RING token
- Cross-chain bridges supporting token cross-chain transferring between Ethereum(ERC-20)/Tron(TRC-20) and Darwinia network, fungible token and non-fungible tokens will be supported.
    - The features will follow the design from Parity Bridge.
    - The NFT cross-chain code protocol will follow the proposal from the Drawinia Network RFC-0005
    - The current RING/KTON tokens on Evolution Land will use this feature to finish the cross-chain transfer.
    - The current game NFTs on Evolution Land will use this feature to transfer between Ethereum/Tron through Darwinia Network.
- Tools and Documents
    - Web wallet providing user interface for users to interact with. M1
    - Blockchain browser: help common user check transaction and data M2
    - Tutorials for users and token holders about staking and nominating.
    - Documents for validators to setup nodes and join the network

Currently we are developing based on Substrate 1.0 rc, to setup the initial POC-1 testnet.  Later we will refactor code to comply with latest Substrate 2.0 design and trait, as Substrate 2.0 has no stable release yet, we'd start from what is there (the POC-1 testnet release at the time of writing).  Changes to Substrate 2.0 might cause refactorings and delay the plan.

### Milestones

- Start: already started, can view the current status of the project and development here:
    - https://github.com/darwinia-network/darwinia
    - https://github.com/darwinia-network/darwinia/milestone/1 (WIP)
- M1 (2 weeks): Darwinia PoC1 Testnet.  Include RING/KTON token runtime and Grigott runtime(Issuing KTON buy locking RING). 
    - Features and functions
        - Research on the tokens economic and staking protocol of Darwinia Network, and finalized the design paper
        - Develop several SRML modules based on Substrate, and run a public testnet.
        - Develop a web wallet based on polkadot-js.
        - Develop a blockchain browser for the testnet to view blocks and transactions.
    - Deliverables
        - Docker container running a Substrate node with a simple native token system runtime, can connect to testnet and syncing blocks.
        - A design paper introducing this project, and the technical structure of it, including token economics and staking.
        - Telemetry demonstrate the nodes status of the testnet
        - A prototype web wallet for users and tester to play with.

- M2 (4 weeks): Darwinia PoC2 Testnet. Including staking runtime.
    - Features and functions
        - A simple blockchain browser.
        - Staking runtime and functions.
        - Web wallet updates to this new functions
        - A simple blockchain browser.
        - Testnet tokens faucet.
    - Deliverables
        - Docker container running a substrate node with staking runtime included, can connect to testnet and syncing blocks.
        - Running node can get free tokens from faucet, and testing validator functions, running as validators. And normal users can support validators by nominating.
        - Users and view the blockchain data and extrinsics using blockchain browser.

- M3 (6 weeks): Darwinia PoC3 Testnet. Release candidate for mainnet launch(2019Q4), with runtimes including cross-chain NFT bridge, fungible token bridge between Ethereum and Tron, and experimental contract module.
    - Features and functions
        - Cross-chain NFT encoding and bridging Ethereum/TRON testnet and the POC-3 Testnet.
        - Cross-chain fungible token bridging, from Ethereum ERC-20 and TRON TRC-20 to Darwinia’s native tokens, e.g. RING and KTON.
        - Experimental contract runtime support. (Using pDSL for testing and experimental, only support command line)
        - Upgraded web wallet and blockchain browser with better user experience.
- Deliverables
        - Docker container running a substrate node with NFT/Token swapping runtime included, can connect to testnet and syncing blocks.
        - User can use web wallet to test the NFT and token bridging, e.g. transferring a NFT token from Ethereum testnet to Tron testnet. (Evolution Land’s alpha version, can be used as a scenario)
        - Documents about how to deploy a sample contract on the experimental contract model
        - Blockchain browser can view the NFT token’s encoding ids, and search NFT by id.
 
After that, there could more testnet for testing and security auditing and preparing for the mainnet launch at Q4 2019. 
This Darwinia Network is based on Substrate and willing to connect to Polkadot finally. The grant award will be used to support the release candidate version of the Solo model mainnet. The cost of each week(only R&D) is around $20k.
We would be willing to requesting funding of $30K for this project. 
 
For M1 milestone, we are willing to request $5K. For M2 milestone, we are willing to request $10K. For M3 milestone, we are willing to request $15K.
We are ok to accept DOTs as payments, all in DOTs is good.

## Additional Information
**Tech & Ecosystem**

Darwinia Network is committed to being a parachain for Polkadot, which we are preparing for both Tech and Ecosystem.
You can check our github and homepage for tech detail

**Home**: https://darwinia.network/

**GitHub**: https://github.com/darwinia-network

Meantime, Darwinia Network design a Staking mode to build ecosystem to bid Polkadot parachain. We look forward to Polkadot’s advising and support.

Community
We host a meetup about blockchain in Nanjing ,China to help build Polkadot community. Here are some photos and reference for the meetup.  We look forward to Polkadot team coming to Nanjing!
Photos for the meetup: https://docs.google.com/document/d/102bC3WZneeKwS2OQl7eJ31D1U--BGyDbfYvflAcbJss/edit?usp=sharing

**News for the meetup:**

https://www.huodongxing.com/event/1496429656800

https://mp.weixin.qq.com/s/9KuIkOt3CY_oKdnBAkaNYA

https://mp.weixin.qq.com/s/xfqTKTUpElOPp1hzwBnukQ

**Is it open source?** 

Our code will be fully open source.

