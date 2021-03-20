# General Grant Proposal

- **Project:** Subauction

## Project Overview :page_facing_up:

In Ethereum, NFT industry is really testing networks limits these days, so we expect there's quite some potential exploring the space within Polkadot ecosystem.

Inspired by parachain candle auction mechanics, we started working on a prototype of NFT auction system while participating in Encode hackathon (awarded 2nd place in Polkadot category).

This document describes a vision for NFT marketplace platform built on top of NFT infrastructure projects being developed now on Polkadot.

We believe the ecosystem might benefit from more generic implementation of our initial prototype of NFT auctions with English auction type. Also, we'd like to take a different path than most of the projects built on Ethereum and apply a curated quality-over-quantity approach with some specific features available in the Polkadot ecosystem.

### Project Details

What we already accomplished:

- English auction type (creation, bidding, removal)
- NFT minting using ORML pallet and NFT standard schema
- Media integration with upload to IPFS
- NFT and funds locking on the network, exchange of those funds
- Development of our custom auction UI

#### Candle Auction Type

Candle auction is a variant of the English auction where the last part of the auction is randomized in the sense that it can be concluded anytime. This prevents bidders from leaving their bids to the last few minutes or seconds and it's actually more fair in the internet environment where bots can bid on behalf the buyers. Configuration of such an auction will be very similar to the English one.

#### Top-up Auction Type

This is a very popular auction type used by charities. Each participant will pay a "top-up fee" which is based on the bid he made minus the closest lower bid. Which effectively means that each participant will pay the top-up fee except the first and the last bidder. The last bidder wins the auction, obtains the item and only pays the item's price. We believe that bringing this kind of auction type enables entities to raise funds for good causes so that we can connect socially responsible projects with supporters and philanthropists.

#### Governance & Content Curation

As stated in the project overview, we're strong believers of quality over quantity approach. We'd also like to re-introduce the concept of scarcity and exclusivity in NFT space which is slowly fading out in Ethereum world in our point of view. To make that happen, we'd set up DAO for content curation where we would initially serve as the curators to avoid possible abusive content and eventually allow community to participate.

#### Business Model Mechanics

To keep on moving this project forward, we obviously need predictable revenue streams to secure resources of different parts of our NFT marketplace such as content curation, new NFT content partnerships and of course ongoing product development. We'll research applicable business models and go-to-market strategies that align with our overall vision of NFT marketplace.

#### Application UI

Finally, we need easy and enjoyable user interface so we can develop long-term relationship with our users. We will build the application interface where people can mint own NFT tokens, put them on sale via different auction types, browse existing auctions and participate by bidding.

### Ecosystem Fit

We aim to build consumer facing application that possibly integrates with already being developed NFT infrastructure projects and allows creating and bidding on NFT auctions of different auction types.

## Team :busts_in_silhouette:

### Team members

- Michael Repetny (Product dev at Subauction, previously co-founder of web analytics Zeerat, graduate of University of Economics)
- Petr Mensik (Blockchain dev at Subauction, previously Jva/Clojure backend developer, graduate of Ostrava University of Technology)
- Jindrich Zeleny (Blockchain dev at Subauction, previously BI engineer, graduate of Brno University of Technology)

### Team Website

- https://polkadotters.medium.com

### Legal structure

- LLC in the Czech Republic

### Team's experience

