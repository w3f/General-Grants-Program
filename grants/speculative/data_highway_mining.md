# Project name

DataHighway Mining

## Abstract

DataHighway Mining will involve participation through either token mining or IoT hardware mining initially. Token mining rewards the user with a Mining Speed Boost (MSB) to incentivize participants to hold and lock certain tokens for a period of time, whereas hardware mining rewards them with a MSB to incentivize owners of certain hardware to maintain its uptime over a period of time. The MSB is a multiplier that is determined through sampling their eligibility with oracle services. Users that are eligible for a MSB must claim it in order for it to increase the staking rewards that they may receive as a result of them participating as a Proof of Stake (PoS) validator or nominator on the DataHighway.

## Project Description

### A brief description of the project.

DataHighway Mining will involve token mining and hardware mining initially. DataHighway token mining involves a holder of certain tokens such as MXC (Ethereum ERC-20 token), IOTA or DOT tokens to configure a time period to lock some of their tokens in a smart contract or to just hold that quantity in an account. This information is recorded in the DataHighway token mining configuration runtime module. Users are also incentivized to share access to their LPWAN hardware on the DataHighway by configuring a time period throughout which they are willing to ensure its uptime will be maintained.

A DataHighway token mining oracle service is used to take samples of how many tokens are in that account or locked in the smart contract at random times over the defined time period, and the results are recorded on the DataHighway token mining sampling runtime module. Likewise there will be a DataHighway hardware mining oracle service that will take samples of whether a users' configured hardware is online at random times over the defined time period. The samples will be recorded on the DataHighway hardware mining sampling runtime module.

After the end of the the time period the DataHighway's token mining eligibility runtime module uses the DataHighway's token mining rates runtime module to calculate a Mining Speed Boost (MSB) that the holder of those tokens may claim (i.e. 1.2x). Likewise, the DataHighway's hardware mining eligibility runtime module uses the DataHighway's hardware mining rates runtime module to calculate a mining speed boost that the owner of the shared LPWAN hardware may claim (i.e. 1.2x).

After user's claim their eligibility using the DataHighway's token/hardware mining claims runtime module, that MSB will be applied to that user's staking rewards, which result from them participating in the DataHighway as a Proof of Stake (PoS) validator or nominator to secure the parachain.

### An indication of why this project is good for the ecosystem.

DataHighway Mining has been architected across multiple runtime modules to maintain a separation of concerns to improve developability and ease on-chain upgrades through DAO governance.

DataHighway Mining is an inclusive approach that will realize a broadened inter-chain outreach by incentivizing different communities to diversify their means of participation and encourage investment from new participants. It will also incentivize usage of LPWAN secure hardware.

### An indication of how you will integrate this project into Substrate / Polkadot.

DataHighway Mining is a Substrate-based chain that will become a parachain using Cumulus.

### An indication of why your team is interested in creating this project.

DataHighway Mining will incentivize new and diversified channels of investment and inter-chain participation, which is crucial to grow the IoT community of the Polkadot ecosystem.

## Team members

