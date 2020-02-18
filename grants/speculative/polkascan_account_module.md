# Grant Application: Polkascan Account Module

## Project description
This project extends Polkascan with an enriched `account`-module. The `account`-module can currently be found under the `Accounts`-`Accounts`-menu-structure. In its current state `accounts` have no support for the identity-pallet, have limited attributes, have limited associated entities and only support balances on the `account`-detail page. This project enriches the `account`-entity and thus provides a more complete picture of an account's state (identity, attributes and balances) and activities (associated events/extrinsics) as defined in the Kusama-CC3 runtime. The intended architecture is sufficiently general purpose to provide similar functions to other Substrate-based blockchain.

## Objectives
1. Identity: provide support for the `identity`-pallet.
2. Attributes: addition of account attributes and account classifications.
3. Associations: addition of `1-n`-associations with events & extrinsics.
4. Balances: addition of more complete account balances.

## Technical challenges
### 1. The general-purpose trade-off
From the start of the Polkascan-project we have set out to make Polkascan a general-purpose block explorer and analytics platform that works well with any Substrate-based blockchain. This goals puts constraints on quick fixes and forces us to make architectural choices that allow support for multiple runtimes and multiple blockchains. There is an inherent trade-off between development of features for a single blockchain/runtime with a high pace on one hand and development of features for a general purpose blockchain/runtime with a lower pace on the other hand. Needless to say we believe the latter serves us and the community as a better long-term strategy. This section provides some topics that discuss those trade-offs.

### 2. Considerations with standardized pallets.
Substrate is on the verge of its stable 2.0 release. This stable release will allow for the launch of Polkadot and many other production networks by other teams. Substrate-based blockchains allow for on-chain governance and runtime upgrades. Therefore those networks will always be subject to changing functionality. Although, teams building Substrate-based blockchains have complete freedom to design their runtimes, it is to be expected that some dominant design patterns emerge that will be used by those teams. Many blockchains will use standardized components such as Substrate-pallets for obvious reasons that those have broad community support or simply because those will be audited in some way. Substrate-pallets related to `accounts` could to some extent already be considered a key building blocks for rich account support in Substrate-based chains, for the simple reason that they provide compelling features. In turn those `pallets` provide compelling features for Polkascan.

We have handpicked a number of Substrate-pallets that are in our opinion sufficiently mature (due to the nearing Polkadot launch) to warrant support in our analytics platform Polkascan. This project aims to provide meaningful additions to the Polkascan `account`-module from the following Substrate-pallets: `identity`, `staking`, `democracy`, `council`, `technical committee` and `treasury`.

### 3. Considerations with database-indexes
It is widely known that Substrate - as a blockchain development framework - allows you to build any blockchain. Substrate is therefore general-purpose and in turn we have always aimed to make Polkascan general-purpose. `Accounts`, as implemented in Kusama/Polkadot - and likely many other blockchains - follow the `account/nonce`-pattern that keeps a state of accounts in the runtime. Substrate also allows for blockchains with other design patterns for accounts (utxo) or even for blockchains without any support for accounts at all. `Accounts` are therefore not an essential component of Substrate and thus not an essential component of Polkascan.

We have received a number of requests over the past few months to support seemingly simple features in Polkascan which are at odds with the `general-purpose`-trade-off mentioned earlier. Examples include: a) filtering events for accounts, b) incoming balance transfers, c) staking activity, d) additional tabs on the account-detail page, etc. 

The difficulty with those requests is that the architecture of Polkascan chooses to store the `event` & `extrinsic`-entities in a general purpose data model. An `extrinsic` or `event` does not have a fixed data structure and can allow for `zero` to `n` association with `accounts`. Although Polkascan provides full decoding for both `extrinsics` and `events`, the `general-purpose`-trade-off for those entities in Polkascan's storage layer lies in its free-form `JSON`-structure for `extrinsics` and `events`. The feature requests require database indexes for accounts in those free-form `JSON`-structures. This is an architectural challenge this project aims to solve. Thus those feature requests require a `general-purpose account indexing`-mechanism for `account`-like occurrences in `extrinsics` and `events`. Those database indexes are required to ensure that the explorer remains functional when the network it harvests scales up.

