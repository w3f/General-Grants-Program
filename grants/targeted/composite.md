# Composite IDE Grant Application

## Project Description

**Composite is an IDE that simplifies developing, debugging, and deploying smart contracts. The result is increased productivity for experienced developers and a way to enlarge the developer pool by attracting new-to-crypto developers.**

**Composite is built from the ground up for blockchain and is blockchain-agnostic. Composite is currently available as a "pre-alpha" version for Ethereum.** 

**The proposed project would add support for Polkadot, smart contracts on parachains, creating and updating Substrate runtimes, and improving the IDE itself. With the grant, two public beta versions will be released.**

We learned from interviews that blockchain development tools aren't as mature as developers like. Even the Ethereum toolchain, arguably the best in the industry, is still quite immature. 

Polkadot faces an additional and unique challenge. Polkadot introduces many new concepts and technologies (parachains, Substrate, extrinsics, etc), which create a new barrier to entry.

To increase the adoption rate of Polkadot, it is imperative to ease the transition for experienced developers and to provide the best on-boarding experience for new-to-crypto developers. Composite can play an important role in that experience.

Unlike most IDEs, Composite is built from the ground up for blockchain. This enables us to add unique features such as one-click install and update of development toolchains (which is not as trivial as it should), ABI interactions, Substrate specific UI and tools, and more.

For example, developers will be able to create a new Substrate blockchain by walking through an optional wizard that walks the developers through the basic settings of the runtime. The functions `version`, `authorities`, and `execute_block` in `lib.rs` will be emphasized so it's clear those are the three key functions that might need customization. We will add templates for new rs files. Even subkey generation and management should be handled from with Composite. Basically, developers shouldn't be forced to fall back to the command line, and they should not have to read the manual to get started.

We will actively seek feedback from Polkadot users during development and will use their feedback to improve the product and adjust direction.

A complete list of developers interviewed, partnerships, and the confirmed grant is available in the Google doc. A video of the current pre-alpha version of Composite with support for Ethereum [can be seen here](https://www.youtube.com/watch?v=wMAC_MxOnvU).

## Team members

* Ronald Mannak
* Jorn van Dijk
* Thomas Hecker
* Additional help from several freelancers and technical contributors

## Team Website	

Don't have one yet.

## Legal Structure 

California LLC

## Team's experience

* Ronald is a Bay Area-based open source developer of Swifthereum, JSON-RPC Codable, NaiveSwiftCoin, and other frameworks. Ronald co-founded crypto startup Coral, and two (non-crypto) hardware startups. He worked as consultant to FirstCoin. His PhD research topic was trust in P2P networks (not finished). Ronald has 9 years of iOS and MacOS development, several years of C development and UX design before that. 
* Jorn and Ronald are former college roommates and worked together at two different startups. Composite is the third project they're collaborating on. Jorn has over 10 years of iOS and MacOS developer experience.
* Thomas started as a researcher for Fraunhofer Institute & Mercedes Benz was leading the mobile product management at Daimler’s digital transportation division Moovel. 

## Team Code Repos

* https://github.com/ronaldmannak
* https://github.com/jvdijk
* https://github.com/compositeapp

## Team LinkedIn Profiles

* https://www.linkedin.com/in/ronaldmannak
* https://www.linkedin.com/in/jornvdijk/
* https://www.linkedin.com/in/thomashecker

## Intended language of development

* Swift
* Bash

Choosing a language is per definition accepting a compromise. While many new projects use Javascript/Electron, we deliberately chose to create a native application. 

We believe native apps provide a user experience unmatched by Electron apps. Not only are native apps obviously better with it comes to performance and use of resources, native apps also automatically support the accessibility features that come with MacOS. Composite is likely the only crypto tool that can be used by developers who depend on accessibility features.

The obvious downside is a more complex port to Linux and Windows. With MacOS seemingly being the platform of choice for most developers nowadays, we provide the best experience for the largest group first, and will decide whether or not to port Composite to other platforms at a later stage.

## Deliverables

We will release at least two public betas during the six months of the project.

* Public Beta 1 
	* Goal: Basic usable version with integration of end-to-end tool chain
	* Use: to get valuable feedback from developers
	* Release: end of month 3
	* Features:
		* Initial Subtrate/Polkadot UI
	
* Public Beta 2
	* Goal: Speed, stability, and UI improvements based on feedback from Beta 1. 
	* Use: For production work.
	* Release: end of month 6
	* Features:
		* integration of latest Polkadot toolchain
		* Improved editor
		* Improved toolchain install wizard

* Long term ambition is to become the default IDE for smart contracts with support added for all major blockchains. After Public Beta 2, development on Composite will continue, with focus on improved integration with already supported blockchains and additional support for more blockchains.

## Development Roadmap

Like business plans and the waterfall model, milestones are valuable tools when used in corporate projects with almost no unknowns and uncertainties. For most startups, a roadmap too rigid is [counter-productive](https://steveblank.com/2009/08/31/the-customer-development-manifesto-reasons-for-the-revolution-part-1/
), as lean-startup promotor Steve Blank states.

Rigid milestones and detailed cost estimates are not a great fit for creating a tool for a new revolutionary blockchain platform that hasn't launched yet, that has no current users, incomplete documentation, and is actively under development (even during the Christmas week [five commits](https://github.com/paritytech/Substrate/graphs/commit-activity) were pushed to the repo). 

Instead, we propose the following features of a minimum viable product that's achievable in six months.

* Polkadot/Substrate toolchain integration (12 weeks - $95k)
	* One click install and update of toolchain.
	* Wizard for creating new Substrate blockchains.
	* Templates for smart contracts.
	* Bash integration existing Polkadot/Substrate toolchain (compile, deploy, unit tests, subkey, and lint if available).
	* UI for interacting with toolchain, e.g. ABI (at least two iterations with user testing)
	* Templates and default Substrate files with highlighted placeholders, etc.

* Editor (8 weeks - $60k)
	* Replace existing editor module 
	* Add Rust language support
  	* Add Visual warning and error
	* Explore Auto-complete
	* Explore language server for additional languages
  
* App (3 weeks - $25k)
  * Integrate Sparkle auto update.
  * Explore sandbox for App Store compatibility.
  * Set up unit tests and continuous deployment.
  
* Documentation (1 weeks - $10k)
	* Blogpost 'Creating a Substrate blockchain in Composite'
	* In-app documentation 

* Removed from original proposal:
	* Book (possibly in a separate application)

## Grant

So far, Composite has been **completely self-funded**. Requested grant:

* **$190,000** 

For reasons stated above, it is not in the interest of W3F nor the project to tie payments to the completion of milestones. We propose a payment scheme that's independent of milestones, is fair to both parties, and gives us the flexibility needed to deliver the best product possible.

The idea is to split the grant into manageable pieces that will be paid in a fixed schedule over time, and giving W3F the power to stop the project at any time, without having to pay the remaining amount if somehow expectations aren't met.

* The grant is paid in 12 biweekly non-refundable installments during the six month project period. (If preferred, six monthly payments would work as well).
* Up to 50% of the grant is paid in Dot. E.g., a biweekly installment would be $7,916.66 in fiat plus the equivalent value in Dot. In case of monthly installments, the monthly payment would be $15,933.33 in fiat plus Dots valued $15,933.33.
* W3F can continuously track progress in the develop/w3f branch.
* Payments can be stopped any time at W3f's discretion, e.g. when W3F is not satisfied with direction or progress. The project will then be considered cancelled.


## Additional Information

* One confirmed unannounced grant (see Google form for details).
* Very early pre-alpha version with Ethereum support is available.
