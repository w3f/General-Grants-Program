# Python Substrate API

## Project description
This project develops a Python Substrate API client and libraries for general use. The client will be modeled after polkadot-js/api. 

Our organization is on an ongoing mission of building the Polkascan multi-chain explorer. With our first wave grant (https://medium.com/web3foundation/web3-foundation-grants-wave-one-winners-2a9cd39f1fbc), the Python-libraries we developed - Py-Scale-Codec (https://github.com/polkascan/py-scale-codec) and Py-Substrate-Interface (https://github.com/polkascan/py-substrate-interface) - have been limited in scope to match the requirements of our block explorer use-case. This project extends and feature-completes these two libraries that have been developed as part of the Polkascan project for general use.

We believe in the success of Substrate and Polkadot, we are highly invested in the ecosystem from day one and are highly invested in Python. This project aims to lower the friction of using Python with Substrate-based chains and the completion of the client libraries will benefit many teams in the community. On top of that, a generalized Python Substrate API will give many more developers easy access to integrate existing Python applications or any other language based application with existing and new Substrate chains. 

### Why Python Substrate API is good for the ecosystem
While high quality well documented APIs help communities integrate with products in general, and while at first glance Python is great for Web (2.0) Development, Python Substrate API will be especially helpful for machine learning, complex data analysis, visualization and it is great language for scientific computing.

### Why our team is interested
This work fits WEB3SCAN's (Polkascan's) short-term agenda of building its multi-chain explorer (Polkascan MC and its public instance https://polkascan.io) and a generalized Substrate Block Explorer (Polkascan PRE). 

This work fits WEB3SCAN's (Polkascan's) mid-term agenda of building a full Python-based Polkadot Runtime Environment (PRE) of which a feature-complete Python Substrate Interface is a key component. Please refer to the Outlook section for details. In addition we believe that our organization is best positioned to complete this project in a timely and cost-effective manner by the highest quality standards.

## Organization & team
### Legal structure
Dutch BV (Limited Liability Company)

### Execution
Work of this grant will be contracted and executed by the legal structure, its employees or its subcontractors under direct supervision of the leadership team.

### Open-source license
All artifacts which result from this grant will be open-sourced under the GPLv3 license.

### Leadership team
* Emiel Sebastiaan (Emiel)
* David-Jan Hoogendoorn (Dave)
* Arjan Zijderveld (Arjan)

### Team's experience
Our team has worked together for over 10 years and is responsible for the Polkascan project, which provides the first and only multi-chain explorer for any Substrate-based blockchain. The team is also responsible for the Polkasource project, which provides ITSM services in the Polkadot ecosystem. 

### Team websites
#### WEB3SCAN
Company website: https://web3scan.com

#### Polkascan
* Live multi-chain explorer: https://polkascan.io
* Medium: https://medium.com/polkascan 
* Twitter: https://twitter.com/polkascan 

#### Polkasource
* Medium: https://medium.com/polkasource
* Twitter: https://twitter.com/polkasource
* DockerHub: https://hub.docker.com/u/polkasource

### Team code repositories
* openAware BV: https://github.com/openaware (internal repositories)
* Polkascan: https://github.com/polkascan (public open-source repositories)
* Polkasource: https://github.com/polkasource (public open-source repositories)
* Emiel: https://github.com/emielvanderhoek (personal GitHub account)
* Dave: https://github.com/dave4you (personal GitHub account)
* Arjan: https://github.com/arjanz (personal GitHub account)

### Team LinkedIn profiles
* Dave: https://nl.linkedin.com/in/dhoogendoorn
* Arjan: https://nl.linkedin.com/in/arjanzijderveld

## Development Roadmap
Please note the team also has other features and work items outside of this grant application (though all in relation to the Polkascan mission). 

Our prior work on the Python Substrate API in relation to the block explorer use-case has been mostly focused on implementing the SCALE-codec, with a particular narrow focus on development of a generalized SCALE-**decoder**. 

This project extends prior artifacts and implements new artifacts:

1. Extend Py-Scale-Codec with:
    * a generalized SCALE-**encoder**
2. Extend Py-Substrate-Interface with:
    * standard methods to target all native Substrate JSON-RPC-methods
    * helper methods to implement SCALE-decoded inputs and outputs
