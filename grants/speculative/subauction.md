# General Grant Proposal

* **Project:** Subauction

## Project Overview :page_facing_up: 
In Ethereum, NFT industry really tests the limits these days, so we expect there's quite some potential exploring the space within Polkadot ecosystem.

Inspired by parachain candle auction mechanics, we started working on a prototype of NFT auction system while participating in Encode hackathon (awarded 2nd place in Polkadot category).

This document describes a vision for NFT marketplace platform built on top of NFT infrastracture projects being developed now for Polkadot.

We believe the ecosystem might benefit from more generic implementation of our initial prototype of NFT auctions with English auction type. Also we'd like to take a different path than most of the projects built on Ethereum and apply a curated quality-over-quantity approach.

### Project Details 

What we already accomplished:
* Classic English auction type (creation, bidding, removal)
* NFT minting using ORML pallet and NFT standard schema
* Media integration with upload to IPFS
* NFT and funds locking on the network
* Development of our custom auction UI

#### Candle Auction Type

Candle auction is a variant of the English auction where the last part of the auction is randomized in the sense that it can be concluded anytime. This prevents bidders from leaving their bids to the last few minutes or seconds and it's actually more fair in the internet environment where bots can bid on behalf the buyers. Configuration of such an auction will be very similar to the English one.

#### Top-up Auction Type

This is a very popular auction type used by charities. Each participant will pay a "top-up fee" which is based on the bid he made minus the closest lower bid to his one. Which effectively means that each participant will pay the top-up fee except the first and the last bidder. The last bidder wins the auction, obtains the item and only pays the item's price. What's more we believe that bringing this kind of auction type enables entities to raise funds for good causes so that we can connect socially responsible projects with supporters and philantropists.

#### Governance & Content Curation
As stated in the project overview, we're strong believers of quality over quantity approach. We'd also like to re-introduce the concept of scarcity and exclusivity in NFT space which is slowly fading out in Ethereum world from our point of view. To make that happen, we'd set up DAO for content curation where we would initially serve as the curators to avoid possible abusive content and eventually allow community to participate.

#### Business Model Mechanics
To keep on moving this project forward, we obviously need predictable revenue streams to secure resources of different parts of our NFT marketplace such as content curation, new NFT content partnerships and of course ongoing product development. We'll research applicable business models and go-to-market strategies that align with our overall vision of NFT marketplace.

#### Application UI
Finally, we need easy and enjoyable user interface so we can develop long-term relationship with our users. We will build the application interface where people can mint own NFT tokens, put them on sale via different auction types, browse existing auctions and participate by bidding.


### Ecosystem Fit 
Rather than to compete with already being developed NFT ifrastructure projects, we aim to build the NFT marketplace solution for end users to create and participate in NFT auctions of different types.

## Team :busts_in_silhouette:

### Team members
* Michael Repetny (Product dev at Subauction, previously co-founder of web analytics Zeerat, graduate of University of Economics)
* Petr Mensik (Blockchain dev at Subauction, previously BI engineer, graduate of Brno University of Technology)
* Jindrich Zeleny (Blockchain dev at Subauction, previously backend engineer, graduate of Brno University of Technology)

### Team Website	
* https://polkadotters.medium.com/

### Legal structure	
* LLC in the Czech Republic

### Team's experience
We participated in the Encode hackathon winning 2nd prize in Polkadot category and we also made a suggestion to existing orml-nft to expose a trait to be consumed with other pallets (https://github.com/open-web3-stack/open-runtime-module-library/issues/347). Our team members are also graduates of Substrate Runtime Developer Academy. Last but not least, we run the biggest Polkadot community in Czechia (Polkadotters) where we gather valuable market feedback.

Besides blockchain development, each member has 5+ years experience in Computer Science in different areas such as BI, software development and entreprise-grade engineering.

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

### Milestone 3: Governance & Content Curation
...

### Milestone 4: Research Business Model Mechanics
...

### Milestone 5: Implement NFT marketplace application UI
...

### Community engagement

We plan to inform on our progress after each Milestone delivered via our already established community engagement channels such as https://polkadotters.medium.com, https://twitter.com/Polkadotters1 and https://www.facebook.com/groups/232197797602358/

## Future Plans
Please include the team's long-term plans and intentions.
