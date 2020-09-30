# Project name
`offchain::ipfs`

# Project Description

Based on community feedback we received after announcing the Rust IPFS initiative, we would like to enable the
Substrate off-chain worker to make IPFS calls via a relay on the Substrate host. While this was at best cumbersome
and at worst infeasible for Substrate users before, the availability of a Rust-native IPFS implementation not only
makes this possible without external HTTP servers, but also optimizes network usage and performance significantly.

Once embedded, `offchain::ipfs` would enable common IPFS operations such as
* Storing data within IPFS via `ipfs.add`, `ipfs.dag.put`, and `ipfs.block.put`
* Retrieving data from IPFS via `ipfs.get`, `ipfs.dag.get` and `ipfs.block.get`
* Exchanging data with peers via `ipfs.bitswap`
* "Swarming" with the global IPFS network via libp2p

This would benefit the ecosystem by bringing together two mission-critical pieces of Web3 technology, allowing content
and data to be marshaled to and from Polkadot parachains, and improving availability in both networks. We believe that
this would be a valuable addition to Substrate and as such, we’d like to propose this to be available within the
official Substrate repository. Of course, we are willing to take Parity’s guidance on that.

While there are other implementations of IPFS (Go and JavaScript) we would prefer to natively embed IPFS in Rust to
keep the codebase consistent and leverage the performance and resource utilization benefits that Rust provides.

# About the Team

