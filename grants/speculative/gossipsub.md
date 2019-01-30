# Gossipsub

## Project Description

* A scalable, efficient, extensible baseline pubsub (publish-subscribe, messaging) protocol for p2p networks and decentralized applications on top of them. See [here](https://github.com/libp2p/rust-libp2p/pull/767) for more information.
* An indication of why this project is good for the ecosystem: his gossipsub implementation in Rust, once complete, will be scalable for decentralized, p2p networks, unlike floodsub, and is thus suited for networks that aim to be mainstream.
* An indication of how you will integrate this project into Substrate / Polkadot: I've been working on it since June, to integrate into rust-libp2p (which is used by Substrate and thus by Polkadot).
* An indication of why your team is interested in creating this project: it's just me. You can't really have a scalable p2p network without a scalable p2p library.

## Team members
James Ray

## Team Website	
Not created specifically for gossipsub.

## Legal Structure 
Individual

## Team's experience
CV: https://sustergy.wordpress.com/cv/.

## Team Code Repos
https://github.com/libp2p/rust-libp2p/pull/767

## Team LinkedIn Profiles
https://www.linkedin.com/in/jameschristopherray/

## Development Roadmap
I've already worked on this since June, preparing and implementing, and adapting to the now stabilized API. Finish developing the spec, which includes methods for leave and heartbeat. Write tests. Request review to merge. Make any suggested changes, if needed. ETA for completion: 1–3 months. Implement in a live network (I plan to implement with Ethereum 2.0).
* Indicate the amount of funding required. Both the amount per milestone and the total amount. Total amount: $100,000 AUD. However, since this project may be used by any p2p network, I'm not expecting the funding to be derived from just one entity. This amount also factors in that I have worked in the Ethereum sector since roughly June 2017, with only (30 ETH (sold for $4.3k AUD to buy a high-end computer for fast compilation) received so far from a generous member of the community)[https://twitter.com/peterk/status/1089689124989210626]. Granted, a significant portion of this time has been spent learning, but see my [CV](https://sustergy.wordpress.com/cv/) for productive contributions.
* If the team would consider part payments in fiat and/or dots then please suggest a percentage here. My first response is yes, I would consider. However, I can't see whether DOTs are on an exchange yet. In frankness, saving up to buy a studio so I don't have to pay for rent is probably my most important financial priority at the moment. After that, I'll be more inclined towards riskier, illiquid investments, but I already put 100 ETH in SKRAPs back in ~Jan 2018, which was a rash decision. 5 ETH or less would've been OK.
* What are the team’s long-term plans and intentions after the grant has been awarded? As stated, finish gossipsub, then work on Ethereum 2.0, 3.0, etc. Working on Ethereum could take 10 years until it is sufficiently good and stable not to need more improvements and there are then other projects that look like they could be more useful, e.g. implementing liberal radicalism, p2p energy markets like Grid+, decentralized search engines, reputation systems, UX improvements like with Tenzorum, etc.

## Licensing
Please indicate the type of license that will be used for this project.

In order to successfully receive grant funding for your application it is necessary for the project to have **open source** code. As an example, it would be fine to use the GNU GPL v3 license.

At the moment I have no license, but my code is openly available at https://github.com/libp2p/rust-libp2p/pull/767. The reason for this is to protect myself as I am poor at the moment. Once $100K has been raised, I will be happy to change the license to CC0, defaulting to MIT if CC0 is not deemed to be legally applicable in a particular jurisdiction, and then defaulting to GNU GPL v3. Indeed, the public can have my word that I will change to such a license once I receive $100k. Lying or reneging on my words would be unwise, from a spiritual and moral perspective and because it would affect my reputation and ability for people to trust me.

## Additional Information
Any additional information that you think is relevant to this application.

These bullet points won't be applicable to all projects. Some of the information may have already been included in the description section, if so then no need to state it again.

* What work has been done so far? See above.
* Are there are any teams who have already contributed (financially) to the project? See above.
* Have you applied for other grants so far? Yes, with the Ethereum Foundation, Gitcoin Grants, and Protocol Labs. Protocol Labs only award grants prospectively, and did not award. Haven't heard back from the other two yet, while I applied two weeks ago and a week ago, respectively.
* Are there any other projects similar to yours? See below.
* How is your project different? Gossipsub has already been implemented in Go at https://github.com/libp2p/go-libp2p-pubsub/blob/master/gossipsub.go. But Rust is better for long-term all-roundedly good software. https://www.rust-lang.org/. There are also some implementation details that are different between the two projects, e.g. using hashes instead of IDs; returning objects when expecting to do something with them, e.g. grafting peers to topics, but the graft isn't completed, etc.
