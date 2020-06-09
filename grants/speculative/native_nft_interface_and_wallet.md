# Native NFT Interface & Wallet

## Project Description
NFT or Non Fungible Tokens refer to a wide category of data structures with the majority of the standards being defined for Smart Contract implementations. When defining an NFT structure at the native chain code level there are currently no basic NFT interfaces that a type can implement to be classified as an NFT structure. Also, the NFT definitions at the Smart Contract level account for handling the ownership of the NFTs at the Contract level itself, with no common definition of a wallet which can be used to represent the account ownership for different implementations NFT. 

This project aims to define a very basic NFT interface with a minimum set of methods that all NFTs have in common and define a wallet interface to represent the account ownership of the NFTs. The project also aims at defining a base implementation of the NFT and NFT wallet interfaces with create and transfer NFT transactions, along with a more specialized novel interface and implementation called an "interNFT" which will have functionalities targeted more towards interchain ownership transfers and maintenance of NFTs. This grant application is however for seeking resources for the basic NFT and NFT wallets implementation only, while the milestones will include deliverables for both the NFT and interNFT implementations.

#### About Persistence

Persistence is an Interoperability Middleware for Institutional and Open Finance use-cases. The core product of Persistence, the SDK, is a set of standardized tools that can be used to model Exchanges and Marketplaces by tokenizing and trading ‘real world’ financial assets (such as Invoices, Bills of Lading/Commodities, Letters of Credit, Solar Credits, etc.). Since all the Exchanges are built using the same set of standard SDK modules and specs, there is native interoperability between all the exchanges. The Decentralised and Open Finance features of Persistence applications are leveraged for more efficient capital allocation in a trust minimized, borderless and 24/7 manner. 

This new paradigm of Open Finance use-cases can be facilitated within the Persistence Ecosystem using its continuously evolving toolset, which currently includes modules like, Reputation, Contract, Escrow, Access Control, Hierarchy, NFT, and RFT.  Persistence (then in stealth and building the Comdex dApp) was the first project on the Cosmos ecosystem to execute an Interchain NFT asset transfer transaction.

Features of the Persistence ecosystem:
* Native interoperability between all applications participating in the ecosystem.
* The applications are also interoperable across different protocols/platforms.
* Singular representation of data, i.e. each object is allowed to exist only once in the whole ecosystem.
* Flexibility in the level of transaction validation privacy level, covering the whole spectrum from open public validation to permissioned private validation.
* Privacy-preserving transaction validation allowing interoperability between publicly and privately validated dApps.

#### Motivation

The main purpose of Persistence SDK is to allow for interoperability between sovereign exchanges trustless-ly. To allow interoperability with dApps built on Persistence SDK across platforms, the same SDK with similar interfaces and consistent application operations has to be implemented on them.

The long term motivation for this interaction is to build-out the complete Substrate version of Persistence SDK, as a PDK (Parachain Development Kit). The Persistence PDK will import the Substrate PDK for defining its runtime with a set of modules required to interoperate with dApps built with Persistence SDK. This will allow:
* The applications built using the Persistence PDK to be interoperable with applications built with Substrate
* The applications built using the Persistence PDK to be interoperable with each other
* The applications built with the SDK on other platforms (Cosmos) to be interoperable with applications built with the Persistence PDK.
* Singular representation of data across chains instead of a need for recreating the same assets for different applications.
* Consistency in functionality and operation of the Persistence SDK across platforms.

Cross-platform interaction:
* The Persistence Hub will operate as a singular chain operating on the Tendermint and Cosmos stack.
* The Persistence SDK applications can interoperate with each other by either connecting to the Persistence Hub that is built on the Tendermint Stack or through a relayer chain if operating on the Substrate stack.
* The Substrate Persistence relayer chain will bridge to the Persistence Hub chain to establish interoperability between wallets maintained on the two different platforms.
* The Substrate Persistence relayer chain will connect to the Polkadot relayer chain also and will be interoperable with it. 
* The dApps built using the SDK may also directly connect with each other or other Hubs like the Polkadot relayer or the Cosmos Hub or Ethereum by implementing external/custom modules and bridges.
* The Persistence token will only be utilized for staking and fees on the Persistence Hub on Cosmos.
* The NFTs and refunged-NFTs can interoperate across hubs on the two platforms.