### 4. Considerations with scaling
The Substrate-based blockchains we have seen in the wild so far have not yet seen any significant throughput. Blockchain analytic technologies - such as Polkascan - need to remain functional even at the scale and capacity we have seen with the Bitcoin and Ethereum chains. Well designed general-purpose blockchain analytic technologies favor data harvesting from `events` and `extrinsics` over `state/storage requests` for the simple reason of the performance benefits of the former.

### 5. Considerations with incomplete events
The proposed work of this grant relies heavily on emitted traces of a runtime about its state through events. A simple example illustrates this. Substrate's `indices`-pallet currently emits `event` when an `account_index` is created and emits an `event` when an `account_index` is reaped (removed). Account creation and reaping could occur at any given block. If the platform requires to provide historical analytics on the number of active accounts, it is simply easier (lower footprint) to process `creation`-events and `reaping`-events than to request the complete state for all `accounts`. In its current state with only a few thousand accounts it might still be workable to iterate through storage requests for every account for every block. But this does not scale well with an increase of an order of magnitude of accounts and certainly does not work when the objective is to provide a `near real-time`-analytics platform that has to process everything within the additional constraint of the blocktime of a few seconds. Storage requests simply have too high a footprint.

This in turn assumes and requires proper design of those emitted traces. I.e. any features built on events require those events to be 1) complete, 2) precise and 3) meaningful. In the provided example there should be both a `NewAccount`-event and `ReapedAccount`-event (`complete`), those events need to be emitted only once when the respective state-change happen (`precise`) and those events should leave traces to the `account` they refer to (`meaningful`). Our research so far has addressed a number of shortcoming regarding shortcomings on those criteria for `events` for key Substrate-pallets.

### 6. Considerations with balances
Account balances are arguably among the most important data-points in blockchains. Providing support in a real time analytics platform such as Polkascan is challenging for it combines most considerations that have been discussed in this section.

In general, any account can have balance changes with every new block. A conservative example illustrates this: Assume a blockchain has 10.000 accounts (though this could be orders of magnitude higher). In order for a `dumb` real time analytic platform to keep up with the tip of the blockchain and provide balance data for all accounts for every block it could use a so-called `dragnet`-strategy. It would require to execute 20.000 storage queries (for `freeBalance` and `reservedBalance`) within 6 seconds. If you include `vesting`, `bonding` & `locks`, it would even increase by a higher factor. This also assumes you would start running the analytics platform when the blockchain launches. Even if you manage to keep up with that number of storage queries, you would practically never catch up with the tip of a blockchain that has been running for any significant number of blocks.

A solution in going from a `dumb` analytics platform to a smarter one, lies in the realization that most of the time, most account balances do not change. We apply three main strategies to make Polkascan smarter in providing support for all historical and real-time account balances.

1. Identification
Identifying when accounts have balance changes, significantly lowers the number of storage queries regarding account balances. I.e. only those account balances that have changed are requested.
2. Prediction
The ability to predict account balance changes makes it unnecessary to query account balances altogether.
3. Fail-safe
Since there is an inherent risk of `identification` and `prediction` to be incomplete, a fail-safe consists of account balance snapshots at larger block intervals.

This project will focus on implementing the `identification` and `fail-safe` strategies. Over time (and beyond the scope of this project) maturing identification and prediction strategies will make the fail-safe strategy less important or even redundant.

### Why the Polkascan Rich Account Module is good for the ecosystem
The Polkascan Rich Account Module provides meaningful data for the community and its individual members. Examples include:

- Provide meaningful identities for accounts
- Classification of accounts as: `validator`, `nominator`, `treasury`, `council member`, `technical committee member`, etc
- Rich list: lists accounts in descending order of balance
- Bonding activity per account
- Slashing per account
- Voting activity per account
- Treasury activity
- etc.

