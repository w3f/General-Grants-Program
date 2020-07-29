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

### Deliverables

* node.js server for authentication system.
* Hasura graphql server for discussion posts.
* Prisma graphql server for storing on-chain data
* React application for polkasembly front end.
* Docker/Kubernetes/helm chart configuration for deployment
* ci-cd pipelines configuration for automated deployments
* mocha test suite for unit testing.
* Deployed websites https://kusama.polkasembly.io https://polkadot.polkassembly.io

### Milestone 1 - Create governance tool for discussion.

* Create a harvester service which watches a substrate node and store proposals, refrenda, motions, treasury proposals etc in a persistence database with metadata for fast access. This service will be referred as node watcher.
* Create database for discussion posts, comments, reactions.
* Create user authentication service which allows user to signup, login, add/change email, forget password, link address etc.
* User should be able to signup/login with polkadot js extension.
* Create a bot user which watches for changes in node watcher database and create a post in on chain posts section whenever there is a new proposals, refrenda, motions, treasury proposals etc proposed on chain.
* Users who have created the corresponding proposal should be able to edit the post made by bot and add detailed description. This should be done by matching linked address in polkassembly with proposer address on-chain.
* Create an Editor with markdown support to create/edit posts.
* Users should be able to second proposal, vote on referendum from within polkasembly itself.
* Users should be able to add polls to post if they want to test popularity of any proposal/motion offchain.
* Users should be able to comment on posts.
* Users should be able to react on posts with upvote downvote.
* User should be able to subscribe to posts and get email alert on new comments on posts.
* User should be able to subscribe for notifications/email on new on-chain posts creation.

### Milestone 2 - Deploy polkassembly on its own infrastructure

* Take out polkassembly from parity servers.
* Create a seperate google cloud account for polkassembly deployment.
* Setup kubernetes cluster for authentication node.js server, Frontend React app, Hasura graphql server, Node watcher node js process, postgres cloud sql database.
* Create a sendgrid account for email service.
* Setup ci cd pipelines for deploying staging and production environment for polkadot and kusama.
* Setup billing for cloud infrastructure.
* Create Product documentation/videos for polkassembly.


### Milestone 3 - Add features.
- Add tech committee proposals in on-chain posts section.
- Show results of past referenda.
- Add events in a timeline for on-chain posts when a proposal was proposed -> Converted into referendum -> Passed.
- Add search functionality to polkassembly
- Add pagination support for post lists.
- Add filter support for posts lists.
- Optimise polkassembly for Search Engines.
- Show time left for running proposals
- Flag items that the logged in account already 'actioned'
- Add support for a user personal tracker which enable Tracking of a discussion or onchain events such as motions.
- Add deleting comments support.


## Future Plans
Polkassembly is a complex product, we've been building it for 9 months and we can only cover core features during the 3-month period. We will continue working on polkassembly in the future to make it more complete and mature.

We are optimistic about the prospects of Substrate and will maintain good communication with the Substrate community and developers. We are striving to provide high-quality governance services for chains based on Substrate.

### Open-source license
Each component in this grant scope will be open sourced, all required code to leverage the components in this grant scope will be open sourced as well. The license is Apache License 2.0.

## Additional Information
Polkassembly is running at https://polkadot.polkassembly.io/ and https://kusama.polkassembly.io/ for polkadot and kusama respectively.
