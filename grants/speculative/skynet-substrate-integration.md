# General Grant Proposal

- **Project Name:** Pallet for Decentralized Off-Chain Storage on Skynet
- **Team Name:** Skynet Labs

## Project Overview :page_facing_up:

### Overview

Our intention is to build an integration with Skynet for easily making use of decentralized off-chain storage from any project using FRAME.

Skynet is a decentralized storage platform built to use the Sia blockchain network for storage, but in a way that's accessible via the web and available to anyone, without concerning themselves with cryptocurrencies or special software. Skynet allows for hosting of robust web-app frontends and storage of application data in a way where users retain control over their data and application data is interoperable between applications.

### Project Details

The Skynet Pallet will allow Polkadot projects to access any Skynet Portal on the network using off-chain workers in order to do the following on Skynet:

- Upload Files and return the Skylink for use by the runtime
- Download a Skyfile to storage or for use by runtime
- SkyDB getJSON: download an object from SkyDB's mutable storage at a consistant publicKey/dataKey pairing
- SkyDB setJSON: save an object on SkyDB using a privateKey/dataKey pairing.
- Data Verification for all interactions with a portal, using storage proofs from the Sia network.\*
- Subscribing to SkyDB entry changes (pending future Substrate development of long-running off-chain worker processes).\*

_\* These items require significant additions to Skynet Core._

Communication with portals happens by utilizing portal HTTP APIs along with additional processing and cryptography on the client-side.

Some use cases where we believe Skynet will be useful:

- Chains where interaction focuses on client-side web apps
- Off-chain storage for NFTs
- On-chain referencing of user-generated-content
- Indirect communication for chain-external data (where another service can publish to skynet, to be consumed by the off-chain worker)
- Persistance of runtime data that isn't saved to storage

### Ecosystem Fit

The most similar project in the ecosystem that we are aware of is the `offchain:ipfs` fork of Substrate that implements an ipfs node in Rust along with an example pallet.

IPFS has many differences in performace, ease-of-use, availability and infrastructure as compared to Skynet, but critical to this conversation is that Portals will be taking care of much of the overhead that an IPFS node would. Because of this, we do not intend to need to make modifications to Substrate core for integration, instead working from the perspective of a pallet, allowing for easier maintenance and community up-take in the long term.

## Team :busts_in_silhouette:

### Team members

- **Leader**: David Vorick, _CEO | Skynet Labs_
- **Skynet Labs Team Members** including:
  - Chris Schinnerl
  - Matthew Sevey
  - Daniel Helm
  - Marcin Swieczkowski
- **Skynet Labs Community Contributors**:
  - TBD
- **Polkadot Ecosystem Collaborators**:
  - TBD

### Contact

- **Contact Name:** Daniel Helm, _Developer Evangelist for Skynet Labs_
- **Contact Email:** daniel@nebulous.tech
- https://siasky.net/

### Legal Structure

- **Registered Address:** 177 Huntington Ave Ste 1703, PMB 71942, Boston, Massachusetts 02115-3153 US
- **Registered Legal Entity:** Nebulous Inc.

### Team's experience

The Skynet Labs team (recently renamed from Nebulous) has been responsible for the development and oversight of the Sia blockchain network and serveral projects in its ecosystem for many years. The team's most recent significant project is Skynet, a web-accessible decentalized storage protocol built to enable usage of Sia storage for users and developers without reliance on running any specialized software or obtaining any cryptocurrency. Skynet hosts over 200 community-created web apps, and has been seen many signifigant partnerships and integrations.

### Team Code Repos

- https://gitlab.com/NebulousLabs/Sia
- https://github.com/NebulousLabs/skynet-webportal
- https://github.com/NebulousLabs/skynet-js

### Team LinkedIn Profiles

- https://www.linkedin.com/in/david-vorick-6758a66a/
- https://www.linkedin.com/in/sevey/
- https://www.linkedin.com/in/dghelm/

## Development Roadmap :nut_and_bolt:

### Overview

- **Total Estimated Duration:** 4 Months

### Milestone 1 - Skynet Immutable Off-Chain Storage Pallet (Immutable Data Functionality)

- **Estimated Duration:** 2 months

