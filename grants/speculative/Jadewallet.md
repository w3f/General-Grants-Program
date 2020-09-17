# Jadewallet

## Project Description
**Jadewallet** is making a new paradigm of custody, which based on Jadepool SaaS and Jadepool Hub uses **multi-party computation (MPC)** and **threshold signature scheme (TSS)** technology to provide our clients the most trusted and secure custody solution.

**MPC** and **TSS** gives clients total autonomy over whose digital assets and multisignature ability with keyless cryptographic security.

<img src="https://ipfs.io/ipfs/QmNokuRsE5dXN4X47opiNuAcqdGB7xtKkZAwCiVh5rJigN" style="zoom: 100%;" />

#### Prototype Preview

<img src="https://ipfs.io/ipfs/QmaWbbTC1zH6MDMqjYhq1UrN6QMpQ5sVKLrZKGDm136qp8"  />



### About NBLTrust

We established our company in April 2017 and recognized the encryption and security issues related to blockchain long before the advent of the blockchain wave.

So far, NBLTrust has already developed its own storage products for blockchain tokens and offers technical support with high performance to global markets as well as other blockchain applications. Our products include SaaS for custody, blockchain infrastructure, hardware multisig wallet. We provide custody services for our customers such as **HashKey, Math Wallet, Cybex, Chain. Game**. Polkadot and Kusama have been already supported in our custody services.



**Jadepool SaaS**

One-stop platform for asset custody, trading and wealth increment. It is dedicated to providing institutions and qualified individual investors with custodial, trading and wealth increment services that are tailored to their business needs. Customized risk control services, simple web management interface and rich API interface make asset management more secure, easier to use and faster.

- Support for 30+ blockchains and 700+ tokens representing 75% of market cap
- 95% of funds stored in cold wallet
- $150 million in transactions



**Jadepool Hub**

Designed for secure management of blockchain tokens for institutions. It separates token storage system back ends from the account system, interacts via encrypted channels with client system. It also contains risk control functions such as withdrawal limit, manual verification. The hot and cold wallet are safely separated.



## Team members

* Alex Xu

* BoHao Tang

* Daizong Zhang

* Kevin Li

* Hilbert Zhou

* Yi Zhang

* Andy Yi

* Kristie Guo

* Steven Wu

  

## Team Website	
* https://www.nbltrust.com/#/en/team

  

## Legal Structure 
Tuolian(Shanghai) Tech Co., Ltd.



## Team's experience
* Alex Xu: Co-Founder and CTO in NBLTrust for 4 years, core developer in our three custody products. IT Consultant in IBM for 9 years. **Polkadot Ambassador China**. Worked as TA in two training courses hold by Parity in China.
* BoHao Tang: Senior full-stack developer and architect in NBLTrust for 3 years, core developer for Jadepool Hub. Sofeware engineer in Ubisoft for 4 years, indie game developer for 4 years. **The Winner of Substrate Hackathon** by PolkaWorld in 2019.

* Daizong Zhang: Core backend developer of the Jadepool SaaS. 5+ years Golang backend development, currently focusing on the blockchain field.
* Kevin Li: 6 years native mobile development experience, 3 years React Native, Flutter Hybrid and front-end development experience, graduated from Syracuse University.
* Hilbert Zhou: 2 years ops experience on AIX, websphere and Power. 7+ years backend service development experience including HFT, CTA and blockchain.
* Yi Zhang: Key member of our DEX project, and financial derivative product. Many experiences in decentralized architecture design and product design. Work in IBM as an IT consultant over 7 years.
* Andy Yi: Product manager in NBLTrust for 3 years, responsible for Jadepool SaaS design and operation. 9 years QA Manager experience, worked for General Electric, Hua Wei and Travelzen.com.
* Kristie Guo: Product manager of Jadepool Hub. 2+ years software engineer experience. Worked at Lending Club in San Francisco, graduated from Cornell University.
* Steven Wu: Product manager in NBLTrust for 3 years. 6+ years product manager, and 4+ years full stack development experience. An ex start-up co-founder.



## Team Code Repos
* https://github.com/nbltrust

* https://github.com/alexxuyang

  

## Development Roadmap
We will require 4 months to complete this project. 9 full-time employees (5 developers), at a total cost of $40,000.

Ideally, we can receive part payment at the end of each milestone: $40,000 / 4.

We would be willing to accept payment in DOTs or KSMs.



**Milestone 1:** (weeks 0-4)

- MPC core:
  
  - Use Rust and Python to make a demo work on a single pc.
  
- Wallet app:
  - App architecture and framework. (weeks 0-2)
  - Network layer and data model. (weeks 0-2)
  - Create a general wallet in Jadepool SaaS. (weeks 2-4)
  
- Jadepool SaaS api:
  - Create a MPC wallet. (weeks 0-2)
  - Join a MPC wallet. (weeks 0-2)
  - Backup a MPC wallet. (weeks 0-2)
  - Restore a MPC wallet. (weeks 2-4)
  - Relay message to MPC server. (weeks 2-4)
  
- MPC server:
  - Receive message from each party.
  - Dispatch message to specific party.
  
- Deliverables (plan 10.09):  MPC core https://github.com/nbltrust/threshold-signature-lib

  

**Milestone 2:** (weeks 4-8)

- MPC core:
  - Work with MPC server.
  - Test and fix issue.
  
- Wallet app:
  - Make MPC core as a library which can be called by using Dart. 
  - Make MPC logic work on iOS with a local test server.
  - Create a MPC wallet (keygen).
  - UI
  
- Jadepool SaaS api:
  - Withdraw logic
  - Transaction history
  - Test and fix issue.
  
- MPC server:
  
  - Test and fix issue.
  
- Deliverables (plan 11.06):  TestFlight https://testflight.apple.com/join/k2nXCif2

  

**Milestone 3:** (weeks 8-12)

- Support ETH

- Backup and restore wallet

- Notification

- Test and fix issue

- Release 0.5.0 Beta version

- Deliverables (plan 12.04): TestFlight https://testflight.apple.com/join/k2nXCif2

  

**Milestone 4:** (weeks 12-16)

- Support DOT/KSM
- Settings
- Localization
- UI details
- Test and fix issue
- Release 0.6.0 Beta version
- Deliverables (plan 12.31):  
  - dart-scale-codec https://github.com/nbltrust/dart-scale-codec
  
  - TestFlight https://testflight.apple.com/join/k2nXCif2
  
    

## Future Plans
We are planning to support staking, separating stash and controller accounts in the future. Finally, the app will be submitted to App Store when it is ready for version 1.0.0 release.

Since **Jadewallet** is mainly served for business clients,  we will keep exploring and meeting clients need for Polkadot/Kusama. 
