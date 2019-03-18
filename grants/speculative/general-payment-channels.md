# General Payment Channels

## Project Description
Kava Labs Inc will build a general purpose payment channel implementation for the Polkadot community as a public good. This essential component to a blockchain ecosystem will provide a building block for projects and developers building with substrate and Polkadot, whether that be in practical end user payment applications, dApps seeking a faster UX for transactions, or theoretical layer 2 research projects.
We’ll provide a payment channel implementation as a substrate runtime module that is available to be integrated into any new chain using substrate.

Kava Labs is the first interledger solutions provider, working towards linking up many blockchains using the  Interledger Protocol to enable fast streaming cross chain payments. The first step in this goal is ensuring blockchains have payment channel primitives needed for fast payments. We have and are working with a number of organizations to bring payment channels and integrations to their ecosystems.

Benefits for Polkadot/Substrate:
 - adds an essential component to the Polkadot ecosystem
 - well tested, payment channel module available for anyone to use and build on
 - fast scalable payments
 - easy integration into parachains and (d)apps
 - easy onboarding to layer 2 concepts and development
 - central community focus point for expanding Substrate’s layer 2 capabilities
 - future integration with  Interledger to enable a lightning network style experience for Substrate/Polkadot chains with interoperability across the top market cap coins
 - a self contained example project for future developers - both for parachain and application layer developers


## Team members
See https://kava.io/team
 - Scott Stuart
 - Brain Kerr
 - Ruaridh O’Donnell
 - Kevin Davis
 - Kincaid O’Neil
 - Rob Laverty


## Team Website
 - https://kava.io

## Legal Structure
Provided in Google Form.

## Team's experience
See https://kava.io/team for team profiles. Kava is a blockchain research and development team, founded in 2017, that brings its expertise to develop scaling and interoperability solutions for open source communities. Kava is responsible for the development of the open source Interledger integrations for bitcoin and ethereum. Kava is currently working with leading blockchain organizations like Tendermint(Cosmos) and MakerDao to bring their communities the benefits of the Interledger network.


## Team Code Repos
 - https://github.com/Kava-Labs/
 - https://github.com/Kava-Labs/switch-api
 - https://github.com/Kava-Labs/switch
 - https://github.com/Kava-Labs/kava


## Team LinkedIn Profiles
Please see https://kava.io/team for links


## Development Roadmap
Timeline: 12 weeks

Milestones:
 - M1: Design of the payment channel architecture (3 weeks)  
   Deliverable: an architecture design customized to the polkadot ecosystem.
 - M2: Construct the payment channel module (3 weeks)  
   Deliverable: a initial release of a  payment channel module and accompanying tests
 - M3: Construct the interfaces (4 weeks)  
   Deliverable: a js library to send payment channel txs and to verify claims
 - M4: Documentation and tidy up (2 weeks)  
   Deliverable: a finished project, with developer documentation, examples, and a working demo of payment channels

Result: The code and module developed by Kava will be made open source for the Polkadot/Interledger communities to freely use and include in any project. We will include documentation and code examples to help developers and new users get started both with our module and layer 2.

Long term, our plans are to move a wide range of blockchain projects onto layer 2 and connect them using the Interledger Protocol. This involves several different areas of work, from creating the plugins into Interledger nodes, to providing access by hosting liquidity, to integrating into existing wallets.


## Additional Information
There are no similar projects on polkadot with the exception of [AdEx’s OUTPACE](https://github.com/adexnetwork/adex-protocol-substrate) who are building layer 2 payments as part of a larger application specific protocol. Whereas Adex's payment channels require the interactive signing of messages with at least two (2) off-chain validators, we are seeking to build general purpose channels for direct p2p payments. The first implementation will be undirectional, while future implementations could expand upon this one to create bidirectional channels with collaborative close, as well as routed payment channel networks.