3. Implement a new Python (Falcon) application: Substrate-Interface-API with:
    * support for all native Substrate JSON-RPC-methods
    * support for dynamic runtime defined discovery methods to list, identify and metadata definition of individual storage-functions, call-functions, event_types, type_primitives and constants
    * support for enriched dynamic runtime defined storage-functions with SCALE-decoded inputs and outputs
    * enriched dynamic runtime defined call-functions with SCALE-decoded inputs that produce unsigned extrinsic payloads ready for signing
4. Implement a new Angular application: Substrate-Interface-GUI with:
    * minimum functionality to demonstrate usage of all endpoints and methods
5. Implement Docker support with:
    * a dockerfile for independent repositories.
    * a versioned docker image for the Python Substrate API application
    * docker compose setup for multiple live networks to prove this project provides a generalized Python Substrate API.
    * a docker compose setup for a full stack of the Python Substrate API application in combination with a Substrate-clients for Kusama network.
    * a docker compose setup for a full stack of the Python Substrate API application in combination with a Substrate-clients for Edgeware network.

### Architecture
The white components in figure 1 are provided by Substrate. The colored components are provided by the work of this project.
![afbeelding](https://user-images.githubusercontent.com/14069142/64250421-60b1b580-cf16-11e9-9bb9-840af6b30b6e.png)
_Figure 1: Architecture of the generalized Python Substrate API stack_

### Example
The left-hand side of figure 2 shows how a storage function is currently executed using Substrate's JSON-RPC API. When looking at the technical forums (such as Riot) the very first question any developer asks when using the Substrate JSON-RPC is about codec related issues with the JSON-RPC. The storage function has two input parameters: 1) the storage_key for the low-level key/value store and optionally 2) a blockhash to lookup a particular historical state in the key-value store. The result data is SCALE-encoded and not very useful since it misses any decoding context.

The right-hand side of figure 2 shows how the Python Substrate API solves this user-experience problem. In this case the storage function has multiple (variable number of) input parameters: 1) module, 2) storage_function, optionally depending on the particular storage function 3) a variable number of function parameters and 4) block_number. The result data is SCALE-decoded and has a decoding context.
![afbeelding](https://user-images.githubusercontent.com/14069142/64329436-8cdd3d00-cfcf-11e9-9b75-e637bde77c46.png)
_Figure 2: Example of an enriched storage call with runtime context_

### Scope
Account creation, account management and cryptographic signing remains off-scope for this project. WS-API with push events remains off-scope for this project.

## Funds Required Overall
25,000 USD and the team would accept 100% of payment in DOTs

### Timeline and Milestones
This project will be executed in two full months and can commence as soon as the grant application is approved.

#### Milestone 1: duration: 4 weeks
Basic application architecture with all artifacts
- Artifact 1: `py-scale-codec` repository in the `polkascan` organization on Github
- Artifact 2: `py-substrate-interface` repository in the `polkascan` organization on Github
- Artifact 3: `substrate-interface-api` repository in the `polkascan` organization on Github
- Artifact 4: `substrate-interface-gui` repository in the `polkascan` organization on Github
- Artifact 5: `substrate-interface` repository in the `polkascan` organization on Github

Full compatibility with native Substrate JSON-RPC
- Author RPC-methods
```
RPC 1.1. author_insertKey(keyType, suri, maybePublic) // Insert a key into the keystore.
RPC 1.2. author_pendingExtrinsics() // Returns all pending extrinsics, potentially grouped by sender
RPC 1.3. author_removeExtrinsic(bytesOrHash) // Remove given extrinsic from the pool and temporarily ban it to prevent reimporting
RPC 1.4. author_rotateKeys() // Generate new session keys and returns the corresponding public keys
RPC 1.5. author_submitExtrinsic(extrinsic) // Submit a fully formatted extrinsic for block inclusion
```
- Chain RPC-methods
```
RPC 2.1. chain_getBlock(hash) // Get header and body of a relay chain block
RPC 2.2. chain_getBlockHash(blockNumber) // Get the block hash for a specific block
RPC 2.3. chain_getFinalizedHead() // Get hash of the last finalized block in the canon chain
RPC 2.4. chain_getHeader(hash) // Retrieves the header for a specific block
```
- State RPC-methods
```
RPC 3.1. state_call(method, data, block) // Perform a call to a builtin on the chain
RPC 3.2. state_getChildKeys(childStorageKey, key, block) // Retrieves the keys with prefix of a specific child storage
RPC 3.3. state_getChildStorage(childStorageKey, key, block) // Retrieves the child storage for a key
RPC 3.4. state_getChildStorageHash(childStorageKey, key, block) // Retrieves the child storage hash
RPC 3.5. state_getChildStorageSize(childStorageKey, key, block) // Retrieves the child storage size
RPC 3.6. state_getKeys(key, block) // Retrieves the keys with a certain prefix
RPC 3.7. state_getMetadata(block) // Returns the runtime metadata
RPC 3.8. state_getRuntimeVersion(hash) // Get the runtime version
RPC 3.9. state_getStorage(key, block) // Retrieves the storage for a key
RPC 3.10. state_getStorageHash(key, block) // Retrieves the storage hash
RPC 3.11. state_getStorageSize(key, block) // Retrieves the storage size
RPC 3.12. state_queryStorage(keys, startBlock, block) // Query historical storage entries (by key) starting from a start block
```
- System RPC-methods
```
RPC 4.1. system_chain() // Retrieves the chain
RPC 4.2. system_health() // Return health status of the node
RPC 4.3. system_name() // Retrieves the node name
RPC 4.4. system_networkState() // Returns current state of the network
RPC 4.5. system_peers() // Returns the currently connected peers
RPC 4.6. system_properties() // Get a custom set of properties as a JSON object, defined in the chain spec
RPC 4.7. system_version() // Retrieves the version of the node
```

Introduction of runtime specific JSON-RPC methods
- Runtime RPC-methods for SCALE-decoded metadata specification
```
RPC 5.1. runtime_getMetadata() // Retrieves SCALE-decoded JSON-data of the runtime metadata specification of the current state
RPC 5.2. runtime_getMetadataByHash(hash) // Retrieves SCALE-decoded JSON-data of the runtime metadata specification of a distinct historical state by blockHash
RPC 5.3. runtime_getMetadataByBlockNumber(blockNumber) // Retrieves SCALE-decoded JSON-data of the runtime metadata specification of a distinct historical state by blockNumber
```

- Runtime RPC-methods for discovery of runtime modules
```
RPC 6.1. runtime_getModules() // Retrieves a list of the runtime modules of the current state
RPC 6.2. runtime_getModulesByHash(hash) // Retrieves a list of the runtime modules of a distinct historical state by blockHash
RPC 6.3. runtime_getModulesByBlockNumber(blockNumber) // Retrieves a list of the runtime modules of a distinct historical state by blockNumber
```

- Runtime RPC-methods for discovery of runtime call function specifications
```
RPC 7.1. runtime_getCallFunctions() // Retrieves specification of the runtime callFunctions of the current state
RPC 7.2. runtime_getCallFunctionsByHash(hash) // Retrieves specification of the runtime callFunctions of a distinct historical state by blockHash
RPC 7.3. runtime_getCallFunctionsByBlockNumber(blockNumber) // Retrieves specification of the runtime callFunctions of a distinct historical state by blockNumber
RPC 7.4. runtime_getCallFunction(module, callFunction) // Retrieves specification of one specific runtime callFunction of the current state
RPC 7.5. runtime_getCallFunctionByHash(module, callFunction, hash) // Retrieves specification of one specific runtime callFunction of a distinct historical state by blockHash
RPC 7.6. runtime_getCallFunctionByBlockNumber(module, callFunction, blockNumber) // Retrieves specification of one specific runtime callFunction of a distinct historical state by blockNumber
```

- Runtime RPC-methods for discovery of runtime storage functions specifications
```
RPC 8.1. runtime_getStorageFunctions() // Retrieves specification of the runtime storageFunctions of the current state
RPC 8.2. runtime_getStorageFunctionsByHash(hash) // Retrieves specification of the runtime storageFunctions of a distinct historical state by blockHash
RPC 8.3. runtime_getStorageFunctionsByBlockNumber(blockNumber) // Retrieves specification of the runtime storageFunctions of a distinct historical state by blockNumber
RPC 8.4. runtime_getStorageFunction(module, storageFunction) // Retrieves specification of one specific runtime storageFunction of the current state
RPC 8.5. runtime_getStorageFunctionByHash(module, storageFunction, hash) // Retrieves specification of one specific runtime storageFunction of a distinct historical state by blockHash
RPC 8.6. runtime_getStorageFunctionByBlockNumber(module, storageFunction, blockNumber) // Retrieves specification of one specific runtime storageFunction of a distinct historical state by blockNumber
```

- Runtime RPC-methods for discovery of runtime event specifications
```
RPC 9.1. runtime_getEvents() // Retrieves specification of the runtime events of the current state
RPC 9.2. runtime_getEventsByHash(hash) // Retrieves specification of the runtime events of a distinct historical state by blockHash
RPC 9.3. runtime_getEventsByBlockNumber(blockNumber) // Retrieves specification of the runtime events of a distinct historical state by blockNumber
RPC 9.4. runtime_getEvent(module, event) // Retrieves specification of one specific runtime event of the current state
RPC 9.5. runtime_getEventByHash(module, event, hash) // Retrieves specification of one specific runtime event of a distinct historical state by blockHash
RPC 9.6. runtime_getEventByBlockNumber(module, event, blockNumber) // Retrieves specification of one specific runtime event of a distinct historical state by blockNumber
```

- Runtime RPC-methods for discovery of runtime constant specifications and values
```
RPC 10.1. runtime_getConstants() // Retrieves specification and SCALE-decoded JSON-data of the runtime constants of the current state
RPC 10.2. runtime_getConstantsByHash(hash) // Retrieves specification and SCALE-decoded JSON-data of the runtime constants of a distinct historical state by blockHash
RPC 10.3. runtime_getConstantsByBlockNumber(blockNumber) // Retrieves specification and SCALE-decoded JSON-data of the runtime constants of a distinct historical state by blockNumber
RPC 10.4. runtime_getConstant(module, storageFunction) // Retrieves specification and SCALE-decoded JSON-data of one specific runtime constant of the current state
RPC 10.5. runtime_getConstantByHash(module, storageFunction, hash) // Retrieves specification and SCALE-decoded JSON-data of one specific runtime constant of a distinct historical state by blockHash
RPC 10.6. runtime_getConstantByBlockNumber(module, storageFunction, blockNumber) // Retrieves specification and SCALE-decoded JSON-data of one specific runtime constant of a distinct historical state by blockNumber
```

Documentation
- Artifact 1: Getting started with the Python SCALE-codec
- Artifact 2: Getting started with the Python Substrate Interface
- Artifact 3: Documentation and usage of all RPC-methods for use with Postman
- Artifact 4: Documentation and usage of all RPC-methods with the GUI 
- Artifact 5: Running the Python Substrate API

Payout: 12,500 USD

#### Milestone 2: duration: 4 weeks
Introduction of runtime specific JSON-RPC methods
- Runtime RPC-methods for discovery of runtime type registry
```
RPC 11.1. runtime_getTypeRegistry() // Retrieves SCALE-decoded JSON-data of the runtime types of the current state
RPC 11.2. runtime_getTypeRegistryByHash(hash) // Retrieves SCALE-decoded JSON-data of the runtime types of a distinct historical state by blockHash
RPC 11.3. runtime_getTypeRegistryByBlockNumber(blockNumber) // Retrieves SCALE-decoded JSON-data of the runtime types of a distinct historical state by blockNumber
RPC 11.4. runtime_getType(type) // Retrieves SCALE-decoded JSON-data of one specific runtime type of the current state
RPC 11.5. runtime_getTypeByHash(type, hash) // Retrieves SCALE-decoded JSON-data of one specific runtime type of a distinct historical state by blockHash
RPC 11.6. runtime_getTypeByBlockNumber(type, blockNumber) // Retrieves SCALE-decoded JSON-data of one specific runtime type of a distinct historical state by blockNumber
```

- Runtime RPC-methods for handling custom runtime types
```
RPC 12.1. runtime_getCustomTypes(specVersion) // Retrieves custom types and their respective decoding context for a specific runtime specification
RPC 12.2. runtime_setCustomTypes(specVersion, data) // Sets custom types in bulk and their respective decoding context for a specific runtime specification
RPC 12.3. runtime_addCustomType(specVersion, type, data) // Adds one specific custom type and its respective decoding context for a specific runtime specification
RPC 12.4. runtime_removeCustomType(specVersion, type) // Removes one specific custom type and its respective decoding context for a specific runtime specification
RPC 12.5. runtime_resetCustomTypes(specVersion) // Removes all custom types and their respective decoding context for a specific runtime specification
```

- Runtime RPC-methods for runtime storage functions (examples in appendix 1)
```
RPC 13.1. runtime_getState(module, storageFunction[, params]) // Retrieves SCALE-decoded JSON-data of one specific runtime StorageFunction of the current state by calling the storageFunction with SCALE-decoded inputs 
RPC 13.2. runtime_getStateByBlockHash(module, storageFunction[, params], hash) // Retrieves SCALE-decoded JSON-data of one specific runtime StorageFunction of a distinct historical state by blockHash by calling the storageFunction with SCALE-decoded inputs 
RPC 13.3. runtime_getStateByBlockNumber(module, storageFunction[, params], blockNumber) // Retrieves SCALE-decoded JSON-data of one specific runtime StorageFunction of a distinct historical state by blockNumber by calling the storageFunction with SCALE-decoded inputs 
```

- Runtime RPC-methods for runtime call functions (examples in appendix 2)
```
RPC 14.1. runtime_composeCall(module, callFunction[, params]) // Composes a SCALE-encoded extrinsic payload of a specific transaction type ready for signing by an external library
```

Documentation
- Artifact 1: Getting started with the Python SCALE-codec
- Artifact 2: Getting started with the Python Substrate Interface
- Artifact 3: Documentation and usage of all RPC-methods for use with Postman
- Artifact 4: Documentation and usage of all RPC-methods with the GUI 
- Artifact 5: Running the Python Substrate API

Payout: 12,500 USD

## Outlook
This project should lead to the go-to library/application for any application developer that intends to interact with any Substrate-runtime. The artifacts of this project provide a rich API to the Substrate-runtime with full decoding context.

This project should lead to WEB3SCAN's Polkasource product-line to service public/private node services which enriched APIs beyond the basic JSON-RPC API that Substrate offers.

The generalized Python Substrate API aligns with our mid-term objective of building a full Python-based implementation of the Polkadot Runtime Environment (PRE). Critical components for building a Python PRE are: 1) SCALE-codec, 2) Trie DB, 3) Libp2p Networking, 4) Consensus Babe/Grandpa. 5) WASM interpreter. Time can work in our favor since some components (3 and 5) may be available soon due to work in neighboring communities.

