# Encointer Testnet Cantillon
## Project Description
The Encointer Association (EA) plans to develop an Encointer testnet named “Cantillon” ([spec](https://github.com/encointer/encointer-node/blob/master/doc/TESTNET_SPECIFICATION.md)). This testnet shall become a parachain to Kusama once Kusama is ready to host parachains.
The goal of the Cantillon Testnet is to deploy a [SubstraTEE](https://github.com/scs/substraTEE)-based PoA Blockchain that allows to bootstrap local currencies and take out daily Unique-Proof-of-Personhood ceremonies as defined in the encointer [whitepaper](https://github.com/encointer/whitepaper/blob/master/encointer_whitepaper.pdf). 
A mobile phone app that allows to perform key signing meetups has already been developed for [PoC1](https://encointer.org/2019/11/10/development-update-1/).

### Benefit for Polkadot Ecosystem
Encointer enables decentralized identities (DID) to be uniquely bound to real persons. Such DID claims can be useful throughout the entire ecosystem, i.e. for social networks like [subsocial](https://devpost.com/software/subsocial) or in conjunction with [KILT](https://kilt.io/). Moreover, Encointer allows to implement local currencies - a novelty in the cryptocurrency space. As Cantillon builds on top of SubstraTEE for privacy, this testnet also serves as a real-world use case for TEE-based privacy enhancement on substrate blockchains.


## Team members

* Alain Brenzikofer: @brenzi on github, Department Head, Developer

extended team on request:
* Marcel Frei: @electronix on github, Project Manager for substraTEE, Developer
* Christian Langenbacher: @clangenb on github, SubstraTEE Developer


## Team Website
* https://encointer.org

## Legal Structure 
Encointer Association, Zürich, Switzerland

## Team's experience
Alain Brenzikofer follows Blockchain developments since 2011. He works for SCS since 2012 where he started working on blockchain projects in 2016 and was appointed to lead a new department for "Decentralized Systems" in summer 2018. As a private initiative, he designed a new cryptocurrency ecosystem [encointer - An Ecological, Egalitarian and Private Cryptocurrency and Self-Sovereign Identity System](https://encointer.org). 
With his team at SCS, he developed [SubstraTEE](https://github.com/scs/substraTEE), a privacy-enhancing trusted off-chain computing platform for substrate blockchains.

Alain presented both above projects at sub0.1 conference in Berlin 2019

## Team Code Repos
* https://github.com/encointer/encointer-node
* https://github.com/encointer/encointer-app
* https://github.com/scs/substraTEE

## Team LinkedIn Profiles
* https://www.linkedin.com/in/alain-brenzikofer-9a4480165/

## Development Roadmap
The Cantillon Testnet will be built on top of PoC1 code. (PoC1 only allows to test a single meetup using a single currency). While the business logic for PoC1 was coded as a runtime module, an extended version of this logic will be instantiated inside a SubstraTEE-worker enclave.

In order to fulfill the ([Cantillon testnet specification](https://github.com/encointer/encointer-node/blob/master/doc/TESTNET_SPECIFICATION.md)), the following tasks are planned:

*  migrate encointer-ceremonies module to SubstraTEE-worker STF
*  [scs/substraTEE-worker#70](https://github.com/scs/substraTEE-worker/issues/70) (IPFS read API for STF)
*  implement new public on-chain request new_currency(ipfs#, id)
    *   see [BOOTSTRAPPING](https://github.com/encointer/encointer-node/blob/master/doc/BOOTSTRAPPING.md) for details
*  implement multi-currency setup identified by local currency id's
*  implement daily ceremony scheduling
*  implement rules for registration
*  implement randomized meetup assignment
*  implement rules for witnessing and validation
*  implement faucet for onboarding
*  make encointer-app available on Google Play Store


### Key Testnet Differences to Encointer Whitepaper
*  no dPOET consensus. Use PoA
*  This testnet shall become a parachain to Kusama based on substrate
*  no decentralization. The Parachain will feature PoA consensus with Kusama as root-of-trust.
*  no proportional fees. Classical per-transaction base fees will be applied
*  confidential state updates will be implemented with SubstraTEE. For the sake of debugging, enclaves will NOT be run in production mode
*  no private smart contracts yet
*  ceremonies will happen daily at high sun instead of every 41 days.

### Validation
The Cantillon testnet will be validated (centralized) by the EA in order to facilitate easy upgrades and focus on the essential features instead of security.

### Milestones

#### M1: Bootstrap new local currency with bot population

Demonstrate the following success scenario:
1. Deploy Cantillon testnet validators
1. Define geo-boundaries of new local currency for test-bots
1. Perform a bootstrapping ceremony with a group of bots
1. Grow bot population constantly with every ceremony (happening daily) to evaluate scalability (Acceptance after 5 successful ceremonies)

#### M2: Perform ceremonies with mobile phone app 

Demonstrate the following success scenario:
1. Define geo-boundaries of new local currency for the city of Zurich
1. Perform a bootstrapping ceremony with a group of people
1. Grow population until at least two meetups will be assigned and performed.

A set of tutorials will be published:
*  how to bootstrap your own local currency in your city
*  user onboarding with mobile phone app and faucet
*  how to take out meetups

#### M3: (Kusama Parachain)

Becoming a Parachain is out of scope for this proposal because details are not yet well known on how to become a parachain on Kusama. Moreover, SubstraTEE uses custom host-calls for its runtime which will not work for Parachains without modifications (only affects remote attestation of TEE’s).

### Timeline
T0: project start (upon agreement)
M1: T0 + 3 months
M2: T0 + 4 months

## Long-Term Plans
Encointer aims at becoming a parathread or parachain on Polkadot. Once the *Cantillon* testnet shows stable performance and acceptable scalability, the launch of mainnet is planned 

## Additional Information
While this application only names @brenzi as a single developer, he will employ his team at SCS (SubstraTEE) where necessary to achieve the stated goals. With increasing exposure, encointer plans to recruit more developers.
