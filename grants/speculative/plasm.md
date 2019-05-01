# Plasm

## Project Description
Plasm is a Substrate Runtime Module Library which allows developers to add Plasma functions to their Substrate chain. Since we are making SRML, we can also make both plasma parent chains and plasma child chains with Substrate. [We have made some Plasma chains by using Plasm](https://www.youtube.com/watch?v=T70iEgyuXbw&feature=youtu.be). We aim to be a Plasma parachain once Polkadot is ready. You can see our slide deck from [here](https://docs.google.com/presentation/d/1c-O0Ch-m2vX4bo4KMO5KxrDQlyDqn3Kl36gjo--5A5k/edit#slide=id.p).

Today, there are many problems in this space like the scalability of a public blockchain, security of L2 and so on. Plasma is one of the ideal solutions for these problems public blockchain is facing. However, there are many derivative "Plasmas" and this makes developers difficult to understand how Plasma works. Plasm is a simple but versatile SRML and makes it easier for developers to make Plasma chain with Substrate. You can choose one of the plasma solutions from Plasm and apply it to your use case. This means Plasm allows you to use Plasma freely and easily. In the future, we would like to make a GUI developer tool to use Plasm. Our goal is to bring infinite scalability into the Polkadot ecosystem.

* Plasm has some features.
    * It deals with many types of "Plasmas". (Both UTXO based model and account-based model.)
    * We have already had some rust implementations. Check out our GitHub.
    * Developers can define original transaction logics by themselves.
    * Substrate chain can be both a parent chain and a child chain.
* Scalability is needed in the Polkadot ecosystem. Since Plasm is SRML with high versatility and expansibility, we are also making a Plasma paracahin. In addition, Plasm makes it easier even for other developers to make a Plasma chain.
* We believe that blockchain is the social infrastructure. As an operating system for the next generation, we think Plasma like hierarchical/layered specification which brings high social scalability is needed.

## Team members
* Sota Watanabe (CEO)
* Takumi Yamashita (CTO)

## Team Website	
* https://staked.co.jp/  （New web page is coming soon）

## Legal Structure 
Incorporated in Japan

## Team's experience
Staked Technologies is a blockchain company which aims to build digital economy where everyone belongs. 

* Sota is the CEO of the company. He also is a Polkadot ambassador in Tokyo. As an ambassador, he is hosting Polkadot and Substrate meetups at least once in a month and making Japanese document for developers. (e.g. Substrate Tutorials and [Polkadot whitepaper Japanese edition](https://github.com/stakedtechnologies/PolkadotWP)) In addition to that, he is a blockchain researcher at the University of Tokyo. He became the researcher at the age of 23, the youngest record. He used to work at Chronicled, a San Francisco based blockchain company which uses blockchain for supply chains. 

* Takumi is the CTO of the company. He was the world finalist of the ACM-ICPC International Collegiate Programming Contest 2016|2017 and he was selected one of the 21 best U25 engineers by an NPO which is supported by Japanese Government in 2018. In 2018, he has made his own blockchain platform called [Proskenion](https://proskenion.github.io/).


## Team Code Repos
* https://github.com/stakedtechnologies/Plasm

## Team LinkedIn Profiles
* https://www.linkedin.com/in/sota-watanabe-b962b3110/

## Development Roadmap
Listed some of our milestones below. In parallel with making our product, we will make the Japanese community as well.

- M1: Build the prototype modules including (5 weeks)
    - Plasm-Core
        - UTXO
        - Parent
        - Child
    - Plasm-Client
        - Operator
        - Wallet
- M2: Implement a plasma chain with Plasm and connect it to the Polkadot Testnet (1 week)
- M3: Support Plasma Cash (2 weeks)
- M4: Support [Plasm Chamber](https://github.com/cryptoeconomicslab/plasma-chamber) (1 week) 
- M5: Build a GUI developer tool (2 weeks)
- M6: Documentation

After successful implementation, we will research and implement ZK-SNARKs and 99% fault tolerant consensus algorithm on our plasma chain in parallel with making real use cases.

## Additional Information
* [Our demo video in English](https://www.youtube.com/watch?v=T70iEgyuXbw&feature=youtu.be)
* [Plasm without technical explanations](https://docs.google.com/presentation/d/1er_QAOuRk4h97FCq8Sjp5h4YNQSOsRbO4mtiuCgInhY/edit?usp=sharing)

### What work has been done so far?
* Plasm Rust implementations.
* UTXO Rust implementations.
* Plasm Demo.
* Presented Plasm at Sub0.

### Are there are any teams who have already contributed (financially) to the project?
We have accepted seed financing from a Japanese VC.

### Have you applied for other grants so far?
No

### Are there any other projects similar to yours?
[GunClear](https://github.com/w3f/Web3-collaboration/pull/83/files)

## How is your project different?
From our understanding, they are making Plasma bridge to Ethereum. We are making SRML(s) and try to make it easier for developers to use Plasma. We are similar in that we are both using Plasma, but the approach is completely different.