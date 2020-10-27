# Pocket4D

## Project Description
It's an embeddedApp/Dapp container, which runs Mini-Program inside existing iOS/Android/Desktop applications.
  
- Make `Mini-Program` distributed and can be another form of Dapp.
- Every app can be a super app using this framework.
- Decentralized application system using Decentralized Storage and blockchain
 

## What is `Mini-Program` and `W3C Mini App`, and Why

There are several pain-points for current Dapps, for example:

1. Most of Dapps are built for web/browser, not for mobile.
2. Most of Dapps are using domain system to access, it might be blocked by DNS firewall.
3. Most of Dapps are not user-friendly and not yet providing good experience due to lack of rich apis (compared to mobile device).
4. Most of Dapps are rely on other applications, eg. Browser extensions or mobile wallet.

The idea of `Mini-Program` is somehow powerful and successful in a way, we think it can be used in the `Web3` system rather than stayed in those big companies' warehouse.

For people who are not familiar of `Mini-Program`, please refer to our wiki:
[Background of Mini-Program](https://github.com/Pocket4D/Pocket4D-Wiki/blob/master/introduction.md#background)

And `W3C Mini App`, please refer to
[W3C Mini App white paper](https://www.w3.org/TR/mini-app-white-paper/)



## The Pocket4D solution

The Pocket4D propose a solution to introducing `Mini-Program/Mini App` to `Web3` ecosystem.

For client side:
1. Integrate `Web3/crypto` libraries with our container, started from `Substrate/Polkadot`
2. Embedding a light-weight and fast javascript engine to container
3. Implementing `Mini-Program/Mini App` with our cli and front end markups.

For blockchain side:
1. Use `Substrate` to start a blockchain with IPFS module, to store the `Mini App` bundlde so that Each `Mini App` bundle has a hash address to access, not using domain system (won't blocked by DNS firewall)
2. Build a governing module and distributed system, defining network roles such as `miners`, `validators`, `host` and `dapps`, and try to create a new eco-system of dapps.

Finally, we may see:

1. Dapps are running inside mobile app, without worrying rejected by AppStore(s).
2. Dapps can be dynamically updated like a `web-app`.
3. Dapps are provided richer apis by container/host than browser/webview.
4. Dapps are distributed by blockchain, by using decentalized storage and economic models, governed by community not AppStore(s).


## What have been doing and status

This project is pretty big and consist of many parts.

**Client side**:
1. [Pocket4D](https://github.com/Pocket4D/Pocket4D), the Dapp Container, a flutter plugin with running `Mini-App` inside. Status: Heavily developing
2. [quickjs_dart](https://github.com/Pocket4D/quickjs_dart), a light weight javascript engine, binded and published as dart/flutter plugin. Status: Heavily developing
3. [p4d-rust-binding](https://github.com/Pocket4D/p4d-rust-binding), a rust binding libraries for dart/flutter, supporting Substarte/Polkadot and more. Status: Start developing, applying an Open Grant
4. [Pocket4D-CLI](https://github.com/Pocket4D/Pocket4D-CLI), a complier to compile `Mini-App` to specific format for container.Status: Heavily developing

**Server/Blockchain side**
1. [Pocket4D-Server](https://github.com/Pocket4D/Pocket4D-Server), a test server for bundle storage, proof of concept and local developing. Status: Proof of concept
2. [p4d-substrate-node](https://github.com/Pocket4D/p4d-substrate-node), a substrate node with IPFS module. Status: Start developing

**A proof of concept demo**:
Click to download an [Android Poc Demo](https://pocket4d.s3-ap-southeast-1.amazonaws.com/poc0_demo/pocket4d-poc0-demo.apk)

**Documents and designs**
[Pocket4D-Wiki](https://github.com/Pocket4D/Pocket4D-Wiki)




## Team members
* Wei Su (Michael So): Project Manager and iOS/Android/Flutter/Javascript developement
* Ian Tan: Front-end and Mini-Program Framework developement
* Lulu Ren: Blockchain and SmartContract developement
* Yaolong Cui: Product Manager
* Bruce Huang: Adviser and Business Development

The development will be mainly done by 2-3 full-time and one part-time engineer. The remaining people will provide necessary support to the development.

## Team Website	
* https://pocket4d.io (In progress)
* https://firestack.one
  

## Legal Structure 
SHANGHAI NIEPAN INFORMATION TECHNOLOGY CO., LTD., a startup company focusing on blockchain development in China.

## Team's experience

Team FireStack was founded in late 2018 focusing toolings for blockchain and smart-contract developers.

In 2018 to 2020, we've made several SDK tooling project for Zilliqa, Harmony. We also did solutions for DEXs, CEXs and DEFI projects.

We have different technical and bussiness background, some of them are working for famous Blockchain project, and some of them are in famous internet companies.

We love open-source project and the engineers all love commiting and helping others. The team mainly write C/C++, Javascript, Kotlin, Swift, Java, Rust, and Go. We are also familiar with Solidity and some other "SmartContract Script" languages

* Wei Su(Michael So): Founder and Lead Developer of Pocket4D.
* Ian Tan: Senior fullstack and blockchain developer, who is working in some famous internet company globaly, and former Zilliqa team member.
* Lulu Ren: Senior back-end and smart-contract engineer, who is working for Zilliqa
* Yaolong Cui(Ken Cui): Product manager, who is working for some famous fin-tech company in China.
* Bruce Huang: Founder and Adviser to FireStack, former CEO of Madalicai.com, former Director of Alibaba Cloud Computing.


## Team Code Repos

- Pocket4D: https://github.com/Pocket4D
- FireStack: https://github.com/FireStack-Lab


## Team LinkedIn Profiles
* Bruce Huang: https://www.linkedin.com/in/the-bruce-huang/

## Development Roadmap
https://github.com/Pocket4D/Pocket4D-Wiki

## Technical Design
https://github.com/Pocket4D/Pocket4D-Wiki/blob/master/technical-design.md

## Additional Information

* What work has been done so far?
  * A experimental JSEngine with QuickJS and DartLang 
  * A simple Mini-Program compiler
  * A simple Test Server hosting js/html/css bundle
* Are there are any teams who have already contributed (financially) to the project?
  * No.
* Have you applied for other grants so far?
  * No.
* Are there any other projects similar to yours?
  * No.
* How is your project different?
  * Open-source `Mini-Program` full stack solution 
  * Decentralized Storage for `Mini-Program` frontend bundle.
  * More design and updates are in [Pocket4D Wiki](https://github.com/Pocket4D/Pocket4D-Wiki)
