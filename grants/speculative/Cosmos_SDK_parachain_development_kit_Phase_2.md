# Cosmos-SDK parachain development kit. Phase 2

## Project Overview
We are going to build functionality that allows anyone who has built a chain with the Cosmos SDK to turn that chain into a full Polkadot parachain. The purpose here is that any sovereign chain created with the Cosmos SDK could connect with Polkadot and not be responsible for their own security.

By this moment, we've implemented a basic integration between Substrate and Cosmos SDK. We replaced Tendermint consensus and network layer used in Cosmos with Substrate-based “sub-node”. We've implemented a new Substrate pallet that acts like Tendermint. We minimized changes in Cosmos SDK to allow Cosmos developers to change consensus and network layers of their applications as easy as possible. To run Cosmos SDK with the Substrate you need only enable a few flags during the node start (disable Tendermint consensus and enable grpc). 

Our application has basic features for transaction and block producing and validation. Besides such basic abilities, Cosmos and Tendermint have a set of useful interactions, our Substrate integration should provide similar features. Cosmos CLI uses Tendermint to interact with applications, to allow such interactions through Substrate, we`ve added an RPC server.

Also, both Substrate and Cosmos SDK contain other pallets\modules useful for blockchain developers. Some of them are validators election and consensus, slashing, governance, etc. Many of them are related to Substrate or Cosmos native tokens.  In our case, application logic is implemented by Cosmos SDK, so the Cosmos token is the main one. There are two ways to allow Substrate modules to use all the benefits of token: associate Substrate tokens with Cosmos ones or ignore Substrate tokens and make additional pallets which can affect Substrate state according to Cosmos commands. We plan to use the second approach.

Also, we want to provide stable work of our nodes in case of crashes, forks, etc. A more detailed description can be found in the Development Roadmap.

It is good for Polkadot ecosystem because:
* Polkadot and Cosmos systems have similar purposes and ideas, the possibility of their interoperability will be useful for both systems;
* Developers will be able to use Cosmos SDK and it`s modules in their blockchain connected to the Polkadot Relay chain.

This project will be integrated to Substrate as one or more modules that can be easily added to an arbitrary Substrate-based application. In the future, we plan to extend our project so that Substrate-Cosmos-based applications will be able to act as parachains.

## Project Details

Working with both Substrate and Cosmos frameworks, we understood that integration between this system is possible, but in some aspects, it's a challenging task. We`ve analyzed and described the scope of work that should be done to use the Cosmos SDK app on top of Substrate in the same way as it works on top of Tendermint. Now it's difficult to analyze the details of the connection to the mainnets - Polkadot Relay Chain and Cosmos Hub - because both parachains and zones are still operating in test mode.

There are many different features that should be implemented, we propose to start from the most critical ones: finish ABCI on Substrate side to expand the interaction between Cosmos CLI and node; tie validator election and consensus rules in Cosmos and Substrate; Automate the launching of both node and allow log monitoring. The details are described below.

In the current version, Substrate and Cosmos acts as two separate applications that can interact using ABCI interface based on GRPC.

The transaction processing scheme of our application is shown on Fig. 1.   