## Company
[Equilibrium](https://equilibrium.co)

## Members
* Mark Henderson - Rust Developer, Project Manager
* Vesa-Ville Piiroinen - SME / Research Advisor
* Joonas Koivunen - Rust Developer
* Lukasz Jedrzejczyk - Rust Developer

## Experience
Mark Henderson, in addition to being a [Rust IPFS core contributor](https://github.com/ipfs-rust/rust-ipfs/commits?author=aphelionz), is also a [core contributor to OrbitDB](https://github.com/orbitdb/orbit-db/commits?author=aphelionz), which is a CRDT-based database system reliant on IPFS. For over a year, his full-time job was working on OrbitDB which, in addition to adding features and increasing performance in the distributed OrbitDB system, entailed both dealing personally with the idiosyncrasies of IPFS and also helping community members do the same.

Lukasz Jedrzejczyk has followed the development of Rust since before it became stable in 2015 and has been a proactive contributor to the [Rust compiler](https://github.com/rust-lang/rust/pulls?q=is%3Apr+sort%3Aupdated-desc+author%3Aljedrz+is%3Amerged) and its [StackOverflow community](https://stackoverflow.com/search?q=user:1870153+[rust]). He has participated in the creation of the Concordium blockchain and its ecosystem, concentrating on its client's network capabilities.

Joonas Koivunen is an [Rust IPFS core contributor](https://github.com/ipfs-rust/rust-ipfs/commits?author=koivunej) and was instrumental in delivering the functionality proposed in a recent Protocol Labs devgrant. He is a seasoned Rust developer who has contributed to not only core Rust tooling like [cargo](https://github.com/rust-lang/cargo/pull/3924) and [clippy](https://github.com/rust-lang/rust-clippy/pull/1967), but is also a contributor to projects that Rust IPFS depends on, such as `rust-libp2p` and `aes-ctr`.

Vesa-Ville is the Chief Research Officer at Equilibrium. As former CTO and co-founder of Haja Networks, he worked on the original theory, research and design of the [Ambients](https://github.com/ambientsprotocol/whitepaper), a protocol for distributing and executing deterministic programs safely in a decentralized, content-addressed network like IPFS. He has decades of experience in distributed systems, databases, and interoperability solutions. 

Together, we believe this team is uniquely qualified to complete this task, both the implementation and communicating with the community in terms of the provided reference implementation and best practices when using, implementing, and interacting with IPFS in general.

## Relevant Repositories
* https://github.com/ipfs-rust/rust-ipfs
* https://github.com/orbitdb/orbit-db
* https://github.com/ljedrz/lambda_calculus
* https://ambients.org

## Profiles / Resumes
* https://www.linkedin.com/in/joonas-koivunen-70273412/
* https://ipfs.io/ipfs/QmcHxD94cvJgq5ZZxQkEi7SRMwD5dBnkhQ3zzaVFqNWFJb
* https://www.linkedin.com/in/ljedrz/
* https://www.linkedin.com/in/vesa-ville-piiroinen-5b6b14/

# Development Roadmap

## Overall Schedule

The grant team will allot three months to this project with four team members allocated part time. If the work
started on May 25th and continued to August 25th it would total [65 working days](https://www.timeanddate.com/date/workdays.html?d1=25&m1=5&y1=2020&d2=25&m2=8&y2=2020&ti=on&).

Since this work will take place during the summer, the schedule might drift a bit due to vacations. Vacation plans
and schedule changes will be communicated clearly as soon as they are known.

## Docker Container

The grant team commits to delivering an OCI-compliant image of a reference implementation as part of the final
deliverable, for running the software in an OCI-runtime like Docker. This will help especially with the goal of
Milestone 3, since it will ease community adoption and provide more opportunities for education and mentoring as
well. Additionally, we will provide instructions on how a user may build their own image from the source code
with any modifications they need.

## Milestone 1: Integrate `offchain::ipfs` into Substrate
> Estimated timeframe: May 25 - June 25

In order to maximize impact and bring features to the Substrate community as quickly as possible, the grant team
will start by implementing [rust-ipfs](https://github.com/ipfs-rust/rust-ipfs/) “as-is” into Substrate core. As it requires a deeper integration than a typical
pallet might be able to provide, we would prefer this to be a PR against [paritytech/substrate](https://github.com/paritytech/substrate), but are open to
following Parity’s guidance as to the best way to integrate this.

This way Substrate users with off-chain workers enabled can immediately start testing and ultimately using the IPFS API.

### Deliverables:
* Integrating rust-ipfs on the Substrate host as a long-running process available to accept requests from the offchain-worker
* A libp2p integration, either by leveraging the the Substrate-internal libp2p, or by creating a separate integration
so as not to conflict
* Writing off-chain worker functions that make said requests to the on-host IPFS node
* Documentation, tests and examples of the delivered code and functionality

## Milestone 2: Unlock more Rust IPFS Features
> Estimated timeframe: June 25 - July 25

Once IPFS is firmly integrated into Substrate, we would like to take the time and refine the integration, both on the
Substrate and within rust-ipfs itself by adding features and hardening the existing code. 

While the work in Milestone 1 will be incredibly useful on its own, the addition of [`ipfs.add`](https://docs.ipfs.io/reference/api/cli/#ipfs-add), global swarming, and
garbage collection would allow for parachain-based IPFS clustering. That is, anything that ends up on-chain could
potentially be pinned by any other nodes on that same parachain. This enables incredible benefits and only requires
the network to leverage its own nature and feature set.

Content would be requested via `offchain::ipfs`, or an off-chain HTTP call followed by `offchain::ipfs::add`. Then, the
off-chain worker would add the CIDs to the block as transactions.

### Deliverables:
* [`ipfs.add`](https://docs.ipfs.io/reference/api/cli/#ipfs-add), which "pins" content by default
* Unpin capabilities, which then would enable:
  * IPFS garbage collection of unpinned data
* Ability to bootstrap peers and join the global network
* Documentation, tests, and examples for the above

This could also lead parachain developers to do things like incentivizing IPFS content sharing (aka block providing), or joining a cluster.

## Milestone 3: Create reference implementation and community resources
>Estimated Timeframe: July 25 - August 25

Once the above work is done, `offchain::ipfs` will be functionally complete. In order to increase adoption and
foster community engagement, the grant team will provide thorough documentation, guidance and mentorship with
regards to implementing IPFS in a number of forms.

### Deliverables
* Finalized documentation, tests, and examples from Milestones #1 and #2
* A glossy web site documenting the API endpoints, perhaps in the “mdbook” format favored by the Rust community.
* A series of blog posts about `offchain::ipfs`
    * The problem statement and overall vision behind integrating IPFS to Web3 ecosystem 
    * How `offchain::ipfs` solves the problem, how people can use it, and how implementing this gives you de-facto “parachain based IPFS clustering”
    * Best practices and future ideas
* A video demo and walkthrough of how this works
* Posting on aggregator sites like Hacker News and selected subreddits, and then being available to answer questions as they arise
* The aforementioned Docker image, including instructions on how to customize and rebuild the image.

This will benefit both the project and Substrate alike since all of the above items are potential for PR and
marketing, popularizing all of the technologies and organizations involved. One particular project that could benefit greatly from this effort is [Subsocial](http://subsocial.network/), who we are in active contact with.

# Risks

## #1. The Substrate ecosystem is evolving fast (and that’s a good thing)
Likelihood: High
Impact: Medium/High

The grant team plans on targeting version ^2.0.0 of Substrate. As this is currently a release candidate, everybody
in the ecosystem will need to be prepared for the “rug to be pulled out from beneath them” in terms of bugs,
regressions, and breaking changes. The grant team accepts this risk as part of a thriving open source ecosystem
in the web3 industry, and will mitigate this by following releases closely and communicating as frequently as
possible with our contacts both within web3 and the community at large.

## #2 `offchain::ipfs` will, of course, rely on rust-ipfs
Likelihood: Certain
Impact: Medium/Low

The highest level deliverable from this effort is the embedded IPFS node within a Substrate host. This refers specifically to https://github.com/ipfs-rust/rust-ipfs, which started as a community effort and is now being actively stewarded by Equilibrium.  As the effects of risk #1 start to materialize, updates to rust-ipfs will become necessary to either address Substrate version compatibility, or to take advantage of new Substrate features. Equilibrium acknowledges this risk and, as stated in the final section of this proposal, plans on maintaining this project as long as they are able.

## #3 Releasing transient dependencies happens on other projects’ timelines
Likelihood: Medium/Low
Impact: Very High

Rust-ipfs will need to rely on released dependencies in order to be published on crates.io and included in other Rust projects sustainably. There are a small (less than a handful) number of PRs and other such loose ends that will need to be resolved before the end of Milestone 1. However, the grant team cannot guarantee this outcome since we do not have direct control over the other projects. This risk can be mitigated - but not fully avoided - by proceeding along with Milestone 2 and 3 during any hold-ups that arise due to waiting for PR approvals.

# Future Plans

After this grant we will be exploring how to bring decentralized pinning to the Polkadot ecosystem. This could be a parachain that talks to Filecoin or a native pinning implementation on Substrate. The purpose of this is to make IPFS available to the entire Polkadot ecosystem without needing to implement it in your Substrate stack. The end result is arguably the first decentralized technology stack that can deal in large amounts of data, while making use of a consensus system. Once this is possible our singular goal is to develop and market applications using this new stack.

We want to make a code base that will last into the future. Equilibrium, along with the support of the community, pledges to continue to maintain the `offchain::ipfs` to the best of their ability and within any financial constraints that exist.

Much like we will build upon community efforts, we will also enable and encourage others to build upon our work. This will be a twofold effort that includes both permissive licensing and community outreach: on-boarding as many new contributors as possible, mapping the work out into issues of different levels of difficulty, and by providing mentoring.

# Additional Information

## Other Funding Sources
Rust IPFS is funded in part by two Protocol Labs dev grants: Phase 1 and Phase 2. We also have an [OpenCollective page](https://opencollective.com/ipfs-rust/), which is not yet active.

## Open Source Licensing
Rust IPFS itself is dual licensed under Apache 2.0 / MIT. The grant team is comfortable with the contributions that may land in Substrate core to be licensed under the GPLv3.0.