As a first step to starting this process, the proposal is to build out the NFT Interface and Wallet Modules and maintain it on Substrate and make sure that the updates to that module remain in synchrony with the requirements and updates on Substrate. An implementation of the NFT interface and Wallet called interNFT, which is focused on inter blockchain operability of NFT will also be included as part of the project but no funding will be required for it/won’t be a part of the grant but will be a part of the Roadmap.



## Team members
* Deepanshu Tripathi (Team Leader)
* Abhinav Kumar
* Puneet Mahajan   

## Team Website    
* https://persistence.one/

## Legal Structure 
Persistence Holdings, Singapore Pte Ltd

## Team's experience
* The team has built end-to-end a decentralized commodity trading platform call Comdex [http://comdex.sg/], [https://explorer.persistence.one/]
* The team was one of the first in the world to build out a native interchain NFT transfer [https://blog.cosmos.network/1st-non-standard-ibc-transaction-executed-by-persistence-2-2-79eb4397d48d]
* The team has experience with payment & banking API integrations, full-stack dApps, and related tooling development.

## Team Code Repos
* https://github.com/persistenceOne
* https://github.com/auditOne

## Team LinkedIn Profiles
* Deepanshu Tripathi:  https://www.linkedin.com/in/deepanshutr/
* Abhinav Kumar: https://www.linkedin.com/in/avkr003/
* Puneet Mahajan: https://www.linkedin.com/in/puneet-mahajan-/

### What is a Native NFT?
Any NFT definition at the native chain code level as opposed to being defined on the Smart Contract layer can be categorized as a Native NFT. Each parachain may have specialized native definition of an NFT and be categorized as an NFT(as opposed to a fungible token, or a record or a wallet) as long as they implement the NFT interface. The definition of the native NFT interface should be as basic and elementary as possible and to be fully backward compatible with older native NFT definitions too.

### What is a Native NFT wallet.

A Native NFT wallet is a structure that maps account identifiers to a set of references of the NFTs owned by the account. The wallet can maintain ownership of any structure that implements the NFT interface. The base implementation should allow for send NFT operations to other accounts.   

### What is an interNFT?
InterNFT is a natively implemented NFT structure for Blockchain applications that implement interoperability protocols. The interNFT is defined by a basic interface that any NFT structure has to implement to be called an interNFT. The ownership of interNFT is maintained by the interNFT wallet. The combination of interNFT and interNFT wallet allows the ownership of the interNFT to be exchanged across interoperable chains while the execution logic of the NFT is still maintained at the native chain.

## Definitions 
### NFT
* `NFT`: An NFT or a Non-fungible Token is a structured unit of data that represents the properties of a unique entity, or the entity itself( if it’s a digital asset and all its properties are contained by the NFT). In this document `NFT` will also refer to a basic interface, implementation of which will classify a structure as an `NFT`.

* `NFT ID`: A reference to the `NFT`. The address is convertible to a String for reference.

* `NFT Wallet`: an array of references(`NFT ID`) to Account ID.

* `NFT Classification ID`: an identifier of the type or denomination of the NFT.

### interNFT
* `interNFT`: An implementation of the `NFT` interface. The `interNFT` is defined to allow for maximum application logic flexibility in one interface and is focused on interchain ownership transfer. In this document `interNFT` will also refer to a basic interface, implementation of which will classify a structure as an `interNFT`

* `classification`: a representation of the type or grouping for an `interNFT`, e.g. an `interNFT` "Toyota Corolla" will be of `classification` car.

* `trait`: a charectersitic/variable related to an `interNFT` defined by `classification` e.g. "top speed" can be a `trait` of `classification` car.

* `signature`: a cryptographic signature using a private key on bytes of information. A signature can be verified against the public key of the signing private key and sign bytes. 

* `fact`: a piece of information. A `fact` can carry `signature`s from `account`(s) e.g. "100 mph (ca. 161 km/h)" is a fact and an `account` can attest it by signing it with their private key.

* `property`: the value of a `trait` is `property`. Every `property` has a `trait` identifier and a corresponding fact `fact` e.g. 

* `account`: a singularly identifiable identity of each actor on the application. An `account` is generally identified by a public key.

* `maintainers`: a group of one or more accounts that can issue and mutate `properties` of a `classification` of `interNFT`

* `interNFT wallet`: a mapping of a set of `interNFT ID`s against an `account` ID. An `interNFT wallet` specifies the `interNFT`s owned by and an account.

* `height`: the block height of the chain. Used as a measure of time for `interNFT` time-bound operations.

* `lock`: the `height` after which the `interNFT` is allowed to be transferred out of an `interNFT wallet`. 

* `burn`: the `height` after which the `interNFT` is allowed to be burned/redeemed by the owner of the `interNFT`. 

* `interNFT ID`: A reference to the `interNFT` specifying the hash of the NFT Immutable, the address of the originating chain, and the class of the NFT. The address is convertible to a String for reference.

* `immutables`: `trait`s of the `interNFT` that do not change after being issued. The hash of these properties is a  part of the NFT Address( `interNFT ID`).

* `mutables`: `trait`s of the `interNFT` that can be changed through transactions defined on it.

## Interfaces

### NFT

#### ID interface 

An interface to be implemented by any type that servers as an identifier for another object/s.  

ID interface{

    // String returns representation of the ID in a human redable string 
   String() string

    // Bytes return the byte array of the ID 
   Bytes() []bytes

   // Compare compares the ID to the given ID returning the integer difference between the bytes of the identifier, for sorting or matching
   Compare(ID) int
   }

#### NFT interface

A barebone interface to be implemented by any structure that can be classified as an NFT 

NFT interface {

    // ID returns the identfier for the NFT as an ID interface
   ID() ID
   
   // ClassificationID returns the classification/type/denomination for the NFT as an ID interface
   ClassificationID() ID
}

#### NFT Wallet interface

A basic interface for a wallet for structures implementing the `NFT` interface

NFTWallet interface {
    // AccountAddress returns the accountAddress of the account which the NFTWallet belongs to
   AccountAddress() AccountAddress
   
   // NFTIDs returns the identifier, for all the NFTs stored in the wallet, as an ID interface
   NFTIDs() []ID
}

### interNFT 

####  InterNFT interface 

An interface that implements the NFT interface, adding interoperability functionalities to it 

InterNFT interface {

    // Implementing the NFT interface
    NFT

    // ChainID returns the idendtifier, for the NFT's native Chain, as an ID interface
   ChainID() ID
    
    // HashID return the identifier, for the immutable properties of the InterNFT, as an ID interface
   HashID() ID
    
    // MaintainersID returns the identifier, for the maintainer froup of the InterNFT, as an ID interface
   MaintainersID() ID

    // Properties returns the properties of the interNFT as a properties interface
   Properties() Properties
    
    // CanSend returns a boolean telling if the interNFT can be sent or not given the current height
   CanSend(Height) bool

    // CanBurn returns a boolean telling if the interNFT can be burnt or not given the current height
   CanBurn(Height) bool
}

#### Height interface

An interface to define a block height type for a chain, used as a metric of time.

{
    Height interface {
    
    // Count returns the block count for the Height
   Count() string

    //Current height 
    // IsGraterThat returns a Boolean to tell if the Height is grater than a given Height/Current Height
   IsGraterThat(Height) bool
}

#### Signature interface 

An interface for any type that represents a cryptographic signature that can be verified

Signature interface {
    
    // String returns the human-readable string format of the Signature
   String() string
   
   // Bytes returns the byte array of the cryptographic signature 
   Bytes() []byte
    
    // ID returns the identifier for the Signature as an ID interface
   ID() ID
   
   // Verify returns a boolean to tell if the signature is valid of not given the public key of the signer and the signed bytes
    Verify(PublicKey, []byte) bool
    
    // HasExpired returns a boolean to tell if the Signature has expired given a Height/Current Height interface
    HasExpired(Height) bool
}

#### Signatures interface 

An interface for a container of a collection of Signatures. The Interface handles the deterministic operations on the Signature collection.  

Signatures interface {
   
    // Get returns a Signature stored in the Signatures given an Identifier for it
   Get(ID) Signature

    // Add appends a given Signature with the Signatures Collection
   Add(Signature) error
   // Add removes a given Signature from the Signatures Collection
   Remove(Signature) error
   // Add mutates a given Signature in the Signatures Collection
   Mutate(Signature) error
}

#### Fact interface 

An interface to define a type for any kind of information is the system which is non-consequential to the application logic but has to be stored for provenance. 

Fact interface  {

    // String returns the human-readable string format of the information stored by the Fact
   String() string
   
   // Bytes returns the byte array of the information contained by the Fact
   Bytes() []byte

    // Signatures return the cyptographic signatures on the Fact as Signatures interface 
   Signatures() Signatures
}

#### Property interface

An interface to define any kind of property associated with an interNFT

Property interface {
    
    // Name returns the name of the Property
   Name() string
    
    // ID returns the identifier, of the Property, as an ID interface
   ID() ID
   
   // Fact returns the Fact associated with the Property
   Fact() Fact
}

#### Properties interface 

An interface for a container of a collection of Properties. The Interface handles the deterministic operations on the Property collection.  

Properties interface {
    
    // ID returns the identifier, of the Properties, as an ID interface
   Get(ID) Property

    // Add appends the given Property with the Properties collection 
   Add(Property) error
   // Add removes the given Property from the Property collection
   Remove(Property) error
   // Add mutates the given Property in the Property collection
   Mutate(Property) error
}

#### Properties interface 

An interface for any type of Trait associated with a Classification of interNFT 

Trait interface {

    // Name returns the name of the Trait
   Name() string
   
   // ID returns the identifier, for a Trait, as an ID interface
   ID() ID

    // IsMutable returns a Boolean to tell if a property value of Trait can be mutated or not
   IsMutable() bool
}

#### Traits interface 

An interface for a container of a collection of Traits. The Interface handles the deterministic operations on the Trait collection. 

Traits interface {

    // Get returns a Trait for the given ID
   Get(ID) Trait
}

#### Classification interface 

An interface for a representation of type/class/denomination of the interNFT

Classification interface {

    // Name returns a human redable name for the classification
   Name() string

    // ID return the identifier, for the classification, as an ID interface
   ID() ID
    
    // Traits returns the traits associated with the Classification
   Traits() Traits
}

## Salient Features 
**Division of responsibility**
The NFT functionality is split into two modules, the NFT, and NFT wallet modules. NFT module handles the mint, mutation, and burns logic with the NFT wallet module handling the ownership transfer transactions. Both modules can operate independently on different chains.

**Singular representation/instantiation**
The NFTs are addressed by the same hash of the immutable properties, enforcing singular representation/instantiation of NFT across chains.

**Singular wallet implementation**
NFT wallet module implements the wallet and transfers logic and is agnostic to other custom logic related to the NFTs allowing for a singular wallet implementation of all the NFT types. 

**Implementation flexibility**
The NFT module implements all the basic functional requirements of an NFT with no restrictions on the extension of the functionalities to account for more complex application logic, as long as the implementation satisfies the NFT interface.

**Reduced load on interchain protocol**
The two modules comprising the NFT functionality do no need to communicate with each other to sync the state at each transaction. They function pretty independently only with only a few transactions requiring inter-chain operability(interchain send, burn transactions).

**Commoditization**
All the NFTs are represented with a class or classification allowing for transactions to address NFTs though classes instead of direct addresses and hence allowing for NFT commoditization.

**Trusted minting, mutation and burn execution and Interoperability with private chains**
 The minting, mutation, and burn logic is implemented natively on the issuing chain and is always handled by the same chain instead of handing over the mutation logic to the recipient chain on NFT transfer to a different chain. This allows for private and privately validated chains to also exchange their NFTs with other chains while ensuring the execution environment trust and logic privacy(if required).

**Native implementation and interoperability**
The NFT module is implemented at the native chain application logic level instead of at the Smart Contract level, leveraging the chain’s native interoperability protocols to transfer NFTs between chains instead of permissioned bridge Smart Contracts.


## VS ERC721

The proposed NFT structure is implemented at the native chain code level rather than at the smart contract level making it more ephemeral. ERC721 is the most popular NFT standard in general. The standard is very well suited for smart contract-based applications running on a single chain. But there are some disadvantages to using the same in a multi-chain environment on which the proposed standard is designed to improve upon:

**NFT origin address (Rigid Design)**
*Problem:*
An NFT itself is not meaningful when transferred to another chain. The invariants and operations related to the NFT may be hacked leading to a bunch of attack vectors(like duplication, double-spends). In the case of Ethereum, the NFT resides in it’s issuing contracts with the ownership being changed to a wallet address or smart contract by the contract itself. But in a multichain environment with separate chain states, this might not be possible.
*Solution:*
In the proposed design the NFT always resides in the issuing chain state with the issuer chain logic issuing, mutating, or burning the NFT. The ownership of the NFT is transferred through a reference to the NFT, the NFT Address structure which records the address of the Issuer chain for look-up, a hash of the invariants, to ensure singular representation, and the class or classification of the NFT. The reference may be passed around between wallets on different chains and the Owner address being updated on the Issuing chain (to prevent double-spending).

**NFT wallet (Lower Visibility)**
*Problem:*
One cannot directly query all the NFTs owned by their address in the ERC721 standard. The owner address has to be queried against the issuing-contract to get all the NFTs owned by the address. A new NFT assigned to a wallet may slip under the notice of the owner. In a multichain wallet scenario, the complexity of NFT tracking becomes amplified.
*Solution:*
The proposed standard implements an NFT wallet where all the NFTs of different classes form all the Issuer chains can sit. The wallet can be queried against either the NFT address or the NFT class or get all the NFTs owned.

**Smart Contract vs Native implementation**
*Problem:*
NFT transactions are heavier to execute because of the larger Byte volume that has to be modified on each transfer or mutation. This multiplied by the complexity of running the transaction logic on smart contracts increases the overall cost and reduces the TPS of NFT transactions. Also, ERC721 is known to have a defect where an NFT transferred to a contract that does not or incorrectly implements the on-received logic leads to the NFT getting lost irrecoverably and immutably.
*Solution:*
The proposed solution implements the NFT transaction logic natively in the applications rather than on a smart contract running in an EVM or WASM execution environment, making the transactions much optimized, faster, and cheaper, also less prone to mistakes made by the smart contract implementers.



## Development Roadmap
To define native NFT and NFT Wallet interfaces, build base modules implementing NFT, NFT wallet interfaces. Build a more refined implementation of the NFT interface, i.e. interNFT and a wallet with interchain maintenance and ownership transfer features(No funding requested for interNFT module implementation).

### Funds Required 
30,000 USD(50% as vested DOTs)

### Time Required 
8 Weeks + Maintenance(including interNFT implementation)

### Roadmap

#### Milestone 1-Interface Definition-$10,000
Defining the NFT, NFT Wallet interfaces.

##### Duration
2 Weeks

##### Acceptance criteria/Definition of Done
* Consensus on the interface definition with the grants team
* Inline interface documentation
* Interface document

##### Deliverables
* NFT interface specification document
* NFT wallet interface specification document 
* NFT interface code definition
* NFT wallet interface code definition

#### Milestone 2-Base NFT module definition-$10,000 
Build a base NFT module implementing the NFT interface with transactions.

##### Duration
2 Weeks

##### Acceptance criteria/Definition of Done
* Inline code documentation
* Module documentation
* NFT interface implementation tutorial document
* 90% unit test code coverage for the base NFT module
* Transaction for an account to be able to create and assign a base NFT should execute within acceptable performance criteria

##### Deliverables
* Base NFT module implementation
* Base NFT create and assign transaction
* Base NFT module code documentation
* NFT interface implementation tutorial document

#### Milestone 3-Base NFT wallet definition-$10,000
Build a base NFT wallet module implementing the NFT wallet interface and transactions.

##### Duration
2 Weeks

##### Acceptance criteria/Definition of Done
* Inline code documentation
* Module documentation
* NFT Wallet interface implementation tutorial document
* 90% unit test code coverage for the base NFT Wallet module
* Transaction for an account to be able to send a base NFT should execute within acceptable performance criteria

##### Deliverables
* Base NFT Wallet module implementation
* Base NFT Wallet send transaction
* Base NFT Wallet module code documentation
* NFT Wallet interface implementation tutorial document

#### Milestone 4-interNFT definition-$0
Build the interNFT and interNFT wallet interfaces and implementing modules.

##### Duration
2 Weeks

##### Acceptance criteria/Definition of Done
* Inline code documentation
* Module documentations
* 90% unit test code coverage for the base interNFT modules

##### Deliverables
* Modules for interNFT operations
* InterNFT module code documentations
* InterNFT implementation tutorial document

#### Milestone 5-Update & Maintenance-$0
Upkeep and maintenance of the NFT and interNFT interface, module, test cases, documents, and tutorial definitions

##### Duration
Ephemeral

##### Acceptance criteria/Definition of Done
* Up to date module documentation for every release
* 90% unit test code coverage for all modules
* Up to date tutorial documentation for every release

#### Deliverables
* Stable code base for every release
* Module documentation for every release
* Tutorial documentation for every release

## Outlook
The Native NFT and interNFT interfaces, modules, and their transactions help achieve a common basic standard for NFT definition and interchain operability.

## Addition Information

### Implementation at Pallet vs PDK vs WASM
The NFT standard may be implemented at any of the levels, Substrate Pallet, Persistence PDK, or WASM smart contract:
If a singular NFT spec has to be created for the project with native wallet and transaction speed optimization then Substrate Pallets might be the best case. The pallet can be maintained and updated to ensure the singular NFT standard is usable across evolving use cases. 
If the NFT standard is to be offered as an option with others also available then the pallet can be made a part of the Persistence PDK. Though this approach will restrict the NFT interoperability between sovereign chains as they would implement multiple NFT standards. 
Alternatively, the NFT standard could be defined as a WASM smart contract with considerations to adapt the standard to the multi-chain interoperability use case. This approach too suffers from performance degradation, errors at the hand of contract implementers, and weaker standard enforcement.

### Use Cases and how it benefits the ecosystem
The standard has been designed for multi-chain NFT interoperability and exchange use cases. Possible use cases for NFT standard:
* Mint and trade digital assets
* Tokenize and trade Securities
* Tokenize and trade ownership of real-world assets
* Issue non-tradable certificates and badges
* To tokenize an asset and use ownership transfer to represent collateralization 
* As inputs for WASM contracts and more complex business logic

### Related Work:
* Usetech: NFT Parachain (https://github.com/usetech-llc/nft_parachain)