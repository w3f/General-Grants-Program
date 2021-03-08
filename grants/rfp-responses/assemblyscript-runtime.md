# AssemblyScript Runtime Proposal

## Project Description

*In response to the Alternative Polkadot Runtime Generation (AssemblyScript) RFP.*

Polkadot has the ability to load, swap or upgrade it’s Blockchain features by having a decoupled design. The two main components are the Polkadot Host and the supplied Wasm code that is executed in the Polkadot Runtime Environment using a Wasm Interpreter.

Currently the most matured way of generating Runtimes is using Rust and Parity-built tools. The end goal of this project is to deliver the tools necessary to build Runtimes in AS, however in this initial project we will define, prioritise and deliver an Account-Based PoC AS Runtime. In order to do that, we need to develop utils and modules in AssemblyScript first.

Some of the deliverables listed in this proposal are the utilities that will accommodate the calls between a Polkadot Runtime and AS Wasm Runtime blob.

The main benefit of delivering those utilities is that everyone building AS Wasm Runtimes will have to use them, otherwise they must implement them themselves. Having such libraries available will help anyone who wants to develop their runtime in AS.

The other part of the deliverables is the Account-based PoC AS Runtime. We think that it will be beneficial because it will provide a better understanding of the work required for developing AS Runtime Generation tool and it would be the first step towards that goal. 

LimeChain is a blockchain-agnostic development company with a strong passion for developer tooling. We see Polkadot as an exciting technology and we hope to be able to help the developer community through various dev tools and implementations.


## Team members
* Daniel Ivanov, Christian Vesselinov (leads)
* Lyubomir Kiprov


## Team Website	
* https://limechain.tech

## Legal Structure

* LimeLabs Ltd., incorporated in Bulgaria, Dragan Tsankov 23A, 1113, Sofia, Bulgaria

## Team's experience
LimeChain is a blockchain development company with offices in London, UK and Sofia, Bulgaria. Since 2017, LimeChain has worked on 50+ blockchain projects, including a strong track record of building developer tools for different protocols such as Ethereum, EOS, Aeternity and Corda. Some of the companies LimeChain has worked with are Celo, P&G, Raiffeisenbank, Status, Dapper Labs and Maker among others. The proposed developer team in particular also has experience with Substrate.

The team is currently working on a AssemblyScript implementation of the SCALE codec:
- https://github.com/LimeChain/assemblyscript-scale-codec

A few Interesting commits:
- https://github.com/aeternity/aepp-aeproject-js
- https://github.com/LimeChain/etherlime
- https://github.com/LimeChain/eoslime


## Team Code Repos
* https://github.com/LimeChain
* https://github.com/Daniel-K-Ivanov
* https://github.com/bakasura980
* https://github.com/thcrnk

## Team LinkedIn Profiles
* https://www.linkedin.com/in/daniel-k-ivanov/;
* https://www.linkedin.com/in/lyubomir-kiprov/;
* https://www.linkedin.com/in/chris-veselinov/

## Development Roadmap

Based on our research we have concluded that there are 3 major components that will be reused in any AssemblyScript Runtime. The three components are:
- AssemblyScript SCALE Codec
- Polkadot WASM API
- Runtime Interface Client

In addition to the ones listed above, anyone who wants to build AS runtime will have to implement Primitives and Modules depending on their use case. Most of the Primitives and Modules will be required in every Runtime (f.e Balances).

The diagram below will provide better understanding of the listed components.