### Why our team is interested
This work fits WEB3SCAN's (Polkascan's) agenda of building its multi-chain explorer (Polkascan MC and its public instance https://polkascan.io) and a generalized Substrate Block Explorer (Polkascan PRE).

Our team has been researching the challenges of this project over the past few months and some parts have found their way as features on https://polkascan.io. This project allows us to mature, complete and polish our research activities and perform development activities to include the features in the open-source version of Polkascan for the benefit of the community.

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

This project extends existing artifacts:

1. Extend the [Polkascan-PRE-Harvester](https://github.com/polkascan/polkascan-pre-harvester) artifact.
2. Extend the [Polkascan-PRE-Explorer-API](https://github.com/polkascan/polkascan-pre-explorer-api) artifact.
3. Extend the [Polkascan-PRE-Explorer-GUI](https://github.com/polkascan/polkascan-pre-explorer-gui) artifact.
4. Extend the Docker-Compose [Polkascan-PRE-Explorer-GUI](https://github.com/polkascan/polkascan-pre) artifact.

### Scope
This project is scoped to support Kusama CC3, which manifests the current design specifications of the Polkadot relay chain.

## Funds Required Overall
30,000 USD

### Timeline and Milestones
This project will be executed in two full months and can commence as soon as the grant application is approved.

#### Milestone 1: duration: 4 weeks
Basic application architecture
- Artifact 1: `polkascan-pre-harvester` repository in the `polkascan` organization on Github
- Artifact 2: `polkascan-pre-explorer-api` repository in the `polkascan` organization on Github
- Artifact 3: `polkascan-pre-explorer-gui` repository in the `polkascan` organization on Github
- Artifact 4: `polkascan-pre` repository in the `polkascan` organization on Github

1. Deliverables: Identities
The deliverables in this section will enable the harvester (artifact 1) to store data related to identities, sub-identities and judgement in a data-structure to be disseminated by the explorer-api (artifact 2). The explorer-ui will visualize those data for accounts as followed throughout the user-interface: 1) if the account has an identity set it will show the identity with its judgements, 2) if no identity is set for an account but the account has an account-index (short address), it will show the account-index, 3) in any other case it will default to showing only the regular full address, which is the current situation.
```
Deliverable 1.1. Harvester modifications to store data for (sub)identities/judgements (artifact 1)
Deliverable 1.2. Explorer API modifications to disseminate data for (sub)identities/judgements (artifact 2)
Deliverable 1.3. Explorer GUI modifications to visualize data for (sub)identities/judgements (artifact 3)
```

2. Deliverables: Generalized account storage-structure for database indexes
The deliverables in this section will enable the harvester (artifact 1) to store index-able data related to account-occurrences within events and extrinsics with references to the respective events and extrinsics with meaningful context per attribute or association. The account attributes and associations will be disseminated by the explorer-api (artifact 2). These api end-points can in turn be utilized by the explorer-gui (artifact 3). Those changes are described in sections 3 and 4 of the deliverables.
```
Deliverable 2.1. Harvester modifications to store database-indexes for accounts (artifact 1)
Deliverable 2.2. Explorer API modifications to disseminate data based on database-indexes for accounts (artifact 2)
```

3. Deliverables: New account classifications
Accounts can have various roles within a runtime. In order to determine those roles a number of database-indexes need to be implemented for accounts using the storage-structure described in section 2 of the deliverables. The following classifications will be implemented for accounts and made visible through the explorer-gui (artifact 3).
```
Deliverable 3.1. Classify an account as: `IsValidator` // account is in the validator set of the current session
Deliverable 3.2. Classify an account as: `IsNominator` // account is in the nominator set of the current session
Deliverable 3.3. Classify an account as: `IsCoucilMember` // account is currently in a member of the council
Deliverable 3.4. Classify an account as: `IsTechnicalCommitteeMember` // account is currently in a member of the technical committe
Deliverable 3.5. Classify an account as: `IsTreasury` // account is a/the treasury account
Deliverable 3.6. Classify an account as: `IsRegistrar`// account is currently in a registrar
Deliverable 3.7. Classify an account as: `IsSudo` // account currently has Sudo authorization
Deliverable 3.8. Classify an account as: `WasValidator` // account is in any validator set
Deliverable 3.9. Classify an account as: `WasNominator` // account is in any nominator set
Deliverable 3.10. Classify an account as: `WasCoucilMember` // account is in any council member set
Deliverable 3.11. Classify an account as: `WasTechnicalCommitteeMember` // account is in any technical committee member set
Deliverable 3.12. Classify an account as: `WasRegistrar` // account has at any point been a registrar
Deliverable 3.13. Classify an account as: `WasSudo` // account had Sudo authorization at any point
```

Payout: 15,000 USD

#### Milestone 2: duration: 4 weeks
Basic application architecture
- Artifact 1: `polkascan-pre-harvester` repository in the `polkascan` organization on Github
- Artifact 2: `polkascan-pre-explorer-api` repository in the `polkascan` organization on Github
- Artifact 3: `polkascan-pre-explorer-gui` repository in the `polkascan` organization on Github
- Artifact 4: `polkascan-pre` repository in the `polkascan` organization on Github

4. Deliverables: New account associations
Accounts can have various associations describing their respective activity within a runtime. In order to determine those activities a number of database-indexes need to be implemented for accounts using the storage-structure described in section 2 of the deliverables. The following associations will be implemented for accounts and made visible through the explorer-gui (artifact 3). Those associations will be implemented as distinct tabs on the account-detail page in the explorer-gui.
```
Deliverable 4.1. Account lifecycle activity // Lists all account lifecycle activity (new/reaped) for given account
Deliverable 4.2. Balances transfer activity // Lists all incoming, outgoing transfers, claims and deposits for given account
Deliverable 4.3. Staking bonding activity // Lists all bonding and unbonding activity for given account
Deliverable 4.4. Staking lifecycle activity // Lists all validator sessions for given account
Deliverable 4.5. Staking authored blocks activity // Lists all blocks authored for given account
Deliverable 4.6. Staking slashing activity // Lists all slash events for given acccount
Deliverable 4.7. Staking imonline activity // Lists all ImOnline activity for given account
Deliverable 4.8. Democracy proposal activity // Lists all propose and second activity for given account
Deliverable 4.9. Democracy referendum activity // Lists all referenda voting activity for given account
Deliverable 4.10. Council motion activity // Lists all proposed motions and votes for given account
Deliverable 4.11. Council member activity // Lists all council election terms for given account
Deliverable 4.12. Council election activity // Lists all council election voting activity for given account
Deliverable 4.13. Treasury spending activity // Lists all treasury spending proposals for given account
Deliverable 4.14. Identity lifecycle activity // Lists all lifecylce activity related to identities for given account
Deliverable 4.15. Technical committee proposal activity // Lists all lifecycle activity of proposals and votes for given account
```

5. Deliverables: Account balance snapshots & storage
The deliverables in this section will enable the harvester (artifact 1) to store data related to historical and current balances to be disseminated by the explorer-api (artifact 2). These api end-points can in turn be utilized by the explorer-gui (artifact 3). Those changes are described in section 7 of the deliverables.
```
Deliverable 5.1. Harvester modifications to store data for historical and current balances (artifact 1)
Deliverable 5.2. Explorer API modifications to disseminate data for historical and current balances (artifact 2)
```

6. Deliverables: Accurate current and historical balances
Accounts can have various associations describing their respective activity within a runtime. In order to determine those activities a number of database-indexes need to be implemented for accounts using the storage-structure described in section 2 of the deliverables. The following associations will be implemented for accounts and made visible through the explorer-gui (artifact 3). Those associations will be implemented as distinct tabs on the account-detail page in the explorer-gui.
```
- Deliverable 6.1: Current account balances on account details pages.
- Deliverable 6.2: Current account balances on account overview pages (rich list).
- Deliverable 6.3: Historical account balances table data.
- Deliverable 6.4: Historical account balances chart/graph data.
```

7. Deliverables: Documentation
```
- Deliverable 7.1: Development update
```

Payout: 15,000 USD


## Outlook
This project contributes to achieving the mid-term goals as outlined in our article on [Polkascan Economic Analysis](https://medium.com/polkadot-network/polkascan-economic-analysis-a5861abef63f), featured on the Polkadot Network blog.

## Additional Information
### Similar projects and differentiation
We are building multi-chain exploration and data analytic technology of which the Polkascan-stack is a key component. The Polkadot-ecosystem already shows signs of other block explorers. Particularly interesting is [Polkadot JS Apps](https://polkadot.js.org/apps/#/explorer). In contrast to Polkascan this project has a focus on the current state of the blockchain, rather than focusing on full historical and multi-chain analytics. Like Polkascan however this project has developed its entire stack from the ground up and is like Polkascan a project that has been around from day one. A key difference is that the Polkadot JS Apps project has a Typescript/Javascript codebase and the the Polkascan project has a Python codebase. This is a logical choice given the different goals and objectives of both projects. The other block explorers in the ecosystem all re-use major parts of the technology-stack of either Polkadot JS Apps project ([Polka.io](https://polka.io/)) or the Polkascan-project ([Subscan ](https://kusama.subscan.io/)and [Boka](http://boka.network/#/Kusama)).