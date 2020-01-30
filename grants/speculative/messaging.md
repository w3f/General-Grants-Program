# HOPR

## Project Description
This grant application supports the development of a decentralized and privacy-preserving messaging protocol called HOPR. Within the framework of this grant application we will provide an implementation of the payment layer of HOPR in Substrate. Validity Labs recently started developing HOPR as a privacy-preserving and incentivized messaging protocol which provides:
* metadata-privacy (and not just end-to-end encryption) via Chaumian onion encryption
* incentives for relayers that get paid by the sender of a message or third parties (similar to meta-transactions currently discussed for other blockchains) instead of just relying on services by altruistic parties (e.g. as required for TOR)
* efficient implementations without proof-of-work or SNARKs that would hinder adoption on embedded or mobile devices
* a scalable network architecture (in contrast to snowball-messaging, e.g. Whisper)
* a payment layer that is currently being implemented for Ethereum. Here we aim to provice a more efficient implementation of the payment layer with Substrate / Polkadot
* a messaging layer that is building upon the SPHINX message format

While we have seen some prior work in the ecosystem towards privacy-preserving messaging protocols (e.g. Whisper, Orchid, Matrix), we are still missing a go-to protocol that is scalable, provides metadata anonymity and incentivizes node operators.

## Team members
* team lead: Dr. Sebastian Bürgel
* developer: Robert Kiel
* developer: Matt Swezey

## Team Website	
* https://validitylabs.org

## Legal Structure 
Validity Labs AG, registered in Zug, Switzerland.

## Team's experience
Sebastian is co-founder and CTO of Validity Labs and leads a mostly technical team of 17. Before co-founding Validity Labs he worked as a Postdoctoral researcher at ETH Zurich in the domain of microtechnology for biomedical applications. Prior to Validity Labs, he co-founded SONECT, a Swiss fintech startup backed by PostFinance and other major financial infrastructure providers. Sebastian has been developing in the Ethereum ecosystem since 2015, the first public example was a decentralized lab book developed during the hack.ether.camp hackathon in 2015 (https://github.com/dlabbook https://youtu.be/GXSTKjS7UZE).

Robert holds an MSc degree in Computer Science from TU Darmstadt with a specialization in IT security. He is full time with Validity Labs since beginning of August 2018 to work on the architecture and implementation of a privacy-preserving messaging protocol.

Matt joined Validity Labs in November 2017 as a decentralized application developer and has worked across the full dApp stack from smart contracts to web technologies. He is also CEO of Pactum IO, LLC, providing graphical user interfaces for creating configurable smart contracts. Matt holds a degree in Computer Science from Midwestern State University Texas.

## Team Code Repos
* https://github.com/validitylabs
* https://github.com/validitylabs/messagingProtocol

## Team LinkedIn Profiles
* https://www.linkedin.com/in/scbuergel/
* https://www.linkedin.com/in/robert-kiel-176878161/
* https://www.linkedin.com/in/matt-swezey-46691755/

## Intended language of development
* JavaScript
The first implementation of the HOPR protocol will be in JavaScript in order to cater to both backend services running as a NodeJS CLI application as well as browser-based dapps. We deem this crucial for fast adoption of early showcases that give us a feeling for the viability of the approach.

* Rust
Within the framework of this grant application, we will decouple the payment layer from the message layer and provide a Substrate implementation of the payment layer in Rust. The existing and more complex message layer thus does not have to be entirely re-written in Rust in order to complete the grant within the anticipated timeline and budget. Integration via APIs in both directions is however in scope of this grant and needs to be implemented.

## Development Roadmap
This grant application is targeting a 4 months implementation and assessment timeline during which we aim to reach the following milestones:
* Milestone 1: 
   * decouple existing message and payment layer
   * detailed documentation of payment layer
   * Deliverables: architecture, implementation and documentation detailed publicly on GitHub
   * Duration: 1 month
   * Funding: CHF 25'000
* Milestone 2: Substrate implementation
   * Rust implementation of existing HOPR smart contract logic that has initially been built on Ethereum
   * Deliverables: Working code available publicly on GitHub
   * Duration: 2 months
   * Funding: CHF 40'000
* Milestone 3: Integration, testing & reporting
   * integrate the new Substrate implementation with message layer
   * testing and documentation
   * tutorial article and video that details how to setup a HOPR node and participate in the network
   * report outcomes and detail future work
   * Deliverables: Report summarizing the work available as blog post and demonstrate in at least on public event
   * Duration: 1 month
   * Funding: CHF 25'000

The total funding is CHF 90'000. Validity Labs plans to spin out the protocol in a separate legal entity that generates revenue by taking a cut of relayer fees (this initial business model is under discussion and might be subject to change) in order to sustainably finance protocol development.

## Additional Information
Validity Labs started some initial research and development on this project which is publicly available under https://github.com/validitylabs/hopr (GPL3 license). The initial research and development is so far exclusively financed by Validity Labs, no further grant applications are pending at this time.
