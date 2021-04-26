# General Grant Proposal

* **Project:** Cosmos-SDK parachain development kit. Phase 3

## Project Overview :page_facing_up:

### Overview

The ultimate goal of the “Cosmos SDK Parachain development kit” is to create tools that allow building Polkadot parachains with the Cosmos SDK. We develop functionality that allows anyone who has built a chain with the Cosmos SDK to turn that chain into a full Polkadot parachain, so any sovereign chain created with the Cosmos SDK could be connected with Polkadot and not be responsible for its own security. Cosmos developers should be able to reuse any Cosmos modules in their blockchain without the necessity to modify them.

To make such a migration as simple as possible, we try to minimize changes in Cosmos and implement all necessary functionality on the Substrate side. At the same time, we seek not to modify the core modules of Substrate. The model of Cosmos-Tendermint interactions provides enough flexibility for this. Cosmos SDK offers various modules for application logic, and Tendermint core is responsible for network and consensus layers.

The core idea of our integration is to replace Tendermint with Substrate-based network and consensus layers. We have implemented a new Substrate pallet that acts like Tendermint. 

The details of our approach are laid out in the [documentation](https://github.com/adoriasoft/polkadot-cosmos-docs).

Cosmos SDK is designed to work on top of a consensus with absolute finality where each received block has already been finalized. Tendermint works in this way, excluding the possibility of forks. So, the Cosmos SDK doesn't support fork resolution at all, and an application will ignore any block that is not a child of the previously processed block. In Substrate hybrid consensus, block producing and finalizing are two separate protocols; not all produced and processed blocks will be finalized, making forks possible. GRANDPA, in contrast to Tendermint, finalizes a chain of blocks at once. So, a fork in Substrate (actually, it’s normal behavior for non-finalized blocks) will cause a crash of the Cosmos application.

During this phase we plan to focus on the problem with forks: application based on Cosmos SDK can't work on top of blockchains without instant finality. It breaks the security of any Cosmos app that uses Substrate hybrid consensus where forks of non-finalized blocks are possible. This restriction includes both independent chains and parachains. To avoid changes in Substrate consensus, we propose modifying Cosmos SDK by adding roll-back mechanisms to process forks correctly. We will create a specific version of Cosmos [BaseApp](https://docs.cosmos.network/v0.39/core/baseapp.html) that can deal with forks that is crucially important for building Cosmos-based parachains. We will launch a Cosmos-based application with the modified BaseApp with Substrate consensus, cause a fork and demonstrate the application's stability.

It is good for Polkadot ecosystem because:
* Polkadot and Cosmos systems have similar purposes and ideas, the possibility of their interoperability will be useful for both systems;
* Developers will be able to use Cosmos SDK and its modules in their blockchain connected to the Polkadot Relay chain.

This project will be integrated to Substrate as one or more modules that can be easily added to an arbitrary Substrate-based application. In the future, we plan to extend our project so that Substrate-Cosmos-based applications will be able to act as parachains.

### Project Details

So far, we have implemented a significant part of ABCI functionality, including the following:
- Transaction verification and broadcasting;
- Transaction and block processing;
- Requests about the current Cosmos stage;
- Validator updates in Substrate according to Cosmos staking;
- Validator rewards in Cosmos according to the activity in Substrate.

More details are described in the [documentation](https://github.com/adoriasoft/polkadot-cosmos-docs).

In Cosmos SDK, Tendermint core encapsulates the Network and Consensus layers of a node. It interacts with the Application layer, which defines the system's business logic, using [ABCI](https://docs.tendermint.com/master/spec/abci/) protocol. The communication between customer application and Tendermint core is similar to 'client-server,’ customer application is the server, and Tendermint core is the client.
In the current version of our integration, Substrate and Cosmos acts as two separate applications that can interact using ABCI interface based on GRPC.

The transaction processing scheme of our application is shown on Fig. 1.   

![Figure 1](https://raw.githubusercontent.com/adoriasoft/polkadot-cosmos-docs/master/img/Architecture-direct.png)
Figure 1 - Transaction and block processing in Substrate-Cosmos app

Cosmos users may interact with Cosmos runtime using standard Cosmos CLI, but using Substrate RPC instead of Tendermint, as it's shown on Fig.2.

![Figure 2](https://raw.githubusercontent.com/adoriasoft/polkadot-cosmos-docs/master/img/CLI-scheme.png)
Figure 2 - Interaction between Cosmos CLI and Cosmos node using Substrate RPC

In Tendermint, block producing and finalization are a single process, so forks can happen only in the case of the validators misbehavior. Substrate [consensus](https://wiki.polkadot.network/docs/en/learn-consensus) divide this process into two parts: BABE\AURA for block producing and GRANDPA for block finalization; this approach is faster, but creates orphan blocks. A few alternative chains may be produced by AURA/BABE and only one of them will be finalised by GRANDPA. In this case, nodes that followed alternative chains have to rollback to the block where the fork happened. 

A typical workflow of block processing in Cosmos includes the following ABCI calls: `BeginBlock`, multiple `DeliverTx`, `EndBlock`, `Commit`. Cosmos SDK doesn't support state rollbacks, so `BeginBlock` with a height less than the current maximum height will cause an error. This restrictions makes a stable work of Cosmos app with Substrate consensus impossible.

Any Cosmos application has a central controller - [BaseApp](https://docs.cosmos.network/v0.39/core/baseapp.html) - that is responsible for communication between the Consensus layer and Cosmos modules. We are going to add fork resolution mechanisms to this controller. It will cause modifications on the Cosmos side that we'd like to abandon because we try to give a tool that allows launching any Cosmos-based app as it is without modifications. At the same time, we plan not to modify each Cosmos module, but only the central controller that is responsible for managing block processing in general. Also, we don't plan to modify the ABCI protocol.

Initially, we implemented ABCI calls `BeginBlock` and `EndBlock` into `on_initialize` and `on_finalize` respectively because they are responsible for similar things. We found a strange behavior that `on_initialize` can be called multiple times on the same block height and even after `on_finalize` on this height. Also, it was impossible to get a hash of the current block during `on_initialize`. According to the [reply](https://github.com/paritytech/subport/issues/43) of support:
1) `on_initialize` is called any time that a runtime function is called from the client, so it is normal to see multiple calls to `on_initialize`.
2) There is no guarantee that `on_finalize` will execute after `on_initialize`.
3) `on_initialize` and `on_finalize` are called before the block hash and extrinsic root are calculated, so it is expected that you would not be able to access them in either function; these values are calculated immediately after calling `on_finalize`.
 
That's why ABCI calls during block processing didn't work correctly and they were moved to an off-chain worker. At the same time, off-chain workers were designed for executing various off-chain tasks, for example, serving as oracles. In Cosmos-Substrate integration they are interconnected unseparable components that can't work independently. So, making ABCI interactions directly from Substrate runtime using runtime interfaces seems to be more natural than delegating this work to a separate process - off-chain worker. A modified version of BaseApp makes it possible.

### Ecosystem Fit

[Polkadot<>Cosmos bridge](https://github.com/ChorusOne/wormhole-bridge) - "Wormhole is a bridge to connect a Substrate-based blockchain to a Cosmos-SDK based blockchain. Specifically it connects substrate light client running inside cosmos chain to substrate chain and cosmos light client running inside substrate chain to cosmos chain."

We are building not a bridge, but an SDK that allows launching native blockchain application created with Cosmos SDK on top of Substrate consensuses. Such chains can work as independent chains or as parachains. 

[Substrate IBC](https://github.com/octopus-network/substrate-ibc) - 
"This pallet implements the standard IBC protocol. The goal of this pallet is to allow the blockchains built on Substrate to gain the ability to interact with other chains in a trustless way via IBC protocol, no matter what consensus the counterparty chains use."

IBC is an important component of Cosmos SDK that is used for interblockchain communication. This pallet can work together with the ABCI pallet because ABCI can connect IBC on the Cosmos application layer with IBC on the Substrate layer to provide communication.

## Team :busts_in_silhouette:

### Team members

* Oleksandr Marukhnenko - Team Leader
* Alex Pozhylenkov - Blockchain Engineer
* David Knyshenko - Blockchain Engineer
* Marianna Yasko - Blockchain Engineer

### Team Website 

* https://adoriasoft.com
* https://blockchainonline.academy/

### Legal Structure

The company registered under the laws of Estonia

Registry code: 14422124

Name: Adoriasoft OÜ

Address: Harju maakond, Tallinn, Lasnamäe linnaosa, Sepapaja tn 6, 15551

Legal form: Private limited company

Value Added Tax identification number: EE102046849

### Team's experience

Our team has rich experience with different blockchain technologies from building dApps to core blockchain development where we worked with different ledgers including Substrate, Cosmos, Bitcoin and Ethereum. We`ve successfully finished two phases of Cosmos-SDK parachain development kit project supported by Web3 grants. There we created a basic integration between Substrate and Cosmos SDK.

### Team Code Repos

* https://github.com/adoriasoft/polkadot_cosmos_integration
* https://github.com/adoriasoft/cosmos-sdk
* https://github.com/VeriBlock (public / private repos)
* https://github.com/tokenio (private solidity repos)
* https://github.com/adoriasoft/ton_fungible_token 
* https://github.com/adoriasoft/ton_payment_mixer (2nd place in TON contest)

## Development Roadmap :nut_and_bolt:

### Overview

* **Total Estimated Duration:** 3 months
* **Full-time equivalent (FTE):**  4

### Milestone 1 — Fork-robust Cosmos app

* **Estimated Duration:** 2 months
* **FTE:**  4

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can launch a Cosmos application with an updated BaseApp |
| 0c. | Testing Guide | The code will have proper unit-test coverage to ensure functionality and robustness. In the guide we will describe how to run these tests |
| 1. | Fork-resistant BaseApp | We will create a modified version of Cosmos BaseApp that will correctly process forks |  
| 2. | Cosmos application with modified BaseApp | We will create an application based on Cosmos SDK with correct fork processing that can work on top of Substrate consensus through ABCI pallet |  
| 3. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Milestone 2 — Cosmos app on top of Substrate

* **Estimated Duration:** 1 months
* **FTE:**  4

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can launch a Cosmos-based network with modified BaseApp on top of Substrate |
| 0c. | Testing Guide | The code will have proper unit-test coverage to ensure functionality and robustness. In the guide we will describe how to run these tests |
| 1. | Updated ABCI pallet | We will migrate all ABCI calls in the ABCI pallet from off-chain worker to pallet methods (`on_initialize`, `abci_tx`, `on_finalize`) and move validators' list from an additional DB to the storage. |  
| 2. | Substrate fork test | We will create a test that causes a fork in Substrate to demonstrate that Cosmos application and ABCI pallet process it correctly |  
| 3. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |


### Community engagement

During the previous phases of the project, we created and publish several articles related to the project.

1) [Polkadot vs Cosmos](https://adoriasoft.com/blog/blockchain-technologies-polkadot-vs-cosmos/)
2) [Cosmos SDK parachain development kit](https://adoriasoft.com/blog/adoriasoft-will-enable-chains-built-with-the-cosmos-sdk-to-be-a-polkadot-parachain/)
   
The latter was also republished in different [media](https://coinmarketcap.com/ru/headlines/news/polkadot-parachain-to-replace-cosmos-sdk-now-with-adoriasoft/).

An article about the lattest milestone will be published soon. We will definitely produce articles about this phase.

## Future Plans


### Phase 4 (10-12 weeks)

**Slashing**

Slashing mechanisms prevent or, at least, minimize validators misbehavior in both Substrate and Cosmos systems. Each validator has a deposit that can be slashed in case of malicious actions. Fishermen in Substrate or Hackers in Cosmos can send claims about misbehavior. 

High-level misbehavior like validator collusion is difficult to detect automatically and it may require claims from users and voting for decisions. We think that this case doesn`t depend on consensus and will work in Cosmos app with no changes. Simpler cases like equivocating can be detected and claimed automatically. We think about usage off-chain workers for this purpose.

It will be enough to launch separate DPoS Cosmos-Substrate blockchains. 

Another issue of medium importance is the reward system - native Cosmos reward work correct only if the consensus can provide the list of signers for each block that doesn’t work with GRANDPA where a chain of blocks is finalized at once.

*Planned deliverables:*
- Connect Substrate equivocating detection with Cosmos slashing.
	
**Governance + Runtime upgrade**

Both systems have government mechanisms that allows to change system parameters and even the source code in the case of Substrate. Governance mechanisms are controlled by referendum system, where each change must be approved by token-based voting. Cosmos internal governance can work despite of used consensus. We want to allow Cosmos users to manage not only the Cosmos part of their nodes, but the Substrate part too. A special case of governance is runtime upgrade that needs additional research.

*Planned deliverables:*
- Allow Substrate parameters updates using Cosmos governance;
- Allow Substrate runtime updates using Cosmos governance.
  
### Phase 5

**Connection to Relay chain and Cosmos hub**

The main goal of our project is to allow blockchains based on our Substrate-Cosmos SDK to interact in both Polkadot and Cosmos systems. Cumulus is designed to work with Substrate-based chains and probably can't be connected to our Cosmos-based application level "out-of-the-box." The description of specific changes requires an in-depth analysis of the Cumulus.

*Planned deliverables:*
- Add IBC module to Cosmos and connect it with IBC pallet;
- Connect node to Cosmos Hub;
- Add Polkadot consensus and XCMP to Substrate part;
- Implement Cosmos module for using XCMP;
- Connect node to a test Relay Chain.

### Phase 6 

**ABCI Snapshots**

Cosmos ABCI contains a set of Snapshots methods that allows to create and share the state on specific height without the whole chain of previous blocks.
- `ListSnapshots` - used during state sync to discover available snapshots on peers.
- `LoadSnapshotChunk` - used during state sync to retrieve snapshot chunks from peers.
- `OfferSnapshot` - OfferSnapshot is called when bootstrapping a node using state sync. The application may accept or reject snapshots as appropriate. Upon accepting, Tendermint will retrieve and apply snapshot chunks via ApplySnapshotChunk. The application may also choose to reject a snapshot in the chunk response, in which case it should be prepared to accept further OfferSnapshot calls.
- `ApplySnapshotChunk` - The application can choose to refetch chunks and/or ban P2P peers as appropriate. Tendermint will not do this unless instructed by the application.

*Planned deliverables:*
- implement Snapshot methods in Substrate RPC;
- probably, extend Cosmos snapshots with Substrate state.

**Substrate RPC**

There are a set of additional APIs in Tendermint RPC([Info_rpcs and Websocket_rpcs](https://docs.tendermint.com/master/rpc/#/)), they are not critical for the work of Substrate-Cosmos node, but make user interface more convenient and usable.

*Planned deliverables:*
- implement all methods from Tendermint RPC in Substrate RPC.



## Additional Information :heavy_plus_sign:

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:

* Work you have already done.
  
  During two previous phases we implemented the ABCI pallet that connects Substrate and Cosmos ([Github repo](https://github.com/adoriasoft/polkadot_cosmos_integration)).
  
* Wheter there are any other teams who have already contributed (financially) to the project.
    
  No.
* Previous grants you may have applied for.
  
[Cosmos-SDK parachain development kit. Phase 2](https://github.com/w3f/General-Grants-Program/blob/master/grants/speculative/Cosmos_SDK_parachain_development_kit_Phase_2.md).