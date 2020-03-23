# Subsocial. Chapter 2

## Project Description

[Subsocial](http://subsocial.network) is a set of Substrate v2 pallets with web UI that allows anyone to launch a decentralized censorship-resistant social network aka community. Every community will be running on its own Substrate chain. Such decentralized communities could be connected via a Polkadot-based relay chain.

Subsocial is a long-term project and would like to become a Kusama parachain in the near future. It could serve as a social UI to Kusama governance. This means that people can participate in discussions around council applications, runtime upgrates, referenda, treasury proposals, etc in a trylly decentralized and transparent way.

The keys points that we want to address in this grant application:
- Refactor Subsocial v1 SRML to Substrate v2 pallets.
- Add support for Polkadot browser extension.
- Add integration with Kusama network.
- Improve overall user experience of web UI.

## Team Members

**Alex Siman** – Software Architect and Project Manager at Subsocial. Alex is a Polkadot Ambassador, a founder of “Polkadot Ukraine”, and a blockchain and UI developer at Joystream.org – a user-governed video platform built on top of Substrate. He has been building complex web apps since 2008. In 2017 he started to write smart contracts on Solidity and integrate them with dapps. Since 2019 he has been developing Substrate modules and building custom UIs for them with Polkadot API. Links: [GitHub](https://github.com/siman), [LinkedIn](https://www.linkedin.com/in/alexsiman/)

**Oleg** – Frontend Developer (TypeScript, React). Oleg develops UI for Subsocial using a fork of Polkadot.js Apps. His main contribution to this project can be found in UI repo:
https://github.com/dappforce/dappforce-subsocial-ui/commits?author=mell-old

**Vlad** – Backend Developer (Rust, C++). Vlad writes SRML and tests for Subsocial. His main contribution to this project can be found in Substrate runtime repo:
https://github.com/dappforce/dappforce-subsocial-runtime/commits?author=F3Joule

## Team Website

https://github.com/dappforce

## Legal Structure

Sole Proprietorship based in Ukraine.

## Project Repos

[Runtime](https://github.com/dappforce/dappforce-subsocial-runtime) - Substrate v1 module. The main blockchain logic of Subsocial is here. It can be used with other Substrate-based blockchains.

[Node](https://github.com/dappforce/dappforce-subsocial-node) - Substrate v1 based blockchain node. This repo assembles all Substrate modules required to launch Subsocial as a standalone blockchain.

[Off-chain Storage](https://github.com/dappforce/dappforce-subsocial-offchain) - Stores text data of blogs, posts and comments to IPFS. Builds user feeds and notifications in Postgres based on Substrate events like BlogCreated, PostCreated, etc. Supports full text search by indexing text data of blogs, posts and comments into ElasticSeach database.

[Web UI](https://github.com/dappforce/dappforce-subsocial-ui) - A mobile-friendly web UI for Subsocial blockchain. Built with TypeScript, React, Polkadot API libs and Ant Design UI components. Supports SEO for blogs, posts and comments by fetching data from Substrate and IPFS nodes on the server side.

[Blockchain Apps](https://github.com/dappforce/dappforce-subsocial-apps) - A fork of [Polkadot.js Apps](https://github.com/polkadot-js/apps) with added support for custom types of Subsocial pallets (blockchain). This app allows to look at blockchain storage, blocks, execute transactions and much more.

[Docker](https://github.com/dappforce/dappforce-subsocial-starter) - Start all parts of Subsocial in Docker containers with a single script. This repo will help you deploy Subsocial blockchain, offchain storage and web UI.

## License

GNU GPL v3.

## Development Roadmap

*NOTE*: Blog and space are synonyms in this document because later (in M3) we want to merge `Blog` with `Profile` and name this new structure as `Space`.

### Milestone 1

#### Substrate Pallets

Move the runtime from Substrate v1 to v2.

Refactoring: Reimplement comments by reusing `Post` struct. We found out that Post and Comment structs share a lot. That's why it makes sense to have one struct instead of two. Also we want to support other kinds of posts such as Poll, Proposal, Runtime Upgrade, etc.

New pallet: **Space Multi-Ownership**. Multiple accounts should be able to co-own a space (blog). This will reflect a real world situation like with startups or organizations where there are more then one co-founder. With this pallet it should be possible for a current owner of a space to add new co-owners and/or remove existing one, and/or change a threshold. All subsequent changes to the list of co-owners of a space can be executed only after `N` signs out of `M` co-owners, where `N` is a current threshold. Every space co-owner should be able to write a post to the space they co-own and make a new proposal to change a space co-owners and/or threshold.

New pallet: **Block (ban) Accounts per Space**. Blocked accounts should not be able to react (upvote/downvote) or comment on the posts of a space they are blocked at.

#### Off-chain

IPFS: support uploading of images. It should be possible to upload images on such forms as: Edit Space, Edit Post.

#### Front-End

Bump Polkadot.js libs and fix a lot of isses that will pop up after this.

Refactor Subsocial custom Substrate types to new format of how they should be described to be able to use them with newest Polkadot.js API.

Integrate UI with Polkadot browser extension.

Optimize data fetching from Substarte: Use a **multi query** to load array of comments, posts or spaces with one Substrate query. This means that the code that makes multiple requests to Substrate to retrieve get data from its storage via `api.query.[pallet].[storage]()` should be refactored to `api.query.[pallet].[storage].multi()` that is one request.

New feature: Move a post from one space to another. A user that is moving a post should own both spaces.

New screen: See **space (account) activity**. It should be possible to filter a space activity by type: Comments, Posts, Reactions, Follows, Spaces. This feature is similar to a user activity on Trello, GitHub or StackOverflow. This is essential in order to shed more light on good or bad actors in Kusama/Polkadot governance. *As a bonus:* this feature (sceeen) could be integrated with other project(s) that show(s) analytics on Kusama/Polkadot governance.

Space owners should be able to **hide a space, post, comment**: mark as them as `hidden` in Substrate and don't show on UI and don't include in user feed and notifications.

##### New type of posts specific to Kusama governance:

- Runtime upgrade.
- Referendum.
- Treasury proposal.

##### Other Kusama integrations:

Show labels along with account address or space name: `Validator`, `Council member`, `Proposer`, etc.

Integrate with Kusama Identity pallet: show such fields like Twitter, Riot, etc. plus show a `Verified` sign from registrars on a space page and preview in comments.

#### Documentation & Docker:

Both documentation and Docker containers should be updated to reflect new features and changes introduced in this milestone.

### Milestone 2

#### Substrate Pallets

New pallet: **Post Tags**. Tag a post (up to 5-10 tags per post max). Tag names should be stored in Substrate and they should be unique per space. Tags with the same names but in different spaces are different tags with different ids.

New pallet: **Poll**. Similar to polls on Twitter and Telegram. This kind of post is helpful in such situations when a proposer whants to ask Kusama/Polkadot community an opition about changin some parameter or other features update before making an actual proposal on-chain.

New pallet: **Mentions**. It should be possible to mention a space in a post by a space handle. On UI side the mentioning process should be similar to Twitter, when a user starts to type `@` and then a **@handle** of some space.

#### Off-chain

Improve offchain indexing of Substrate events (new space, post, reaction, etc). It should be possible to recover from a downtime of the offchain server and continue indexing of new spaces and post in order to create users' feeds and notifications.

#### Front-End

##### New React components:

**Space Navigation Editor** like on Medium, where a space owner can specify what menu items they want to see on space layout. These menu items could be of different type: Outer URL, specific post, other space, posts filtered by tags.

**Team Members**. If a space is an organization, it should be possible to specify who is on the team. This means that space owners should be able to create relationships between spaces: Organization Space <--> Team Member Space(s).

**Space layout with navigation** menu and preview of team members, if this is an Organization Space.

New type of post: **Poll**.

Add tags to post in post editor.

Sign up (unboarding).

Sign in.

##### User notifications:

It should be possible to notify users about activity that they are subscribed to on other messengers and via in-browser push notifications. Looks like these ways of notificaiton are most popular withing Polkadot community:

- Telegram (create a bot)
- Riot (create a bot)
- Web push

##### New kinds of post:

**Share a link** to outer site on Subsocial like you can share an outer link on Facebook, Twitter or Reddit. This should fetch a link preview and put its content on IPFS. This is sort of caching of fetched previews. Could be implemented as a new post extension "Link Preview". As a bonus: It could be possible to re-fetch a link preview.

**Share a post** from Subsocial to outer social media sites like Facebook, Twitter, LinkedIn, Reddit, etc.

##### Other UI features

Support mentioning (@) in Markdown editor of post or comment. 

Render mentions (in posts and comments) as a link to a corresponding space's page.

#### Documentation & Docker:

Both documentation and Docker containers should be updated to reflect new features and changes introduced in this milestone.

### Milestone 3

#### Substrate Pallets

Refactoring: Merge `Blog` and `Profile` Rust structs and their corresponding Substrate storages into a new `Space` struct. We found out that Blog and Profile structs share a lot. And such as we want to support other kinds of similar structs such as Project, Organization, Community, it makes sense to generalize them into a new extendable `Space` struct.

Per-space score (reputation) of an account (space). This is way to secure good spaces (blogs) from bad actors that could cheat their score in a scammy spaces they own.

New pallet: **Flag (report) a Post** to space moderators. Reports should be weighted by a per-space reputation of a reporting account (space). When reporting, an optiobal rationale could be provided.

New pallet: **Topics** (part of `Tags` module). Topics can refer a group of related or alias Tags. Space owners should be able to created, and updated topics. Content of any topic should be saved on IPFS and can include a logo, name, description and related tags. CID of topic content's stored in a corresponding Substrate struct of a Topic.

New pallet: **P2P Encrypted Messaging** aka one-to-one private on-chain (with content in IPFS) chat between two accounts.

New pallet: **Recurring Payments** (aka paid subscriptions). A space owner(s) shoud be able to specifiy a beneficiary account that will receive recurring payments from the paid subscribers (aka fans). Fans (space followers) should be able to subscribe to any space that has paid subscriptions enabled. Every X blocks (specified by a space owner(s)), Y amount of native tokens should be transferred from every subscriber's account to a beneficiary account of a space. This pallet could be similar to [Ethereum ERC 1337](https://github.com/ethereum/EIPs/pull/1337) but still needs a research on what is the best way to implement it as a Substrate pallet.

#### Off-chain

Offchain + UI: Refactor the way how we build feed and notifications for users. Currently the offchain builds feed and notifications per account. But such as every account that wants to receive feed and notifications should have a space, it means that the offchain should build feed and notifications per space.

Generate small compressed previews of uploaded images (space avatar, post cover image) and store them on IPFS. This is would help to load UI faster and make it lighter.

Compress content of blog, post, comment when adding to IPFS. Look at such algos as snappy, lz4, deflate, etc. Maybe serialize content info with Proto Buffers instead of JSON? A research is required to understand if this makes sense in terms of CPU vs disk space consumption.

#### Front-End

##### New type of posts specific to Kusama governance:

- Council application program.
- Validator program.
- Tip (reward awesome)

##### Improvements: UX and accessibility

UX: Onboarding process of new users. The process should be similar to what we see on Medium or Twitter: their UIs suggest a new user (right after a signup) to subscribe to tags / spaces (blogs) of interest.

SEO: Generate a sitemap.xml for blogs and posts on server.
  
Add **i18n support**. Users should be able to switch UI to other supported languages. This doesn't mean that we are going to add translations per se, but rather to add support for internationalisation on UI.

New screens: Posts of the Day/Week/Month/All time. This should be based on the amount of upvotes vs downvotes on posts of a certain period.

**New UI themes**. Create a couple of modifications of our current UI theme or even adapt some open source HTML themes for blogs. Idea behind this feature is to show the community how flexible Subsocial is so they can fork it and create their own custom themes for their blogs/organizations.

#### Documentation & Docker:

Both documentation and Docker containers should be updated to reflect new features and changes introduced in this milestone.

### Possible features (could be implemented)

*Also we would like to implement the next features but not sure how much time and enffort it will take to implement all of the above features. So no promises here.*

(**Maybe**) (Runtime): Split (refactor) Subsocial's mono pallet into a separate pallets: spaces (blogs), posts, reactions, follows, scores for a better re-usability and composability.

(**Maybe**) (Runtime) Whitelist / blacklist tags that are allowed to use or restricted per space.

(**Maybe**) (UI) Show notification bell on spaces that have new posts. (See on Reddit in side-menu).

(**Maybe**) (Offchain) Add GraphQL support for feed and notifications. This would make it easier for the third-parties to integrate with Subsocial.

(**Maybe**) (Runtime) Custom tx fee based on a score (reputation) of your space (account).

## Additional Information

### What work has been done so far?

We have successfully delivered all three milestones from [the first grant](https://github.com/w3f/General-Grants-Program/pull/143).

Here you can check out Subsocial testnet and web UI: http://testnet.subsocial.network

### Are there any teams who have already contributed (financially) to the project?

Only Web3 Foundation.

### Have you applied for other grants so far?

Yes, applied for [the first technical grant](https://github.com/w3f/General-Grants-Program/pull/143) from Web3 Foundation.

### Are there any other projects similar to yours?

Steemit, Pepo, Pepeth, Voice (by EOS).

### How is your project different?

We are building our project on Substrate and because of this we already have quite different architecture that allows to upgrade a logic of our blockchain with no forks required.
