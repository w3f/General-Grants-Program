# Project name

Rad substrate client

## Project Description

Substrate provides low-level RPC libraries to talk to nodes but nothing beyond.

We’re building a functional Rust client to interact with nodes,
that comes with domain objects, apis for constructing valid transactions, as well as
an emulator for testing the runtime.

## Team members

* Eleftherios Diakomichalis
* Thomas Scholtes
* Igor Zug
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

We are developing a Rust client for substrate that provides concrete domain objects 
as part of the SDK. By domain objects we mean, for example, a concrete type for a 
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
can use the same client infrastructure.

### Milestone 3 — Documentation, user testing & performance improvements — 1 month — $15,000

We aim to focus on documentation in order to improve the developer experience, as well as
iterate over the core functionalities with more users beyond our team.

## Future Plans

We will continue maintaining and evolving the client based on the ecosystem's needs.

## Additional Information

It's the first time we are applying for a web3 grant. All of the existing work has been financed by Monadic.
