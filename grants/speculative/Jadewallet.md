# Jadewallet

## Project Description
**Jadewallet** is a revolutionary self-custody solution that is built on foundation of the cutting-edge technologies including **MPC (multi-party computation)** and **TSS (threshold signature scheme)**. **Jadewallet** will be integrated into the Jadepool Custody system (includes Jadepool SAAS and Jadepool Hub, see details in 'Related Products' section below), to form a complete self-custody which is dedicated to provide users with the most professional and secure solution.

The feature of **MPC-based Threshold Signature** offers users the complete control over their digital assets and the ability to achieve multi-signature with keyless cryptographic security.

<img src="https://ipfs.io/ipfs/QmPA4fmURX4fkPUejUsmQBDpU1RZDda8wNh4yxkf3eL23t" style="zoom: 100%;" />

The main disadvantage of multisig is that different blockchains requires different implementations, though plenty of blockchains don't even support multisig. Instead, **TSS** is obviously a better choice as it is entirely based on cryptography. Therefore, supporting **TSS** on each blockchain is always possible in spite of the blockchain's own implementation and features. Furthermore, signers' privacy will be well protected as their information won't be visible in transaction. It also reduces cost and avoids smart contract related risks since signature will be generated through **MPC** instead of executing a smart contract on chain. 

As stated above, **TSS** is basically cross-chain. Considering Polkadot is also devoted to connect and integrate multiple blockchains, **TSS** technology together with Polkadot can make managing multi-chain assets convenient and more secure. 




### A Typical Flow Preview
<img src="https://ipfs.io/ipfs/QmaWbbTC1zH6MDMqjYhq1UrN6QMpQ5sVKLrZKGDm136qp8" style="zoom: 100%;" />

For instance, Alice, Bob and Chris together create a 2-3 wallet to share assets management and they decide to make a transfer. First Alice initiates the transfer and then Bob and Chris both receive push notifications. Since their wallet requires two signatures, Alice must wait for one of her friends to join the signing session before moving to the next step. Assuming Bob joins the session first, Alice and Bob both signs the transaction by using **MPC** technology and then the transaction will be broadcast to blockchain.




### Related Products

#### Jadepool SaaS

##### Funds Management & Risk Control

Jadepool SaaS is a one-stop platform for asset custody, trading and wealth increment. It is dedicated to provide institutions and qualified individual investors with services that are tailored to their business needs. Customized risk control services, simple web management interface and rich API interface make asset management more secure, fasterand easier to use.

Jadepool SaaS provides **Jadewallet** services including notification/message, order processing, session management, etc.



#### Jadepool Hub

##### Monitor Blockchain & Process Transaction 

Jadepool Hub is the software solution that automates blockchain-related services of multiple blockchains and thousands of tokens. It is mainly responsible for signing & broadcasting transactions, monitoring blockchain and securely managing crypto assets etc. The main services it provides include deposit, withdrawal, cold storage, staking etc. Over 30 blockchains has been supported.

Jadepool Hub provides **Jadewallet** services including building unsigned tx, broadcasting tx, monitoring addresses' and txs' status on blockchain, etc.



## Team members

* Alex Xu

* BoHao Tang

* Daizong Zhang

* Kevin Li

* Hilbert Zhou

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
We need 3 months and 9 full-time employees (5 developers) to complete the project. The estimated total cost is $30,000.

We are hoping to receive a share of grant by the end of each milestone: $30,000 / 3.

We accept grant in DOTs or KSMs.



### Milestone 1 (1 month)

- MPC core:

  - Implement key generation for creating secret shares without trusted dealers (keygen).
  - Implement using the secret shares to generate a signature (signing).
  - Implement a local test server to relay messages between multi parties.
  - Implement a demo to show keygen and signing process.

- Wallet app:
  
  - Build app architecture and framework with Flutter: network layer, data model, encryption mechanism, etc.
  
- Server API:
  - Create a MPC wallet
    - The api needs params such as wallet name, threshold, number of members, UUIDs to identify a wallet in database. 
  - Join a MPC wallet.
    - Add members to a specific wallet.
  - Backup a MPC wallet
    - Users can upload encrypted secret shares to server. The decryption key is always in users' control.
  - Restore a MPC wallet
    - A user could apply for restoring his own secret share.
    - Other members in same wallet group need to approve the application.
    - The applicant can fetch his encrypted secret share only if all other members agree the application.
  - MPC P2P channel and session management
    - Implement the P2P channel to dispatch message between multi parties. 
    - Manage the session with exception handling, such as timeout, network error, etc.

- Deliverables:  https://github.com/nbltrust/threshold-signature-lib

  - MPC core source code
  - MPC core document
  - MPC core demo
  
  

### Milestone 2 (1 month)

- Wallet app

  - Make MPC core as a library which can be called by using Dart. 
  - Any user can create a MPC wallet and invite other members to join the wallet.
  - To activate a wallet, members need to do keygen process to generate secret shares on their mobile devices.

- Server API:
  - Implement transfer logic
    - It will generate a transaction order on server when a member apply for sending a transaction.
    - The order would be marked as failed if any member reject it.
    - Create a signing session when members are ready to sign. Connect users -> construct raw tx -> review tx -> sign tx.
    - Broadcast the signed transaction to blockchain.
  - Transaction history
    - Record transaction history for all wallets.
  - Push notification

- Deliverables:  TestFlight https://testflight.apple.com/join/k2nXCif2

  

### Milestone 3 (1 month)

- Users can make DOT/KSM transactions with MPC protocol
  - Serialize and deserialize data with SCALE Codec.
  - Users can transfer with keep-alive check (default) or not, user can set it in advanced options.
  - Users can add a "tip" to increase transaction priority.
  - A MPC signing session would be created for members to sign the transaction.
  - A signed transaction would be broadcasted to Polkadot/Kusama.
- Users can backup secret shares
  - The wallet app would reminder users to backup secret shares.
  - A random decryption key would be generated to encrypt a secret share.
  - Encrypted secret shares would be upload to server.
- Users can restore secret shares
  - If accidents occur like mobile phone lost, a user need to restore his secret share before accessing wallet.
  - The user need to make an restore application.
  - Until other members agree the application, the user has not the right to fetch his encrypted secret share.
  - After encrypted secret share fetched, the applicant could use the decryption key to decrypt it.
- Deliverables: 
  - dart-scale-codec https://github.com/nbltrust/dart-scale-codec
  - TestFlight https://testflight.apple.com/join/k2nXCif2



## Future Plans
Our future plan is to integrate **Jadewallet** with [Polkadot/Substrate Portal](https://polkadot.js.org/apps) which will bring support of staking and separating stash/controller accounts. The App will be submitted to App Store once the 1.0.0 version is released.

**Jadewallet** wants to be the portal of institutional investors into the Polkadot community.



## Additional Information

### What work has been done so far?

1. Jadepool Hub has already supported DOT and KSM.
2. MPC core has been partially implemented.

### Are there any teams who have already contributed (financially) to the project?

No.

### Have you applied for other grants so far?

No.

### Will users who are not part of Jadepool Hub/SaaS be able to use Jadewallet?

Yes. Jadepool Hub and Jadepool SaaS are both back-end services so they are transparent to end users.

### References

[1] [Secure multi-party computation](https://en.wikipedia.org/wiki/Secure_multi-party_computation)

[2] [Threshold Signatures Explained](https://academy.binance.com/security/threshold-signatures-explained)

[3] [Technology | Polkadot](https://polkadot.network/technology/)