![runtime-diagram](https://raw.githubusercontent.com/LimeChain/General-Grants-Program/images-branch/grants/rfps/images/assemblyscript-runtime.jpg)

We will start with the WASM API first, then we will proceed with implementing a Storage Module into the Runtime and the Aura module. Once we have all of these things we will implement the State transition function and all of its related dependencies. At the end of the development we should be able to run an Account-based chain using our PoC Runtime.

The code will be released with Apache 2.0 license.

Keep in mind that the estimates for the implementation of each milestone takes into account that AssemblyScript is not mature and a lot of the basic language utils do not exist. They must be implemented.

### Milestone 1 — WASM API Mock — 15 days

The Polkadot Host requires the WASM blob to provide an API. In this milestone we will define the Polkadot WASM API entries in our PoC AssemblyScript Runtime.

For the successful completion of this milestone we can define the following criteria:
1. Deliver a mocked Polkadot HOST API in AssemblyScript. We will not implement all of the entries. More specifically:
    - “Core_version” - Once called it will return the WASM runtime information as per the specification.
    - “Core_execute_block” - Once called it will decode the Block Data parameters and return true. This function will be mocked in this first milestone.
    - “Core_initialize_block” - Once called it will decode its params. This function will be mocked in this first milestone. 
    - “BlockBuilder_apply_extrinsic” - Once called it will decode the Extrinsic param. This function will be mocked in this first milestone and will return an array of zero length (one byte zero value).
    - “BlockBuilder_inherent_extrinsics” - Once called it will parse the Inherents-Data. This function will be mocked in this first milestone and return an empty array
    - The rest of the Entries (that are present in the specification) will be throwing unimplemented errors once called or mocked if it is required.
2. Extend the AssemblyScript SCALE library with the missing types that must be decoded.
3. Compile the AssemblyScript into WASM blob and use it as a runtime in order verify that there is a successful communication between the Polkadot Host and the AS Runtime (although it won't be a functional one).
4. We will provide both inline documentation of the code and a basic README tutorial describing how the WASM API Mock can be tested.

**Full-Time Employees: 2**

**Days: 15**

### Milestone 2 — Storage Module  — 18 days

In this milestone we will implement the basic functionality for setting and getting storage from the AS Runtime using the Polkadot HOST API.

For the successful completion of this milestone we must:
1. Deliver the ability to:
    - Set storage at a given key using the exposed “ext_storage_set” function
    - Retrieve a storage value by a given key using the exposed “ext_storage_get” function
    - Read a storage value by a given key and offset params using the exposed “ext_storage_read” function.
    - Clear the storage of the given key and its value using the exposed “ext_storage_clear” function.
    - Check whether a given key exists in the storage using the exposed “ext_storage_exists” function.
2. Implement Accounts / Balances module such that:
    - We are able to read the balance of an account
    - We are able to change the balance of an account
3. Extend the SCALE Library with the required types - Account / Balances.
4. Be able to read the genesis account balances.
5. Develop Unit tests for Storage Module read & write operations.
6. Deliver both inline documentation of the code and a basic README tutorial describing how one can run the Storage Module tests.

**Full-Time Employees: 2**

**Days: 18**

### Milestone 3 — Support for Aura consensus — 13 days

In this milestone we will implement the Aura Module functionality into the AS Runtime.
For the successful completion of this milestone we must:
1. Implement the functionality for loading and setting the “authority list” defined in the genesis state.
2. Implement Aura Runtime API “slot_duration” and “check_inherent” functions
3. Develop Unit tests for the Aura module API.
4. Deliver both inline documentation of the code and a basic README tutorial describing how one can run the Aura Runtime tests.
5. Run our PoC Runtime using the Aura consensus.

**Full-Time Employees: 2**

**Days: 13**

### Milestone 4 — State Transition function — 26 days

In this milestone we will implement the State transition function into the AS Runtime. As part of the State transition function we will have to implement the previously mocked WASM API functions and more specifically, we must:
1. Implement the “initialize_block”, “execute_block”, “finalize_block”, “apply_extrinsic”, “inherent_extrinsics”, “random_seed”, “validate_transaction”
2. Develop Unit tests for the implemented runtime entries.

For the successful completion of this milestone we must be able to run the PoC Runtime successfully. The runtime must be able to:
1. Define genesis state and account balances
2. Run its Aura consensus.
3. Sync/Initialize/Execute blocks.
4. Being able to process Account Balance transfers (Extrinsics)
We will build a Docker image with our Substrate chain, using the PoC AS Runtime in order to demonstrate the functionality.

**Full-Time Employees: 2**

**Days: 26**

### Future Plans
After we deliver a PoC Runtime, we will evaluate the efforts for building alternative Runtimes and we will be able to provide feedback on the Polkadot Runtime specification and its integration with a Polkadot Host.

Once we produce this PoC Runtime we would like to extend it and add more Modules and Pallets in the future. We would like to produce a framework that is well documented and is able to support developers in building their own AssemblyScript Runtimes.

We will contact the AssemblyScript documentation maintainers to list the PoC Runtime and all of the utilities that we’ve implemented during this exploration period. This would benefit the AssemblyScript community as-well, as there are a lot of missing libraries.

In mid to long term, LimeChain hopes to continuously add value to the Polkadot development community with further implementations, SDKs and libraries.
