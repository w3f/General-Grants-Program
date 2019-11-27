# Secure, Statically-typed Substrate Smart Contracts in Haskell

## Project Description

### Summary
The objective of this project is to produce specifications for enabling Haskell development of Substrate Smart Contracts. Through this grant, our team will research and evaluate the existing Substrate Smart Contract ecosystem and produce detailed recommendations for implementation plans to be considered for future grants. At the end of this project, we will deliver:

* Technical requirements documents defining future projects. Such projects may include:
  * A Haskell eDSL for writing smart contracts for Substrate blockchains
  * Sample contracts written in Haskell to serve as tests, examples, and a starting points for developers.
  * Tooling that makes writing Haskell smart contracts more pleasant
  * Tooling for interacting with any Substrate smart contract
* Scoping and estimation for each distinct development project
* A development roadmap which ties together the various projects

### Impact on the Ecosystem
**Security**: Haskell-based smart contracts are more secure by default because they are written in a strongly-typed functional language. Enhanced security will be a competitive advantage and will help attract institutions who want to build secure smart contract applications.  

**Adoption**: Smart contracts written in functional programming languages have been adopted by several blockchain projects today. This grant will make Substrate blockchains more compelling to application developers and grow the functional smart contract ecosystem. Examples of other projects with functional smart contract languages are:
  * Cardano: Cardano smart contracts are written in Plutus, a strictly-typed pure functional language, that is embedded in Haskell.
  * Kadena: Kadena uses the Pact smart contract language, whose interpreter is built in Haskell. In collaboration with Kadena, Obsidian has been building an Integrated Development Environment (IDE) for writing smart contracts.
  * Tezos: Tezos is implemented in OCaml and its smart contracts are written in Michelson, both of which are functional programming languages. Obsidian has been collaborating with Tezos to help secure, decentralize, and grow the network.  
  
**Future-Proofing**: As smart contracts and their applications inevitably grow bigger and more complex over time, Haskell is a great tool for implementing and managing that complexity without creating unintended consequences.  

**Talent**: This project will expose Polkadot to a growing pool of functional smart contract developers.  

**Ecosystem and Tooling Growth**: This project will also help identify more collaboration opportunities that build upon the scope of this proposal, such as a web-based IDE for writing Haskell smart contracts.

### Integration with Substrate and Polkadot
Smart contracts written in Haskell will be compatible with any Substrate blockchain. This project will attract Haskell developers, developers from other functional programming communities, and developers from existing functional programming blockchain communities, thus increasing the adoption of Substrate.

### Obsidian's Interest in this Project
Obsidian Systems is a software consulting firm focused on delivering high-quality software quickly. Since our founding 4 years ago, we have worked with many companies across several fields. Our core competencies are security, cryptography, programming language theory, and application development, all of which have found a natural application in blockchain. As a result, we have expanded rapidly in the blockchain space and we are interested in  uncovering new opportunities for collaboration.
We understand that secure and reliable software is of the utmost importance in the blockchain space. We want to apply our knowledge-base in ways that makes blockchains, no matter their complexity, more secure and reliable through the use of Haskell and crypto/security best practices. 


## Team Members
Obsidian Systems was founded in 2014 by Ali Abrar and Ryan Trinkle, who continue to serve as its managing partners today. Today it consists of approximately 39 software developers, quality assurance engineers, management professionals, and other staff.

Obsidian Systems designs and develops high quality software solutions to pressing business problems. Our experienced team has delivered mission-critical solutions to a variety of high-profile clients, including several Fortune 500 companies and national retail firms. These solutions are currently used by thousands of employees and tens of thousands of consumers every day. Every project at Obsidian includes a Product Owner, a Development Manager, Software Developers, Quality Assurance, and, if required, a Designer.
	

## Team Website	
https://obsidian.systems/

## Legal Structure 
Obsidian Systems LLC is a Delaware limited liability company.  
Our legal address is P.O. Box 1206, New York, NY 10159.
Our office address is 19 W 21st St, Suite 503, New York, NY 1001.

