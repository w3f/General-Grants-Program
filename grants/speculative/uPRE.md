# Project name

uPRE (upgradable Polkadot Runtime Environment)

## Project Description

#### A brief description.
  The solution from uPRE is to deploy the protocol code of the blockchain system on the blockchain in a certain data format. The client will continuously obtain the latest blockchain protocol code on the blockchain and update the local blockchain protocol code, and execute the latest code, so as to achieve the automatic upgrading of the blockchain system.

#### Why this project is good for the ecosystem？
  [Polkadot Runtime Environment Protocol Specification paper](https://research.web3.foundation/en/latest/polkadot/Polkadot-Runtime-Environment/) proposed the concept of upgradable in RE. However, there still exist a lot of problems for upgrading in such a decentralized system, especially blockchain system like Polkadot:

  * Drawbacks are introduced when manipulating upgrade. Upgrades need to be deployed by trusted institution, which offends the feature of decentralization of blockchain.
  * Upgrade leading to soft fork or hard fork brings bad effect to the comunity. Even worse, upgrade disables continuous service during the upgrade period, which is unacceptable.

  The uPRE project addresses above mentioned limitations. The uPRE is focus on upgrade the Runtime with continuous service during the upgrade period without hard fork. Morever, in consideration of concurrent execution of the Runtime code, uPRE proposes software transactional memory to ensure the correctness of concurrent execution and code automatic analysis for non-memory execution.

#### How to integrate uPRE into Substrate / Polkadot?
  The intergration starts with modification of the Runtime Environment implementation. The modification includes the Runtime code compilation, management and execution. The Runtime code compilation is alterative, while management and execution is necessary.

  Polkadot paper has described that the code for the Runtime of the chain would be compiled to WebAssemply. There is no need for code compilation if compiled code remains to be WebAssemply. But to support for more various of the Runtime code language, the Runtime code is recommended to compiled to LLVM intermediate representation.

  The Runtime code management and execution phase is for code concurrent execution. Code manager holds historical versions of the Runtime intermediate representation code, and responses specific one when requested by client. In execution phase, intermediate representation code is executed dynamiclly by LLVM Just-In-Time interpreter. To implement code automatic analysis and software transactional memory, variables are marked and software transactional memory code is generated at compiler level, which means development of Just-In-Time interpreter.


  ![uPRE architecture](http://doc.asresearch.io/download/pdfs/fig_architecture.pdf)

## Team members
Leader：
* Xuepeng Fan
  Former technical director of Nebulas. Doctor of computer system architecture of Huazhong University of Science and Technology, visiting scholar at the University of California, San Diego. His research interests are blockchain system, distributed system, parallel programming, computer system reliability, etc. He has published many academic papers in top international conferences and journals.

Members：
* Zaiyang Tang
  Former senior researcher of Nebulas. Doctor of computer system architecture of Huazhong University of Science and Technology, visiting scholar at the University of Aizu and Telecom SudParis, his research interests include distributed systems, wireless networks and blockchain consensus. He has published papers on some top journals and conferences like TPDS, ICDCS, etc.
* Yulong Zeng
  Former senior researcher of Nebulas. Doctor of the institute of interdisciplinary information science of Tsinghua University, visiting scholar at the University of Michigan and Aarhus University. He hold a bachelor's degree in Yao's class of Tsinghua University. He won the gold medal in the Chinese Mathematical Olympiad (CMO). His research interest is game theory and mechanism design. He has published many papers as the first author in top international conferences such as EC, AAAI and AAMAS.
* Chenmin Wang
  Former senior engineer of Nebulas, former Tencent research and development engineer; former Huawei research and development engineer. Master in computer of Zhejiang university, former Dolphin Browser research and development engineer.
* Ruby Wu
  Former marketing director of Nebulas. Master of finance, Chinese University of Hong Kong; Bachelor of applied mathematics in National University of Singapore; Bachelor of liberal arts and science in Waseda University; her research interests are blockchain finance and tokenomics. She previously worked in the capital markets division of Standard Chartered Bank and investment banking division of China International Capital Corporation Limited.

Advisor：
* Aero Wang
  Co-founder of NEO&Nebulas, co-founder of BitsClub, founder of OpenIP, serial entrepreneurs of blockchain community, graduated from School of Architecture, Southeast University.

## Team Website
* https://asresearch.io/

## Legal Structure
ASResearch is an decentralized collaborated organization, all the organizational and collaboration rule including add/deduct partners, benefit/dividend distribution, proposal management and etc is conducted through blockchain and managed by multi-signed smart contract, currently team members are located in Beijing, Shanghai and San Francisco.

## Team's experience
ASResearch consists of a number of PhDs and masters who engaged in blockchain studies with solid research capabilities and knowledge in multiple related areas for a long time. All members of ASResearch have valuable experience and expertise in blockchain development and marketing.

Meanwhile, ASResearch actively cooperates with universities and research institutes for active exploration of basic theories  and deep understanding of all aspects of blockchain system.

## Team Code Repos
* https://github.com/ASResearch

## Team LinkedIn Profiles
* https://www.linkedin.com/in/zaiyang-tang-9a48a8151/
* https://www.linkedin.com/in/chenmin-wang-02756888/
* https://www.linkedin.com/in/ruby-wu-34938531/
* https://www.linkedin.com/in/xuepeng-fan-4a77a558/
* https://www.linkedin.com/in/aero101/

## Development Roadmap

  * Milestone 1 - Publish relevant technical paper - 2 monthes - $8,000
    - Technical paper achieves the release in forms of academic article, including sections of introduction, background, architecture, implementation and evaluation.
    - Technical paper describes the limitations of upgrading the Runtime;
    - Introduces technology of Just-In-Time compilation and software transactional memeory background;
    - Illustrates architecture design purpose and priciple, as well as upgrade procedure;
    - Explains the detail implementation of architecture components;
    - Gives each component and the whole system performance evaluation and analysis results.

  * Milestone 2 - Accomplish the development of uPRE in C++ - 2 monthes - $12,000
    - This milestone should achieve the implementation of uPRE in C++, including the compomemts of:
    - Interprocess between the Runtime and the Runtime Environment;
    - Tools for the Rumtime source code deployment;
    - The Runtime on chain code parse and management;
    - Code automatic analysis, code generation of LLVM Just-In-Time interpreter for concurrent execution.
    - 100% code coverage of the uPRE unit test as well.

  * Milestone 3 - Implement Rust bridge of uPRE - 1 monthes - $5,000
    - Providing Rust interface of uPRE as Polkadot uses Rust.

  * Milestone 4 - Integrate with the existing Polkadot Runtime and integrate test - 1 monthes - $5,000
    - This milestone should achieve that the Polkadot Runtime upgrades with continuous service providing without hard fork.
    - Integrate test should achieve bug free and optimized released software.


  * The team's long-term plans and intentions
    - The solution of BRE is to deploy the protocol code of the blockchain system on the blockchain in a certain data format. The client will continuously obtain the latest blockchain protocol code on the blockchain, update the local blockchain protocol code, and execute the latest code, so as to achieve the automatic upgrading of the blockchain system. More specifically, BRE adopt LLVM JIT to execute high-level language code on the chain.
    - On the basis of the automatic upgrade, BRE further solves the problem of concurrent execution of different versions of the code on the chain. Although a naive solution could be using global mutex to ensure sequential execution, the performance could be declined. Thus, we propose to adopt transactional memory to gain fine-grained parallel and further improve the execution performance on the premise of ensuring correctness. The working flow of this proposal includes an static program analyzer which figures out the possible parallel program slices, an dynamic program instrumentation tool which insert guarding code to ensure correctnees, and also a transactional memory runtime as the implementation of the inserted guarding code.
    - Providing the ability of extending library for smart contracts. Compared to upgrading the protocol code of Polkadot, it should be more common of upgrading the functionalities of smart contract library. For example, a parachain may need new cryptogrphy primitives, or need to upgrade existing implementation due to optimization or bug fix. Thus, we long-termly plan providing the ability of extending smart contract library without hard-fork. This needs to extend the execution engine of WASM and providing specific interfaces for smart contracts.

## Additional Information
### Related techniques by other team
We have initiated the structure design and technical implementation of this project since October 2019, some projects in the industry is attempting in the similar direction.

[Tezos](https://tezos.com/) is the first permissionless blockchain, who gives the concept of self-amendment, and accepts and deploys protocol upgrades without the need to hard fork, to deal with the blockchain upgrade problem. The candidates of amendment proposal are voted by StakeHolders, and then achieve upgrade by exposing two procedures functions `set_test_protocol` and `promote_test_protocol` to the protocol. Since Tezos’ implementation programming language OCaml is functional programming, supporting the feature of compilation on the fly, there will provide service continuously during the upgrade time.

  Nevertheless, the way of Tezos self-amendment, or upgrade in other words, still has limitations.

* First of all, Tezos’ upgrade functions replace the current protocol with a new one, instead of keeping the historical protcols available at the same time, making it impossible to run the previous after upgrade done unless reverse replacement again. Suppose that Tezos is in the situation where the current protocol is the latest while transactions to be verified and validated isn’t. In that case, the latest protocol must cover all possibilities that Tezos may reach, which in require of protocol backward compatible, and makes protocol logic complicated further.
* Second, protocols being executed concurrently is impossible either, much less correctness of concurrent execution results.


### Grant from other institutions

As a team, ASResearch has submitted the application from ECF ( Ethereum Community Fund) on early Augest 2019, the application is not related the above work. The projects submitted for ECF is bascially projects related to Ethereum, including:
* An Identity Inference Approach for Blockchain based on Graph Deep Learning : this project is an academic paper, in this paper, we propose I2GL, an identify inference approach based on graph deep learning to address these challenges. Specifically, I2GL constructs a transaction graph and aims to infer the identity of nodes using graph embedding technique based on Graph Convolutional Networks.

* The Matthew Effect in Computation Contests: High Difficulty May Lead to 51% Dominance: this project is an academic paper, in this paper, in this paper, we study the computation contests where players compete for searching for a solution to a given problem with a winner-take-all reward.

* Developer Incentive Protocol: Decentralized Address and Smart Contract Ranking & Rewarding Mechanisms: this is project is a protocol. In this project, we introduce a decentralized mechanism for fairly ranking the decentralized applications on blockchain and rewarding their developers. The main characteristic of the protocol is that users who invoke different applications contribute more to the total ranking score. We introduce three kinds of manipulations, bribe, Sybil attack and splitting decentralized applications. We then analyze the properties against these manipulations of the developer incentive protocol in a game theoretical way.