![Figure 1](https://i.ibb.co/bP713sJ/Architecture-direct.png)
Figure 1 - Transaction and block processing in Substrate-Cosmos app

Cosmos users may interact with Cosmos runtime using standard Cosmos CLI, but using Substrate RPC instead of Tendermint, as it's shown on Fig.2.

![Figure 2](https://i.ibb.co/nPJPqtJ/CLI-scheme.png)
Figure 2 - Interaction between Cosmos CLI and Cosmos node using Substrate RPC

The project development can be divided into several main points (we will describe the reasons why these components are important in this section and the list of features we are going to implement in the Development Roadmap section):

### ABCI and RPC

The implementation of ABCI and RPC are related things because RPC is used to redirect calls from CLI to the Cosmos app using ABCI.

Firstly we want to provide a necessary functional RPC like the Tendermint has, here is the Tendermint documentation of the RPC https://docs.tendermint.com/master/rpc/#/. It will allow full use of the Cosmos CLI and to get important information about the node state for the Cosmos developers. 

Here it is a short description of the RPC:
- `Websocket rpcs` - subscribe/unsubscribe are reserved for websocket events.
- `Info rpcs` - Informations about the node APIs.
- `Tx rpcs` - transaction broadcast APIs.
- `ABCI rpcs` - ABCI apis (`abci_query` method, `abci_info` method)
- `Unsafe rpcs` - unsafe apis (`dial_seeds` method, `dial_peers` method)

We will focus on `Tx_prcs` and `ABCI_rpcs`, because they are most important for interaction with node. Methods from Info_rpcs and Websocket_rpcs are also important and will be implemented during the next phases.

Also, we will implement other ABCI functions such as `Query`, `Info` etc. That is used by the Tendermint RPC (rpc `abci_query` method redirects the data to the ABCI `Query` method).

The list of the remaining ABCI functions:
- `Query` - query for data from the application at current or past height (is used by the abci_query rpc method).
- `Info` - returns information about the application state (is used by the abci_info rpc method). Used to sync Tendermint with the application during a handshake that happens on startup.
- `Echo` - echo a string to test an abci client/server implementation
- `Flush` - signals that messages queued on the client should be flushed to the server. It is called periodically by the client implementation to ensure asynchronous requests are actually sent, and is called immediately to make a synchronous request, which returns when the Flush response comes back.
- `SetOption` - set non-consensus critical application specific options.

There is also a set of `Snapshot` methods that allows to create a snapshot of the current state and share it, these features are not critical for the system but may have a number of unexpected difficulties and may be implemented later

### Validators and Consensus

Network security depends on consensus mechanisms. Both Substrate and Cosmos use DPoS BFT consensuses but with some differences. Staking during validators elections is one of the main token use cases. In our case,  Substrate is responsible for the consensus layer, but token and stacking logic is defined in Cosmos, so we need to elect Substrate validators according to the Cosmos stacking system. For this purpose we will need to match Cosmos and Substrate validator addresses, so that they can be elected in Cosmos and participate in consensus in Substrate. 

Also, in Substrate consensuses, all validators are equal because of NPoS election, but in Cosmos validator`s weight in consensus depends on its stake, so we need to use weighted voting in BABE and GRANDPA

### Nodes synchronization 
In the current versions, a user launches two separate programs - Substrate node and Cosmos node that interact using GRPC. These nodes must be synchronized for correct work. Also, it may be inconvenient for a user to work with two separate windows.

### Pallet subscription
In the current version our abci pallet works almost independently and other pallets can't interact with it. We consider that it will be useful to allow other pallets to subscribe to the abci pallet like it`s done in the session pallet.

### Transaction fees
In our application, each Cosmos transaction is covered with a Substrate transaction, so transaction fee must be paid twice - in Cosmos and Substrate native tokens. In the current version we use signed Substrate transactions and predefined accounts with large balances. We suppose that matching Substrate and Cosmos tokens will not give any profit, but enlarge the database and complicate transaction processing. We propose to use unsigned Substrate transactions.

## Ecosystem Fit 
No.

## Team members
* Oleksandr Marukhnenko - Team Leader
* Alex Pozhylenkov - Blockchain Engineer
* David Knyshenko- Blockchain Engineer


## Team Website	
* https://adoriasoft.com
* https://blockchainonline.academy


## Legal Structure 

The company registered under the laws of Estonia

Registry code: 14422124

Name: Adoriasoft OÜ

Address: Harju maakond, Tallinn, Lasnamäe linnaosa, Sepapaja tn 6, 15551

Legal form: Private limited company

Value Added Tax identification number: EE102046849


## Team's experience
Our team has rich experience with different blockchain technologies, including Substrate and Cosmos. We`ve successfully finished the first phase of Cosmos-SDK parachain development kit project supported by Web3 grant. There we created a basic integration between Substrate and Cosmos SDK.


## Team Code Repos
* https://github.com/adoriasoft/polkadot_cosmos_integration
* https://github.com/adoriasoft/cosmos-sdk
* https://github.com/VeriBlock (public / private repos)
* https://github.com/tokenio (private solidity repos)
* https://github.com/adoriasoft/ton_fungible_token 
* https://github.com/adoriasoft/ton_payment_mixer (2nd place in TON contest)

## Development Roadmap

### Milestone 1 — Finish ABCI and RPC main features— (6-7) weeks

Here we will give a general description of the features we want to implement and how they will look like for end-users, it is difficult to predict some implementation details “under the hood” and they may vary.

In the current version we've implemented the main methods of ABCI (checkTx, deliverTx, beginBlock, endBlock, commit, initChain), but there is a set of other useful ABCI methods that can be implemented (Info, SetOption, Query, Flush, Echo). Tendermint acts as an intermediary between Cosmos CLI and application, the same should be done by Substrate. Some of these calls are just redirected by Tendermint, but others may be processed in a more complex way. Also, Tendermint reacts on Cosmos ABCI responses, and one of the most important cases is validators list and consensus parameters updates according to EndBlock response.

**ABCI and RPC**
* We will implement Transactions broadcast APIs and ABCI in Substrate RPC APIs similar to https://docs.tendermint.com/master/rpc/#/ .
* We will implement the calls of Info, SetOption, Query, Flush, Echo ABCI methods  in Substrate RPC and ABCI_pallet so that they can be used for interaction between Cosmos CLI and Cosmos node.
* We will implement the processing of ABCI responses in ABCI pallet similar to their processing in Tendermint (excluding validator list and consensus parameters updating in EndBock, it will be done during next milestone)

**Transaction fees**
* Cosmos transactions will be covered with Substrate unsigned transactions.

**Other**
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will build a Docker image with (e.g.) our Substrate chain, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.


### Milestone 2 — Validators, consensus, node synchronization and other features— (7-9) weeks

**Validators election and consensus**
* We will modify ABCI pallet so that it will be able to update the list of validator with their weights and consensus parameters according to EndBlock responses.
* We will connect BABE and GRANDPA pallets to Substrate node and use weighted voting in these consensuses.
* We will configure Substrate and Cosmos so that validators partisipating in Substrate consensus will get rewards in Cosmos token.

**Nodes synchronization**
* We will modify Cosmos launcher so that it will be able to start Substrate node automatically, possibly as a daemon, using special flags.
* Cosmos nodes will be able to monitor substrate logs and stop both nodes in the case of a crash.

**Pallet subscription**
* We will provide other Substrate pallets functionality to subscribe on abci pallet like it's done in session pallet.

**Other**
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will build a Docker image with (e.g.) our Substrate chain, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.


## Future Plans

### Phase 3 (10-12 weeks)

**Nodes synchronization**

Unsynchronization can be caused by a number of reasons: one of the nodes can crash, blockchain or state storage may be damaged.  In the case of unsynchronization between Cosmos and Substrate, chain and state should be returned to a shorter chain, it's related to the fork resolution problem, described in next subsection. 

*Planned deliverables:*
- Synchronize nodes in case of asynchronization (choose the shorter chain and request other blocks from the network);
- Simulate an attack that causes asynchronity.

**Fork resolution**

In Tendermint, block producing and finalization are a single process, so forks can happen only in the case of the validators misbehavior. Substrate consensus divide this process into two parts: BABE\AURA for block producing and GRANDPA for block finalization; this approach is faster, but creates orphan blocks. So, Cosmos-Substrate nodes should detect forks, roll-back their state and choose finalized branches.  

*Planned deliverables:*
- Connect Cosmos rollback mechanisms with Substrate;
- Simulate an attack that causes fork.
	
**Governance + Runtime upgrade**

Both systems have government mechanisms that allows to change system parameters and even the source code in the case of Substrate. Governance mechanisms are controlled by referendum system, where each change must be approved by token-based voting. Cosmos internal governance can work despite of used consensus. We want to allow Cosmos users to manage not only the Cosmos part of their nodes, but the Substrate part too. A special case of governance is runtime upgrade that needs additional research.

*Planned deliverables:*
- Allow Substrate parameters updates using Cosmos governance;
- Allow Substrate runtime updates using Cosmos governance.

**Slashing**

Slashing mechanisms prevent or, at least, minimize validators misbehavior in both Substrate and Cosmos systems. Each validator has a deposit that can be slashed in case of malicious actions. Fishermen in Substrate or Hackers in Cosmos can send claims about misbehavior. 

High-level misbehavior like validator collusion is difficult to detect automatically and it may require claims from users and voting for decisions. We think that this case doesn`t depend on consensus and will work in Cosmos app with no changes. Simpler cases like equivocating can be detected and claimed automatically. We think about usage off-chain workers for this purpose.

*Planned deliverables:*
- Connect Substrate equivocating detection with Cosmos slashing.
	
**Transaction priority**

Transactions in the transaction pool are ordered according to some priorities, a validator may want to prioritize transactions according to a custom criterium.
Substrate method `validate_transaction` returns `TransactionValidity` struct, its field `priority` determines the transaction priority in the transaction pool. We add simple logic that increases the priority of transactions according to Cosmos respond, actually:

`priority += GasWanted - GasUsed`

We want to analyze and make the priority system more customizable.
	
*Planned deliverables:*
- More complex, possibly, customizable transaction priority system.

### Phase 4 (10-11 weeks)

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

There are a set of additional APIs in Tendermint RPC( Info_rpcs and Websocket_rpcs https://docs.tendermint.com/master/rpc/#/ ), they are not critical for the work of Substrate-Cosmos node, but make user interface more convenient and usable.

*Planned deliverables:*
- implement all methods from Tendermint RPC in Substrate RPC.

### Phase 5
The main goal of our project is to allow blockchains based on our Substrate-Cosmos SDK to interact in both Polkadot and Cosmos systems. Now it's difficult to describe the details of this phase because both systems are still under development and many aspects may be changed, so deliverables.

*Planned deliverables:*
- Add IBC module to Cosmos;
- Connect node to Cosmos Hub;
- Add Polkadot consensus and XCMP to Substrate part;
- Implement Cosmos module for using XCMP;
- Connect node to Polkadot Relay Chain (probably to a test relay chain, because the mainnet will have a rather complex procedure of registration new parachains).

## Additional Information
For detailed estimation of this and next phases, please, follow link https://docs.google.com/spreadsheets/d/1XmjpptwhcV1PIFM7F6hpsbtW7W44XvW7kAfrenXTSUg/edit#gid=0 
