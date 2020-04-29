## Project Description

Plasm Network is a scalable DApps platform on Polkadot. Originally Plasm is a set of Plasma Substrate Runtime Module Libraries that allows developers to add Plasma functions to their Substrate chain. We have published our white paper draft1. You can find further information from [here](https://github.com/stakedtechnologies/plasmdocs/blob/master/wp/en.pdf).

Since we are making modules, we can also make a parachain by importing these modules. We aim to be one of the firstest scalable parachains once Polkadot is successflly launched. We believe that a scalable general DApps platform is needed because Polkadot relaychain does not support smart contracts. So what's new on Plasm network?  

With this grant, we keep developing Plasm and we plan to implement OVM, optimistic virtual machine on Plasm network. OVM is a virtual machine that is designed to support all layer2 protocols. The most important thing is that OVM can be a unification of all layer2 solutions. This means Plasm will be not only for Plasma but also for **other layer2 scaling solutions** such as **Lightning Network** and **Raiden Network** (State Channel). We try to implement all layer2 solutions on Polkadot. The potential is huge simply because Plasm network can handle many use cases like DeFi, gaming, and IoT with OVM. 

You can find more info about OVM from [here](https://medium.com/staked-technologies/the-scalable-dapps-platform-on-polkadot-b31fbe1b786b) and [here](https://medium.com/plasma-group/introducing-the-ovm-db253287af50).

## Team Members

Joint team between Stake Technologies and Cryptoeconomics Lab

* **Sota Watanabe:** Sota is the CEO of Stake Technologies. He is a youngest blockchain researcher at the university of Tokyo and a Polkadot official ambassador in Tokyo. He previously worked at Chronicled, a blockchain startup in San Francisco.
* **Takumi Yamashita:** Takumi is the CTO of Stake technologies. He was the world finalist of the ACM-ICPC International Collegiate Programming Contest 2016|2017 and he was selected one of the top 16 best U25 engineers by an NPO which is supported by Japanese Government in 2018.
* **Task Ohmori:** Task is the lead engineer at Stake Technologies. He is a silver medalist of the international physics olympics in 2012 and 2013. Master at the university of Tokyo. 
* **Shuhei Hiya:** While he was studying computer science at university, Shuhei won MITOU Super Creator Award from Japanese Ministry of Economy Trade and Industry.  Shuhei then founded a startup that develops Backend as a Service for IoT companies after graduating university. After transferring the ownership of the service to other IoT startup, he joined Cryptoeconomics Lab(CEL) with his interest on distributed systems in 2018.  Now he researches fraud proof systems and off-chain scaling solutions for public blockchains and develops an L2 application framework at CEL’s R&D teams as its Chief Scientist.

## Team Website

* https://staked.co.jp/ 
* https://www.cryptoeconomicslab.com/

## Legal Structure

Incorporated in Japan

## Team's experience

* **Stake Technologies:**
    * Stake Technologies is a company which realizes the vision of Web3.0. Stake focuses on Polkadot and making a scalable DApps platform called Plasm Network. In addition to that, we try to develop a security audit tool for Substrate developments. 

* **Cryptoeconomics Lab:**
    * Cryptoeconomics Lab develops a general-purpose L2 application framework based on their research on fraud proof systems and runs PoC projects using offchain scaling solutions to create real use cases of public blockchains. CEL’s Ethereum Foundation Grant-backed research team has its distinctiveness and strongness on to their ability to constantly produce tangible outcomes in development. Now their framework is more generalized with an all fraud-proof systems’ shared language on Layer2 called OVM (Optimistic Virtual Machine). Including their next expected deliverable developer tools in the framework, it will allow individual Dapps developers to build their own application more flexibly and easily without sacrificing security. In cooperation with various business-domain experts, such as Chubu Electric Power and IoT platform company, CEL’s adoption team creates application use cases of public blockchains, putting the R&D team’s research outcomes into practice.

## Team Code Repos

* https://github.com/stakedtechnologies/Plasm
* https://github.com/cryptoeconomicslab/plasma-rust-framework/

## Team LinkedIn Profiles

* https://www.linkedin.com/in/sota-watanabe-b962b3110/

## Development Roadmap

Plasm Development + OVM implementation

* **M1: Plasm Operator Trading**
    * Implementing the logics of Plasm operator trading.
    * Plasm Operator trading is an SRML.
    * Making a UI demo by using Polkadot JS.
    * Basic documentation to explain how to obtain and test the software.
    * Delivering the software inside a Docker container.
* **M2: OVM Specification**
    * OVM is proposed by Plasma Group and its contract and client are still under the development. So we will keep contributing to make general design and implementation of OVM and especially in this grant, we make a specification for Substrate & Polkadot.
    * Making a documentation about how to implement OVM on Plasm Network.
* **M3: DApps Reward Mechanism**
    * Implementing the logics of Plasm DApps reward mechanism.
    * We will make a SRML so that other projects can reuse this mechanism.
    * Make a demo.
    * Basic documentation to explain how to obtain and test the software.
    * Delivering the software inside a Docker container.
* **Milestone 4: Lockdrop Module**
    * Implementing Lockdrop modules (for Substrate) so that everyone can use Lockdrop.
    * This is ETH lockdrop contract and BTC lockdrop contract (script).
    * Basic documentation to explain how to obtain and test the software.
    * Delivering the software inside a Docker container.
* **Milestone 5: OVM Plasma contract**
    * Designing minimal OVM Plasma contracts written in ink!.
    * Designing a shared commitment and deposit contract.
    * Designing and implementing Universal Adjudication Contract and dispute resolution logic for Substrate contracts.
    * Implementing basic predicates (a little piece of smart contracts that function as either an atomic proposition or logical operator) to construct a smart contract that resolves L2 disputes for Substrate
    * Combining the basic predicates, we will add a necessary set of predicates for Plasma and offline atomic swap.
    * Basic documentation to explain how to obtain and test the software.
    * Delivering the software inside a Docker container.
* **Milestone 6: Substrate adapter of Plasma child chain**
    * Designing L1 adapter for Substrate from plasma childchain.
    * Implementing L1 adapter for Substrate from plasma childchain.
    * Basic documentation to explain how to obtain and test the software.
    * Delivering the software inside a Docker container.
* **Milestone 7: Documentation and Optimization**
    * Writing a document for smart contract development on Plasm
    * Adding a code generator for Substrate to the OVM compiler, which enables optimized claim size and dispute cost (TBD)
    * Make a demo and a tutorial in English and in Japanese.

#### What is Plasm operator trading?

Operator trading is a mechanism to buy and sell the right to be a Plasma operator. Since the right is tradable, this is similer to M&A. A plasma operator gets constant basic income by creating Plapps owning to Plasm treasury. If the Plapp is meaningful for the community, the creator receives higher revenue. As a result, other players may want the right to operate the Plapp. The successor will receive the reward instead of a previous operator. The important thing is that the buyer does not need to take over the operation itself though the buyer has ownership. Through this mechanim, we assume that the new off-chain market will be created. 

## Additional Information

### What work has been done so far?

We have been developing Plasm Network and launched the first testnet and published [the white paper](https://github.com/stakedtechnologies/plasmdocs/blob/master/wp/en.pdf). In terms of Plasma, the minimum viable product is ready. We will implement OVM and will be ready for Lightning Network.

### Are there are any teams who have already contributed (financially) to the project?

* No

### Have you applied for other grants so far?

* Yes. We have applied Plasm in the wave2 and finished all milestones. This is a continuous application.

### Are there any other projects similar to yours?

* I think NO. Please let us know if there are any.

## How is your project different?

NA