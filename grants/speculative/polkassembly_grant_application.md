# Polkassembly

## Project Description

Polkassembly is a platform for anyone to discover and participate in Polkadot and Kusama governance. You can browse proposals made on chain, discuss with the community and vote directly from the website using a browser extension. Proposal authors are the only one able to edit the proposal post and description. You can get notifications for discussions of interest or when a new proposal appears on-chain if you choose to add your email.

Polkassembly use polkadot.js api for extracting blockchain data relevant to governance and store proposal, refrenda, motions etc in persistance storage for quick refrencing. A bot user creates posts whenever there is a new governance item created onchain. It uses polkadot.js extension for signup/login and linking address to the account. User with a linked account can edit posts proposed by him onchain. Polkassembly provides a post and comments thread to enable governance discussion for the governance action.

Using some of the off chain features users can do sentiment analysis, vote offchain, subscribe to posts etc. Polkassembly also provides onchain features as seconding proposals, voting for referendum, motions etc. Relevant data like seconds, votes are shown in realtime from chain.

Scope of this grant will include provide hosting costs for polkassembly as well as cover the costs for future development.

## Team members
* Nikhil Ranjan, Full stack developer
* Yogesh Kumar, Designer, Full stack developer

## Team Website
* Website: https://polkassembly.io
* Polkadot: https://polkadot.polkassembly.io/
* Kusama: https://kusama.polkassembly.io/
* Twitter: https://twitter.com/polkassembly

## Legal Structure
PREMIURLY ONLINE PRIVATE LIMITED (Registration Awaited)

## Team's experience
Our team has good blockchain development experience. We are familiar with Web3 and Substrate framework and polkadot ecosystem.

## Team Code Repos
* https://github.com/Premiurly/polkassembly

* https://github.com/niklabh
* https://github.com/itsyogesh

## Team LinkedIn Profiles
* https://www.linkedin.com/in/niklabh
* https://www.linkedin.com/in/itsyogesh/

### Milestone 1 — Deploy polassembly on its own infrastucture
* Take out polkassembly from parity servers.
* Create a seperate google cloud account for polkassembly deployment.
* Setup kubernetes cluster for authentication node.js server, Frontend React app, Hasura graphql server, Node watcher node js process, postgres cloud sql database.
* Create a sendgrid account for email service.
* Setup ci cd pipelines for deploying staging and production polkadot and kusama production environment.
* Create Product documentation for polkassembly.

### Milestone 2 — Add features for better governance.
* Add tech committee proposal
* Show results of past referenda
* Add events in the time-line
* Provide search feature
* Add pagination

## Future Plans
Polkassembly is a complex product, we've been building it for 9 months and we can only cover core features during the 3-month period. We will continue working on polkassembly in the future to make it more complete and mature.

We are optimistic about the prospects of Substrate and will maintain good communication with the Substrate community and developers. We are striving to provide high-quality governance services for chains based on Substrate.

### Open-source license
Each component in this grant scope will be open sourced, all required code to leverage the components in this grant scope will be open sourced as well. The license is Apache License 2.0.

## Additional Information
Polkassembly is already live and running at https://polkadot.polkassembly.io/ and https://kusama.polkassembly.io/ for polkadot and kusama respectively.
