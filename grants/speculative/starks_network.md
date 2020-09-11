## Starks Network

## Project Overview
> Monopolies like Facebook and Amazon, they track our every move, they monitor every moment in our lives and they exploit our data for profit. These companies are the kings and they rule over kingdoms far larger than any nation in human history. They won; we lost. ...The way we win is by creating a new, democratic, decentralized Internet, where it is the users, not the kings who have sovereign control over their data. An Internet that is of the people, by the people and for the people.
>
> -- Richard Hendricks, "Silicon Valley"

### Brief Description

Zero-knowledge proof (zkp) is a cryptographic technology which enables you to prove that you know a secret without revealing it. It is a powerful tool in the paradigm of Web 3.0 where people can prove certain attributes about themselves without giving away their private data. It can also be used to prove computational integrity which can result in novel applications such as a private smart contract on a blockchain. 

However, it requires tremendous expertise to construct a zkp for certain computation. This hinders the adoption of this powerful technique for everyday use. Wouldn't it be great if we can construct a zkp for any general purpose computation without a deep understanding of zkp? Enter the [Distaff VM](https://github.com/GuildOfWeavers/distaff), a zk-STARK virtual machine written in Rust. For any program executed on Distaff VM, a STARK-based proof of execution is generated. This proof can then be used by anyone to verify that a program was executed correctly without knowing the inputs to the program or even the program itself. 

