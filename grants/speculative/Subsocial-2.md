# Subsocial. Chapter 2

## Project Description

[Subsocial](http://subsocial.network) is a set of Substrate v2 pallets with web UI that allows anyone to launch a decentralized censorship-resistant social network aka community. Every community will be running on its own Substrate chain. Such decentralized communities could be connected via a Polkadot-based relay chain.

Subsocial is a long-term project and would like to become a Kusama parachain in the near future. It could serve as a social UI to Kusama governance. This means that people can participate in discussions around council applications, runtime upgrades, referenda, treasury proposals, etc in a trylly decentralized and transparent way.

The keys points that we want to address in this grant application:
- Refactor Subsocial v1 SRML to Substrate v2 pallets.
- Add support for Polkadot browser extension.
- Add integration with Kusama network.
- Improve overall user experience of web UI.

## Team Members

**Alex Siman** – Software Architect and Project Manager at Subsocial. Alex is a Polkadot Ambassador, a founder of “Polkadot Ukraine”. He has been building complex web apps since 2008. In 2017, he started to write smart contracts on Solidity and integrate them with dapps. Since 2019 he has been developing Substrate modules and building custom UIs for them with Polkadot API. Links: [GitHub](https://github.com/siman), [LinkedIn](https://www.linkedin.com/in/alexsiman/)

**Oleg** – Front-end Developer (TypeScript, React). Oleg develops UI for Subsocial. His main contribution to this project can be found in Subsocial UI repo:
https://github.com/dappforce/dappforce-subsocial-ui/commits?author=mell-old

**Vlad** – Back-end Developer (Rust, C++). Vlad writes SRML and tests for Subsocial. His main contribution to this project can be found in Substrate runtime repo:
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

### Milestone 1 - Move to Substrate v2

#### Substrate: Move the runtime from Substrate v1 to v2.

The current Subsocial is based on Substrate v1 (April 2019).
We are going to upgrade our codebase (both Substrate and UI sides) to Substrate v2 and corresponding Polkadot.js API libs. As a side-effect of this move, it will allow us to use Polkadot browser extension to sign extrinsics on UI.

#### Substrate: Re-implement comments by reusing `Post` struct:

We found out that `Post` and `Comment` structs have a lot in common. That's why it makes sense to have one more genericc struct instead of two separate. Also, we want to add support for other kinds of posts (in the later grants) such as (on-chain) `Poll`.

Updated `Post` structure will look something like this:

```rust
#[derive(Encode, Decode, Clone, Eq, PartialEq, RuntimeDebug)]
pub struct Post<T: Trait> {
  pub id: PostId,
  pub created: WhoAndWhen<T>,
  pub updated: Option<WhoAndWhen<T>>,
  pub hidden: bool,

  pub blog_id: Option<BlogId>,
  pub extension: PostExtension,

  pub ipfs_hash: Vec<u8>,
  pub edit_history: Vec<PostHistoryRecord<T>>,

  pub total_replies_count: u16,
  pub shares_count: u16,
  pub upvotes_count: u16,
  pub downvotes_count: u16,

  pub score: i32,
}

#[derive(Encode, Decode, Clone, Eq, PartialEq, RuntimeDebug)]
pub struct PostUpdate {
  pub blog_id: Option<BlogId>,
  pub ipfs_hash: Option<Vec<u8>>,
  pub hidden: Option<bool>,
}

#[derive(Encode, Decode, Clone, Eq, PartialEq, RuntimeDebug)]
pub struct PostHistoryRecord<T: Trait> {
  pub edited: WhoAndWhen<T>,
  pub old_data: PostUpdate,
}

#[derive(Encode, Decode, Clone, Copy, Eq, PartialEq, RuntimeDebug)]
pub enum PostExtension {
  RegularPost,
  Comment(CommentExt),
  SharedPost(PostId),
}

#[derive(Encode, Decode, Clone, Copy, Eq, PartialEq, RuntimeDebug)]
pub struct CommentExt {
  parent_id: Option<PostId>,
  root_post_id: PostId,
}

impl Default for PostExtension {
  fn default() -> Self {
    PostExtension::RegularPost
  }
}
```

Updated storage for comments will look something like this:

```
/// Ids of direct replies by a parent post id.
pub ReplyIdsByPostId get(fn reply_ids_by_post_id): map PostId => Vec<PostId>;
```

Updated extrinsics for posts/comments creation/editing:

```rust
pub fn create_post(
    origin, 
    blog_id_opt: Option<BlogId>, 
    extension: PostExtension, 
    ipfs_hash: Vec<u8>
) {}

pub fn update_post(
    origin, 
    post_id: PostId, 
    update: PostUpdate
) {}
```

#### Substrate: New pallet: Blog Multi-Ownership:

Multiple accounts should be able to co-own a blog. This will reflect a real world situation like with startups or organizations where there are more then one co-founder. With this pallet it should be possible for a current owner of a blog to add new co-owners and/or remove existing one, and/or change a threshold. All subsequent changes to the list of co-owners of a blog can be executed only after `N` signs out of `M` co-owners, where `N` is a current threshold. Every blog co-owner should be able to write a post to the blog they co-own and make a new proposal to change a blog co-owners and/or threshold.

Possible structures for the new pallet (Space equals to Blog):

```rust
type SpaceId = u64;

type ChangeId = u64;

pub struct WhoAndWhen<T: system::Trait + pallet_timestamp::Trait> {
  pub account: T::AccountId,
  pub block: T::BlockNumber,
  pub time: T::Moment,
}

/// This struct describes current owners of a particular space (blog).
pub struct SpaceOwners<T: Trait> {
  pub created: WhoAndWhen<T>,
  pub space_id: SpaceId,
  pub owners: Vec<T::AccountId>,
  pub threshold: u16,
  pub changes_count: u64,
}

/// This struct describes a change to space (blog) owners.
pub struct Change<T: Trait> {
  pub created: WhoAndWhen<T>,
  pub id: ChangeId,
  pub space_id: SpaceId,
  pub add_owners: Vec<T::AccountId>,
  pub remove_owners: Vec<T::AccountId>,
  pub new_threshold: Option<u16>,
  pub notes: Vec<u8>,
  pub confirmed_by: Vec<T::AccountId>,
  pub expires_at: T::BlockNumber,
}
```

Possible storage:

```
SpaceOwnersBySpaceById get(space_owners_by_space_id): map SpaceId => Option<SpaceOwners<T>>;

SpaceIdsOwnedByAccountId get(space_ids_owned_by_account_id): map T::AccountId => BTreeSet<SpaceId> = BTreeSet::new();

NextChangeId get(next_change_id): ChangeId = 1;

ChangeById get(change_by_id): map ChangeId => Option<Change<T>>;

PendingChangeIdBySpaceId get(pending_change_id_by_space_id): map SpaceId => Option<ChangeId>;

PendingChangeIds get(pending_change_ids): BTreeSet<ChangeId> = BTreeSet::new();

ExecutedChangeIdsBySpaceId get(executed_change_ids_by_space_id): map SpaceId => Vec<ChangeId>;
```

Possible extrinsics:

```rust
/// Can be called during a new blog (space) creation. 
pub fn create_space_owners(
    origin,
    space_id: SpaceId,
    owners: Vec<T::AccountId>,
    threshold: u16
) {}

/// Can be called by the current blog (space) owner to propose
/// a change to the current ownership of the blog.
pub fn propose_change(
    origin,
    space_id: SpaceId,
    add_owners: Vec<T::AccountId>,
    remove_owners: Vec<T::AccountId>,
    new_threshold: Option<u16>,
    notes: Vec<u8>
) {}

/// Can be called by any current blog owner to confirm a change.
/// When a threshold reached, the change gets accepted.
pub fn confirm_change(
    origin,
    space_id: SpaceId,
    change_id: ChangeId
) {}

/// Can be called by the account that proposed this change.
pub fn cancel_change(
  origin,
  space_id: SpaceId,
  change_id: ChangeId
) {}
```

#### Substrate: New pallet: Block (ban) Accounts per Blog:

Blocked accounts should not be able to react (upvote/downvote) or comment on the posts of a blog they are blocked at. On UI part it should be possible to see a list of blocked accounts on a blog page.

Possible storage (Scope equals to Blog here:

```
pub type ScopeId = u64;

pub IsAccountBlockedInScope get(is_account_blocked_by_scope): map hasher(blake2_256) (ScopeId, T::AccountId) => bool = false;

pub BlockedAccountsByScope get(blocked_accounts_by_scope): map hasher(blake2_256) ScopeId => BTreeSet<T::AccountId>;
```

Possible extrinsics:

```rust
/// Only a blog owner can block an account
/// if this account is unblocked in this blog yet.
pub fn block_account(
    origin,
    scope_id: ScopeId,
    subject_acc: T::AccountId
) {}

/// Only a blog owner can block an account,
/// if this account is blocked in this blog now.
pub fn unblock_account(
    origin,
    scope_id: ScopeId,
    subject_acc: T::AccountId
) {}
```

#### UI: Bump Polkadot.js libs:
 
Bump Polkadot.js libs and fix a lot of breaking issues that will pop up after this.

#### UI: Refactor Subsocial's custom Substrate types:
 
Refactor Subsocial's custom Substrate types to new format of how they should be described to use them with newest Polkadot.js API.

#### UI: Integrate with Polkadot extension:

Integrate UI with Polkadot.js browser extension. This will allow users to sign their Subsocial transactions via Polkadot.js extension.

#### UI: Use multi-query to optimize data fetching from Substrate:

Optimize data fetching from Substarte's storage: Use a **multi query** API to fetch the arrays of comments, posts or blogs with a single Substrate query. This means that the code that currently makes multiple requests to Substrate node to get data from its storage via `api.query.[pallet].[storage]()` should be refactored to `api.query.[pallet].[storage].multi()` – that is one request.

#### UI: New feature: Move a post from one blog to another:

A user (a post author) should be able to move their post from one blog to another. A user that is moving the post should own both blogs.

#### Documentation & Docker:

Both documentation and Docker containers should be updated to reflect new features and changes introduced in this milestone.

### Milestone 2 - Kusama integration

#### Substrate: Make off-chain data generic

Make a field with **off-chain data** on such structures as `Blog` and `Post` more generic. Currently, every `Blog` adn `Post` has such fied as `ipfs_hash: Vec<u8>` where we store IPFS hash of off-chain content related to blog or post. It should be possible to specify not only IPFS hash, but also DAT id or a tuple of table with id of a private database (ex. MongoDB) in blog or post structures.

What we have now:

```rust
pub struct Blog<T: Trait> {
    // ...
    pub ipfs_hash: Vec<u8>
}

pub struct Post<T: Trait> {
    // ...
    pub ipfs_hash: Vec<u8>
}
```

This should be changed to something like this:

```rust
enum Payload {
    IpfsHash(Vec<u8>),
    DatId(Vec<u8>),
    PrivateDb(
        /// Table or collection name.
        Vec<u8>,

        /// Unique id in a table (relational DBs)
        /// or document id (NoSQL DBs).
        Vec<u8>
    )
}

pub struct Blog<T: Trait> {
    // ...
    pub payload: Payload
}

pub struct Post<T: Trait> {
    // ...
    pub payload: Payload
}
``` 
 
#### UI: New type of posts specific to Kusama governance:

It should be possible to attach to a post on Subsocial the info about Kusama events such as:
- Runtime upgrade.
- Referendum.
- Treasury proposal.

In other words, the author of a runtime upgrade or referendum/treasury proposal, should be able to write a description to their upgrade or proposal to Kusama on Subsocial. And anyone else, that has a profile on Subsocial, will be able to comment on it.

#### UI: Support Kusama Identity pallet:

Integrate with **Kusama Identity pallet**: Show such fields like Twitter, Riot handle, etc. plus show a `Verified` sign from Kusama registrars on Subsocial profiles' pages and profiles' previews in comments sections under the posts.

#### UI: Show Kusama role labels on profiles:

Show **role labels** along with account address or profile name: `Validator`, `Council member`, `Proposer`, etc. The info for labels should be based on the live chain info from Kusama nodes. Subsocial UI is going to connect to a selected Kusama node and get the info about the current list of validators, council members and proposers.

#### Off-chain: Upload images to IPFS and show on UI (a post page)

IPFS: Support **uploading of images** when creating or editing a post. Currently, there is Edit Post form on Subsocial. There is a Markdown Editor that lets users to write posts in Markdown. Additionally to the text editing functionality, it should be possible to upload images to IPFS and attach them to the posts on Edit Post form. Then when rendering post, images should be inserted from IPFS into HTML.

#### UI: New component: Profile/account activity:

New component: See **profile/account activity**. It should be possible to see a profile/account activity on their profile page. It should be possible to filter profile/account activity by activity type: Comments, Posts, Reactions, Follows, Blogs. This feature is similar to a user activity on Trello, GitHub or StackOverflow. This is essential functionality in order to shed more light on the good or bad actors in Kusama/Polkadot governance. *As a bonus:* this component could be integrated with other project(s) that show(s) analytics on Kusama/Polkadot governance.

Activity data will be loaded from off-chain storage stored in PostgreSQL tables. We already have tables for user activity, where we build personalized news feeds and notifications per account.

#### Substrate + UI: New feature: Hide blogs and posts:

Blog owners should be able to **hide their blogs and posts**: i.e. mark as them as `hidden` in Substrate storage. Substrate's web UI show respect this `hidden` field and don't show hidden entities on its UI. This also means that neither hidden blogs nor posts should not be included in users' feeds and notifications. 

#### Documentation & Docker:

Both documentation and Docker containers should be updated to reflect new features and changes introduced in this milestone.

## Additional Information

### What work has been done so far?

We have successfully delivered all three milestones from [the first grant](https://github.com/w3f/General-Grants-Program/pull/143).

Here you can check out Subsocial testnet and web UI: http://testnet.subsocial.network

### Are there any teams who have already contributed (financially) to the project?

Only Web3 Foundation.

### Have you applied for other grants so far?

Yes, applied for [the first technical grant](https://github.com/w3f/General-Grants-Program/pull/143) from Web3 Foundation.

### Are there any other projects similar to yours?

Steemit, Pepeth, Akasha World, Voice (by EOS).

### How is your project different?

We are building our project on Substrate and because of this we already have quite different architecture that allows to upgrade a logic of our blockchain with no forks required.
