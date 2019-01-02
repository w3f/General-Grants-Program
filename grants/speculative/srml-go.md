# SRML-GO

## Project Description
The goal is to port the substrate runtime module library [srml](https://github.com/paritytech/substrate/tree/master/srml), and some of their dependencies from Rust to Go. In addition to the necessary compiler toolchain and supporting documentation and tutorials, to make it possible to write runtime code with Go while still running full nodes with the reference Rust client.

We see great potential in this effort to make the substrate technology stack the first choice for any team planning on building their own application specific chains.

## Why are we getting involved
Jsgenesis is developing [Joystream](https://www.joystream.org), a user governed video platform powered by the blockchain.

We intend to build Joystream on substrate, and wish to develop our runtime modules in Go.

## Progress so far
In early December 2018, we started in this endeavor by doing some research into mainline Go's compiler support for producing WASM modules, looking at alternatives such as tinyGo, porting the [parity-codec](https://github.com/Joystream/parity-codec-go) repo to Go, adding some [test coverage](https://github.com/paritytech/parity-codec/pull/23) and doing some [basic WASM executor tests](https://github.com/Joystream/tinygo-wasm-substrate) on test runtime code, compiled with patched tinyGo's wasm compiler.

## Team members
The following team members from Jsgenesis will be working on the project:

* Konstantin Yegupov - role: leader developer
* Mokhtar Naamani, Co-Founder/CTO - role: project manager

## Team Website
* Company [Jsgenesis AS](https://www.jsgenesis.com)
* Project [Joystream](https://www.joystream.org)

## Legal Structure
Jsgenesis AS is a Private Limited Liability Company incorporated in Oslo, Norway.

## Team's experience
* Konstantin is a software developer with over a decade of experience in Java, Python, Javascript, Go and Rust. Specializing in backend systems development, and Linux OS systems management.

* Mokhtar is a software developer with 5+ years experience in software engineering (C/C++, Javascript, Solidity, Truffle/Drizzle framework), systems operations, in particular working on distributed p2p technology, such as [Joystream classic](https://github.com/JoystreamClassic), experience with Ethereum smart contract development, and most recently exploring cosmos/tendermint sdk.

## Team Code Repos
* Parity Codec https://github.com/Joystream/parity-codec-go
* Substrate tinyGo runtime modules https://github.com/Joystream/tinygo-wasm-substrate
* Mokhtar https://github.com/mnaamani
* Konstantin https://github.com/kyegupov
* https://github.com/Joystream
* https://github.com/JoystreamClassic

## Team LinkedIn Profiles
* https://www.linkedin.com/in/mokhtarnaamani/
* https://www.linkedin.com/in/konstantin-yegupov-7017aa4

## Intended language of development
* Golang - [tinyGo](https://github.com/aykevl/tinygo) -  a Go compiler for microcontrollers


## Development Roadmap
We estimate that we will require 3 months (12-weeks) to complete this project. We intend to have 1 developer working 30H/week and 1 project manager, at a total cost of $45,000.

Ideally, we can receive part payment every four weeks.

### Milestones
> Approach A - Waterfall

Based on the dependency tree of the srml modules, and perceived complexity, they will be ported in order, over a series of milestones:

- Weeks 1,2,3
  * metadata
  * support-procedural
  * support
  * system
- Week 4
  * balances
  * assets
  * example
- Week 5/6
  * treasury
  * democracy
  * council
- Week 7/8
  * consensus
  * upgrade-key
  * session
- Week 9
  * timestamp
  * staking
- Week 10/11
  * contract
  * aura
  * grandpa
- Week 12
  * Documentation - publish to [godoc.org](https://godoc.org/)
  * Tutorial: [Creating a new runtime module](https://substrate.readme.io/docs/creating-a-custom-substrate-chain#section-step-3-create-a-new-runtime-module)

> Approach B - Higher level modules first

Alternatively we can select higher level modules to implement first and build the required functionality in the base level modules (system and support) as required.

> The best approach can be determined after further discussion with core paritytech team.

We can only accept payment in fiat.

We intend that all project deliverables would be transferred to the paritytech github organisation upon completion, but expect to continue to contribute to the codebase, as we will be dependent on it for the Joystream project.

All source code will be freely licensed under GPLv3.

## Additional Information
* Given some of the [limitations](https://github.com/golang/go/issues/25612) of mainline Go WASM compiler, we are choosing to use [tinyGo](https://github.com/aykevl/tinygo). Since tinyGo is a subset of Go it will require working with maintainers to ensure it can support all the requirements for this project.

* Implementation of some dependencies of the srml modules may be done by another team that might be working on a full Go implementation of the core substrate codebase. These dependencies constitute common code that needs to be compiled both with mainline Go compiler as well as to web assembly, and so collaboration will be necessary to find the best solution to this challenge.

* Time estimates are made with the assumption that the current srml Rust code will remain unchanged over the period of this project which may not necessarily be accurate. As code continues to mature, features added, and bugs are fixed it may require revisiting already completed modules, which might require additional time to complete the project.
