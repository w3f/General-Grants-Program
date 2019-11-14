# Sunshine by Web3 Garden

Web3 Garden is committed to building infrastructure to empower the underprivileged and liberate the oppressed. Sunshine is one of the flagship projects.

## Project Background

We are designing and building a library of governance-oriented modules for a Polkadot parachain. This aligns with the Web3 Hermit governance parachain, but the scope of the initial grant is more narrow than a generic "DAO" chain.

This grant application is for the design and implementation of four loosely coupled modules, a runtime to configure the modules to support instances of `sunshine` fund coordination mechanisms, and a Polkadot-js interface for user interaction. The three-month objective includes
* four loosely coupled modules
* a Polkadot-js user interface for organizations that use the modules
* a CLI tool for testing modules by constructing extrinsics with `substrate-ext`

Sunshine uses four modules:
1. Court: define dispute conditions for each milestone associated with a grant and the repercussions — execute live accordingly
2. Bank: define the pool of funds, its members, and the conditions for membership `=>` uses instances of `vote` for each `council` (based on `treasury`)
3. Vote: define and configure voting algorithms to govern courts or banks
4. Futarchy: define metagovernance `=>` how the vote module can change according to the preferences of stakeholders `=>` push the limits of application-based governance with metagovernance

## Legal Structure

Private limited company

## Team Background

As the leading contributor and maintainer of the [Substrate Recipes](https://github.com/substrate-developer-hub/recipes), Amar has devoted the past eight months to identifying and studying common design patterns used to build runtimes with substrate. He has been designing the modules to support sunshine for the past eight months while at Parity. He presented on the project at Sub0 and more recently organized the module requirements in the [sunshine documentation](https://web3garden.github.io/sunshine-book/).

Most recently, Amar spent some time studying the `rust-libp2p` codebase to implement some behavior for `s/kademlia`. This experience exposed him to high quality Rust code that abstracts shared behavior into traits and designs generic APIs around the trait objects. During this time, he was mentored by David Craven, an ex-Parity core developer and author of [substrate-ext](), an RPC for generating extrinsics to send to Substrate nodes. An extension of this project will be built for testing the modules as part of the second and third milestones. David will mentor this part of the project and contribute as necessary to build the tooling described further below.

During Amar's last month working full-time at Parity, he will focus on documenting the tooling around testing and benchmarking substrate runtimes. This work will inform the design of the loosely coupled modules proposed in this grant and the testing of the configured runtime. His work on this has already [begun](https://github.com/substrate-developer-hub/recipes/pull/81).

**\A ppl**
* linkedin
* github profiles

Noah __

Jake __

David Craven

ADVISOR:
- Jack Platts for business development and alignment with demand

## Team Code Repos

* sunshine
* sunscreen-ui (place frontend design css?)
* monetary futarchy (upgrade proposals for monetary policy...)
* rpc3p0?

# Development Roadmap

## MILESTONE 1: Design and Document Spec for Module Library
- user research for interfacing with fund coordination committees - "what governance mechanisms serve a useful purpose and what structure adds unnecessary complexity?"
- focus on using React and specifying the required types for Polkadot.js (and planning the corresponding required Substrate types) `=>` **should have a documentation-based spec for all the modules**
- documentation will define a few use cases like open source funding or charity-based governance

## MILESTONE 2: UI and Finish MVP Demo with Command Line Tool
* basic version of all modules with tests
* basic UI for sunshine as an instance that uses the four modules
* command line demo with RPCs based on substrate-ext

## MILESTONE 3: Docs, Demos, and Finished Modules
* four finished modules with a `traits` module for shared behavior
* command line demos for testing (and possibly benchmarking) the configured organizations
* UI for organizations with certain features (maybe a standardized process for adding features with UIs)

# Additional Information

Work has been done so far
* design of mechanisms in this documentation
* already experienced with substrate development, working on the primary source of documentation on runtime architecture patterns

Have you applied to other grants so far?
No.

Are there any projects similar to yours? If so, how is your project different?
Flowchain seems to be oriented around the governance of DeFi based stability protocols that assume coordination of liquidity provision. Our governance modules may compliment the governance and participation in the Laminar protocol. We believe that we will introduce nuanced governance that lends itself to increased flexibility for applications with changing requirements.