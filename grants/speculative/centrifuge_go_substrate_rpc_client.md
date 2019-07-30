# Go Substrate RPC Client 

## Project Description
We are building a Substrate RPC client in Go. The client will be modelled after polkadot-js/api. We believe in the success of Substrate and Polkadot and are highly invested in Go. We want to lower the friction of using Go with Substrate-based chains and believe this broadening of client libraries will benefit many teams in the community. On top of that, a Go Substrate RPC client will give many more developers easy access to integrate existing Go applications with new Substrate chains.
Our team is mainly based in Berlin, part of the local (and international) blockchain ecosystem. We are currently implementing a Substrate-based chain and are integrating our Go-based application with it. Having a more standardized, fully-featured Go RPC client for Substrate will make our work much easier launching the Substrate-based chain + the accompanying application and also, most importantly, help the community overall who work with Go to interact with the Polkadot/Substrate ecosystem of Blockchains.

## Team Members
* Philip Stehlik
* Philip Stanislaus
* Vimukthi Wickramasinghe


## Team Website	
https://centrifuge.io/ 

## Legal Structure 
German GmbH

## Team's Experience
The Centrifuge team, overall, has built a decentralized platform for the financial supply chain (invoices, purchase orders, warehouse receipts) comprising of a P2P network and Ethereum smart contracts over the last 1.5 years. [The platform](https://medium.com/centrifuge/the-centrifuge-protocol-the-inner-workings-4fcbc9f7aa2f) allows [tokenization of any digital assets](https://medium.com/centrifuge/user-mintable-privacy-enabled-nft-via-ethereum-erc-721-662ba7e4425). A strong team in the [DeFi movement](https://medium.com/centrifuge/tinlake-bringing-individual-non-fungible-assets-to-defi-f5ff0c77cadd), they are now building a Centrifuge-specific chain with Substrate and are integrating their existing Go application with the Substrate chain. The Centrifuge team as a whole has deep knowledge in distributed/decentralized applications, libp2p, Golang, Solidity and Ethereum overall, zkSNARKs, and tokenization of assets with NFTs. The sub-team for this project is listed below.

Philip Stanislaus will be the main engineer building the RPC client. Philip has 12+ years of experience as a full-stack engineer. He delivered hundreds of projects and worked with some of the most renowned development ecosystems (Gigster Inc. and Swish Labs). Most recently, Philip worked with the Centrifuge team on the JavaScript client (https://github.com/centrifuge/tinlake.js) and UI (currently private) for Tinlake (https://tinlake.com), a DeFi platform that allows users to tokenize assets and use them as collateral for loans from MakerDAO, Compound and others. Last year, Philip was the lead architect and engineer on THORChain, a decentralized exchange protocol built on top of the Cosmos SDK. He wrote most of the open sourced protocol (https://github.com/thorchain/THORChain) as well as the block explorer (https://github.com/thorchain/THORChain.info) and the decentralized exchange (https://github.com/thorchain/ASGARDEX).

Philip Stehlik will be the main contact for the grant application, and the project overall. He will be leading the project/product design and be part of the architecture/implementation team of the Go-Substrate RPC client implementation. Philip has been developing and delivering software projects for 15+ years. He created and implemented financial software projects at companies like Apple, Coca Cola, Red Bull, Toyota and more. He co-founded Taulia (https://taulia.com) in 2009 and lead the team from product inception to more than 200 employees. He developed the first versions of the product, integrations into ERP systems, data-exchange and mapping technology, as well as the web platform. Taulia now serves 90 of the Fortune 100 companies, connects more than 1.5million companies worldwide and provides more than $6bn per quarter in financing to the companies on the network. 
Today, Philip the co-founder and CTO of Centrifuge (https://centrifuge.io - founded in 2017, today 18 people-strong, based in Berlin), where he developed the initial version of the product and built out the team. Centrifuge enables decentralized, secure, provable data exchange between businesses. They exchange documents like invoices, orders, real-estate agreements, funding agreements, and more - all tamper-proof and secure. The exchanged documents are then tokenized on Ethereum to bring these assets into the DeFi ecosystem. Philip is leading the Centrifuge Chain implementation based on Substrate.

Vimukthi (Vim) Wickramasinghe will be an engineer working on the RPC client implementation. Vim started his career as Software Engineer at the London Stock Exchange Group in 2010 working on high performance backend and frontend applications. Since then he worked as Software Engineer in track&trace (AfterShip) and robo advisors (Scalable Capital) working with Java, Node.js, and Go. Vim is working as software engineer at Centrifuge on the go-centrifuge implementation as well as the Substrate-based Centrifuge Chain implementation. Vimukthi implemented the Go version of beanstalkd https://github.com/beanstalkg/beanstalkg (originally implemented in C).

## Team Code Repos
* https://github.com/centrifuge/go-centrifuge
* https://github.com/centrifuge/protocol
* https://github.com/centrifuge/centrifuge-ethereum-contracts
* https://github.com/centrifuge/tinlake
* https://github.com/centrifuge/precise-proofs
* Philip Stanislaus: https://github.com/philipstanislaus 

## Team LinkedIn Profiles
* Philip Stehlik: https://www.linkedin.com/in/pstehlik/
* Philip Stanislaus: https://www.linkedin.com/in/philipstanislaus/ 
* Vimukthi Wickramasinghe: https://www.linkedin.com/in/vimukthicom


## Intended Language of Development
Go

## Development Roadmap
Please note the team also has other features and work items outside of this grant application. The timeline below is not based on three people working full-time but rather cumulative 1 full-time person.

Deliverables marked with * have a detailed list of types/methods that will be implemented in the next section “Specification Details”

### Timeline and Milestones
#### Milestone 1
Duration: 4 weeks
Deliverables:
* D1: Repository including a README that describes the project and explains how to run, test and contribute
* D2: Local testnet in a docker container that will also run on CI
* D3: Coded types including unit tests*
* D4: Metadata handling including unit tests*
* D5: Basic version of the Go Substrate RPC Client including end-to-end tests that run on CI*
* D6: Script to run tests from local docker image against a deployed Substrate chain
* Verifiable by:
* D1, D2: Investigating GitHub repository 
* D3, D4, D5, D6: CI build and test status, documentation, running tests locally from a docker image against a deployed Substrate chain (e.g. Alexander network)
 
Payout: 10,000 USD

#### Milestone 2
Duration: 4 weeks
Deliverables: 
* D7: Primitive types including unit tests*
* D8: RPC core functionality*
* D9: Full-featured integration and functional end-to-end tests
* Verifiable by:
* D7, D8, D9: CI build and test status, documentation, running tests locally from a docker image against a deployed Substrate chain (e.g. Alexander network)

Payout: 10,000 USD

#### Milestone 3
Duration: 4 weeks
Deliverables
* D10: RPC types including unit tests*
* D11: Remaining RPC functionality*
* D12: Documentation with the following functionality: a) Simple connect, b) Listen to blocks, c) Unsubscribe from listening
* Verifiable by:
* D10, D11: CI build and test status, documentation, running tests locally from a docker image against a deployed Substrate chain (e.g. Alexander network)
* D12: Investigating GitHub repository

Payout: 10,000 USD

### Specification Details
#### D3: Coded types including unit tests
This deliverable includes the following types:
* Codec types
    * AbstractArray
    * Base
    * Compact
    * Enum
    * Int
    * Option
    * Set
    * Struct
    * StructAny
    * Tuple
    * U8a
    * U8aFixed
    * UInt
    * Vec
    * VecAny

#### D4: Metadata handling including unit tests
This deliverable includes the following types:
* Primitive types: 
    * Hash
* RPC types: 
    * Metadata
    * RuntimeVersion

This deliverable includes the following methods:
* state
    * ▸ getMetadata(block?: Hash): Metadata
    * ▸ getRuntimeVersion(hash?: Hash): RuntimeVersion

#### D5: Basic version of the Go Substrate RPC Client including end-to-end tests that run on CI
This deliverable includes the following methods:
* chain
    * getBlockHash(blockNumber?: UInt): Hash

#### D7: Primitive types including unit tests
This deliverable includes the following types:
* Primitive types
    * AccountId
    * AccountIndex
    * AccountInfo
    * Address
    * Bool
    * Bytes
    * Call
    * Data
    * Event
    * EventRecord
    * Extrinsic
    * ExtrinsicEra
    * ExtrinsicSignature
    * H160
    * H256
    * H512
    * I8
    * I16
    * I32
    * I64
    * I128
    * I256
    * Moment
    * Null
    * Origin
    * Signature
    * ExtrinsicPayload
    * StorageData
    * StorageKey
    * Text
    * Type
    * U8
    * U16
    * U32
    * U64
    * U128
    * U256
    * USize
    * Weight
    * WeightMultiplier
#### D8: RPC core functionality
This deliverable includes the following types:
* RPC types
    * Block
    * Header
    * SignedBlock

This deliverable includes the following methods:
* chain
    * ▸ getBlock(hash?: Hash): SignedBlock
    * ▸ getFinalizedHead(): Hash
    * ▸ getHeader(hash?: Hash): Header
* state
    * ▸ getChildKeys(childStorageKey: StorageKey, prefix: StorageKey, block?: Hash): Vec<StorageKey>
    * ▸ getChildStorage(childStorageKey: StorageKey, key: StorageKey, block?: Hash): StorageData
    * ▸ getChildStorageHash(childStorageKey: StorageKey, key: StorageKey, block?: Hash): Hash
    * ▸ getChildStorageSize(childStorageKey: StorageKey, key: StorageKey, block?: Hash): U64
    * ▸ getKeys(prefix: StorageKey, block?: Hash): Vec<StorageKey>
    * ▸ getStorage(key: StorageKey, block?: Hash): StorageData
    * ▸ getStorageHash(key: StorageKey, block?: Hash): Hash
    * ▸ getStorageSize(key: StorageKey, block?: Hash): U64

#### D10: RPC types including unit tests
This deliverable includes the following types:
* RPC types
    * ChainProperties
    * Digest
    * DigestOf
    * DigestItem
    * ExtrinsicStatus
    * Health
    * NetworkState
    * PeerInfo
    * StorageChangeSet

#### D11: Remaining RPC functionality
This deliverable includes the following methods:
* author
    * ▸ pendingExtrinsics(): Vec<Extrinsic>
    * ▸ submitAndWatchExtrinsic(extrinsic: Extrinsic): ExtrinsicStatus
    * ▸ submitExtrinsic(extrinsic: Extrinsic): Hash
* chain
    * ▸ subscribeFinalizedHeads(): Header
    * ▸ subscribeNewHead(): Header
    * ▸ subscribeRuntimeVersion(): RuntimeVersion
* state
    * ▸ subscribeStorage(keys: Vec<StorageKey>): StorageChangeSet
    * ▸ queryStorage(keys: Vec<StorageKey>, startBlock: Hash, block?: Hash): Vec<StorageChangeSet>

## Funds Required Overall
30,000 USD

## Outlook
The team is currently building a Substrate-based chain and is planning to integrate the chain with their existing Go-based application https://github.com/centrifuge/go-centrifuge. With that, the Go Substrate RPC client will find actual usage from day one and the team will maintain and support the client going forward and collaborate with other community members on new feature additions and changes.

## Additional Information
* The team would accept 20% of payment in DOTs
* The team is currently implementing a Substrate-based chain.
* The team has extensive experience integrating their Go application with Ethereum
* A rudimentary integration of the existing Centrifuge Go application with the Substrate chain exists already. This work, as described in this application, will be to write a general/standard the client library and make it generally available.

To speed up development, we made the following design decisions:
* @centrifuge/go-substrate-rpc-client will be using futures and channels
* @centrifuge/go-substrate-rpc-client includes RPC methods, but initially not the convenience methods for Storage chain state, Extrinsics and Constants. These convenience methods will be easy to add in a 2nd step.
* Encoding and decoding will be done using https://github.com/Joystream/parity-codec-go/tree/develop/withreflect
* Number handling will be done using https://golang.org/pkg/math/big/ 