We participated in the Encode hackathon winning 2nd prize in Polkadot category. We were also in touch with Acala team managing the ORML pallets and we discussed a couple of our proposals to enhance the NFT pallet and they have actually accepted our [PR](https://github.com/open-web3-stack/open-runtime-module-library/pull/351). Our team members are also graduates of Substrate Runtime Developer Academy. Last but not least, we run the biggest Polkadot community in Czechia/Slovakia (Polkadotters) where we gather valuable market feedback.

Besides blockchain development, each member has 5+ years experience in Computer Science in different areas such as BI, software development and entreprise-grade engineering.

### Team Code Repos

- https://github.com/polkadotters/SubAuction
- https://github.com/polkadotters/SubAuction_Frontend

### Team LinkedIn Profiles

- https://www.linkedin.com/in/repetny
- https://www.linkedin.com/in/petr-men%C5%A1%C3%ADk-2566394b/
- https://www.linkedin.com/in/jindrich-zeleny

## Development Roadmap :nut_and_bolt:

### Overview

- **Total Estimated Duration:** ~3 months
- **Full-time equivalent (FTE):** 3.5
- **Total Costs:** ~70,000 USD

### Milestone 0: Implement Auction Type Generalisation + UI wireframes

See Auction Type Generalisation for definitions.

- **Estimated Duration:** 2-4 weeks
- **FTE:** 3.5
- **Costs:** $15,000
- Implement:
  - the Auction Type Generalisation from currently developed type of English auction
  - static UI wireframes to visualize intended user flow and UI mechanics
- Deliver docker-compose file to run node
- The code will have proper unit-test coverage to ensure functionality and robustness.
- Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

### Milestone 1: Implement Candle Auction Type

See [Candle Auction Type](#candle-auction-type) and [Top-up Auction Type](#top-up-auction-type) for definitions.

- **Estimated Duration:** 1-2 weeks
- **FTE:** 2.5
- **Costs:** $10,000
- Implement:
  - the Candle Auction Type, a specific type for NFT auction to prevent snipping (placing bids in the very last second to gamble the system)
  - the Top-up Auction Type, a specific type for NFT auction to prevent snipping (placing bids in the very last second to gamble the system)
- Deliver docker-compose file to run node
- The code will have proper unit-test coverage to ensure functionality and robustness.
- Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

### Milestone 2: Design interactive UI mockup

- **Estimated Duration:** 2-4 weeks
- **FTE:** 1.5
- **Costs:** $10,000
- Implement:
  - the Candle Auction Type, a specific type for NFT auction to prevent snipping (placing bids in the very last second to gamble the system)
  - the Top-up Auction Type, a specific type for NFT auction to prevent snipping (placing bids in the very last second to gamble the system)
- Deliver docker-compose file to run node
- The code will have proper unit-test coverage to ensure functionality and robustness.
- Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.
  ...

### Milestone 3: Governance & Content Curation

See [Governance & Content Curation](#governance-&-content-curation) for definitions.

- **Estimated Duration:** 2-4 weeks
- **FTE:** 2.5
- **Costs:** $20,000
- Implement:
  - the content curation system and introduce governance DAO to prevent possible abusive content
- Deliver docker-compose file to run node
- The code will have proper unit-test coverage to ensure functionality and robustness.
- Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.
  ...

### Milestone 4: Research Business Model Mechanics

See [Business Model Mechanics](#business-model-mechanics) for definitions.

- **Estimated Duration:** 1-2 weeks
- **FTE:** 1
- **Costs:** $5,000
- Implement:
  - research of applicable business model mechanics to apply to NFT marketplace
  - adjust program to match changes suggested by business model perspective of introduced mechanism design
- Deliver docker-compose file to run node
- The code will have proper unit-test coverage to ensure functionality and robustness.
- Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.
  ...

### Milestone 5: Implement NFT marketplace application UI

See [Application UI](#application-ui) for definitions.

- **Estimated Duration:** 2-4 weeks
- **FTE:** 2
- **Costs:** $10,000
- Implement:
  - frontend application (React/TS) to provide user facing interactivity to our blockchain program
  - views: create auction, wallet sign in, bidding mechanism and listing mechanics
- Deliver docker-compose file to run node
- The code will have proper unit-test coverage to ensure functionality and robustness.
- Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.
  ...

### Community engagement

We are well positioned within Polkadot ecosystem to create our own product since we started Polkadotters community that is currently having over 4k members and supporters. Therefore we will have plenty of space to carefully test our product and receive valuable feedback from the community. We will also try to gather support from other Polkadot ecosystem projects since we already have a good reputation within a space and we are confident that we will be able to promote the project properly.

Our progress will be regularly published to the social media to gain enough attention and for the sake of transparency of the whole project.

Our channels

- https://polkadotters.medium.com
- https://twitter.com/Polkadotters1
- https://www.facebook.com/groups/232197797602358/

## Future Plans

We're huge fans of NFT space and really believe that Polkadot ecosystem will benefit from having NFT marketplace that can be able easily integrated into other NFT solution standards developed on Polkadot. Our end result should be a feature-specific pallet that could be pluggid in to another blockchain applications and a NFT auction marketplace site with curated content.