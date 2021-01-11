# General Grant Proposal

* **Project:** Governance OS Voting

## Project Overview :page_facing_up: 

### Overview

The goal of this project is to extend the [previously performed work on the Governance OS](https://github.com/w3f/General-Grants-Program/blob/master/grants/speculative/nuclei_governance_os.md) with a set of voting focused pallets. We will focus on building some pallets we have seen missing from the ecosystem and also on unifying their APIs in order to support their integration with other pallets from the ecosystem. Having a unified and standardized API for voting pallets is crucial to the Governance OS as we want to let people swap their organizations to whatever voting system they may want.

Namely, we will focus on the following:
1. Reference Liquid Demoracy pallet.
2. Quadratic Voting extension to the previous pallet.
3. Conviction Voting pallet.
4. Collusion Resistant scheme in the form of a Partial Lock Commit Reveal (PLCR) voting pallet.

### Ecosystem Fit 
The ecosystem already has some voting focused pallets in place, however they seem to suffer from the following issues:
- They are tightly coupled to non voting focused code. For instance the `democracy` and `collective` pallets also have to support things related to members selection, referendums, vetos etc...
- None of them are instantiable by runtime users, they need runtime developers to manually configure them. In our case, we want to let users create their own organizations with the voting system of their choosing without having to code a custom runtime.
- Their APIs are not uniform, meaning that they cannot be transparently swapped between each others. This makes sense for them as they are tightly coupled to other features as previously outlined but may be an issue when building more modular systems.

## Team :busts_in_silhouette:

### Team members
* Eliott Teissonniere
* More people may join later on

### Team Website	
* https://nuclei.studio
* https://governanceresearch.institute

### Legal Structure 
Nuclei Studio is an Estonian based company under the `OÜ` status (Private Limited Company).

### Team's experience
I built my own consultancy and blockchain development studio under the name of Nuclei. I currently contract with both Nodle and Ternoa as their Blockchain Architect and help them build their own Substrate based parachains.
Prior to this, I was the CTO of BitNation and led the development of multiple smart contract based governance tools and released the world’s first smart contract for marriages on the Ethereum blockchain before freelancing for over two years.

Interesting code:
- [Governance OS](https://github.com/NucleiStudio/governance-os) previous work funded by a Wave 8 grant and which we plan to expand with more features through this grant application.
- [The Nodle Chain](https://github.com/NodleCode/chain) is the chain code for Nodle which I am single handedly developing. In this repo I'd like to highlight the [amendments](https://github.com/NodleCode/chain/tree/master/pallets/amendments) pallet that we use as part of Nodle's governance model, this allows a technical committee to submit "amendments" to the chain (i.e. root calls such as upgrades) that can be reviewed and vetoed by a root committee.
- [Ternoa Chain](https://github.com/capsule-corp-ternoa/chain) contains some early implementations of a NFT like pallet and features related to the safe storage of data linked to the NFTs.
- [pallet-mandate](https://github.com/ETeissonniere/pallet-mandate) is a substrate pallet that gives other pallets like the `collective` the ability to send root calls.
- [ETHLove](https://github.com/ETeissonniere/ETHLove) hosts the marriage smart contract mentioned before.
- [ObsidianSafe](https://github.com/ETeissonniere/ObsidianSafe) is a set of contracts to create a Gnosis Safe like wallet on Ethereum.

### Team Code Repos
* https://github.com/NucleiStudio/governance-os will be where the code for this projects will be hosted.
* https://github.com/ETeissonniere is my personal github, feel free to look around.

### Team LinkedIn Profiles
* https://www.linkedin.com/in/eliott-teissonniere

## Development Roadmap :nut_and_bolt: 

### Overview
* **Total Estimated Duration:** 3 months
* **Full-time equivalent (FTE):**  1 

### Milestone 1 - Liquid Democracy and Quadratic Voting
* **Estimated Duration:** 1 month
* **FTE:**  1

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can use the pallets through a demonstration runtime / node. |
| 0c. | Testing Guide | The code will have proper unit-test coverage to ensure functionality and robustness. In the guide we will describe how to run these tests | 
| 1. | Substrate module: `liquid-voting` | We will create a Substrate module to let the host runtime support the creation of organizations with a liquid democracy scheme, along with an optional mathematical function to configure a quadratic voting style cost computation feature. |  
| 2. | Substrate chain | A demonstration chain and runtime will be provided for testing and reference purposes. |  
| 3. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Milestone 2 - Conviction Voting
* **Estimated Duration:** 1 month
* **FTE:**  1

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can use the pallets through a demonstration runtime / node. |
| 0c. | Testing Guide | The code will have proper unit-test coverage to ensure functionality and robustness. In the guide we will describe how to run these tests | 
| 1. | Substrate module: `conviction-voting` | We will create a Substrate module to let the host runtime support the creation of organizations with a conviction voting scheme. |  
| 2. | Substrate chain | A demonstration chain and runtime will be provided for testing and reference purposes. |  
| 3. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Milestone 3 - PLCR Voting
* **Estimated Duration:** 1 month
* **FTE:**  1

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can use the pallets through a demonstration runtime / node. |
| 0c. | Testing Guide | The code will have proper unit-test coverage to ensure functionality and robustness. In the guide we will describe how to run these tests | 
| 1. | Substrate module: `plcr-voting` | We will create a Substrate module to let the host runtime support the creation of organizations with a collusion resistant, PLCR voting scheme. |  
| 2. | Substrate chain | A demonstration chain and runtime will be provided for testing and reference purposes. |  
| 3. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Community engagement
We'd like to produce instructions on how to use the pallets created through this grant application and eventually create some medium posts to showcase them. We would also publish annoucements about our progress and potentially tweet about as we progress as well.

## Future Plans
Once this grant is complete we expect to have a solid codebase to support various voting schemes. We would like to start researching Zero Knowledge Voting schemes in the near future.

The long term plan is to onboard one or two more team members to create a dashboard in order to easily interact with the Governance OS runtime. We will also bundle all the pallets in a governance focused para{chain, thread} in order to provide the following: easy simulation of different governance models (ideally as research by the Governance Research Institute or other actors), DAO / next gen multisig as a service platform that people can use to setup their own structures (and why not control their other parachains).

Ideally, we'd continue these efforts and end up with a full featured suite focused on DAOs and Open Government initiatives with a set of dashboard and blockchain tools.

## Additional Information :heavy_plus_sign: 
* **What work has been done so far?** We already have a fully working implementation of a simplified token voting scheme as part of the Governance OS which we used to demonstrate our other pallets.
* **Are there any teams who have already contributed (financially) to the project?** We received a Wave 8 grant previously, appart from that this project is entirely self funded and in a bootstrapping phase.
* **Have you applied for other grants so far?** I am representing Nodle for a grant we completed and as part of the Substrate Builder Program. The project and Nuclei company linked to this application did receive a Wave 8 grant previously.