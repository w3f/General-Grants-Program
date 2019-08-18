# Project name
decentralized incentive community

## Project Description
* The whole solution is to create a decentralized incentive community for KOL or star.
* The project will deliver a smart device can sync data in substrate and interact with blockchain.
* There are two kinds of Parachains, both star chain for smart contract algorithm and DID chain for decentralized ID.
* The Dapp run on both Android and IoS.
* The Parachain wallet can show token and DID, transfer token.

## Team members
* Jun: full time researcher and developer
* Yongpeng: for backenk server
* Xuewen: for smart device
* Zhixin: for Parachain wallet

## Team Website	
* https://hardchain-lab.github.io
* https://github.com/hardchain-lab 

## Legal Structure 
No

## Team's experience
* Jun: blockchain scientist in star mine Ltm. two years research experience in Ethereum,
               Polkadot and IPFS. Over 15 years software architect and development experience.    

* Yongpeng: R&D director in star mine. experience in cloud computing,
    lots of experience in android app, Ethereum Web3 SDK and Solidity.
    Implemented the community incentive coin economic model based on Solidity.

* Xuewen: frontend software expert, proficient in js and UI framework like Reactor, VUE. 

* Zhixin: Android and Dapp expert, experience in wallet for BTC, ETH and so on.

## Development Roadmap
We will start the project from August, understand Substrate and Polkadot. Details as following:

* Septerber 2019

Runtime: complete start chain smart contract based on substrate
API server: accept the basic query from Dapp, including the balance, events and transactions.
Device: run light weight node of substrate, build and upload the docker image. management software in device can monitor docker process, upgrade image.
Dapp: get all information about the star coin via API server. Dapp can activate new device, set WiFi for device and so on.
Wallet: complete the UI design and work flow

* October 2019

Runtime: complete DID chain smart contract based on substrate, running as a new separate Parachain.
API server: accept the query from Dapp about DID address, DID ownership and the request of change ownership.
Device: run a new image of DID Parachain, create DID for device and send transaction to change ownership, add new attribute and so on.
Dapp: show the DID of fans, the DID of device. track the ownership change and attribute binding history
Wallet: generate key pair, sign transaction, send transaction and so on.

* November 2019

Runtime: template the star coin smart contract, contract can be customized according to requirement.
API server: stable the server and improve efficiency.
Parachain Wallet: a wallet can keep the Sr25519 secret, sign for transaction. show tokens, devices and DIDs. 

* Future

1. integrate with Kusama test network and test against it.
2. cross chain function, DID Parachain can interact with Start Coin Parachain.
3. wallet can support more tokens such as Kum, Dot and all tokens issued in Parachain.
4. whole solution used in real business case
5. easily customized Parachain and Dapp according to personalized requirements

## Licensing
* GNU GPL v3 license.

## Budget
* We need about 30K dollar to complete the first three months requirements. We can accept the fiat or equailent DOT. 
Four engineers will participate the project

