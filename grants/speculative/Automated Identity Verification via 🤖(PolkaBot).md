# Automated Identity Verification via 🤖(PolkaBot)

## Proposal description
### The project
  
Polkadot and Kusama offer a novelty feature: on-chain governance. It means that anyone can, on-chain, influence how the chain will behave. This could be done for instance by proposing to swap the current runtime with a new version adding/removing/changing features. 

To empower frequent and constructive use of on-chain governance, trust is a necessary ingredient. Otherwise, proposals for critical modifications by previously created pseudo-anonymous accounts would likely not get the necessary number of votes, even if the changes might be beneficial for the network. 

It may help, however, if the account is linked to a real person with a known and proven history. This can be done by an automated, reliable and easy to use identity verification process, which is the ultimate goal of this project. 

These are the components characterizing the concept:

*  Riot as the user interface
*  🤖 as the guiding registry assistant
*  Challenges which verify links between Kusama address and e-mail, riot and twitter


### Why is this project good for the ecosystem
 
We believe that identity is a very important feature. It will be in high demand especially when businesses start using Polkadot. However, to bring added value the validation process needs to be more secure and as comfortable for the user as possible.

That's why we propose an automated identity verification process.

No one has neither time nor motivation to perform manual verification. With the growing popularity of the network, the problem will become more apparent, putting the whole ecosystem at risk. 
 

### How will we integrate this project into Substrate / Polkadot

We are not developing something that will directly be integrated into Substrate. Instead, we are creating an external module. The connection to Polkadot is done with the Polkadot.js libraries. 

### Why is our team interested in creating this project

Wilfried Kopp (Chevdor), is currently operating Registrar #1 and therefore personally involved in the topic. He is also the author and main maintainer of 🤖 which provides first-hand knowledge regarding the integration.

Furthermore we, KI decentralized, want to further support the development of Polkadot as we think it is one of the most interesting Blockchain Projects out there and we want to see it unleashing its full potential, especially with corporate users.

## Grant Team
### Team members

* Wilfried Kopp aka. chevdor
* Constantin Vennekel
* Viktor Freudenhammer



### Team Website	

The KI decentralized website can be found at [KI decentralized](https://www.ki-decentralized.com).

### Legal Structure 

    KI decentralized GmbH
    Mittelstrasse 12-14
    50672 Köln


### Team's experience

> Please describe the team's relevant experience.  If the project involves development work, then we'd appreciated it if you can single out a few interesting code commits made by team members on their past projects.


KI decentralized GmbH is a Blockchain implementation partner focussed on developing DLT applications. Most of the team members started exchanging ideas about Blockchain on numerous Bitcoin Cologne Meetups as early as 2013. This led eventually to the foundation of KI decentralized in February 2017.

Since then, our team gathered project experience with business leaders such as Commerzbank, Daimler, Lanxess and LBBW and technologies such as Bitcoin, Ethereum, Corda, Hyperledger, Polkadot, Lightning & Raiden.


**Wilfried Kopp** aka. **Chevdor** is a Polkadot Ambassador, an active validator and the current operator of Registrar #1. He is also the author of PolkaBot.

He experimented and contributed the ecosystem since its launch and ran nodes such as `Crash Override`, `Acid Burn`, `Zero Cool`.

He has also made the original Docker images for Polkadot and Substrate: 
- [Docker Hub](https://hub.docker.com/u/chevdor)
- [Chevdor Homepage](https://www.chevdor.com/)
- [PolkaBot Repo](https://gitlab.com/Polkabot/polkabot)
- [Srtool: Runtime Verifier](https://gitlab.com/chevdor/srtool) + [article](https://www.chevdor.com/tags/srtool/)

**Constantin Vennekel** has expertise in Bitcoin, Lightning, and Ethereum. He does run Polkadot nodes since PoC1, (Kusama: `ConTa 4 Polka`, `🚀 ConTa 🚀`).

**Viktor Freudenhammer** is a Product Owner and Consultant with expertise in syncing business needs with technology offers.

### Team Code Repos
* [Polkadot PRs](https://github.com/paritytech/polkadot/pulls?utf8=%E2%9C%93&q=is%3Apr+author%3Achevdor)
* [Substrate PRs](https://github.com/paritytech/substrate/pulls?utf8=%E2%9C%93&q=is%3Apr+author%3Achevdor)
* [Polkadot.js UI PRs](https://github.com/polkadot-js/apps/pulls?utf8=%E2%9C%93&q=is%3Apr+author%3Achevdor)
* [Polkadot.js API PRs](https://github.com/polkadot-js/api/pulls?utf8=%E2%9C%93&q=is%3Apr+author%3Achevdor)


### Team LinkedIn Profiles
* [Wilfried Kopp](https://www.linkedin.com/in/wilfriedkopp/)
* [Constantin Vennekel](https://www.linkedin.com/in/constantin-vennekel-b80a38b4/)
* [Viktor Freudenhammer](https://www.linkedin.com/in/viktor-freudenhammer/)

## Development Roadmap
The Roadmap can best be understood with the following diagram:

![Flow Diagram](https://i.imgur.com/0SlcGi9.png)

### Milestone 1: Start of the identification process - 2 weeks - EUR 7'000

Milestone 1 covers the development of groundwork and the set-up of the identification process.

* [ ] Setup environment & dev. tools
* [ ] Definition of the 🤖 commands
* [ ] Set standards for interacting with 🤖 during the registration 
* [ ] 🤖 answers the user and checks account validity
* [ ] Documentation

### Milestone 2: 🤖 Identification & Challenges - 2 weeks - EUR 7'000

Milestone 2 focuses on the challenge process itself, from initiating it, defining the challenges and sending them to the user.

* [ ] concept and format for Email, Riot & Twitter challenges 
* [ ] `requestJudgement` flow (ask the user, check, move on ...)
* [ ] 🤖 keeps user verification states

### Milestone 3: Challenge check & outcome handling - 2 weeks - EUR 7'000

In Milestone 3, we deal with challenge checks and the handling of the outcomes.

* [ ] Handle challenge check failures
* [ ] 🤖 checks the signatures
* [ ] 🤖 provides feedback on the verification status to the user
* [ ] Produce an explanatory video
 

### License 

The plugin will be developed under `Apache 2.0` license.

### Further plans:

We have many ideas to improve the process and will be happy to investigate further after completion of this initial proposal.

Among the ideas for improvement, we can already mention features that improve:
- user experience 
- security for companies, developers and Polkadot users 
  

## Additional Information

> Any additional information that you think is relevant to this application that hasn't already been included.

n/a

> Possible additional information to include:
> What work has been done so far?

- system design
- flow definition
- technical choices


> Are there are any teams who have already contributed (financially) to the project?

No.

> Have you applied for other grants so far?

No, we haven´t applied for any other Polkadot Grant.

> Are there any other projects similar to yours? If so, how is your project different?

There is no other project which is tackling the automated identity verification process at the moment (as far as we are aware of).
