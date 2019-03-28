# Self Sovereign Identity as a Polkadot runtime module following the ERC725 standard and the DIDs specification and using Verifiable Claims

## Project Description

### Introduction
This software will be licensed using GPLv3

The aim of this project is to turn Polkadot into an interconnected global Self Sovereign Id platform. Making these Ids valid and legal and build bridges between countries (p2p) for people and organisations

We will reach this adding Self Sovereign Identity as a Polkadot runtime module following the ERC725 standard and the DIDs specification and using Verifiable Claims.

Any application based on decentralised technologies needs an identity system to offer digital services and interact with the real world. Even more, they need a standard so all dapps can use the same Identity (it's interoperable) are users are protected by [criterias based on user ownership, empowerment and privacy-by-design](http://www.lifewithalacrity.com/2016/04/the-path-to-self-soverereign-identity.html). 

Having this SSI Layer compatible with the substrate technology will open a world of unprecedented lighting possibilities to develop dApps using parachains. Also from a polkadot perspective, a Universal Resolver can also be included at the Runtime.


### Technical abstract
We propose the implementation of a self-sovereign identity system on the top of Substrate and Polkadot. The functional scope of the system includes credential issuance and verification with different algorithms used for this purpose. The system follows a particular standard for W3C's verifiable credentials (with the possibility to be eIDAS and GDPR compliant in the future iterations, providing the confidentiality for personal data as well as the non-repudiation for the execution of the right to erase). While the prototype is built on IPFS and Substrate blockchains using ERC725 v2 standards and W3C DIDs & Verifiable claims specifications. In any case, the architecture is seen to be ledger agnostic.

We propose to store just a Merkle Root of the keys and credentials being held by an entity (user, organisation, etc.) and set a list standard endpoints to query and interact between entities. This way most of the information is transferred off-chain and the whole system should be GDPR compliant.

We propose an open-source implementation for Self Sovereign Identity featuring properties of decentralised public identity network. The platform uses blockchain technology as the decentralised public data infrastructure. In the future, we would like to introduce identity containers where the portable artefacts of SSI are stored, facilitating the creation of verifiable credentials in the portable format.

* DID documents
* Keys
* Verifiable credentials
* Trusted Contact (DIDs whitelist)

### Use cases
* Building your own identity as a person or organisation
* Creating new Identities controlled (owned) by yours
* Creating verifiable credentials (Proofs)
* Using the credentials to authorize against web services.
* Share the verifiable credential with a third party
* Revoke the verifiable credential

## Team members
* Alex Puig
* Jordi Piñana

## Team Website	
* https://caelumlabs.com

## Legal Structure 
We are a LLC company based in Spain.

## Team's experience
Alex Puig has been involved in the Blockchain Technology for the past seven years and involved research&development of self-sovereign identity solutions for the last 2 years. He is also the organiser of Digital Currency Summit and founder of the spanish national blockchain "Alastria".


Caelum Labs is a company with a multidisciplinary team of developers committed to build solutions using decentralised technologies like blockchain. One of our main focus now is to develop a Self-sovereign identity framework (tech&legal) to fill the missing piece needed to bring decentralised apps to the masses.

Recently we organised the Barcelona edition of Rebooting the Web of Trust last March 1st-3rd, where we also presented our proposal and created a group to develop it.

## Team Code Repos
* https://gitlab.com/caelumlabs/sikaris
* https://github.com/alexpuig
* https://github.com/jordipainan

## Team LinkedIn Profiles
https://www.linkedin.com/in/alexpuig/
https://www.linkedin.com/in/jordi-pi%C3%B1ana-pag%C3%A0-69aa1a8a/

## Intended language of development
* Rust

## Development Roadmap
We will require 2,5 months to complete this project. We intend to have 2 developers part-time, at a total cost of $29,500.

Milestones:
* Implement Module to add ERC725 Identities (week 1-2)
* Implement DIDs RUST lib implementation following the W3C standard (week 3-5)
* Implement Verifiable credentials Rust lib implementation following the W3C standard (week 6-8)
* Implement Polkadot integration and a basic implementation of an Universal Resolver (week 8-10)
* Write project documentation (week 9-10)

Ideally, we can receive part payment at the end of each milestone.

We prefer to receive the payment in FIAT but would be willing to consider part payment in DOTs, up to 25%.

We will continue the development in the future to introduce identity containers where the portable artefacts of SSI are stored, facilitating the creation of verifiable credentials in the portable format.

## Additional Information
* ["Identity Containers" paper made during the RWoT8](https://github.com/WebOfTrustInfo/rwot8-barcelona/blob/master/draft-documents/ContainerId.md) by Alex Puig, Oleg Burundukov, Miguel Fernando Jimenez Sola
* [Sikaris: An implementation proposal for a Self Sovereign Identity (SSI) network using Blockchain as a DKPI](https://gitlab.com/caelumlabs/sikaris) by Alex Puig

This project has been lead by Alex Puig for the last 6 months as a Caelum Labs project and, until now it has been funded by us, until now we didn't apply for other grants other than W3F ones.

Now we have an advanced draft of the technical proposal and legal implementations (GDPR and eIDAS) and we base our developments in other projects like Ethereum's identity and data management proposals, W3C DID'S&VC, IPFS and Matrix.
