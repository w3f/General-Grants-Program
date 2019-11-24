# Flowchain by Laminar
Laminar is a DeFi protocol company providing open finance building blocks such as stable currency and margin trading protocols. Flowchain is one of the focusing R&D projects.

## Project Description
We are building a high throughput low cost specialized trading parachain for Polkadot using Laminar's Flow Protocol. We have been R&D our protocol on Ethereum, and ultimately we aim to bridge the on-and-off ramp trading experience with the scale and speed needed, hence we are extending our R&D to Polkadot and substrate. We already have high net worth customer base to tap into for our intended Ethereum mainnet launch, and we believe this will accelerate adoption and bring meaningful transactions to Polkadot and the DeFi industry in general.

Flowchain will include the following parts:
  * Flowchain parachain: with synthetic asset protocol as base building block, a DeX for traders, lenders and risk takers.
  * Flowchain SDKs: to empower developer community to build and integrate financial applications.
  * Flowchain financial service app: integrate with selected Polkadot wallet, to provide friendly experience for various user groups.

## Team members
* Ruitao Su (CEO）
* Bryan Chen (CTO)
* Bette Chen (COO, PM)
* Ermal Kaleci (Senior Software Engineer) 
* Antonia Chen (Chief Economist)
* Tony Yang (Chief Financial Advisor)

## Team Website
https://laminar.one

## Legal Structure
Private limited company.

## Team's experience
The team has extensive experience in blockchain development (substrate and Ethereum in particular) with complimentary expertise in product, full-stack dev, economics, financial markets, and partnership development.

* Ruitao has decades of successful software and app development experience (with awards from Apple, NZ HiTech, and others). In the past few years, as Centrality's CTO, he has successfully delivered decentralized token token generation platforms (https://tgeapp.com) raised over $300+ million worth of Ether, developed next-gen blockchain platform, built various smart contracts, protocols and first-of-its-kind dApps. He has also built various partnership including financial institutes to support Laminar's mission.

* Bryan (his github handle [xlc](https://github.com/xlc) should be very familiar to you) is a core contributor to substrate codebase, a Polkadot community ambassador, and substrate/polkadot lecturer at `YiKuaiLianXi`. He has extensive experience as a full-stack developer, and was previously blockchain architect at Centrality.ai leading charge of core blockchain and associated services development (https://github.com/cennznet). He graduated from University of Auckland with a Bachelor of Engineering specializing in Software.

* Bette has more than a decade product/program/project management experience (with various company awards) in software and high-tech industry. She was previously Product Manager at Centrality, led development of PoS public blockchain, various protocols including dex, identity & permission, asset management etc and built decentralized ecosystem (https://github.com/cennznet, https://cennznetdocs.com/, https://www.onfinality.io/). She graduated from University of Auckland with a Bachelor of Engineering specializing in Software, and an MBA from University of Otago and Duke Fuqua School of Business.

* Ermal is a talented app developer ([ermalkaleci](https://github.com/ermalkaleci)) who has worked on a number of featured and award winning mobile applications (e.g. [healthcare app](https://www.apple.com/healthcare/) and open source libraries (e.g. [CarbonKit](https://github.com/ermalkaleci/CarbonKit)). He has previously developed the [SingleSource](https://www.mysinglesource.io/) KYC identity app, blockchain wallet and signer app.

* Dr. Antonia Chen holds a PhD in Economics from University of Auckland. She has over a decade experience in tech startups, Microeconomics and Mathematical Social Science research field. She has previously designed a dual-token economic model for a public blockchain. She has presented her work in various international conferences. She advises the Laminar team anything economics and modeling.

* Tony is financial market veteran with 20+ year extensive experience as trading manager, dealer, and market maker. He was previously Chief Dealer of a multi-national financial institution, and has managed annual multi-billion dollar (in USD) investment portfolio. He advises the Laminar team anything finance and trading.

## Team Code Repos
* Protocol documentation and Ethereum reference implementation: https://github.com/laminar-protocol/flow-protocol-ethereum
* Protocol whitepapers: https://github.com/laminar-protocol/flow-protocol-whitepaper
* https://github.com/laminar-protocol/flowchain
* Oracle: https://hackmd.io/2JtsjvzAQqq5QqFox5lufg?view

## Team LinkedIn Profiles
* https://www.linkedin.com/in/ruitaosu/<Ruitao Su>
* https://www.linkedin.com/in/xiliang-chen-1ba8ba52/<Bryan Chen>
* https://www.linkedin.com/in/bette-chen/<Bette Chen>
* https://www.linkedin.com/in/ermal-kaleci-98445287/<Ermal Kaleci>
* Dr. Antonia Chen and Tony Yang have no LinkedIn profile

## Team Github Profiles
* Ruitao Su: https://github.com/rsu
* Bryan Chen:  https://github.com/xlc
* Bette Chen: https://github.com/bette7
* Erma Kaleci: https://github.com/ermalkaleci
* Antonia Chen: https://github.com/Antonia-Chen

## Development Roadmap
MVP Flowchain will be a 3 month project, with the following milestones

* M1: R&D protocol design and verification based on work has been done for Flow Protocol (2 weeks)
  - we will create and publish technical specification and runtime module design under our license plan (see below)

* M2: Implementation of runtime modules of synthetic asset (3 weeks)
  - we will implement the synthetic asset runtime modules with the following functions: 
    - implement fToken
    - synthetic asset module to deposit fund, mint fToken, withdraw, get bid/ask price
    - liquidity pool to get spread and get collateral ratio
    - oracle module for accessing external price feed, and allow operator to submit price feed
  - we will deliver a running chain with these modules, together with a docker image, and a tutorial using this protocol via the polkadot ui.
  - we will deploy multiple oracle servers to increase fault tolerance; we will also set up monitoring service to monitor oracle server status and price fluctuation
  - all runtime modules in this and following milestones will be shipped with unit tests

* M3: Implementation of margin trading modules and other features, UI Design & SDK (2 weeks)
  - we are finalizing the details of this part, but will include the following features:
    - create long and short for selected margin positions e.g. short 10 times EURUSD, close position and tracking profit / loss
    - liquidity pool to manage collateral
  - we will deliver a running chain with these modules, docker image to set a Flowchain node, a SDK library, and a tutorial using this protocol

* M4: Implement Flowchain financial service app (4 weeks)
  - we will implement the web app with the following feature: wallet connection, exchange prices for symbols, deposit, exchange fToken (e.g. fEUR), and a simple DeX that can long and short margin positions
  - we will deliver a working web application with these features, and a tutorial to use it

* M5: Integrate all parts, liquidity injection, dry run and documentation (2 weeks)
  - we will go live with the asset and margin trading platform with liquidity and providers on board.
  - we will provide an updated tutorial for participating as trader and liquidity provider, and tutorial for using the asset and trading SDK and the modules for developers to build on top of.

Assumptions:
- there is a stablecoin that we can use as building block for our protocol. While we have taken initiative with various parties in the polkadot community and in the financial world to explore stablecoin options, it in itself is a standalone project and is outside the scope of this particular grant application project.
- ideally there is a trustless Ethereum bridge that we can use to pipe value from our Ethereum contracts into the parachain for high speed trading. We also have discussions with various parties to explore options, and are willing to contribute, but it in itself again warrants a separate project and is outside the scope of this project.

## Additional Information
* Work has been done so far
1. We are drafting and verifying various aspects of the Flow Protocol, which will be the basis for the Flowchain.
2. We are implementing PoC on Ethereum.
3. We are already very experienced with substrate development, example previous substrate work (https://github.com/cennznet/cennznet, https://github.com/xlc/substrate-kitties).

* Are there are any teams who have already contributed (financially) to the project?  
All the work so far is funded by Laminar. We want to extend our R&D to Polkadot platform for reasons mentioned above, hence this grant application.

* Have you applied for other grants so far?  
No.

* Are there any other projects similar to yours? If so, how is your project different?  
Akropolis on Polkadot, but they focus on informal economy. On Ethereum, in the likes of Market Protocol (for derivative trading), DyDx (for margin trading), MakerDAO (as lending provider) etc.
Liquidity is a common challenge in this space. We believe we have a new approach to liquidity provision with new game theory and ability to bridge on-and-off ramp players. As for MakerDAO, they will be our partner on Ethereum, and we will provide complimentary services to it.

* Open Source License:
We will use Apache 2.0.