## Additional Information
### Are there any other projects similar to yours?
* Javascript implementation: https://polkadot.js.org/api/
* Go implementation (WIP): https://github.com/pstehlik/Web3-collaboration/blob/b39538a57e8b0de20f928c04716fa725344bb954/grants/speculative/centrifuge_go_substrate_rpc_client.md
* C++ implementation (WIP): https://github.com/usetech-llc/Web3-collaboration/blob/8042d35356dce871fe368f60388dad492f792cec/grants/speculative/cpp_api.md
* Rust implementation (WIP): https://github.com/brenzi/Web3-collaboration/blob/85da47fb90324c5c6240834a4bcdcfa1f59752a6/grants/speculative/substrate-api-client.md

### How is our project different?
The Python Substrate API application stack is distinct from the other projects mentioned in this paragraph for the obvious reason that it is a Python implementation, in contrast to the languages of the other implementations. Another key difference with the other projects is that our Python Substrate API project not only provides generalized libraries for the respective programming language, but also provides a generalized application that services enriched JSON-RPC endpoints with SCALE-decoded input and output. Thus extending the user-base of the artifacts of this project from Python developers to any developer capable of working with JSON-data.

## Appendix
### Appendix 1: Storage functions available through RPC for Kusama network
```
attestations.RecentParaBlocks({inputparams})
attestations.ParaBlockAttestations({inputparams})
attestations.DidUpdate({inputparams})
authorship.Uncles({inputparams})
authorship.Author({inputparams})
authorship.DidSetUncles({inputparams})
babe.EpochIndex({inputparams})
babe.Authorities({inputparams})
babe.EpochStartSlot({inputparams})
babe.CurrentSlot({inputparams})
babe.SecondarySlots({inputparams})
babe.PendingSecondarySlotsChange({inputparams})
babe.Randomness({inputparams})
babe.NextRandomness({inputparams})
babe.SegmentIndex({inputparams})
babe.UnderConstruction({inputparams})
babe.Initialized({inputparams})
balances.TotalIssuance({inputparams})
balances.Vesting({inputparams})
balances.FreeBalance({inputparams})
balances.ReservedBalance({inputparams})
balances.Locks({inputparams})
claims.Claims({inputparams})
claims.Total({inputparams})
council.Proposals({inputparams})
council.ProposalOf({inputparams})
council.Voting({inputparams})
council.ProposalCount({inputparams})
council.Members({inputparams})
democracy.PublicPropCount({inputparams})
democracy.PublicProps({inputparams})
democracy.DepositOf({inputparams})
democracy.ReferendumCount({inputparams})
democracy.NextTally({inputparams})
democracy.ReferendumInfoOf({inputparams})
democracy.DispatchQueue({inputparams})
democracy.VotersFor({inputparams})
democracy.VoteOf({inputparams})
democracy.Proxy({inputparams})
democracy.Delegations({inputparams})
democracy.LastTabledWasExternal({inputparams})
democracy.NextExternal({inputparams})
democracy.Blacklist({inputparams})
democracy.Cancellations({inputparams})
elections.PresentationDuration({inputparams})
elections.TermDuration({inputparams})
elections.DesiredSeats({inputparams})
elections.Members({inputparams})
elections.VoteCount({inputparams})
elections.ApprovalsOf({inputparams})
elections.RegisterInfoOf({inputparams})
elections.VoterInfoOf({inputparams})
elections.Voters({inputparams})
elections.NextVoterSet({inputparams})
elections.VoterCount({inputparams})
elections.Candidates({inputparams})
elections.CandidateCount({inputparams})
elections.NextFinalize({inputparams})
elections.Leaderboard({inputparams})
elections.Proxy({inputparams})
grandpa.Authorities({inputparams})
grandpa.State({inputparams})
grandpa.PendingChange({inputparams})
grandpa.NextForced({inputparams})
grandpa.Stalled({inputparams})
grandpa.CurrentSetId({inputparams})
grandpa.SetIdSession({inputparams})
imonline.GossipAt({inputparams})
imonline.Keys({inputparams})
imonline.ReceivedHeartbeats({inputparams})
indices.NextEnumSet({inputparams})
indices.EnumSet({inputparams})
offences.Reports({inputparams})
offences.ConcurrentReportsIndex({inputparams})
offences.ReportsByKindIndex({inputparams})
parachains.Authorities({inputparams})
parachains.Parachains({inputparams})
parachains.Code({inputparams})
parachains.Heads({inputparams})
parachains.Watermarks({inputparams})
parachains.UnroutedIngress({inputparams})
parachains.RelayDispatchQueue({inputparams})
parachains.RelayDispatchQueueSize({inputparams})
parachains.DidUpdate({inputparams})
parachains.NextFreeId({inputparams})
session.Validators({inputparams})
session.CurrentIndex({inputparams})
session.QueuedChanged({inputparams})
session.QueuedKeys({inputparams})
session.NextKeys({inputparams})
session.KeyOwner({inputparams})
slots.AuctionCounter({inputparams})
slots.ManagedIds({inputparams})
slots.Deposits({inputparams})
slots.AuctionInfo({inputparams})
slots.Winning({inputparams})
slots.ReservedAmounts({inputparams})
slots.OnboardQueue({inputparams})
slots.Onboarding({inputparams})
slots.Offboarding({inputparams})
staking.ValidatorCount({inputparams})
staking.MinimumValidatorCount({inputparams})
staking.Invulnerables({inputparams})
staking.Bonded({inputparams})
staking.Ledger({inputparams})
staking.Payee({inputparams})
staking.Validators({inputparams})
staking.Nominators({inputparams})
staking.Stakers({inputparams})
staking.CurrentElected({inputparams})
staking.CurrentEra({inputparams})
staking.CurrentEraStart({inputparams})
staking.CurrentEraStartSessionIndex({inputparams})
staking.CurrentEraRewards({inputparams})
staking.SlotStake({inputparams})
staking.ForceEra({inputparams})
staking.SlashRewardFraction({inputparams})
staking.BondedEras({inputparams})
staking.EraSlashJournal({inputparams})
sudo.Key({inputparams})
system.AccountNonce({inputparams})
system.ExtrinsicCount({inputparams})
system.AllExtrinsicsWeight({inputparams})
system.AllExtrinsicsLen({inputparams})
system.NextWeightMultiplier({inputparams})
system.BlockHash({inputparams})
system.ExtrinsicData({inputparams})
system.RandomMaterial({inputparams})
system.Number({inputparams})
system.ParentHash({inputparams})
system.ExtrinsicsRoot({inputparams})
system.Digest({inputparams})
system.Events({inputparams})
system.EventCount({inputparams})
system.EventTopics({inputparams})
technicalcommittee.Proposals({inputparams})
technicalcommittee.ProposalOf({inputparams})
technicalcommittee.Voting({inputparams})
technicalcommittee.ProposalCount({inputparams})
technicalcommittee.Members({inputparams})
technicalmembership.Members({inputparams})
timestamp.Now({inputparams})
timestamp.DidUpdate({inputparams})
treasury.ProposalCount({inputparams})
treasury.Proposals({inputparams})
treasury.Approvals({inputparams})
````

### Appendix 2: Call functions available through RPC for Kusama network
```
attestations.more_attestations({inputparams})
authorship.set_uncles({inputparams})
babe.set_pending_secondary_slots_change({inputparams})
balances.force_transfer({inputparams})
balances.set_balance({inputparams})
balances.transfer({inputparams})
claims.claim({inputparams})
council.execute({inputparams})
council.propose({inputparams})
council.set_members({inputparams})
council.vote({inputparams})
democracy.cancel_queued({inputparams})
democracy.cancel_referendum({inputparams})
democracy.delegate({inputparams})
democracy.emergency_cancel({inputparams})
democracy.external_propose({inputparams})
democracy.external_propose_default({inputparams})
democracy.external_propose_majority({inputparams})
democracy.fast_track({inputparams})
democracy.propose({inputparams})
democracy.proxy_vote({inputparams})
democracy.remove_proxy({inputparams})
democracy.resign_proxy({inputparams})
democracy.second({inputparams})
democracy.set_proxy({inputparams})
democracy.undelegate({inputparams})
democracy.veto_external({inputparams})
democracy.vote({inputparams})
elections.present_winner({inputparams})
elections.proxy_set_approvals({inputparams})
elections.reap_inactive_voter({inputparams})
elections.remove_member({inputparams})
elections.retract_voter({inputparams})
elections.set_approvals({inputparams})
elections.set_desired_seats({inputparams})
elections.set_presentation_duration({inputparams})
elections.set_term_duration({inputparams})
elections.submit_candidacy({inputparams})
finalitytracker.final_hint({inputparams})
grandpa.report_misbehavior({inputparams})
imonline.heartbeat({inputparams})
parachains.deregister_parachain({inputparams})
parachains.register_parachain({inputparams})
parachains.set_heads({inputparams})
session.set_keys({inputparams})
slots.bid({inputparams})
slots.bid_renew({inputparams})
slots.elaborate_deploy_data({inputparams})
slots.fix_deploy_data({inputparams})
slots.new_auction({inputparams})
slots.set_offboarding({inputparams})
staking.bond({inputparams})
staking.bond_extra({inputparams})
staking.chill({inputparams})
staking.force_new_era({inputparams})
staking.force_no_eras({inputparams})
staking.nominate({inputparams})
staking.set_controller({inputparams})
staking.set_invulnerables({inputparams})
staking.set_payee({inputparams})
staking.set_validator_count({inputparams})
staking.unbond({inputparams})
staking.validate({inputparams})
staking.withdraw_unbonded({inputparams})
sudo.set_key({inputparams})
sudo.sudo({inputparams})
system.fill_block({inputparams})
system.kill_storage({inputparams})
system.remark({inputparams})
system.set_code({inputparams})
system.set_heap_pages({inputparams})
system.set_storage({inputparams})
technicalcommittee.execute({inputparams})
technicalcommittee.propose({inputparams})
technicalcommittee.set_members({inputparams})
technicalcommittee.vote({inputparams})
technicalmembership.add_member({inputparams})
technicalmembership.remove_member({inputparams})
technicalmembership.reset_members({inputparams})
technicalmembership.swap_member({inputparams})
timestamp.set({inputparams})
treasury.approve_proposal({inputparams})
treasury.propose_spend({inputparams})
treasury.reject_proposal({inputparams})
```
