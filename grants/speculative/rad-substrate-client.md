# Project name

Rad substrate client

## Project Description

Substrate provides low-level RPC libraries to talk to nodes but nothing beyond.

We’re building a functional Rust client to interact with nodes,
that provides integration with domain objects, apis for constructing valid transactions, as well as
an emulator for acceptance testing the runtime and client.

The key difference between the `scs` client and the goal for our client is that the former provides access to the API dynamically based on the metadata information exposed by the runtime. This in contrast to our client which uses the static runtime information through Rust types.

For example when using `compose_extrinsic!` the module and call are determined by strings and the call arguments can be of any type. It is not possible to enforce validity statically. On the contrary, it is possible to use a call name that does not exist or use fewer or more arguments than expected or arguments of a different type.

Similarly dealing with state storage relies on the user of the client providing storage prefixes manually as strings and choosing the decoding implementation. This is error prone and tedious to repeat for every piece of storage.

The `scs` client cannot be used for generic runtime. Composing valid extrinsics only works if the [`SignedExtension`][signed-extension] data for the runtime is the same as used by the client. The client does not provide APIs for dealing with arbitrary signed extensions.

There are also some design and implementation decisions that hamper the maintainability in the long run and make it prohibitively expensive to extend the library to match our goals.

- Almost none of the provided methods of the client provide any error information.
- The client is not using the RPC libraries used by the substrate node. Instead the implementation hard codes the messages and responses on the RPC layer.
- The code heavily relies on macros which makes it harder to maintain and use for developers.
- The client provides native support for contracts and accounts. Without a generic approach this might break subtly between different runtime implementations and needs to be constantly maintained.

## Team members

* Eleftherios Diakomichalis
* Thomas Scholtes
* Igor Żuk
* Nuno Alexandre

## Team Website	

https://radicle.xyz

## Legal Structure 

It has been shared privately.

# Team's experience

Previously worked at SoundCloud, Contenful, Cosmos & more.

## Team Code Repos

* https://github.com/radicle-dev/radicle-registry

## Team LinkedIn Profiles

* https://de.linkedin.com/in/eleftheriosd

## Development Roadmap

### Milestone 1 — Implement core functionalities — 1 month — $15,000

We are developing a Rust client for substrate that provides integration with concrete domain objects 
used in the Substrate runtime. By domain objects we mean, for example, a concrete type for a 
transfer transaction, a type for the possible events and errors recorded by a transfer 
transaction or a type for the account data stored on chain.

Our client provides APIs for properly constructing valid transactions. This includes 
adding the correct account nonce, fees, lifetime data, genesis hash (“signed extra” in substrate 
parlance), and signing it.

Our client targets dApp developers and provides API and functionality commonly needed by them. 

This includes:

  * Retrieving all events that are associated with a transaction
  * Number of confirmations for a transaction
  * Transaction results and errors
  
Our client comes with an emulator. This emulator is used for testing the runtime. 
The emulator provides additional flexibility over using a running node to do developing and testing.

  * It compiles significantly faster after changes to the runtime.
  * It can be configured to create blocks faster to have tests run faster and
    get quicker feedback during development.
  * It can easily be seeded with fixtures.
  * It is easy to spawn multiple isolated instances whereas on a node all tests
    running against the node share state.


### Milestone 2 — Making the client generic — 1 month — $15,000

We aim to make our client generic and reusable over the domain. This means that a
different runtime implementation with different domain objects (transactions, state, events, errors) 
can use the same client infrastructure. We will write documentation and guides to make the client
accessible to developers.

- in our codebase, we will use the code as a third party library, so we can show that the library is completely decoupled
- we will deliver a "how to get started" guide that explains how you can use the client with the runtime from one of the Substate tutorials (like Substrate cryptokitties or Substrate collectibles -- please let us know which one to use--) 
- we will provide complete documentation for the client
- finally, we will write a blogpost on how to use the client to write acceptance tests for the whole stack

## Future Plans

We will continue maintaining and evolving the client based on the ecosystem's needs.
We’ll expand the client to be usable with light clients.

## Additional Information

It's the first time we are applying for a web3 grant. All of the existing work has been financed by Monadic.
