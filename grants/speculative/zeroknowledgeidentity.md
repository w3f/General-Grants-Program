# **Zero Knowledge Identity**

## **Project Description**

The goal is to implement an anonymous identity system on substrate. At the most primitive level, this anonymous identity system should allow users to prove membership in a set of individuals, stored on chain, by using zero-knowledge proofs of membership and off-chain secrets. We plan to integrate this functionality into the Commonwealth UI to allow people to anonymously link their `web2` and `web3` identities—i.e Twitter, Github, or a token balance without revealing their identity. 

Based on user feedback, by allowing people to privately link `web2` and `Web3` identities, people will be more inclined to participate in governance, knowing that they do not have to "rebuild" their reputation again. Here are some example use cases in more detail.

Linking a token balance:

    Account A has 1000 EDG and wants to prove he has 1000 EDG
    
    Account A likely does not want to post on Commonwealth with Account A
    
    Account A creates Account B to use on Commonwealth Edgeware Discussions
    
    Account B is going to submit proof for Account A on chain saying, "this is my proxy account, and I have a real account that is in that merkle tree"
    
    **Constraints**: Both A and B need EDG to send txs
    
    1. A needs to send tx to get into SMT group
    2. B needs to send tx to prove he knows A's secret in the group
    
    Problem that can't be solve, how does B get EDG without exposing his identity? Someone else needs to do so on B's behalf

Membership of a group:

    A user who qualifies for a certain group will do the following:
    1. Upon receiving membership in the group, add a leaf node to a SMT
    	(a merkle tree as a group name)
    2. This leaf node will have the form Hash(Hash(secret||nullifier)||accountId)
    3. To prove membership, a user submits a proof proving they know the preimage (secret||nullifier) to a leaf node

Linking web2 identity

    A user who wishes to link a web2 identity will do the following:
    1. Register their identity using Edgeware's Identity Service (edgeware-watcher).
    2. Attest to their identity and include a leaf node Hash(Hash(secret||nullifier)||accountId||web3Identity)
    3. If the identity passes verification, this leaf node is appended to the SMT
    4. To prove membership, a user submits a proof proving they know the preimage (secret||nullifier) of the leaf node

***Nullifiers***: nullifiers are needed to prevent re-submitting proofs for auxiliary accounts.

## **Team Members**

- Drew Stone - Lead
- Dillon Chen
- Raymond Zhong
- Thom Ivy
- Jake Naviasky

## **Team Website**

[https://commonwealth.im/](https://commonwealth.im/) and [https://edgewa.re](https://edgewa.re/)

## **Legal Structure**

incorporated in USA as a Delaware C-Corp

## **Team's experience**

Commonwealth Labs is a blockchain company which is focused on building Edgeware, a WASM-based smart contract parachain as well as supporting governance tools. For Edgeware and Polkadot ecosystem governance, among other things, we've built an identity module, a UI to simply the governance process across parachains. Drew Stone, the lead engineer, has been working as an Ethereum smart contract developer and blockchain developer for 2+ years.

Relevant projects to the goal are below:

- Code
    - Miximus-style ZK membership proofs: [https://github.com/drewstone/rust-miximus](https://github.com/drewstone/rust-miximus)
    - Sparse Merkle Tree substrate module: [https://github.com/hicommonwealth/edgeware-node/tree/drew.merkle/modules/edge-merkletree](https://github.com/hicommonwealth/edgeware-node/tree/drew.merkle/modules/edge-merkletree)
- Articles
    - [https://medium.com/commonwealth-labs/anonymous-voting-a-design-survey-12de869dc97f](https://medium.com/commonwealth-labs/anonymous-voting-a-design-survey-12de869dc97f)

## **Team Code Repos**

- Edgeware: [http://github.com/hicommonwealth/edgeware-node](http://github.com/hicommonwealth/edgeware-node)
- Edgeware-watcher: [https://github.com/hicommonwealth/edgeware-watcher](https://github.com/hicommonwealth/edgeware-watcher)
- Edgeware-identity: [https://github.com/hicommonwealth/edge-identity](https://github.com/hicommonwealth/edge-identity)
- Rust-mixmus: [https://github.com/drewstone/rust-miximus](https://github.com/drewstone/rust-miximus)

## **Team LinkedIn Profiles**

[https://www.linkedin.com/in/dillchen/](https://www.linkedin.com/in/dillchen/)

[https://www.linkedin.com/in/drewcstone/](https://www.linkedin.com/in/drewcstone/)

[https://www.linkedin.com/in/raykyri/](https://www.linkedin.com/in/raykyri/)

## **Development Roadmap**

The milestones are spread out over a total of 3 months as following:

- M0: Aggregate all the cryptography tools importable in a portable rust library (1 week)
    - Pairing/bellman/sapling-crypto as pure rust libraries
- M1: Build sparse-merkle tree module to store Pedersen hashes (2 weeks)
- M2: Build off-chain method of creating proofs (3 weeks)
    - Proofs are initially stored on Commonwealth which we are in the process of open-sourcing. Proofs can then be stored on IPFS
- M3: Build ability to verify proofs using bellman-verifier on chain (2 weeks)
- M4: Upgrade Edgeware identity module to store verified identity auxiliary data (2 weeks)
- M5: Integration into the Commonwealth UI (2 weeks)
    - UI should verify proofs to generate badges that other users can see
    - Create some forums such that only those who can prove some membership are allowed to post or validate

## **Additional Information**

**What work has been done so far?**

Implemented MVP data structures + identity structure on Substrate.

**Have you applied for other grants so far?**

No.

**Are there any other projects similar to yours?**

- In terms of zero-knowledge proofs/login: [login with Semaphore](https://ethresear.ch/t/login-with-semaphore-authenticate/6034)
- In terms of zero-knowledge on substrate: [Zerochain private transactions](https://github.com/w3f/Web3-collaboration/pull/96/files#diff-3b30b4271e70cd5811f2d76758da90e0)