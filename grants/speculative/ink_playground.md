# ink! playground

## Project Description

ink! playground is the browser IDE for Substrate's smart contract(srml-contract). This will be similar to [Remix](https://github.com/ethereum/remix), the smart contract IDE of Ethereum.
Currently, if developers want to run ink! smart contract, they have to install substrate and ink into local environment. But this takes many steps, and also it is not easy to run stably because of version compatibility issues or so.
By using ink! playground, Substrate developers can test contracts easily just by writing main code ("lib.rs") on browser.
It doesn't require installing Substrate or running Substrate node. This is very useful for Substrate smart contract developers.
For the future works, ink! playground also provides high level security audits. This is for developer who wants to make high secured smart contracts like for enterprise use.

Overview of the technical specification idea is as follows:
* We put ink! compiler and abi generator on AWS EC2. User send ink! code to server, and then get compiled wasm code and abi.
* We implement test environment for wasm(compiled from ink!) on frontend using javascript. User can test deploying and running wasm code without running substrate node. (instead of this spec, test environment might be run on server)

## Team members
* Task Ohmori
* Takumi Yamashita
* Sota Watanabe

## Team Website
* https://stake.co.jp

## Legal Structure
Incorporated in Japan

## Team's experience
Stake Technologies is a blockchain company which aims to build digital economy where everyone belongs.

* Task is the lead engineer of the company. He was the silver medalist in International Physics Olympiad 2012|2013. He is now a researcher of acoustic engineering at the University of Tokyo.

* Takumi is the CTO of the company. He was the world finalist of the ACM-ICPC International Collegiate Programming Contest 2016|2017 and he was selected one of the 21 best U25 engineers by an NPO which is supported by Japanese Government in 2018. In 2018, he has made his own blockchain platform called [Proskenion](https://proskenion.github.io/).

* Sota is the CEO of the company. He also is a Polkadot ambassador in Tokyo. As an ambassador, he is hosting Polkadot and Substrate meetups at least once in a month and making Japanese document for developers. (e.g. Substrate Tutorials and [Polkadot whitepaper Japanese edition](https://github.com/stakedtechnologies/PolkadotWP)) In addition to that, he is a blockchain researcher at the University of Tokyo. He became the researcher at the age of 23, the youngest record. He used to work at Chronicled, a San Francisco based blockchain company which uses blockchain for supply chains.


## Team Code Repos
* https://github.com/stakedtechnologies/ink-playground

## Team LinkedIn Profiles
* https://www.linkedin.com/in/task-ohmori-604398176/
* https://www.linkedin.com/in/sota-watanabe-b962b3110/
## Development Roadmap

Each milestones represent the feature goals of ink! playground. These also includes UI goals.

- M1: Compike ink! into wasm on AWS stably (3 weeks).
- M2: Run wasm on test environment (3 weeks).
- M3: Choose version of ink! compiler (1 weeks).
- M4: Enable to deploy to the Testnet of Substrate (2 weeks).

## Additional Information.

### Are there are any teams who have already contributed (financially) to the project?
We have accepted seed financing from a Japanese VC.

### Have you applied for other grants so far?
Yes:
* [Plasm](https://github.com/stakedtechnologies/Plasm)

### Are there any other projects similar to yours?
[Remix](https://github.com/ethereum/remix)
[Polkadot-js](https://github.com/polkadot-js/apps)

## How is your project different?
* Remix is a browser IDE for Solidity, the smart contract of Ethereum. This is very useful for solidity developers who want to test contract easily. But, there is still no such useful browser IDE for Substrate contract, so we are making ink! playground which is useful for substrate developers who want to test ink! contracts.
As a technical talk, remix compile solidity using javascript. But ink! playground compike ink! into wasm using original ink projects (https://github.com/paritytech/ink).

* Polkadot-js is a UI for operating substrate node or contract.
Polkadot-js itself doesn't compile the ink! code into wasm, but just uses already compiled wasm code and run that code on substrate node.
On the other hand, ink! playground is going to compile ink! into wasm (on AWS server). Also, we implement test environment for running wasm (without running Substrate node).
