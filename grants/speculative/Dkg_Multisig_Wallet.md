# Project Name
Polkadot DKG multisig Wallet

## Project Description
This is an application for development of a DKG multisig wallet. This project has been discussed with multiple members of the Web3 team, we have also recently finished a PSP regarding this project https://github.com/everstake/PSPs/tree/psp-dkg-multisig-wallet</br>  

&nbsp;&nbsp;&nbsp;&nbsp;DKG multisig wallet will allow users to manage their funds collectively with high security level via the application with the good UX.

&nbsp;&nbsp;&nbsp;&nbsp;Distributed Key Generation (DKG) is a way for a group of nodes to collectively agree on a public/private key pair without any single party knowing the private key. Everyone just knows the public key.

&nbsp;&nbsp;&nbsp;&nbsp;This is actually very hard to achieve but it relies on the fact that lagrange interpolated shares are homomorphic (in that operations can be performed on shares even without knowing the full value). For example, you can add A{share1}+B{share1} to get C{share1} that you can add to someone else’s C{share2} to get the full value of C (assuming A and B were split into 2 shares each).

&nbsp;&nbsp;&nbsp;&nbsp;In general, a multisig wallet which we want to develop can be divided into 3 parts: wallet APP(browser extension, desktop app, etc.), web server and DKG library in Rust.

## Team members
* Vitalii Parkhomenko – team leader/researcher/tech writer
* Aleksei Korobeinikov – developer
* Vadym Grozinok – developer
* Stanislav Chebanenko – front developer

## Team Website
* https://everstake.one & https://atticlab.net

## Legal Structure
ATTIC LAB, Limited Liability Company. 89, Kazimir Malevich str., Kyiv, 03150, Ukraine

## Team's experience
Everstake is an affiliate company of Attic Lab, so members from both teams are going to participate in the project. We have developed VSCode and Atom plugins for Substrate. We have also created a PSP for this project. 

Our prior projects and experience include: Crypto exchange Codex. Cassandra history plugin, Munin plugins, OpenBankIT open-source banking software, EOS History API running on Elasticsearch cluster, My EOS Wallet. (web and mobile), NEO IDE, Teztracker (Tezos blockchain explorer). 

## Team Code Repos
* https://github.com/everstake
* https://github.com/atticlab

## Team LinkedIn Profiles
* https://www.linkedin.com/in/vitalii-parkhomenko-493561187/
* https://www.linkedin.com/in/aleksei-korobeinikov/
* https://www.linkedin.com/in/pavelmidvel/
* https://www.linkedin.com/in/stanislav-c-362685195/

## Development Roadmap
1. Wallet APP
   * Wallet application (160h)
      * Implement UI and layouts - 44h
      * Write main logic and working with adapter - 100h
         * ShowWalletStatus
         * CreateWallet
         * JoinWallet
         * GenerateKey
         * CreateTransaction
         * DoBackUp
       * Test UX of application - 4h
       * Do manual testing - 4h
       * Write unit tests - 8h
   * Adapter in Rust (200h)
      * Write all the methods for external calls - 168h
         * NewDistKeyGen
         * ProcessDeal
         * ProcessResponse
         * ProcessSecretCommits
         * DistKeyShare
         * NewDSS
         * ProcessPartialSignature
         * ConstructFinalSignature
         * VerifySignature
      * Integrate adapter with DKG library - 8h
      * Write unit tests for Rust code - 16h
      * Write unit tests for new compiled JS code - 8h
   * Integration testing adapter with application (16h)
   * Integration testing application with server (8h)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Total for Wallet App: 384h - 1 back-end and 1 front-end developers (2 months)

2. Web server
   * API written with actix
      * Write all the endpoints with asynchronous functionality - 124h
         * NewWallet
         * JoinWallet
         * BroadcastDeal
         * CreateNewTransaction
         * BroadcastPartialSignature
         * BroadcastFinalSignature
      * Write functionality for authentication and encryption - 16h
         * NewUser
         * CheckUser
         * Encrypt
         * Decrypt
      * Integrate functionality with DB - 4h
      * Write unit tests - 16h
      * Configure all this with Docker to easier deploy it to server - 8h

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Total for Web server: 168h - 1 back-end developer (1 month)

3. DKG library
   * VSS (240h)
      * Implement polynomial commitments with Lagrange interpolation - 72h
         * NewPrivPoly
         * RecoverSecret
         * NewPubPoly
      * Implement Dealer functionality (struct which will create shares and deals(set of data such polynomials, sessionID, threshold)) - 56h
         * NewDealer
         * EncryptDeal
         * SecretCommit
      * Implement Verifier functionality (struct which will receive deals from all the participants and verify it) - 96h
         * NewVerifier
         * ProcessEncryptedDeal
      * Write unit tests - 16h
   * DKG(320h)
      * Integrate with VSS functionality - 16h
      * Write functionality to create and process commitments of the secret polynomials - 56h
         * NewDistKeyGenerator
         * ProcessDeals
         * ProcessSecretCommits
      * Write reconstruction key functionality - 32h
         * GenDistKeyShare
      * Write unit tests - 16h

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Total for DKG library: 560h - 2 back-end developers (2.5 months)

4. DSS library
   * Integrate with DKG functionality - 8h
   * Write functionality to produce and check partial signature - 62h
      * ProducePartialSig
      * ProcessPartialSig
   * Write functionality to compute final distributed signature from partial signatures - 56h
      * ComputeFinalSignature
   * Write unit tests - 16h
   * Write integration tests with DKG - 16h

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Total for DSS library: 240h - 1 back-end developer (1.5 month)

5. Documentation
   * Write tutorial to build, test and run DKG functionality - 6h
   * Write instruction overall DKG wallet use - 6h

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Total for Documentation writing: 12h - 1 back-end developer (1.5 day)

### Development team: 
**2 backend developers**

**1 frontend developer**

**Total timeline: 1362 man-hours**

**Total project length: 5.5 months**
# Long-term plans
We would like to continue developing tools and products for Polkadot.
# Additional Information
   * What work has been done so far? Quite a lot of research, discussions with Jeff Burdges and Philipp Jovanovic, we’ve also completed a PSP.
   * Have you applied for other grants so far? We received a grant for development of VSCode/Atom plugins several months ago.
   * Are there any other projects similar to yours? Not to our knowledge.
