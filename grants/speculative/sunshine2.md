# Sunshine

Sunshine is applying for a follow-up grant to fund our ongoing contributions to the Substrate, Rust, and Flutter ecosystems.

Our user research has demonstrated significant ecosystem interest among Web3 grant recipients for grant and bounty infrastructure to outsource developer tasks. We have been public about our intentions to build Gitcoin + Aragon on a substrate chain. The enclosed grant funds our immediate development to realize that vision and, in the process, continue building useful infrastructure for all Substrate-based chains.

## Past Work for the Web3 Foundation

We wrote a [recent blog post](https://meta5.world/posts/ysunshine) listing open source contributions funded by our first Web3 grant. Highlights include
* 7 governance pallets, configured into a runtime and node to express a Substrate DAO Chain
* Rust client and CLI for interacting with the node
* [`substrate-subxt`](https://github.com/paritytech/substrate-subxt/) contributions to support native Rust clients and light clients (w/ 2 Parity projects now using substrate-subxt for this purpose -- ledgeracio, cargo contract)
* Rust client which uses [`ipfs-embed`](https://github.com/ipfs-rust/ipfs-embed) for storage of data not necessary for Substrate runtime storage
    * including tooling around `ipfs-embed` to facilitate error handling and improve the overall API
* Rust-Dart FFI to call Rust client code from Flutter Dart User Interface
    * with intermediate infrastructure open sourced for the wider Rust and Flutter ecosystems
    * native keystore supports modern key management i.e. key rotation

Most of this work fell outside the scope of our first grant, but that never limit what we built. We will continue to exceed expectations and we are just getting started.

## Team <a name = "team"></a>

[Amar](https://github.com/4meta5) started and maintained the [Substrate Recipes](https://substrate.dev/recipes/) as an employee at Parity. He wrote the [`sunshine-bounty`](https://github.com/sunshine-protocol/sunshine-bounty) runtime, node, client, and CLI under Sunshine's first grant. He is an experienced substrate runtime developer.

[David](https://github.com/dvc94ch) worked on substrate core development as an employee at Parity. He is the lead maintainer of [`ipfs-embed`](https://github.com/ipfs-rust/ipfs-embed) and contributes upstream often to [`substrate-subxt`](https://github.com/paritytech/substrate-subxt/) to meet Sunshine's Rust client requirements. David won the surprise category of the Polkadot Launch Hackathon with [`sunshine-keybase`](https://github.com/sunshine-protocol/sunshine-keybase), an implementation of [Keybase's Local Key Security](https://book.keybase.io/docs/crypto/local-key-security) on substrate, using `ipfs-embed`.

[Shady](https://github.com/shekohex) is an experienced Typescript, Flutter, and Rust developer with contributions to many open source projects (i.e. [`nest-access-control`](https://github.com/nestjsx/nest-access-control/graphs/contributors)). He is a pioneer in Rust-Dart FFI development with generic components released alongside his work on the Sunshine Flutter infrastructure i.e. [`flutterust`](https://github.com/shekohex/flutterust).

Recently, the team placed 3rd in the Build your Own Blockchain Category of Hackusama with a [bounty chain prototype](https://github.com/sunshine-protocol/kusama-bounty-chain).

### Legal Structure

US LLC

### Team Code

* [sunshine-protocol](https://github.com/sunshine-protocol)
* [ipfs-rust](https://github.com/ipfs-rust)
* [flutterust](https://github.com/shekohex/flutterust)

## Development Roadmap

There are three themes in this proposal.
1. Nat traversal support for rust-libp2p (@dvc94ch)
2. Dart telemetry server implementation (@shekohex)
3. Sunshine runtime development, which has the immediate purpose of realizing democratic decision-making structures to govern bounties and grants in the Substrate ecosystem (@4meta5)

Due to different team members working on these themes we propose that the milestones in these themes progress independently and without blocking each other. All proposed work will be completed within 3 months. Each employee will be working full-time during this period to finish the tasks described below. All deliverables will include testing along with directions to run the code and tests. All code will be delivered upon request in a docker container.

## Libp2p Nat Traversal
The first theme is adding nat traversal support to rust-libp2p, which is essential for our and other projects building on substrate. Due to different priorities, the parity rust-libp2p team does not have the resources to dedicate to this problem. An [issue](https://github.com/libp2p/rust-libp2p/issues/1722) was opened in rust-libp2p to discuss these issues with the rust-libp2p team and how to move forward.

### Background
Nat traversal and firewall traversal is required when peers want to establish a connection to each other. In a traditional server architecture the server gets a public ip like a phone number. Mobile networks or home networks share an ip address, so you can't directly connect to a device that is on a different network. This is done for multiple reasons. Since the ipv4 address space is a 4 byte number, only ~4 million devices can have a unique ip address. Today's number of devices connected to the internet vastly exceeds that amount. But even in ipv6 with a 16 byte address space that allows every device to have a unique ip, the problem of nat traversal will persist. In most cases you don't want arbitrary connections to be opened to arbitrary devices. So in ipv6 firewalls are configured to only allow outgoing connections and reject incoming connections. Techniques used for nat traversal and firewall traversal are and will remain an important part of p2p networks.

### Milestone A

#### Milestone A1
Transports are assumed by libp2p to have distinct listening and dialing ports. This is an issue when trying to add the quic transport or when using tcp ports with SO_PORTREUSE. Without port reuse, nat traversal becomes impossible without a relay. For the first task, changes to libp2p-core and libp2p-swarm will be made as discussed [here](https://github.com/libp2p/rust-libp2p/issues/1722). The new api will be validated by adding a tcp transport that supports reusing ports and a prototype libp2p-quic crate will be released using this new api. The libp2p-quic crate will live in it's own repo until the rust-libp2p team has the time to review and merge the new transport. Extensive work on the quic transport has already been done by parity employees, but without these api changes it will remain a second class citizen.

#### Milestone A2
Implement the libp2p relay protocol including tests and examples, showing how to use a third party to establish a connection between two peers that cannot communicate because of a local nat or firewall. Deliverables will be a working libp2p-relay crate. The netsim-embed network simulator we developed will help writing automated tests to verify that it functions correctly.

## Dart telemetry server
The second theme is exposing telemetry data and light client metrics to android and ios applications.

### Background
Substrate has great support for monitoring the health of a node. This data is also exposed by the light client, and it provides important performance metrics including ram/disk/cpu/network usage, the sync status of the light client and other metrics useful for debugging.

### Milestone B

#### Milestone B1
Minimal telemetry implementation to capture the current best block and sync status, including a ui progress bar.

#### Milestone B2
Add a telemetry ui displaying the current health, status and resource consumption of the node.

## Bounty and Grant Vote Infrastructure
The third theme is extending sunshine-bounty functionality to support more expressive governance via voting on bounty postings, submissions, and supervisors.

### Background
The Sunshine runtime implements voting infrastructure to enable groups to exercise democratic ideals when making collective decisions.

### Milestone C

#### Milestone C1

Sunshine's [bounty chain prototype](https://github.com/sunshine-protocol/kusama-bounty-chain) placed 3rd in the BYOB Category of Hackusama. The bounty prototype implements bounty governance limited to a single `AccountId`. 

`sunshine-org-bounty` pallet extends `bounty` to enable organizations to vote on bounty postings and submission approval. Vote power for each organization member is proportional to ownership in the associated `OrgId`.

The runtime code will be paired with a Flutter UI for displaying vote progress and notifying users of results.

#### Milestone C2

Voting is generally useful for organization governance, but requiring a vote for every decision is inefficient.

`sunshine-rank` pallet implements ranked choice voting for representative election with enforced term limits. This will be incorporated into `sunshine-org-bounty` to allow representatives to approve bounty submissions below some cost threshold. Group votes will still be required for all submissions exceeding the aforementioned threshold.

The runtime code will be paired with a Flutter UI for displaying vote progress and notifying users of results.

#### Milestone C3

Sunshine Recipes provides clear high-level documentation for `sunshine-bounty` and `sunshine-keybase`. This documentation will help outside projects interested in using our technical stack. For example, the Sunshine Recipes will include detailed instructions demonstrating how to use [`substrate-subxt`](https://github.com/paritytech/substrate-subxt/) to implement a client and light client that can interact with a Substrate node. We know that `ledgeracio` and `cargo contract` within Parity are already using substrate-subxt, but high-level usage documentation will make this path more accessible for other builders in the Polkadot ecosystem.

Recipes included in this milestone will cover
* `substrate-subxt` client configuration
* `substrate-subxt` light client configuration
* `ipfs-embed` client integration
* `sunshine-bounty` learned patterns
* `sunshine-keybase` learned patterns, including `sunshine-chain-pallet` docs for offloading chain data to a set of peers

In summary, these docs will show how to implement a Rust client that uses substrate-subxt to communicate with the Substrate Node and Ipfs-Embed as a content addressed database. This documentation will prove useful to other Substrate projects interested in using these components to improve the efficiency and/or security of their application.

The Sunshine Recipes will follow the same style as [Substrate Recipes](https://substrate.dev/recipes/), using [mdBook](https://github.com/rust-lang/mdBook) as the web interface for the documentation.

## Future Plans

Sunshine Chain will launch in Q1 2021. We are preparing for the launch by building the infrastructure covered in this grant. In particular, Libp2p Nat Traversal is a necessary prerequisite for our native application architecture.

We expect the output of this grant to prove useful to other Substrate-based chains, especially those that adhere to [Local First](https://martin.kleppmann.com/papers/local-first.pdf) design principles.