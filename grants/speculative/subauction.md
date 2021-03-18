# General Grant Proposal

* **Project:** Subauction

## Project Overview :page_facing_up: 
In Ethereum, NFT industry really tests the limits these days, so we expect there's quite some potential exploring the space within Polkadot ecosystem.

Inspired by parachain candle auction mechanics, we started working on a prototype of NFT auction system while participating in Encode hackathon (awarded 2nd place in Polkadot category).

This document describes a vision for NFT marketplace platform built on top of NFT infrastracture projects being developed now for Polkadot.

We believe the ecosystem might benefit from more generic implementation of our initial prototype of NFT auctions with English auction type. Also we'd like to take a different path than most of the projects built on Ethereum and apply a curated quality-over-quantity approach.

### Project Details 

What we already accomplished:
* Working prototype of the English auction (creation, bidding, removal)
* NFT minting using ORML pallet and NFT standard schema
* Media integration with upload to IPFS
* NFT and funds locking on the network
* Development of our custom auction UI

#### Candle Auction Type
#### Top-up Auction Type
#### Governance & Content Curation
#### Business Model Mechanics
#### Application UI

### Ecosystem Fit 
Rather than to compete with already being developed NFT ifrastructure projects, we aim to build the NFT marketplace solution for end users to create and participate in NFT auctions of different types.

## Team :busts_in_silhouette:

### Team members
* Michael Repetny
* Petr Mensik
* Jindrich Zeleny

### Team Website	
* https://<your_domain>

### Legal structure	
* LLC in the Czech Republic

### Team's experience
We participated in the Encode hackathon winning 2nd prize in Polkadot category and we also made a suggestion to existing orml-nft to expose a trait to be consumed with other pallets (https://github.com/open-web3-stack/open-runtime-module-library/issues/347). Our team members have also participated in Substrate Runtime Developer Academy. Last but not least, we run the biggest Polkadot community in Czechia (Polkadotters) where we gather valuable market feedback.

### Team Code Repos
* https://github.com/polkadotters/SubAuction
* https://github.com/polkadotters/SubAuction_Frontend

### Team LinkedIn Profiles
* https://www.linkedin.com/in/repetny
* https://www.linkedin.com/in/petr-men%C5%A1%C3%ADk-2566394b/
* https://www.linkedin.com/in/jindrich-zeleny

## Development Roadmap :nut_and_bolt: 

### Overview
* **Total Estimated Duration:** ~3 months
* **Full-time equivalent (FTE):**  3.5
* **Total Costs:** ~70,000 USD

### Milestone 1: Implement Candle Auction Type
See Candle Auction Type for definitions.

* **Estimated Duration:** 1 month
* **FTE:**  3.5
* **Costs:** $21,000
* Implement:
   * the Candle Auction Type, a specific type for NFT auction to prevent snipping (placing bids in the very last second to gamble the system)
* Deliver docker-compose file to run node
* The code will have proper unit-test coverage to ensure functionality and robustness.
* Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.


### Milestone 2: Implement Top-up Auction Type
...

### Milestone 3: Implement NFT marketplace application UI
...

### Community engagement

We plan to inform on our progress after each Milestone delivered via our already established community engagement channels such as https://polkadotters.medium.com, https://twitter.com/Polkadotters1 and https://www.facebook.com/groups/232197797602358/

## Future Plans
Please include the team's long-term plans and intentions.

## Additional Information :heavy_plus_sign: 
Any additional information that you think is relevant to this application that hasn't already been included.

Possible additional information to include:
* What work has been done so far?
* Are there are any teams who have already contributed (financially) to the project?
* Have you applied for other grants so far?