The Starks Network is a [zk-STARK](https://vitalik.ca/general/2017/11/09/starks_part_1.html) based zkp parachain for the Polkadot/Kusama ecosystem. At its core, it uses the Distaff VM for zk-STARK proof generation and verification. Powered by the [Substrate](https://github.com/paritytech/substrate) blockchain framework, the Starks Network can serve other blockchains and enable applications such as private smart contract and private credential verification.

### Benefit for the Ecosystem

First of all, the Sarks Network falls in line with the vision of Web3. We desire a decentralized Internet where the users can have sovereign control over their data. But the data are often of little use if you don't share them with others. For example, one needs to share their financial and credit information with a bank in order to get a loan. But one loses the control over this information once it enters the database of the bank. With the help of the Starks Network, people can keep their data in their phone and do the KYC computation also in their phone in OFFLINE mode. A zk-STARK proof can be generated and it is all that is needed to convince the bank to permit the loan. As such, the Starks Network enables the users to use their data for thrid-party services and never have to give away of their data anymore.  

Secondly, the Starks Network can provide zkp construction/verification for other parachains in the Polkadot/Kusama network. For example, a DeFi parachain can construct a smart contract for a financial service. And by talking to the Starks Network using XCMP, two parties on the DeFi chain can execute the smart contract (e.g. make a transfer of some asset) without other people knowing the details of the transactions. The Starks Network will prove to be a valuable team player with other blockchains in the Web3 ecosystem. 

### Substrate/Polkadot Integration

Substrate is a powerful blockchain framework. It enables us to bootstrap the skeleton of the Starks Network in a short time. The Starks Network blockchain serves several purposes:

* It keeps a record of all the proof verifications;
* It provides a way to setup a smart contract for a computation and to carry out subsequent actions based on the proof verification result;
* It enables the flow of economic incentives among the users and the verifiers. 

As already mentioned, other blockchains in the Polkadot/Kusama network can interact with the Starks Network via cross-chain message passing. Developers on other chains can design smart contract which benefit from zkp and they don't have to be experts of zkp at all.

### Team Interest

The Glacier Blockchain team is an advocate of the Web3 ideology. It strives to help build an open, transparent and inclusive network which returns the sovereignty of data to their owners. It is a member of the [DIF](https://identity.foundation/) and has contributed to the international standardization of decentralized identity and verifiable credentials. The Glacier Blockchain team has also co-founded the [Web3 Identity Lab](https://medium.com/@KILT_Protocol/web3-identity-lab-395342207d70) with the KILT Protocol team to work on scientific research and technical solutions from verifiable credentials to user privacy protection. 

We have been fascinated by the progress of latest cryptographic primitives such as zero-knowledge proof. We have learned the potential of the Distaff VM project regarding privacy protection and computation integrity through our frequent discussions with the author of the project. We truly believe the combination of a general purpose zk-STARK virtual machine and the Substrate framework will make the Starks Network a valuable player in the Polkadot/Kusama ecosystem. 

## Project Details

### Introduction to the Distaff VM

A high level [architecture of the Distaff VM](https://ethresear.ch/t/a-sketch-for-a-stark-based-vm/7048) is shown as the following.

<img src="https://ipfs.io/ipfs/QmU2wmw6nVGXjQhANtMymd6KSnkubmNPNAe2qxzY1aHZVf" alt="distaff_overview" style="zoom:150%;" />

The Distaff VM provides a set of assembly language which can be used to construct a general purpose computation into a *program* which can be interpreted by the virtual machine. The basic work flow of the VM is:

a. Takes 2 inputs: a program and a set of inputs for the program;

b. Executes the program with the given set of inputs;

c. Outputs hash of the inputs, hash of the outputs generated by the program, and a STARK proof attesting to the correct execution of the program.

Then the verifier can take the hash of the program, hash of the inputs, and hash of the outputs, and uses them to verify the STARK proof. As such, the user can prove to the verifier that she owns some secret data which, when used as the input of a program, can yield certain output. She never has to reveal the input data to the verifier; thus her privacy is protected.  

One way to automate this process is to set up a smart contract on the blockchain which can perform the proof verification. As such, a lot of real-world verification work can be moved on-chain and the users never have to give away their secrets for e.g. credential verification. 

### Architecture of the Starks Network 

The overall system architecture and the basic work flow of STARK proof generation and verification on the Starks Network is shown as following.

<img src="https://ipfs.io/ipfs/QmSDsZZngwipBuKkkXqqfjt8NQPXSpv4BvqqScrJ2gejzB" alt="system_disgram" style="zoom:60%;" />

a. A verifier will set up an on-chain smart contract with a target Distaff VM program embedded.

b. A user will interact with the smart contact, get the program and generate a proof with their secret inputs using the Distaff VM embedded in the user client application (Step 1, 2 and 3). 

c. The user sends the hashes and proof data (results) back to the smart contract via a transaction (Step 4).

d. The smart contract will verify the results using the Distaff VM built in the blockchain node binary, make a decision and update its state (Step 5 and 6).

As such, the user has interacted with an on-chain smart contract without revealing their secret data. It should be noted that the Distaff VM will be made as part of the user client application for proof generation. It will also be made as part of the blockchain node binary and accessible to the on-chain smart contracts. 

### Existing Problem and Our Solution

It seems straightforward to perform step c in the previous section on a Substrate blockchain. However, it is actually not feasible and here is why. Compared to other zkp techniques such as zk-SNARK or Bulletproofs, one disadvantage of zk-STARK is the [relatively large proof size](https://snarkage.substack.com/p/tradeoff-space-and-other-nizks-starks). The typical size of a Distaff VM proof is around 100KB. It would be unrealistic to store all the proofs on-chain as the blockchain storage is kind of expensive. 

**So, is there a way to store the proof data off-chain while we can still make use of them for zkp smart contract verification?**

Thanks to the Substrate framework, we have a tool to solve this problem. An off-chain worker (ocw) is a Substrate subsystem which can process off-chain data in an asynchronous way. It can perform non-deterministic tasks such as Web requests or CPU-intensive computations and write the computation results back to the chain as signed transactions. As such, we can have some *stark data nodes* in the system which will cache the proof data sent by the user in a local data store or even a decentralized data storage such as IPFS. The ocw will check the data store periodically, process the proof data, get the verification results and update the state of an on-chain smart contract with a transaction. This approach can solve the storage problem of off-chain proof data.  

But there are again issues as a result of this approach. What if a node runner tries to cheat with their proof? What if a malicious node sends back incorrect verification results intentionally? We have designed counter measures regarding these threat models and they will be unfolded as our project progresses. In the scope of this grant application, we will focus on the PoC where an on-chain smart contract interacts with the Distaff VM using proof data stored off-chain. 

## Ecosystem Fit 
There are some existing projects which can be related to the Starks Network. In general, they fall into the following categories:

* Blockchain projects which provide confidential computing service using a hardware Trustable Execution Environment (TEE). [Phala Network](https://phala.network/en/) and [SubstrateTEE](https://github.com/scs/substraTEE) are good examples of such projects. The main difference is that we use zkp instead of hardware chips to provide similar functionalities. Our approach makes the Starks Network immune to hardware bugs/failures/backdoors in proprietary CPUs. 
* [Zerochain](https://github.com/LayerXcom/zero-chain) is a Substrate based zkp blockchain project. The main difference from the Starks Network is that it uses zk-SNARK instead of zk-STARK VM as its zkp power house. The zk-SNARK is well known for its small proof size. But it requires a trust setup process to get started which limits its usage. In addition, the function of the Zerochain is focused on private transaction, while the Starks Network aims to provide zkp service for general purpose computations. 
* The [Cairo project](https://medium.com/starkware/hello-cairo-3cb43b13b209) from [StarkWare](https://starkware.co/) (inventor of the zk-STARK technology) announced a few days ago. As explained in the press release, "Cairo is the first production-grade platform for generating STARK proofs for general computation". The description of its functionalities have a lot of similarities to what our Starks Network have to offer. It is fair to say the Cairo project is a powerful counterpart of the Starks Network--only it is built in the Ethereum ecosystem. The whitepaper, documentation and related tooling are yet to come in the next few months (unsure if it is open sourced). And we will closely watch its development as it is exciting and inspiring to have more projects coming in the field of zk-STARKs application. 

## Team members
* Dr. Xiao Zhang - CEO/Project Lead/Blockchain Researcher
* Ming Chow - System Architect/Substrate Developer
* Xinran Chen - Substrate Developer
* Jinjiao Yin - Full-stack developer
* Linjun Lu - DevOps

## Team Website	
* http://www.gbctech.cn/

## Legal Structure 
Glacier Blockchain Technology is a company registered in Yantai, Shandong, P. R. China. 

## Team's experience
**Dr. Xiao Zhang** is a researcher with experience in computer architecture, blockchain and cryptography. He holds a PhD in computer science from the University of Twente of the Netherlands. He is an active advocator of Web3 and also one of the first Polkadot ambassadors in China. His current research interests include decentralized identity, verifiable credentials and zero-knowledge proof technology for privacy protection. 

**Ming Chow** has a bachelor's degree in computer science. He has 10 years of experience in system architect and software development. He has worked in several high-tech companies in Guangzhou and Shenzhen in China and lead the design of several core business software. He is responsible for the Substrate system architecture design for the Starks Network. 

**Xinran Chen** has worked for many years in Internet companies such as Talkingdata, PingCAP and Qiniu.com. He has started working on blockchain product since 2019. He has contributed codes to Boltdb for Tendermint. He is the Substrate developer for the Starks Network. 

**Jinjiao Yin** is a senior computer science student of Shandong Technology and Business University. She is the group leader of the Student Blockchain Lab. During her college time, she has won multiple computer science competition awards. She is specialized in full-stack web app design for blockchain project. 

**Linjun Lu** is a senior software engineering student of Shandong Technology and Business University. She is a senior member of the Student Blockchain Lab. She is particularly interested in application DevOps on Linux platforms.

## Team Code Repos

* Starks Network Node: https://github.com/gbctech/starks-node
* Glacier Blockchain: https://github.com/gbctech
* Xiao Zhang: https://github.com/xz-cn
* Xinran Chan: https://github.com/Lawliet-Chan
* Jinjiao Yin: https://github.com/inoutcode
* Linjun Lu: https://github.com/lulinjun1111

## Team LinkedIn Profiles
* https://www.linkedin.com/in/xzhangcn/
* https://www.linkedin.com/in/%E6%98%95%E7%87%83-%E9%99%88-b41b26187/

## Development Roadmap

### Milestone 1 — Integration of the Distaff VM as a Substrate Native Runtime Module 

- **Estimated Duration:** 1 month
- **FTE:** 3

As the Distaff VM uses the Rust standard library, it is not feasible to compile it as a Wasm runtime module. This means we will have to build it as a native runtime module and make it part of the binary of the blockchain node. This is ok as the Distaff VM module will not change frequently once its design is finalized. And it can still serve the off-chain worker, which will be a Wasm runtime module, via the `runtime_interface` feature of the Substrate framework. The following activities will be carried out in Milestone 1. 

* We will reorganize the Distaff VM project, split its functions into sub-modules and create frame pallet(s) following the conventions of the Substrate framework. 
* We will perform configuration/optimization work to make the VM module easier to use for typical use cases of the Starks Network. 
* We will deliver a working VM module and a document that explains how a user can interact with it via API calls. We will also provide a full test suite (mock and test files) for the VM module describing how the module can be tested. 
* We will deliver a Docker image which contains the VM module and expose its main functionalities via RPC calls.

### Milestone 2 — Implementation of the Off-Chain Worker Module  

- **Estimated Duration:** 1 month
- **FTE:** 3

In this milestone, we will design and implement an off-chain worker (ocw) module for the Starks Network. 

* We will create the ocw which takes the proof data generated by the user client as input and produce verification results as output. To actually perform proof verification, the ocw can access the Distaff VM native runtime module via the `runtime_interface`.
* The input data consist of the following data fields: {program_hash, input_hash, output_hash, stark_proof}. The output will be a pass/fail result. For the sake of demonstration, both the input and output for the ocw will be local files. 
* We will design and deploy a smart contract using e.g. ink! for the ocw to interact with. The ocw will be able to change the state of the smart contract based on the proof verification result. 
* We will deliver a Docker image which contains the ocw and the smart contract implementation. We will write a tutorial on how to interact with the ocw. The user will be able to feed their own Distaff VM proof data as input to the ocw and get the subsequent output. They will also be able to observe the state change of the smart contract as a result of their successful/failed verification. 

### Milestone 3 — Implementation of the Off-Chain Data Storage

- **Estimated Duration:** 1 month
- **FTE:** 3

In this milestone, we will design and implement the **Starks data node** which solves the off-chain STARK proof data storage issue for the Starks Network.

* The Starks data node functions in a similar way as a web server with a database. It provides a public REST API for the users to post their proof data. It saves these data in a local key-value database and makes them available to the ocw. 
* We will design the ocw logic for its interaction with the data node. Basically, the ocw will periodically access the REST API of the data node. It checks if new data is present in the database and if so, fetches them for verification. 
* As storage has a cost, we will create a mechanism for the data node to decide if the incoming data should be stored or abandoned depending on the state of a smart contract on the blockchain. 
* We will deliver the Starks data node as a docker image. We will also provide documentation on how to use it alongside the Starks Network node. The user will be able to spin up both nodes on the same server and observe their interaction given proper input to the REST API.

### Open Source License

All work carried out in this grant project is released under the GPLv3 license.

## Community engagement

We will publish an article on medium upon the completion of this project. Meanwhile, we will give talks and do AMA sessions to advertise the project to the Polkadot community.

## Future Plans
* The Starks Network plans to become a parachain for both the Polkadot and the Kusama network. 
* This application covers stage 1 of the Starks Network project. In stage 2 of the project, we will focus on the UX/UI design and provide several typical use cases (credential, smart contract) for evaluation. A MVP will be running in a testnet. 
* In stage 3, we will experiment the cross-chain communication with other parachains. If things go well, we will provide zkp support to the smart contracts in other parachains (Plasm or Edgeware are our choices right now).
* After its main functionalities are finalized and tested, the Starks Network will issue its own tokens. And we hope other parachains in the ecosystem can benefit from its zkp service. The network will receive economic incentives in the process to sustain its service model.

## Additional Information
* What work has been done so far?

  We have preliminarily integrated the Distaff VM as a native runtime module into the Substrate framework. We have saved the locally generated proof data as binary files and sent them to the Distaff VM module via RPC request. As show in the screenshot below, the VM in Substrate can function correctly and send back verification results indicating a passed/failed verification. 

  ![test_result](https://ipfs.io/ipfs/QmQhUjUSLzpHR7rU4nLQVo2dAvnGLVg1KMWzb5dEueKLqv)

  

* Are there are any teams who have already contributed (financially) to the project?

  No.

* Have you applied for other grants so far?

  No, we are self-funded so far. 
