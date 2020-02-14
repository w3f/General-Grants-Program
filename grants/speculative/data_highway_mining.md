# Project name

Data Highway Mining

## Project Description

### A brief description of the project.

Usage of Data Highway token mining involves a holder of certain tokens such as ERC-20 MXC, IOTA or DOT tokens to configure a time period to lock some of their tokens in a smart contract or to just hold that quantity in an account, and this is recorded in the Data Highway token mining configuration runtime module. Users are also incentivized to share usage of their LPWAN hardware on the Data Highway by configuring a time period throughout which they can ensure its uptime will be maintained.

A Data Highway token mining oracle service is used to take samples of how many tokens are in that account or locked in the smart contract at random times over the defined time period, and the results are recorded on the Data Highway token mining sampling runtime module. Likewise there will be a Data Highway hardware mining oracle service that will take samples of whether a users configured hardware is online at randome times over the defined time period, and record the results on the Data Highway hardware mining runtime module.

After the end of the the time period the Data Highway's token mining eligibility runtime module uses the Data Highway's token mining rates runtime module to calculate a mining speed boost that the holder of those tokens may claim (i.e. 1.2x), and the Data Highway's hardware mining eligibility runtime module uses the Data Highway's hardware mining rates runtime module to calculate a mining speed boost that the owner of the shared LPWAN hardware may claim (i.e. 1.2x).

After user's claim their eligibility using the Data Highway's token/hardware mining claims runtime module respectively, that mining speed boost will be applied to that users staking rewards that result from them participating in the Data Highway as a validator or nominator to secure the parachain.

### An indication of why this project is good for the ecosystem.

Data Highway Mining has been architected across multiple runtime modules to maintain a separation of concerns to improve developability and ease on-chain upgrades through DAO governance.

Data Highway Mining is an inclusive approach that will realize a broadened inter-chain outreach by incentivizing different communities to diversify their means of participation and encourage investment from new participants. It will also incentivize usage of LPWAN secure hardware.

### An indication of how you will integrate this project into Substrate / Polkadot.

Data Highway Mining is a Substrate-based chain that will become a parachain using Cumulus.

### An indication of why your team is interested in creating this project.

Data Highway Mining will incentivize new and diversified channels of investment and inter-chain participation, which is crucial to grow the IoT community of the Polkadot ecosystem.

## Team members

