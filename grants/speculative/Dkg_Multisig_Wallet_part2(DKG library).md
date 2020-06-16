# Project Name
Polkadot DKG multisig Wallet part 2

## Project Description
This is an application for development of a DKG multisig wallet. This project has been discussed with multiple members of the Web3 team, we have also recently finished a PSP regarding this project https://github.com/everstake/PSPs/tree/psp-dkg-multisig-wallet</br>  

&nbsp;&nbsp;&nbsp;&nbsp;DKG multisig wallet will allow users to manage their funds collectively with high security level via the application with the good UX.

&nbsp;&nbsp;&nbsp;&nbsp;Distributed Key Generation (DKG) is a way for a group of nodes to collectively agree on a public/private key pair without any single party knowing the private key. Everyone just knows the public key.

&nbsp;&nbsp;&nbsp;&nbsp;This is actually very hard to achieve but it relies on the fact that lagrange interpolated shares are homomorphic (in that operations can be performed on shares even without knowing the full value). For example, you can add A{share1}+B{share1} to get C{share1} that you can add to someone else’s C{share2} to get the full value of C (assuming A and B were split into 2 shares each).

&nbsp;&nbsp;&nbsp;&nbsp;In general, a multisig wallet which we want to develop can be divided into 3 parts: wallet APP(browser extension, desktop app, etc.), web server and DKG library in Rust.

## Team members
* Aleksei Korobeinikov – developer
* Vadym Grozinok – developer

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
1. DKG library
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
