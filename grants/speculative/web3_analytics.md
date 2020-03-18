# Web3 Analytics

## Project Description

Web3 Analytics is a decentralized Google Analytics alternative aiming to give users the full control of their data. It provides web performance measurement, customized statistics, and data visualization dashboard. With the power of TEE, users' personal data are kept secretly and can only be used in ways approved by users. As a result, users literally get the 100% control of their data.

### The Problem

We are going to build a decentralized off-chain event tracking and analytics tool to solve the privacy problem:

* Web3 developers have no choice but to trust centralized tools like Google Analytics. (More than 70% of the websites are using Google Analytics)
* The big internet companies control all the users data. Users have no way to download or delete their data, neither decide how the data is used by others.
* Finally, users and developers cannot profit from the additional value created by their data.

### How to Protect Personal Data

![](https://i.imgur.com/j6E7mnI.png)

* In Web3 Analytics, the user data is end-to-end encrypted between the user browser and the backend (a confidential contract). The encrypted data is stored in a decentralized storage network.
* Only the user and the confidential smart contract has the access of the encryption key. Therefore users can manage the data and the access of the data.
* Only authorized confidential contracts can analyze the encrypted user data and output the analysis results. The raw data never gets out of the TEE while the analysis results can be displayed on a dashboard.
* All the analysis requests are logged on the blockchain. When the analysis is a part of the data trading, the value of the deal is recorded, and the profit of the deal can be distributed to the data owners in a transparent way.

### Features

The main features of Web3 Analytics are:

* Automatic and customized event measurement and statistics for Web and Mobile apps
* Decentralized data management: Users can 100% manage the collected data and its access permission on a personal data console
* Developer dashboard: Show the visualized analysis results to the developers
* Data Plaza: A marketplace for data trading

The Data Plaza is a novel service to buy and sell data. By putting the data into confidential smart contracts (inside TEE enclaves), the original data is invisible to the buyer. So it enables the trade of data usage but not ownership.

* The buyer writes W3A confidential contract to do the customized analysis
* The contract will only execute if it's approved by the developer and the users
* The computation is done strictly inside the TEE enclave. So there's no data leakage.
* The buyer gets the result after the payment of the data usage.
* The revenue will be distributed to the developers and data owners in a predefined way.


### How is it Decentralized

The analysis and the data management is done by Phala.Network confidential contract. Phala.Network is a decentralized TEE-Blockchain network.

Until the public beta, the data will be served in a semi-decentralized way. The W3A team will store the encrypted data on some public cloud storage providers. The data is encrypted and distributed over the IPFS network. The address of the encrypted files are public available. So everyone can replicate the encrypted data on demand.

We will switch to pure decentralized storage networks when they are available (e.g. Filecoin). This is supposed to happen before our final release.

Finally, the identity management is different for guests and signed in users. For guests, the SDK will generate a key pair as the identity. When a guest signs in (i.e. sign in the personal data console), the console will rotate the temporary key and handle the key management in the future.

### Background

* Confidential Contract: W3A is based on [Phala.Network](https://phala.network), the confidential smart contract protocol share with our earlier W3F grant project [pLIBRA](https://github.com/w3f/Web3-collaboration/blob/master/grants/speculative/pLIBRA.md).
* Relation to Substrate and Polkadot: W3A, pLIBRA, and Phala.Network are built on Substrate and we would like it to become a Polkadot Parachain.

### Open Source

This is an open source project under Apache License 2.0. All the defined milestones will be available to the open source community.

## Team members

* Hang Yin: Blockchain & Smart Contract system design
* Jun Jiang: Privacy Smart Contract and SGX Kernel development
* Shunfan Zhou: Blockchain security research scientist
* Xiaoxuan Tang: Bridge Client development
* Marvin Tong: Project Manager
* Zhe Wang: Business Development

The development will be mainly done by 3 full-time and one part-time engineer. The remaining people will provide necessary support to the development.

## Team Website

* https://phala.network

## Legal Structure

HashForests (Wuhan) co. LTD, a startup company focusing on blockchain development in China.

## Team's experience

HashForests was founded in late 2018 focusing on blockchain and data confidentiality. We have developed a prototype of Intel SGX based smart contract and plugged it into a Graphene based blockchain. We have also developed a few DApps as proof of concept.

In June 2019 we started [LibraChina](https://libra-china.org) and developed a Libra testnet explorer [LibraBlock](https://librablock.io). We started [pLIBRA](https://plibra.io), a privacy-preserving Libra-Polkadot bridge and [got a grant](https://github.com/w3f/Web3-collaboration/blob/master/grants/speculative/pLIBRA.md) from Web3 Foundation.

Before the team was founded, our team members has been worked in Google, DiDi Chuxing, Dji, and Liwoshuo, a famous Chinese startup. We have blockchain experts who initiated Bitcoin Gold, a fork of Bitcoin and now its market cap is ranked around 25th. The team mainly write C++, Js, Rust, Ruby, and Python.

* Hang Yin: Founder and Lead Developer of Bitcoin Gold. Senior Developer of Google. 10 years coding experience.
* Marvin Tong: Senior Product Manager with 3 years experience . Worked in Tencent and Didi which both are the biggest Internet Companies in China. Good at Product Design and Business Development.
* Zhe Wang: Hardware Engineer. Core member of Bitcoin Gold in China.
* Jun Jiang: CTO of KnewOne and Senior Software Architect in Dji. Lead of RubyChina community.
* Shunfan Zhou: Blockchain Security Research Scientist. PhD candidate in Fudan University.
* Xiaoxuan Tang: CTO of Liwushuo. Senior iOS developer and System Architect.

## Team Code Repos

- pLBIRA / Phala.Network Substrate node & bridge: https://github.com/Phala-Network/phala-blockchain
- Phala.Network pRuntime: https://github.com/jasl/sgx_haven/tree/d1 (Private repo, please ask us for access)
- Data Plaza Demo Frontend: https://github.com/Phala-Network/phala-polka-apps
- Phala.Network Whitepaper: https://github.com/Phala-Network/Whitepaper
- Personal projects by team members
  - Bitcoin Gold (Hang Yin): https://github.com/BTCGPU/BTCGPU
  - Rails Engine (Jun Jiang): https://github.com/rails-engine

## Team LinkedIn Profiles

* Hang Yin: https://www.linkedin.com/in/hang-yin-167012a7/
* Marvin Tong: https://www.linkedin.com/in/林-佟-0131b292/
* Zhe Wang: https://www.linkedin.com/in/喆-王-0a99a038/
* Jun Jiang: https://www.linkedin.com/in/jun-jiang-5b9b4153/
* Xiaoxuan Tang: https://www.linkedin.com/in/xiaoxuan-tang-26628784/

## Development Roadmap

* M1: Web SDK & ad-hoc backend
  * 2 weeks, $15k
  * JS SDK to collect predefined and customized stats in Web apps. The traffic is e2e encrypted.
  * An ad-hoc backend with CLI to showcase the SDK
  * Docker image to deploy the backend and a demo web page. Can see and query the collected data in the CLI. Users can check and delete the owned data.
* M2: Implement the backend as a confidential contract
  * 5 weeks, $35k
  * Move the ad-hoc backend to a confidential smart contract based on Phala.Network. So the data is secure.
  * Docker image to deploy the backend contract in Phala.Network dev net. Can query and manage the data as in M1 in the CLI.
* M3: Dashboard, data visualization, and Data Plaza frontend
  * 3 weeks, $20k
  * Replace the CLI by a Web UI dashboard.
  * Develop the Data Plaza to show the available data for customized query & analysis
  * Docker image to deploy the backend and WebUIs as M2. Can see the visualized data in the dashboard and can do basic customized data analysis in the Data Plaza.
* M4: User-side personal data console
  * 3 weeks, $20k
  * Replace the user-side personal data console CLI by a WebUI
  * Docker image to deploy the frontend and backend in M2, M3, plus the personal data console frontend. Users can check, manage, and delete their collected data.
* M5: Documentations and launch of the public beta version
  * 2 weeks, $10k
  * Documentation for deployment, integration and contribution.
  * Launch the above works as a public service (beta) and invite Web3 developers to try it out.
  * Launch the public website and build the community for W3A.

All the deliverables for each milestone will be published in the open source repositories.

The grant will cover the development of W3A till its first public beta. As mentioned earlier, the storage is semi-decentralized but we will switch to a pure decentralized way as soon as possible.

## Long term plans

* Move to a fully decentralized storage
* Launch (mainnet) as the first decentralized analytics protocol
* Build a personal data market on the W3A data exchange protocol

## Additional Information

* What work has been done so far?
  * Phala.Network MVP (via pLIBRA M2)
    * Blockchain Substrate runtime ([repo](https://github.com/Phala-Network/phala-blockchain))
    * TEE miner runtime  ([repo](https://github.com/Phala-Network/phala-pruntime))
    * Blockchain-TEE bridge  ([repo](https://github.com/Phala-Network/phala-blockchain))
  * Data Plaza PoC ([contract](https://github.com/Phala-Network/phala-pruntime/blob/master/enclave/src/contracts/data_plaza.rs) and [frontend](https://github.com/Phala-Network/phala-polka-apps/tree/master/packages/app-phala/src))
  * W3A WIP (50%-90%)
    * Data collection Web SDK
    * Centralized (mock) backend
    * Personal data console frontend
    * Developer dashboard
* Are there are any teams who have already contributed (financially) to the project?
  * No.
* Have you applied for other grants so far?
  * Yes, [pLIBRA](https://github.com/w3f/Web3-collaboration/blob/master/grants/speculative/pLIBRA.md) (WIP).
* Are there any other projects similar to yours?
  * We are the first decentralized Google Analytics alternative. To our knowledge, there's no similar project.
  * Phala.Network's TEE-Blockchain hybrid architecture design is similar to [Ekiden](https://arxiv.org/abs/1804.05141) but supports cross-contract/blockchain interoperability in addition. Thus we can fit into the Web3 technology stack better.
  * Both Phala.Network and [Substrate SGX](https://github.com/libra-china-org/Web3-collaboration/blob/master/grants/speculative/substrate_sgx_proposal.md) use TEE technology and we share some common components.