* Xin Hu (Data Highway Mining Lead）
* Aaron Waegener (Data Highway Mining Business Development)
* Siwon Kim (Data Highway Mining Business Development)
* Piotr Świątek Brzeziński (Data Highway Mining Hardware)
* Stéphane Letz (Data Highway Mining Marketing)
* Jeff Stahlnecker (Data Highway Mining Project Manager)
* Luke Schoen (Data Highway Mining Blockchain Developer)
* Shiun Chen (Data Highway Mining Blockchain Developer)
* Gal Rogozinski (Data Highway Blockchain Developer)
* Alon Elmaliah (Data Highway Blockchain Developer)
* Suhee Lee (Data Highway Mining UX)
* Namgyeong Cho (Data Highway Mining Frontend Developer)
* Christian Groeschel (Data Highway Mining DevOps)
* Lixuan Jia (Data Highway Mining QA)
* Stefan Bachmann (Data Highway Mining QA)
* Aslan Mehrabi (Data Highway Data Scientist)

## Team Website

* http://datahighway.com/

## Legal Structure

Name: Data Highway
Address: DAO on the Polkadot Network

## Team's experience

Please describe the team's relevant experience.  If the project involves development work, then single out a few interesting code commits made by team members on their past projects.

* Luke Schoen
  * Github handle [ltfschoen](https://github.com/ltfschoen)
  * Recently he has contributed to the following:
    * Data Highway development. He built the node and wrote the whitepaper https://github.com/DataHighway-com
    * Edgeware testnet validator. He built a validator guide https://github.com/ltfschoen/edgeware-node
  * Previously he worked at Parity primarily on the following open-source projects:
    * Polkadot.js. Example PR https://github.com/polkadot-js/apps/pull/336
    * Parity Fether. Example PR https://github.com/paritytech/fether/pull/332
    * Parity Ethereum. Example PR https://github.com/paritytech/parity-ethereum/pull/10657
  * Prior to that he was a full-stack Ethereum DApp developer.
    * Peerism. Published a commuity Truffle Box https://www.trufflesuite.com/boxes/peerai-api

* Gal Rogozinski
  * Github handle [GalRogozinski](https://github.com/GalRogozinski)

* Alon Elmaliah
  * Github handle [alon-e](https://github.com/alon-e)

## Team Code Repos
* https://github.com/DataHighway-com/node
* https://github.com/DataHighway-com/documentation
* https://github.com/DataHighway-com/api
* https://github.com/DataHighway-com/mining
* https://github.com/DataHighway-com/website
* https://github.com/DataHighway-com/whitepaper

## Team LinkedIn Profiles

* Luke Schoen [Linkedin](https://www.linkedin.com/in/ltfschoen/)

## Development Roadmap

MVP of the Data Highway Mining will be a 4 month project with the following milestones:

### Milestone 1: Phase 1 (Concept Design)
  * Design
    * Concept Design & Review and update whitepaper (technical specification of protocol and runtime design) under a Creative Commons license plan
  * Duration: 4 weeks
  * Full-Time Employees: Luke Schoen
  * Cost Per Day: 1200 USD
  * Funding: 5,000 USD equivalent in DOTs

### Milestone 2: Phase 2 (Preliminary Design, Implementation, and Documentation)
  * Design
    * Preliminary Design & Review of Substrate runtime modules and update whitepaper.
    * Preliminary Design & Review of Data Highway Mining App UI
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
    * Licensing shall be open-source using Apache 2.0 (or as otherwise recommended)
  * Target date: February 2020
  * Duration: 4 weeks
  * Full-Time Employees: Luke Schoen
  * Cost Per Day: 1200 USD
  * Funding: 15,000 USD equivalent in DOTs

### Milestone 3: Phase 3 (Detailed Design, Implementation, Documentation, and Testnet)

  * Design
    * Detailed Design & Review of Substrate runtime modules and update whitepaper.
    * Detailed Design & Review of Data Highway Mining App UI
    * Preliminary Design to Integrate the Data Highway Mining App UI into LPWAN App Server (Go-based application https://github.com/mxc-foundation/lpwan-app-server) using the Go Substrate RPC client.

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
  * Cost Per Day: 1200 USD
  * Funding: 20,000 USD equivalent in DOTs

### Milestone 4: Phase 4 (Testnet)

  * Design
    * Final Design & Review of Substrate runtime modules and update whitepaper.
    * Final Design & Review of Data Highway Mining App UI
    * Final Design to Integrate the Data Highway Mining App UI into LPWAN App Server (Go-based application https://github.com/mxc-foundation/lpwan-app-server) using the Go Substrate RPC client.
  * Implementation & Testing
    * Preliminary Implementation of Data Highway Mining App UI
    * Final Implementation & Review of Substrate-based chain
  * Documentation
    * Final Documentation & Review
  * Deployment
    * Compatibility with most recent stable commit from the Substrate repository
    * Running chain containing all the above modules
    * Releases shall be tagged and include a Docker image
    * Testnet using NPoS collators
  * Target date: April 2020
  * Duration: 4 weeks
  * Full-Time Employees: Luke Schoen
  * Cost Per Day: 1200 USD
  * Funding: 20,000 USD equivalent in DOTs

### Milestone 5: Phase 5 (Testnet)

  * Design
    * Integration Design & Review of Substrate runtime modules and update whitepaper.
  * Implementation & Testing
    * Detailed Implementation of Data Highway Mining App UI
    * Final Implementation & Review of Substrate-based chain
    * Preliminary Implementation to Integrate the Data Highway Mining App UI into LPWAN App Server (Go-based application https://github.com/mxc-foundation/lpwan-app-server) using the Go Substrate RPC client.
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
  * Cost Per Day: 1200 USD
  * Funding: 20,000 USD equivalent in DOTs

### Milestone 6: Phase 6 (Mainnet)

  * Implementation & Testing
    * Mainnet on Polkadot network Parachain including on-chain upgrades (if any)
    * Final Implementation of Data Highway Mining App UI
    * Final Implementation to Integrate the Data Highway Mining App UI into LPWAN App Server (Go-based application https://github.com/mxc-foundation/lpwan-app-server) using the Go Substrate RPC client.
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
  * Cost Per Day: 1200 USD
  * Funding: 20,000 USD equivalent in DOTs

## Funds Required Overall

100,000 USD equivalent in DOTs

## Future Plans

The Data Highway future plans include preparation of the following specifications and deliverables:

* Data Highway Mining (Whitepaper, Testnet, Mainnet)
* Data Highway Inter-Chain Data Market (Whitepaper, Testnet, Mainnet)
* Data Highway Roaming (Whitepaper, Testnet, Mainnet)
* Data Highway DAO (Whitepaper, Testnet, Mainnet)

## Additional Information

### Funding

### Releases

* Releases shall be tagged and include a Docker image
* Licensing shall be open-source using Apache 2.0 (or as otherwise preferred)

### What work has been done so far?

* Data Highway Mining Whitepaper (Final draft)
* Data Highway Mining Runtime Modules (configuration, rates, samples, eligibility, claims)
* Data Highway Mining Documentation and API
* Data Highway Mining Website
* Data Highway Mining Oracle (MXC ERC-20 tokens)
* Data Highway Mining Inter-Chain Bridge Contract (MXC ERC-20 tokens)

### Are there are any teams who have already contributed (financially) to the project?

MXC Foundation gGmbH is a non-profit that has financed part of milestones M1 and part of M2. However we wish to use funding from a grant application to proceed with subsequent milestones and integrate into the Polkadot platform as a parachain.

### Have you applied for other grants so far?

No

### Are there any other projects similar to yours? If so, how is your project different?  

Similar projects:
* Edgeware's lock-drop
* ChainX's inter-chain asset mining

Data Highway will be an IoT parachain on the Polkadot network 
