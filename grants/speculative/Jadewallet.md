# Jadewallet

## Project Description
**Jadewallet** is a revolutionary self-custody solution that is built on foundation of the cutting-edge technologies including **MPC (multi-party computation)** and **TSS (threshold signature scheme)**. **Jadewallet** will be integrated into the Jadepool Custody system (includes Jadepool SAAS and Jadepool Hub, see details in 'Related Products' section below), to form a complete self-custody which is dedicated to provide users with the most professional and secure solution.

The feature of **MPC-based Threshold Signature** offers users the complete control over their digital assets and the ability to achieve multi-signature with keyless cryptographic security.

<img src="https://ipfs.io/ipfs/QmNokuRsE5dXN4X47opiNuAcqdGB7xtKkZAwCiVh5rJigN" style="zoom: 100%;" />

The main disadvantage of multisig is that different blockchains requires different implementations, though plenty of blockchains don't even support multisig. Instead, **TSS** is obviously a better choice as it is entirely based on cryptography. Therefore, supporting **TSS** on each blockchain is always possible in spite of the blockchain's own implementation and features. Furthermore, signers' privacy will be well protected as their information won't be visible in transaction. It also reduces cost and avoids smart contract related risks since signature will be generated through **MPC** instead of executing a smart contract on chain. 

As stated above, **TSS** is basically cross-chain. Considering Polkadot is also devoted to connect and integrate multiple blockchains, **TSS** technology together with Polkadot can make managing multi-chain assets convenient and more secure. 




### Prototype Preview
<img src="https://ipfs.io/ipfs/QmaWbbTC1zH6MDMqjYhq1UrN6QMpQ5sVKLrZKGDm136qp8" style="zoom: 100%;" />




### Related Products

#### Jadepool SaaS

##### Funds Management & Risk Control

Jadepool SaaS is a one-stop platform for asset custody, trading and wealth increment. It is dedicated to provide institutions and qualified individual investors with services that are tailored to their business needs. Customized risk control services, simple web management interface and rich API interface make asset management more secure, fasterand easier to use.



#### Jadepool Hub

##### Monitor Blockchain & Process Transaction 

Jadepool Hub is the software solution that automates blockchain-related services of multiple blockchains and thousands of tokens. It is mainly responsible for signing & broadcasting transactions, monitoring blockchain and securely managing crypto assets etc. The main services it provides include deposit, withdrawal, cold storage, staking etc. Over 30 blockchains has been supported.



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
Tuolian (Shanghai) Co., Ltd.



## Team's experience
* Alex Xu: Co-Founder and CTO at NBLTrust for 4 years. Core developer in all three custody product teams. IT Consultant at IBM for 9 years. **Polkadot Ambassador China**. Worked as TA in two training courses hold by Parity in China.
* BoHao Tang: Senior full-stack developer and architect at NBLTrust for 3 years. Core developer of Jadepool Hub. Software engineer at Ubisoft for 4 years. Has been indie game developer for 4 years. **The Winner of Substrate Hackathon** by PolkaWorld in 2019.
* Daizong Zhang: Core back-end developer of Jadepool SaaS. 5+ years Golang back-end development. Currently focusing on the blockchain field.
* Kevin Li: 6 years of native mobile development experience. 3 years of React Native, Flutter Hybrid and front-end development experience. Graduated from Syracuse University.
* Hilbert Zhou: 2 years of ops experience on AIX, websphere and Power. 7+ years back-end service development experience including HFT, CTA and blockchain.
* Yi Zhang: Key member of the DEX project and the financial derivative product. Experienced in decentralized architecture design and product design. Worked for IBM as IT consultant over 7 years.
* Andy Yi: Product manager at NBLTrust for 3 years, responsible for Jadepool SaaS design and operation. 9 years of QA Manager experience, worked for General Electric, Hua Wei and Travelzen.com.
* Kristie Guo: Product manager of Jadepool Hub for 2+ years. 2+ years of software engineer experience at Lending Club in San Francisco. Graduated from Cornell University.
* Steven Wu: Product manager at NBLTrust for 3 years. 6+ years of product manager and 4+ years full stack development experience. An ex start-up co-founder.

Founded in 2017 and headquartered in Shanghai, China, Tuolian (Shanghai) Co., Ltd. is a high-tech company specializing in the field of digital asset custody.

To provide overall solutions and related technical services for digital asset custody, Tuolian owns secure custody softwares based on self-developed high-strength classical cryptographic algorithms. And the hot&cold wallet and the hardware wallet products meet the bank's security level requirements. 

Tuolian provides the full package of custody services for well-known institutions such as Math Wallet and HashQuark.




## Team Code Repos
* https://github.com/nbltrust

* https://github.com/alexxuyang

  

## Development Roadmap
We need 4 months and 9 full-time employees (5 developers) to complete the project. The estimated total cost is $40,000.

We are hoping to receive a share of grant by the end of each milestone: $40,000 / 4.

We accept grant in DOTs or KSMs.



**Milestone 1:** (weeks 0-4)

- MPC core:
  
  - Use Rust and Python to make a demo that works on a single pc.
  - Test and fix issue.
  
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
We are planning to support staking, separating stash and controller accounts in the future. The App will be submitted to App Store once it is ready for version 1.0.0 release.

**Jadewallet** wants to be the portal of institutional investors into the Polkadot community.



## Additional Information

### What work has been done so far?

1. Jadepool Hub has already supported DOT and KSM.
2. MPC core has been partially implemented.

### Are there any teams who have already contributed (financially) to the project?

No.

### Have you applied for other grants so far?

No.

### References

[1] [Secure multi-party computation](https://en.wikipedia.org/wiki/Secure_multi-party_computation)

[2] [Threshold Signatures Explained](https://academy.binance.com/security/threshold-signatures-explained)

[3] [Technology | Polkadot](https://polkadot.network/technology/)