## Team's Experience
**Tezos**: Tezos is a blockchain with on-chain governance which is written in OCaml and supports formal verification of smart contracts. Tezos and its smart contract language Michelson are both functional programming languages which facilitate formal verification.

* Ledger: The "Tezos Wallet" application is for making XTZ transactions, originating contracts, delegation, and voting. It fully supports all of Tezos’ functionality besides baking. The “Tezos Baking” application was the first staking application for a hardware wallet used at scale by block producers. It allows a block producer to continuously sign and validate blocks with a private key held in cold storage while also protecting from double signing.

  

  + [Ledger announces integration with the Tezos wallet](https://www.ledger.com/tezos-wallet-app-is-now-available-to-download-on-ledger-live/)

   + [Initial Ledger Apps Release Post](https://medium.com/@obsidian.systems/release-obsidian-systems-tezos-wallet-and-baking-applications-for-the-ledger-nano-s-11876832f935)



* Kiln: Kiln is a tool for both baking and monitoring on the Tezos network. It provides a locally hosted graphical interface, binaries for tezos-client, tezos-node, tezos-baker, and tezos-endorser, and it builds a cache of chain data from the nodes to which it connects.

  

     +  [How to Install Kiln and Bake on Ubuntu](https://medium.com/@obsidian.systems/how-to-install-kiln-and-bake-on-ubuntu-a13d17df63c)
  + [Kiln v0.5.2: Voting and Governance](https://medium.com/@obsidian.systems/kiln-v0-5-2-voting-and-governance-6c04bafe2659)

  

  

See our [Medium Account]([https://medium.com/@obsidian.systems](https://medium.com/@obsidian.systems)) for more information about Kiln and Tezos Ledger applications.)




**Kadena**: The Pact IDE is an integrated development environment for users to develop and deploy smart contracts using the PACT language. It also has a desktop app for writing and deploying smart contracts. In addition, we have also implemented BIP39 to recover the desktop wallet using a mnemonic phrase.  

- [Kadena Pact IDE](https://pact.kadena.io/)
- [Kadena Goes Live, Announces New Token Sale Aiming for $20 Million](https://www.coindesk.com/kadena-goes-live-announces-new-token-sale-aiming-for-20-million)
- [Pact 3.0 is live](https://medium.com/kadena-io/announcing-pact-3-0-4b0a8f35e6a0)
 

**MIT’s Center for Brains, Minds, and Machines**: Obsidian Systems advised graduate researchers at CBMM and set up the computing infrastructure used to conduct research on topics such as artificial intelligence, machine learning, and cognitive science.

We have also worked on implementation projects with a variety of token issuers and blockchain-enabled businesses.


## Team Code Repos
These are repositories for the Kiln and Ledger projects described above
* Kiln - <https://gitlab.com/obsidian.systems/kiln>
* Ledger Applications - <https://github.com/obsidiansystems/ledger-app-tezos>

Reflex platform is a library for building cross platform applications in Reflex, a Functional Reactive Programming (FRP) interface. Obelisk is a framework for building Reflex applications.

* Obelisk - <https://github.com/obsidiansystems/obelisk/>
* Reflex Platform - <https://github.com/reflex-frp/reflex-platform>

In addition to the above , we also have several repositories that are not open source and are for private clients. 

## Team LinkedIn Profiles
* Ryan Trinkle, Partner at Obsidian Systems - <https://www.linkedin.com/in/ryantrinkle>
* Ali Abrar, Partner at Obsidian Systems - <https://www.linkedin.com/in/aliabrar>

## Additional Information
Due to our vast experience in blockchain related projects, we are in a position to produce high quality deliverables in a short amount of time. In particular, we have experience with Haskell smart contract eDSLs, IDEs, and related tooling on multiple protocols. Haskell allows us to produce secure and reliable software which helps us cater to the needs of an end user more effectively. We look forward to collaborating on this project and are confident that we will be able to identify more long term collaboration opportunities.