* Xin (Sheen) Hu (DataHighway Mining Lead）
* Aaron Wagener (DataHighway Mining Business Development)
* Siwon Kim (DataHighway Mining Business Development)
* Piotr Świątek Brzeziński (DataHighway Mining Hardware)
* Jakub Chmielarz (DataHighway Hardware)
* Stéphane Letz (DataHighway Mining Marketing)
* Jeff Stahlnecker (DataHighway Mining Project Manager)
* Luke Schoen (DataHighway Mining Blockchain Developer)
* Shiun Chen (DataHighway Mining Blockchain Developer)
* Suhee Lee (DataHighway Mining UX)
* Namgyeong Cho (DataHighway Mining Frontend Developer)
* Christian Groeschel (DataHighway Mining DevOps)
* Lixuan Jia (DataHighway Mining QA)
* Stefan Bachmann (DataHighway Mining QA)
* Aslan Mehrabi (DataHighway Data Scientist)
* Gal Rogozinski (DataHighway Blockchain Developer)
* Alon Elmaliah (DataHighway Blockchain Developer)

## Team Website

* Website http://datahighway.com/

## Legal Structure

Name: DataHighway
Address: DAO on the Polkadot Network

## Team's experience

Please describe the team's relevant experience.  If the project involves development work, then single out a few interesting code commits made by team members on their past projects.

Possible information to include
* Details of the team's experience in community enagagement
* Details of the team's experience community engagement related to Polkadot and/or Substrate

### A list of blockchain projects that the team has supported and the details of such support

The team have collaborated together to start making the DataHighway a reality.

Xin (Sheen) Hu, Aaron Wagener, and Piotr Świątek Brzeziński are from the MXC Foundation gGmbH's and MatchX's Executive Team. They have created the vision of the DataHighway.

Siwon Kim and Jeff Stahlnecker are experts in community engagement and power MXC's Blog https://blog.mxc.org/ and Telegram community of over 5,000 users.

Xin Hu, Piotr Świątek Brzeziński, and Jakub Chmielarz are building revolutionary secure IoT hardware and AI solutions. DataHighway Mining will incentivize use of such hardware or similar equivalent.  

Stéphane Letz and Suhee Lee provide graphic designs and videography that captivates the community and to support the business development and marketing teams.   

Aslan Mehrabi, Lixuan Jia, and Shiun Chen are proficient in GoLang, and have designed the MXProtocol and built the back-end of the MXC's LPWAN App Server. Github https://github.com/mxc-foundation/lpwan-app-server.

Namgyeong Cho is proficient in React and has built the front-end of MXC's LPWAN App Server.

Luke Schoen is proficient in React, and has experience in Rust. He uses Github handle [ltfschoen](https://github.com/ltfschoen) and has recently contributed to the following:
* Edgeware testnet validator. He built a validator guide https://github.com/ltfschoen/edgeware-node

He previously worked at Parity primarily on the following open-source projects:
* Polkadot.js. Example PR https://github.com/polkadot-js/apps/pull/336
* Parity Fether. Example PR https://github.com/paritytech/fether/pull/332
* Parity Ethereum. Example PR https://github.com/paritytech/parity-ethereum/pull/10657

Prior to that he was a full-stack Ethereum DApp developer on open-source projects such as:
* Peerism, where he published a commuity Truffle Box https://www.trufflesuite.com/boxes/peerai-api

He has leveraged his prior experience at Parity and support from the Substrate Builders Program to build the DataHighway's Substrate-based node so far.

With support from the rest of the team he was able to produce the DataHighway whitepaper https://github.com/DataHighway-DHX, which includes DataHighway Mining.

Christian Groeschel is a DevOps expert. He is using Kubernetes to build a Continuous Integration (CI) pipeline for testing and deploying DataHighway parachain builds using Docker. He is also creating monitoring tools. 

Lixuan Jia is a QA expert who is supported by Stefan Bachmann to oversee the DataHighway.

Gal Rogozinski [(GalRogozinski)](https://github.com/GalRogozinski) and Alon Elmaliah [(alon-e)](https://github.com/alon-e)are leaders from IOTA who are proficient across cryptography and will be sought upon to achieve the inter-chain mining objectives, as necessary.

### Key geographies that the team operates in

* Germany, Korea, China (MXC)
* Israel (IOTA)

## Team Code Repos

DataHighway repositories:

* DataHighway Substrate-based Blockchain Node
  * Github: https://github.com/DataHighway-DHX/node
* DataHighway Documentation & Whitepaper
  * Gitub: https://github.com/DataHighway-DHX/documentation
  * Website: https://dev.datahighway.com/
* DataHighway Website
  * Github: https://github.com/DataHighway-DHX/website
  * Website: http://datahighway.com/
* DataHighway API
  * https://github.com/DataHighway-DHX/api

## Team Twitter Account

* https://twitter.com/DataHighway_DHX

## Team LinkedIn Profiles

* Xin Hu [LinkedIn](https://www.linkedin.com/in/sheenhu/)
* Aaron Wagener [LinkedIn](https://www.linkedin.com/in/aaron-wagener-0424821/)
* Siwon Kim [LinkedIn](https://www.linkedin.com/in/siwonkim/)
* Piotr Świątek Brzeziński [LinkedIn](https://www.linkedin.com/in/piotr-swiatek-brzezinski/)
* Stéphane Letz [LinkedIn](https://www.linkedin.com/in/st%C3%A9phane-letz-12711292/)
* Jeff Stahlnecker [LinkedIn]((https://www.linkedin.com/in/jstahlnecker/)
* Luke Schoen [Linkedin](https://www.linkedin.com/in/ltfschoen/)
* Shiun Chen [Linkedin](https://www.linkedin.com/in/shiun-chen-3a8006129/)
* Suhee Lee [Linkedin](https://www.linkedin.com/in/suhee-lee-05b57153/)
* Namgyeong Cho [Linkedin](https://www.linkedin.com/in/namgyeong-cho-4160b4191/)
* Christian Groeschel [Linkedin](https://www.linkedin.com/in/christiangroeschel/)
* Lixuan Jia [Linkedin](https://www.linkedin.com/in/lixuan-jia-developer/)
* Stefan Bachmann [Linkedin](https://www.linkedin.com/in/stefan-bachmann-245291190/)
* Aslan Mehrabi [Linkedin](https://www.linkedin.com/in/aslan-mehrabi/)
* Gal Rogozinski [Linkedin](https://www.linkedin.com/in/gal-rogozinski-72993977/)
* Alon Elmaliah [Linkedin](https://www.linkedin.com/in/alon-elmaliah/)

## Intended Languages and Technologies of Development
Rust, Go, React, Kubernetes, Docker

## Development Roadmap

MVP of the DataHighway Mining will be a 4 month project with the following milestones:

### Milestone 1: Phase 1 (Preliminary Design, Implementation, and Documentation)

* Design
  * Concept Design & Review and update whitepaper (technical specification of protocol and runtime design) under a Creative Commons license plan
  * Preliminary Design & Review of Substrate runtime modules and update whitepaper.
  * Preliminary Design & Review of DataHighway Mining App UI based on SpeckleOS
* Implementation & Testing
  * Preliminary Implementation of Substrate-based chain published on Github (open-source), with separate token-specific and hardware-specific runtime modules and associated oracle services. All runtime modules shall be shipped with unit and integration tests.
    * Runtime modules
      * Configuration runtime modules. To define the period of lock time and associated asset to mine (i.e. token asset holding to remain available or hardware assets to remain online over a specific period of time)
      * Rates runtime modules. To define the maximum rate multiplier that may be claimed, which varies based on outcomes of sampling and calculation of their eligibility 
      * Sampling runtime modules. To access external data fed by oracle services that take samples of the amount of tokens locked or whether the hardware is online at random times during the configured period of lock time.
      * Eligibility runtime modules
      * Claims runtime modules
      * Asset runtime module. To mint, distribute, and transfer Testnet DHX tokens
    * Oracle services. Initial MVP oracle server shall be deployed.
* Documentation
  * Preliminary Documentation website including:
    * API reference
    * Tutorial for interaction using the Polkadot.js UI
      * Token mining
* Deployment
  * Compatibility with most recent stable commit from the Substrate repository
  * Running chain containing all the above modules
  * Releases shall be tagged and include a Docker image
  * Licensing shall be open-source using GNU GPL v3 for consistency with Substrate (or Apache 2.0 if required)
* Target date: February 2020
* Duration: 4 weeks
* Full-Time Employees: Luke Schoen
* Funding: 20,000 USD equivalent in DOT tokens

### Milestone 2: Phase 2 (Detailed Design, Implementation, Documentation, and Testnet)

* Design
  * Detailed Design & Review of Substrate runtime modules and update whitepaper.
  * Detailed Design & Review of DataHighway Mining App UI
  * Preliminary Design to Integrate the DataHighway Mining App UI into MXC's LPWAN App Server (Go-based application https://github.com/mxc-foundation/lpwan-app-server) using the Go Substrate RPC client.

* Implementation & Testing
  * Detailed Implementation implementation of Substrate-based chain
      * Oracle services. Multiple oracle servers shall be deployed to increase the fault tolerance.
      * Monitoring services. To monitor the oracle server status health and audit data that they feed to the runtime modules.
* Documentation
  * Detailed Documentation website including:
    * SDK reference
    * Tutorial for interaction using the Polkadot.js UI
      * Hardware mining
* Deployment
  * Compatibility with most recent stable commit from the Substrate repository
  * Running chain containing all the above modules
  * Releases shall be tagged and include a Docker image
  * Testnet using PoA collators
* Target date: March 2020
* Duration: 4 weeks
* Full-Time Employees: Luke Schoen
* Funding: 20,000 USD equivalent in DOT tokens

### Milestone 3: Phase 3 (Testnet)

* Design
  * Final Design & Review of Substrate runtime modules and update whitepaper.
  * Final Design & Review of DataHighway Mining App UI
  * Final Design to Integrate the DataHighway Mining App UI into MXC's LPWAN App Server (Go-based application https://github.com/mxc-foundation/lpwan-app-server) using the Go Substrate RPC client.
* Implementation & Testing
  * Preliminary Implementation of DataHighway Mining App UI
  * Final Implementation & Review of Substrate-based chain
* Documentation
  * Final Documentation & Review
* Deployment
  * Compatibility with most recent stable commit from the Substrate repository
  * Running chain containing all the above modules
  * Releases shall be tagged and include a Docker image
  * Testnet using NPoS collators
  * Listing on Polkascan https://polkascan.io
* Target date: April 2020
* Duration: 4 weeks
* Full-Time Employees: Luke Schoen
* Funding: 20,000 USD equivalent in DOT tokens

### Milestone 4: Phase 4 (Testnet)

* Design
  * Integration Design & Review of Substrate runtime modules and update whitepaper.
* Implementation & Testing
  * Detailed Implementation of DataHighway Mining App UI
  * Final Implementation & Review of Substrate-based chain
  * Preliminary Implementation to Integrate the DataHighway Mining App UI into MXC's LPWAN App Server (Go-based application https://github.com/mxc-foundation/lpwan-app-server) using the Go Substrate RPC client.
* Documentation
  * Final Documentation website & Review
* Deployment
  * Compatibility with most recent stable commit from the Substrate repository
  * Running chain containing all the above modules
  * Releases shall be tagged and include a Docker image
  * Testnet using NPoS collators ported to Polkadot network Parachain using Substrate's Cumulus Framework or the Parachain Development Kit (PDK)
  * Parachain Slot Auction on Polkadot Testnet
* Assumption: Polkadot Mainnet Launch in April 2020
* Target date: May 2020
* Duration: 4 weeks
* Full-Time Employees: Luke Schoen
* Funding: 20,000 USD equivalent in DOT tokens

### Milestone 5: Phase 5 (Mainnet)

* Implementation & Testing
  * Mainnet on Polkadot network Parachain including on-chain upgrades (if any)
  * Final Implementation of DataHighway Mining App UI
  * Final Implementation to Integrate the DataHighway Mining App UI into MXC's LPWAN App Server (Go-based application https://github.com/mxc-foundation/lpwan-app-server) using the Go Substrate RPC client.
* Documentation
  * Incorporate Final Review Comments into Documentation website
* Deployment
  * Compatibility with most recent stable commit from the Substrate repository
  * Running chain containing all the above modules
  * Releases shall be tagged and include a Docker image
  * Testnet using NPoS collators
* Target date: June 2020
* Duration: 4 weeks
* Full-Time Employees: Luke Schoen
* Funding: 20,000 USD equivalent in DOT tokens

## Funds Required Overall

100,000 USD equivalent in DOT tokens

## Future Plans

The DataHighway future plans include preparation of the following specifications and deliverables:

* DataHighway Mining (Whitepaper, Testnet, Mainnet)
* DataHighway Inter-Chain Data Market (Whitepaper, Testnet, Mainnet)
* DataHighway Roaming (Whitepaper, Testnet, Mainnet)
* DataHighway DAO (Whitepaper, Testnet, Mainnet)

## Additional Information

### Funding

### Releases

* Releases shall be tagged and include a Docker image
* Licensing shall be open-source using Apache 2.0 (or as otherwise preferred)

### What work has been done so far?

* DataHighway Mining Whitepaper (Final draft)
* DataHighway Mining Runtime Modules (configuration, rates, samples, eligibility, claims)
* DataHighway Mining Documentation and API
* DataHighway Mining Website
* DataHighway Mining Oracle (MXC ERC-20 tokens)
* DataHighway Mining Inter-Chain Bridge Contract (MXC ERC-20 tokens)

### Are there are any teams who have already contributed (financially) to the project?

MXC Foundation gGmbH is a non-profit that has financed part of milestones M1 and part of M2. However we wish to use funding from a grant application to proceed with subsequent milestones and integrate into the Polkadot platform as a parachain.

### Have you applied for other grants so far?

No

### Are there any other projects similar to yours? If so, how is your project different?  

Similar projects:
* Edgeware's lock-drop
* ChainX's inter-chain asset mining

DataHighway will be an IoT parachain on the Polkadot network 
