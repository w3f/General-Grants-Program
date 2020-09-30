# General Grant Proposal

* **Project:** Governance OS

## Project Overview :page_facing_up: 

### Overview

The goal of this project is to build a set of governance runtime pallets to help manage organizations and simulate or implement governance models. Unlike existing pallets from the ecosystem, these would be general purpose modules so that a substrate based chain could host a potentially infinite number of organizations created by its users. This could be used to support more complex multi signatures wallets, handle votes, create DAOs or even use those to manage cities or countries one day (this could probably fit the `Public Voting System` part of the Polkadot Stack).

I started my career as the CTO of a company called BitNation that was seeking to use Blockchain based tools to help governments and nations be more efficient. This is when I first got interested in governance and its surrounding ecosystem. Sadly, BitNation didn't reach its goals but my interest for that problem stayed the same. Lately, I have been putting together something called the `Governance Research Institute` to research for better ways to organize ourselves but also see if there are any products we could already apply to the real world. As a substrate developer I have played around with its modules and ecosystem, but sadly we still seems to lack some tools and pallets to actually create and manage organizations. I'd like to fill that gap for the ecosystem as this is something I am passionate about. Think of it like enabling the possibility to create a DAO as a service parachain which other projects could rely, or they could just integrate with the pallets.

### Ecosystem Fit 
I was able to identify the following similar projects / pallets which are listed below, along with why they are different from this:
- there are various pallets that parachains can use to create their own governance model (aka `democracy`, `collective`...), however they are limited to the parachain itself. Sometimes, people may want their users to be able to create those for themselves too.
- `sunshine` is building some modules for this too, however they also seems to be limited to a parachain's governance model.

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
I currently serve as the Chief Blockchain Architect of Nodle and am building Nodle’s architecture and systems. Prior to joining Nodle, I was the CTO of BitNation and led the development of multiple smart contract based governance tools and released the world’s first smart contract for marriages on the Ethereum blockchain.

Interesting code:
- [The Nodle Chain](https://github.com/NodleCode/chain) is the chain code for Nodle which I am single handedly developing. In this repo I'd like to highlight the [amendments](https://github.com/NodleCode/chain/tree/master/pallets/amendments) pallet that we use as part of Nodle's governance model, this allows a technical committee to submit "amendments" to the chain (i.e. root calls such as upgrades) that can be reviewed and vetoed by a root committee.
- [pallet-mandate](https://github.com/ETeissonniere/pallet-mandate) is a substrate pallet that gives other pallets like the `collective` the ability to send root calls.
- [ETHLove](https://github.com/ETeissonniere/ETHLove) hosts the marriage smart contract mentioned before.
- [ObsidianSafe](https://github.com/ETeissonniere/ObsidianSafe) is a set of contracts to create a Gnosis Safe like wallet on Ethereum.

### Team Code Repos
* https://github.com/NucleiStudio will be where the code for this projects will be hosted.
* https://github.com/ETeissonniere is my personal github, feel free to look around.

### Team LinkedIn Profiles
* https://www.linkedin.com/in/eliott-teissonniere

## Development Roadmap :nut_and_bolt: 

### Overview
* **Total Estimated Duration:** 2 months
* **Full-time equivalent (FTE):**  1 
* **Total Costs:** $20,000, open to receiving a part of funds in DOTs.

### Milestone 1 - Base pallets to represent the core functionalities of an organization
* **Estimated Duration:** 1 month
* **FTE:**  1
* **Costs:** $10,000

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can use the pallets through a demonstration runtime / node. |
| 0c. | Testing Guide | The code will have proper unit-test coverage to ensure functionality and robustness. In the guide we will describe how to run these tests | 
| 1. | Substrate module: `tokens` | We will create a Substrate module to let the host runtime support multiple tokens. Users will be able to create new tokens and send transactions, an entity could be created the possibility to mint or burn tokens. We will try to maintain some kind of API compatibility with existing pallets from Parity and Acala. |  
| 2. | Substrate module: `bylaws` | We will create a Substrate module that will let the host runtime and its users create a set of "bylaws" (permissions) to create rules that a given address need to comply with before triggering certain actions (for instance, "only bob can mint new tokens" or "we need 30% of the token holders to agree to burn some tokens"). |  
| 3. | Substrate chain | Modules `tokens` and `bylaws` of our custom chain will interact in such a way that users are able to create and manage bylaws that could potentially be linked to tokens, and maybe votes. |  
| 4. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Milestone 2 - Organizations Creation and Maintenance
* **Estimated Duration:** 1 month
* **FTE:**  1
* **Costs:** $10,000

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can use the pallets through a demonstration runtime / node. |
| 0c. | Testing Guide | The code will have proper unit-test coverage to ensure functionality and robustness. In the guide we will describe how to run these tests | 
| 1. | Substrate module: `organizations` | We will create a Substrate module that will use the other pallets to create and manage a full featured organization with its own governance parameters. People will be able to create an organization, potentially delete it and interact with it in accordance to the linked bylaws. |  
| 2. | Substrate chain | Modules `tokens`, `bylaws` and `organizations` of our custom chain will interact in such a way that users are able to create and manage their own organizations with their own bylaws, voting tokens and parameters. |  
| 3. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Community engagement

As part of the Program, we require that you produce an article/tutorial and publish it (for example on [Medium](https://medium.com/)). It will explain the work performed during the grant. We'd also like to do a small series of tutorials to explain how to use the modules to setup different kinds of organizations (an improved multisig wallet, a trust fund, a business, a city council...). 

## Future Plans
The future plans would be to onboard one or two more team members to create a dashboard to easily interact with the pallets. We'd also bundle all the pallets in a governance focused parachain in order to provide the following: easy simulation of different governance models (ideally as research by the Governance Research Institute or other actors), DAO / next gen multisig as a service platform that people can use to setup their own structures (and why not, control their other parachains).

Ideally, we'd continue these efforts and end up with a full featured suite focused on DAOs and Open Government initiatives with a set of dashboard and blockchain tools.

## Additional Information :heavy_plus_sign: 
* **What work has been done so far?** No code was written yet, only some architecturing work was performed. As well as some simple research of existing governance models (Polkadot, Kusama, Nodle and Aragon).
* **Are there any teams who have already contributed (financially) to the project?** Not yet, this project is entirely self funded and in a bootstrapping phase.
* **Have you applied for other grants so far?** I am representing Nodle for a grant we completed and as part of the Substrate Builder Program. The project and company (which is mine, not Nodle) linked to this application didn't apply to any grants previously.
* **What is the project's relationship with Nodle?** This project is not linked to Nodle in any way and represents a set of efforts I am pushing individually with the hope they can turn in something bigger over time.