| Number | Deliverable                               | Specification                                                                                                                                                                                          |
| ------ | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 0a.    | License                                   | MIT                                                                                                                                                                                                    |
| 0b.    | Documentation                             | We will provide both inline documentation of the code and a basic tutorial that explains how a user can use the pallet for basic off-chain functionality.                                              |
| 0c.    | Testing Guide                             | The code will have unit-test coverage (min. 70%) to ensure functionality and robustness. In the guide we will describe how to run these tests                                                          |
| 0d.    | Sample Node & Frontend                    | We will document and provide a node and frontend for a trivial use case that integrates our pallet based off the Substrate Node Template and the Substrate Front End Template.                         |
| 1.     | Skynet Off-Chain Worker Pallet (Skyfiles) | We will create a pallet to interact with Skynet from an off-chain worker. For Milestone 1, this will include uploading and downloading immutable files from Skynet using content-addressable skylinks. |

### Milestone 2 - Skynet Immutable Off-Chain Storage Pallet (Mutable Data Functionality)

- **Estimated Duration:** 1 month

| Number | Deliverable                                                 | Specification                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ------ | ----------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0a.    | License                                                     | MIT                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 0b.    | Documentation                                               | We will expand the documentation from Milestone 1 to include SkyDB & registry usage for mutable data.                                                                                                                                                                                                                                                                                                                                              |
| 0c.    | Testing Guide                                               | The code will have unit-test coverage (min. 70%) to ensure functionality and robustness. In the guide we will describe how to run these tests                                                                                                                                                                                                                                                                                                      |
| 0d.    | Sample Node & Frontend                                      | We will expand the sample node and client frontend from Milestone 1 to illustrate usage for storing mutable data on Skynet using SkyDB and the registry.                                                                                                                                                                                                                                                                                           |
| 1.     | Skynet Off-Chain Worker Pallet (SkyDB & registry expansion) | We will extend the pallet from milestone 1 to interact with Skynet's mutable storage layer, a key-value database called SkyDB. This allows getting and setting JSON files and uses public/private key combinations for access-control. This will also contain functionality for generating keys from seed phrases that is interoperable with Skynet's Javascript SDK. This requires the use of a lower-level Skynet component called the registry. |
| 3.     | Skynet Off-Chain Worker Pallet (Verification)               | We will extend the pallet from milestone 2 allow for two important features: Verification of storage proofs for full end-to-end trustless infrastructure, and, pending Substrate's addition of long-running off-chain workers, subscribing to changes of SkyDB entries using Websockets                                                                                                                                                            |

### Milestone 3 - Skynet Immutable Off-Chain Storage Pallet (Trustless Data Verification & Subscription)

- **Estimated Duration:** 1 month

| Number | Deliverable                                   | Specification                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------ | --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 0a.    | License                                       | MIT                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 0b.    | Documentation                                 | We will expand the documentation from Milestone 2 to include data verification of Skyfiles downloaded from Skynet.                                                                                                                                                                                                                                                                                                                                                       |
| 0c.    | Testing Guide                                 | The code will have unit-test coverage (min. 70%) to ensure functionality and robustness. In the guide we will describe how to run these tests                                                                                                                                                                                                                                                                                                                            |
| 0d.    | Sample Node & Frontend                        | We will expand the sample node and client frontend from Milestone 2 to illustrate usage for verifying data taken from Skynet. We also intend to lay the groundwork for subscribing to SkyDB updates, pending the progress of long-running off-chain workers.                                                                                                                                                                                                             |
| 1.     | Skynet Off-Chain Worker Pallet (Verification) | We will extend the pallet from milestone 2 to allow for two important features: Verification of storage proofs for full end-to-end trustless infrastructure, and, pending Substrate's addition of long-running off-chain workers, subscribing to changes of SkyDB entries using Websockets. If this functionality is not yet in place for FRAME, we hope to work with core developers to prepare for implementing this functionality when the feature becomes available. |

### Community engagement

Skynet has a very active developer community, and we'll be sure to create various content around the integration, including promotional write-ups and a highlight video as part of our SiaTV YouTube content.

We engage general audiences and developer audiences with our outreach media, and we'd include content for each audience.

## Future Plans

Skynet Labs will continue to develop Skynet by furthering integrations with blockchain projects needing decentralized, off-chain storage and front-end hosting, while also supporting client-facing applications that fall outside of blockchain programming. Our goal is that the data for these use-cases becomes increasingly interoperable and give users empowerment over their data. Our medium-term plans include user portal accounts and a robust monetization ecosystem.
