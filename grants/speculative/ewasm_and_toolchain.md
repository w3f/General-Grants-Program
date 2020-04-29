# A Substrate Runtime Module for Ewasm and LLVM toolchain

## Project Description

The Second State team is creating a new Ewasm (Ethereum flavored WebAssembly) virtual machine, and a new Solidity / Vyper / YUL / Rust compiler toolchain based on LLVM. The Second State Ewasm is written from scratch to optimize for Ethereum’s particular programming models such as the requirement for deterministic behavior and “native” support for 256 bit integers. It also takes advantage of hardware optimizations from vendors like Qualcomm through our WASI bridge. As a result, it could be much faster and safer than the Ethereum Foundation’s current Ewasm implementation. Furthermore, our LLVM-based toolchain allows developers to benefit from the multiple language frontend support and optimization work done by the larger LLVM community. In this project, we aim to incorporate both the VM and toolchain into the Polkadot ecosystem as Substrate runtime modules (SRML). We will provide comprehensive developer documentation and tutorials as part of this effort.

This project benefits the Polkadot community because it maintains forward compatibility with the Ethereum ecosystem, and provides high performance Ewasm runtime and toolchains for the Polkadot community. It will enable Substrate-based blockchains to leverage the large Ethereum developer ecosystem, and execute current and future Ethereum smart contracts out of the box. The Second State team has been working on Ewasm and compiler toolchains for over a year. We are compiler and virtual machine experts. We are the world’s first team to create working software that compiles and runs Solidity applications on the Ewasm testnet. Find more about related work at Second State: https://www.secondstate.io/buidl/

## Team members

* Name of team leader: Hung-Ying Tai
* Names of team members: Shen-Ta Hsie, Tim McCallum, and Michael Yuan

## Team Website	

* https://www.secondstate.io/buidl/

## Legal Structure 

Will be shared privately via the Google Form.

## Team's experience

Hung-Ying Tai is the Director of Engineering  at Second State. His work on the LLVM-based Solidity compiler, SOLL, was recognized and awarded by the Ethereum Foundation as well as the Ethereum Classic Labs in 2019. Mr. Tai leads the WASM runtime work at Second State, where he also successfully delivered EVM extensions such the Lity rules engine on Solidity and libENI native interface for the EVM in the past. Before the emergence of blockchain, he worked in the field of compiler optimization and virtual machine design.

Dr. Michael Yuan is the CEO of Second State. He is the author of book “Building Blockchain Applications” to be published by Addison-Wesley in 2019. Dr. Yuan has extensive experience developing and commercializing Open Source software. His past experience includes product management and developer programs in major open source companies such as JBoss and RedHat. Dr. Yuan received a PhD from the University of Texas at Austin. 


Tim McCallum leads the developer tools and outreach programs at Second State. He contributes to the BUIDL IDE project, a web-based IDE for dapps across multiple Ethereum compatible blockchains. He maintains the Second State smart contract search engine, an ElasticSearch-based application that enables dapps to consume and use auxiliary data from the blockchain inside smart contracts. Tim writes prolifically and produces videos for developers to learn about dapp and blockchain development. 

Shen-Ta Hsieh is an open-source contributor and translator in various opensource projects including Ampache, Airsonic MusicBrainz Picard, syslog-ng, and KeePassXC. He designs and leads the development of SOLL compiler. Previously, he led an internal project, HaskellEwasm, which compiles Haskell smart contracts into ewasm and also applies formal verification for the applications.

## Team Code Repos

* https://github.com/second-state/soll
* https://github.com/second-state/buidl
* https://github.com/second-state/lity
* https://github.com/second-state/lityvm
* https://github.com/tpmccallum

## Team LinkedIn Profiles

* https://www.linkedin.com/in/hydai/
* https://www.linkedin.com/in/myuan/
* https://www.linkedin.com/in/tim-mccallum-2226413a/
* https://www.linkedin.com/in/shen-ta-hsieh-4a11b242/

## Development Roadmap

The requested funding will be sent over Google Forms.

Day 0: Project start. Setup project management tools and public code repositories for external audit and monitoring. 

Day 30: Complete the following.

* Compile Solidity programs to Ewasm bytecode
* Compile Vyper programs to Ewasm bytecode
* Compile limited Rust programs to Ewasm bytecode
* Bootstrap the Second State Ewasm from command line and execute the bytecode applications
* Demonstrate Second State Ewasm performance advantage over standard Ewasm and EVM in benchmark tests.

Day 60: Complete the following. 

* Bootstrap Ewasm runtime from Substrate
* Provide standard API endpoints to deploy contract bytecode and execute contract methods in Substrate
* Package and release the SRML for the Ewasm component
* Port and pass EVM test suites on Substrate.

Day 90: Complete the following. 

* Integration with the BUIDL IDE tool to directly deploy and test Ewasm dapps from a web app.
* Provide comprehensive documentation for developers. 
* Create at least 5 video tutorials on how to use Ewasm on Substrate blockchains.

Long term: We plan to maintain and optimize the Ewasm runtime and developer toolchain. For example, many performance optimizations are needed before WASM can truly become a competitive server side VM. We also aim to support more LLVM languages as smart contract languages, such as Rust, JavaScript, Go, Swift, etc. 

Our goal is to commercialize these open source technologies as enterprises start to adopt blockchain solutions. We believe that the Polkadot Cross-Chain ecosystem is crucial for driving such business adoption. 

## Additional Information

We have already have an alpha release of the Ewasm VM and its LLVM-based Solidity compiler. We can demonstrate compiling, deploying, and calling Solidity contracts on an Ewasm testnet. This proposal seeks additional funding to complete and optimize the software, especially for the Substrate / Rust ecosystem. 

Second State has received funding from the Ethereum Foundation and Ethereum Classic Labs in the past for early Ewasm proof of concepts. We do not have a current grant, and have not yet applied for a grant for the proposed work.

