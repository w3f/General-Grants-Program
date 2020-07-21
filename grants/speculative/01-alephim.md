# aleph.im integration

## Project Description

Aleph.im is a decentralized cloud infrastructure that works with various blockchains, and accepts multiple chains wallets and addresses schemes.

The goal of this project is to integrate the aleph.im network with the Polkadot ecosystem. So far, the aleph.im network is integrated with Ethereum, Binance Chain, NEO and NULS. 


You can have a look and test the following :
- Personal storage dApp - https://my-beta.aleph.im
- Javascript API - https://aleph-im.github.io/aleph-js/guide/getting-started.html

All of Aleph.im code is released in MIT (nodes, sdk, dApps etc.). 

Following a proposal on PolkaDAO, aleph.im conducted a feasibility study that received positive results. 

- The proposal on PolkaDAO can be accessed at https://alchemy.daostack.io/dao/0x440583455bcd85ab2bd429c015d3aabcae135f0a/proposal/0x5ad0866c7220c769dd53bba48d407f054cf52ea0d9f6d6d1c1f2a50617d4ccd1. 
- The feasibility study and integration steps can be accessed at https://my-beta.aleph.im/#/l/n/eb1197d2d6c8826dbc5acafd98383abd14e7d023e32305ba2c7e123334e6b215 (stored on the aleph.im network). 

This grant request corresponds to Steps 1 and 2 of the above feasibility study. 

## Team members

* Jonathan Schemoul (alias Moshe Malawach)
* Claudio Pascariello

## Team Website	

* https://aleph.im

## Legal Structure 

Aleph.im is a French Simplified joint stock company (‘Société par Actions Simplifiée’), registered under the number 882 412 869 with the Registry of Trade and Companies of Paris (France). The company’s address is is located at 242 Boulevard Voltaire 75011 Paris, France. Aleph.im is represented by the company’s president, Mr. Jonathan Schemoul. 

## Team's experience

The aleph.im team comprises of two members – Jonathan Schemoul (alias Moshe Malawach), Founder of the aleph.im and Claudio Pascariello, UX designer. Based on past projects on building a decentralized network and connectors to other chains, the team has the required experience to carry out this project. For more information, our Linkedin profiles can be accessed at the links below :
* https://www.linkedin.com/in/jonathanschemoul/
* https://www.linkedin.com/in/claudiopascariello/

## Team Code Repos

* https://github.com/aleph-im/pyaleph
* https://github.com/aleph-im/aleph-js
* https://github.com/aleph-im/myaleph
* https://github.com/aleph-im/aleph-client

## Team LinkedIn Profiles

* https://www.linkedin.com/in/jonathanschemoul/
* https://www.linkedin.com/in/claudiopascariello/

## Development Roadmap

Based on the feasibility study, aleph.im will handle the first two integration milestones of the project, which are to :
1. Support Polkadot/Kusama addresses on aleph.im network and dApps
2. Write hashes on Polkadot/Kusama networks (as simple transactions)

#### Milestone 1 - Polkadot addresses support - 1 month - $ 15,000

In order to achieve the first milestone, the following tasks will be done :

1. Support Polkadot/Kusama addresses on aleph.im:
    1. Implement Polkadot address derivation from public key (Python)
    2. Support standard off-chain message signatures on ED25519 (Python)
    3. Support standard off-chain message signatures on SR25519 (Python)
2. Support encryption for Polkadot/Kusama addresses:
    1. Port ECIES to ED25519 and SR25519 on Javascript for dApps
    2. Port ECIES to ED25519 and SR25519 on Python for server-side python sdk
    

#### Milestone 2 - Polkadot/Kusama write support, as an underlying chain - 1 month - $ 15,000

In order to achieve this second milestone, the following tasks will be done: 

1. Implement Polkadot transaction packing on Python (or use other language implementation, if licenses are compatible)
2. Implement API calls to a node to get transaction history
3. Write support module on PyAleph
    * write bulk aleph.im transactions on polkadot,
    * retrieve them,
    * verify hashes and signatures

## Future Plans

We want to integrate with Polkadot in an in-depth manner. This includes:
* Oracles to allow retrieval of off-chain data from the networks
* Support for identitity framework developed in collaboration with synaps.io:
  - Support Polkadot/Kusama addresses as identity source
  - Write identity data on Polkadot/Kusama
  - Set the network as a registar as per https://wiki.polkadot.network/docs/en/learn-identity
* Deeper integration with supported wallets

Those can be done as subsequent grants or other agreements.

## Additional Information

In partnership with synaps.io, aleph.im applied for a Tezos grant for integration with their network. 
