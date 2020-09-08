# Zenlink

## Project Overview

Based on the prediction of the further growth of the DEX ecosystem in the future and the rapid development of the public blockchain technology, we propose a Polkadot network-based, high-liquidity, cross-chain DEX Network, Zenlink.
  
## Project Details

### System Components

In general, Zenlink project consists of the following parts:
- Zenlink DEX Protocol: The top-level unified general DEX protocol.
- Zenlink DEX Module: Polkadot Network Module implemented according to the Zenlink Protocol standard. We prefer to make it to have Auto Market Maker(AMM) function and be easy imported into parachain in multiple ways.
- Zenlink DEX Aggregator: A simple and user-friendly entrance of DEX world which is able to connect with most of DEX on Polkadot, so that user can do one-click trade with multiple DEX on low slippage
- Zenlink Token(ZLK): The native token of Zenlink DEX Protocol which can be used to distribute liquidity benefits and governance, etc
- Zenlink DEX Network: A decentralized exchange network composed of Zenlink DEX Module, Zenlink DEX Aggregator and other DEX Application on parachains.

![Zenlink Ecosystem](https://images-cdn.shimo.im/TrQlWEFKIz34Mv54__thumbnail.png)

### The whole planning of Zenlink

Firstly, Zenlink DEX Module will be implemented based on Zenlink DEX Protocol. In order to complete the Zenlink ecosystem, we would like to deploy it to a substrate blockchain and build a front-end website application, Zenlink DEX Dapp, for test.

Secondly, we would like to build another important component, Zenlink DEX Aggregator. It will connect to Zenlink DEX Dapp.

Thirdly, we will test the full function of Zenlink DEX Module and Aggregator on Kusama. Users also can try it on Zenlink DEX Dapp.

Finally, the whole infrastructure(Zenlink DEX Module and Aggregator) will be deployed to Polkadot, so that Zenlink DEX Dapp will be switched to Polkadot network and published.

![Zenlink Architecture](https://uploader.shimo.im/f/aCpI4JDF0fHIhpjw.png!thumbnail)

## What we will implement in this grant
We will only build prototypes of basic components in this grant because the whole project is too large to be implemented in only one grant.

In this grant, the functional prototypes, Zenlink DEX Module and Protocol, will be validated on a substrate chain. If it works, there will be only a small effect to migrate those components to the better test network, Kusama.

Besides, we will build a user interface website, Zenlink DEX Dapp, which would connect to the substrate chain and allow testers to try the basic function, such as creating trading pair, displaying price and swapping token etc.

The purpose of this grant is that verification function prototype and test user interface in lean way.

## Ecosystem Fit 
No.

## Team members
* Guo hui(Leo Guo), team leader
* Tianling, principal blockchain expert

## Team Website	
* https://zenlink.pro/

## Legal Structure 
The team has no legal entity now, however, we are planning to build a foundation in Singapore. 

## Team's experience
The team is made up of many experienced professionals in the blockchain industry.  

Guo hui(Leo Guo) is the project leader. He joined imToken very early (June 2017) and worked for 3 years as a data analyst and marketing operation specialist. He is very good at trading quotes and user data analysis which helps imToken get 10m users and Tokenlon, imToken’s DEX, achieve 600m trading volume as well.

Tianling was a former senior expert of Alibaba. After leaving it, he joined a blockchain company as the core developer for 3 years. He is familiar with the underlying blockchain design and substrate development and also was in charge of the architecture design. Now, he is the principal blockchain expert of Zenlink team.

Besides, two core team members are joining us. One of the potential candidates has rich experience in product design and management. He has built a nice and user-friendly DEX application. And the other one is a senior front-end dev with 5 years experience, and he will help us build the first DEX web application.

## Team Code Repos
* https://github.com/zenlinkpro

## Team LinkedIn Profiles
No

## Development Roadmap

### Milestone 1 — Implementing Zenlink DEX Module — 1 month — $8,000

Generally, we would like to verify the product prototype in a specific environment.
* Technical specifications and Zenlink DEX Module design.
* We will deliver Zenlink DEX Module on a substrate blockchain.
* It will has Automate Market Maker(AMM) function.

| Deliverable  | Specification  | 
|--------------|---------------|
| Zenlink DEX Module Repository | A git repository containing the dex module source code and a README that describes the work done during this milestone and how to use set up and run at the current stage |
| Tests        | The code will have proper unit-test coverage to ensure functionality and robustness                                                                    | 
| Docker       | Docker image with a Substrate chain using our module, demonstrating its functionality                                                                  | 

### Milestone 2 — Implementing Zenlink DEX Dapp — 1 month — $10,000
Generally, we would like to build an user interface to test and verify the user experience and dex functionality in a specific environment.
* We will implement Zenlink DEX DApp production prototype and ui design.
* We will deliver a DEX Dapp, Zenlink DEX Dapp.
* It will be connect with the above substrate blockchain.
* Testers will be able to try the basic function, such as creating trading pair, displaying price and swapping token etc.

| Deliverable  | Specification | 
|--------------|---------------|
| Zenlink DEX Module Repository | A git repository containing **the dex module** source code and a README that describes the work done during this milestone and how to use set up and run at the current stage |
| Zenlink DEX Dapp Repository | A git repository containing **the dex dapp** source code and a README that describes the work done during this milestone and how to use set up and run at the current stage |
| Tests        | The code will have proper unit-test coverage to ensure functionality of the trading business and robustness                                             | 
| Docker       | Docker image with a Substrate chain using our module and dapp which can demonstrate functionality via web browser at a local machine              | 

## Future Plans
* Migrate the above basic components to Kusama for test
* Build & deploy Zenlink DEX Aggregator on Kusama. 
* Full function test on Kusama.
* Deploy the whole components to Polkadot including Zenlink DEX Module, DEX Dapp and DEX Aggregator.

## Additional Information
* Medium: https://medium.com/zenlinkpro
* Twitter: https://twitter.com/ZenlinkPro
* Whitepaper: https://github.com/zenlinkpro/whitepaper/blob/master/en/zenlink_whitepaper_en.pdf
