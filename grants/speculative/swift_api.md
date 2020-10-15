# Polkadot/Substrate Swift API
## Project Description
Swift API is a library that allows interacting with Polkadot/Substrate from Swift code - the main programming language for Apple ecosystem, effectively enabling Polkadot/Substrate developers to create native iOS and Mac applications.
### Why Swift API is good for the ecosystem
iOS and other parts of Apple’s ecosystem is one of the leading consumer-oriented platforms. We believe that opening the capability to build native iOS dApps for the Polkadot developers should create a positive impact on the user experience and dApps users’ satisfaction.
### How Swift API integrates into Substrate / Polkadot
The library is specifically designed for Substrate / Polkadot based applications development.
### Why our Team is interested
Swift API is the starting point for our longer-term goal to add Polkadot/Substrate support to our product Tesseract (https://tesseract.one/), which provides dApp developers with the capability to create great onboarding and further user experience in their dApps.

For us, it’s a perfect starting point as our team has great experience in creating Swift libraries and frameworks: https://github.com/crossroadlabs/Express, https://github.com/reactive-swift.
## Team members
* Daniel Leping, @dileping on GitHub, CEO
* Yehor Popovych, @ypopovych on GitHub, CTO
## Team Website
* https://tesseract.one
## Team's experience
Our team has been building blockchain applications since 2017 and has worked together on Tesseract (https://tesseract.one/) since 2018.

While working on Tesseract we worked on a very similar library for Ethereum Web3: https://github.com/tesseract-one/EthereumWeb3.swift.

Prior to blockchain technology, we had a wealth of experience in Swift, building applications, and middleware. The most noticeable projects are https://github.com/crossroadlabs/Express, https://github.com/reactive-swift.

The team has a 10-year history of working together, delivering various solutions of high complexity, including the mentioned above Swift Express and Reactive Swift, Cross++ ( cross-platform framework in C++ that allowed to keep the app logic shared while providing the capability to use native UIs) and tens of the web, mobile, and server applications for customers from around the world including the US, EU, Israel, Australia, etc.
## Team Code Repos
* https://github.com/tesseract-one
* https://github.com/crossroadlabs/Express
* https://github.com/reactive-swift
## Team LinkedIn Profiles
* https://www.linkedin.com/in/danielleping/
* https://www.linkedin.com/in/yehor-popovych/
## Development Roadmap
### Milestone 1
#### Duration: 4 weeks
#### Deliverables:
1. Repository with the configured project with SPM and CocoaPods support.
2. Swift SCALE codec implementation for types: AbstractArray, Base, Compact, Enum, Int, Option, Set, Struct, StructAny, Tuple, U8a, U8aFixed, UInt, Vec, VecAny.
3. Implementation of primitive data types: AccountId, AccountIndex, AccountInfo, Address, Bool, Call, Data, Event, EventRecord, Extrinsic, ExtrinsicEra, ExtrinsicSignature, H160, H256, H512, I8, I16, I32, I64, I128, I256, Moment, Null, Origin, Signature, ExtrinsicPayload, StorageData, StorageKey, Text, Type, U8, U16, U32, U64, U128, U256, USize, Weight, WeightMultiplier, Hash.
4. Network providers for WebSocket and HTTP protocols.
5. Generic asynchronous JSON RPC call API with parameters and response serialization/deserialization.
6. Generic asynchronous JSON RPC subscribing API with parameters, response, and events serialization/deserialization.

### Milestone 2
#### Duration: 4 weeks
#### Deliverables:
1. Swift wrapper for C sr25519 library.
2. In-App Keychain implementation with methods for key generation, message signing, key derivation, signature check.
3. Implementation of RPC data types: Metadata, RuntimeVersion, Block, Header, SignedBlock, ChainProperties, Digest, DigestOf, DigestItem, ExtrinsicStatus, Health, NetworkState, PeerInfo, StorageChangeSet.
4. Implementation of standard Substrate RPCs: author, babe, chain, childstate, contracts, engine, grandpa, offchain, payment, rpc, state, system.

### Milestone 3
#### Duration: 4 weeks
#### Deliverables:
1. APIs for custom RPC handlers.
2. APIs for custom user-defined Struct and Enum types.
3. JSON ABI parser with type validation.
4. Integration tests for all standard RPC calls, contract calls, custom RPC calls.
5. API Documentation (in-code and generated HTML).
6. Library usage examples: call, subscriptions, custom RPC implementation (with user-defined types), contract call.

## Future Plans
In the long run, we aim to have Polkadot/Substrate in the list of Tesseract’s supported networks. Swift API library is a prerequisite for our long-term goal, and we consider it a perfect starting point as it immediately provides value for Polkadot/Substrate community.

At Tesseract we provide dApp developers with the capability to create seamless and hassle-free onboarding and user experience. We hope that adding Polkadot to the list of our supported networks will benefit Substrate developers and bring value to the community.
## Additional Information
There already is quite some mainstream language support for Polkadot/Substrate, but Swift still is not there. Here are some examples:
* Javascript: https://polkadot.js.org/api/
* .Net: https://github.com/w3f/General-Grants-Program/blob/master/grants/speculative/dotnet_api.md
* Python: https://github.com/w3f/General-Grants-Program/blob/master/grants/speculative/python_substrate_api.md
* Ruby: https://github.com/w3f/General-Grants-Program/blob/master/grants/speculative/ruby_substrate_api.md
* Go: https://github.com/pstehlik/Web3-collaboration/blob/b39538a57e8b0de20f928c04716fa725344bb954/grants/speculative/centrifuge_go_substrate_rpc_client.md
* C++: https://github.com/usetech-llc/Web3-collaboration/blob/8042d35356dce871fe368f60388dad492f792cec/grants/speculative/cpp_api.md
* Rust: https://github.com/brenzi/Web3-collaboration/blob/85da47fb90324c5c6240834a4bcdcfa1f59752a6/grants/speculative/substrate-api-client.md
