# Sunshine by Web3 Garden

[Web3 Garden](https://web3.garden) is committed to building infrastructure for creating stable, well-governed communities on Substrate.
[**sunshine**](https://sunshine.community) is one of the flagship projects.

## Project Background

We are building governance modules with user interfaces for Polkadot parachains. This aligns with the Web3 Hermit governance parachain, but the scope of the initial grant is four modules that can be configured into a runtime with a UI to deploy and support instances of fund coordination organizations as described in the [documentation](https://web3garden.github.io/sunshine-spec/).

This proposal is NOT for a generic "DAO chain", but the modules will be useful for parachain governance in the absence of a canonical chain for governance; parachains can configure these modules and add them to their chain in lieu of accessing them through SPREE or some other trusted communication channel.

This grant application is for the design and implementation of four loosely coupled modules, a runtime to configure the modules, and a Polkadot-js interface for user interaction. The three-month objective includes
* four loosely coupled runtime modules with a runtime that supports instances of [**sunshine**](https://web3garden.github.io/sunshine-spec/) as an example configuration
* a Polkadot-js user interface for organizations to use the modules
* a CLI tool for testing the modules by constructing extrinsics with [`substrate-subxt`](https://github.com/paritytech/substrate-subxt/)

The runtime will configure four modules:
1. `court`: define dispute conditions for each milestone associated with a grant and the dispute resolution conditions `=>` uses instances of `vote` and `futarchy` for governance of the court's rules
2. `bank`: define the pool of funds, its members, and the conditions for membership `=>` uses instances of `vote` for each `committee` to make decisions, optional use of `futarchy` for enhanced forward guidance on spending decisions (possibly enforced by collateral requirements)
3. `vote`: define and configure voting algorithms to govern courts or banks (*special features used: runtime instancing, offchain-workers*)
4. `futarchy`: define how the vote module can change according to the preferences of stakeholders `=>` push the limits of application-based governance with metagovernance  (*special features used: runtime instancing, offchain-workers*)

The milestones and plan are described in detail further below. The first month will be dedicated to user research and interface design to derive the required functionality for each module. The second month will be dedicated to building the modules and constructing a runtime. The third month will be dedicated to testing and rewriting the modules (for increased modularity by abstracting shared behavior into traits).

## Legal Structure

Private limited company

## Team Background

Amar Singh has devoted the past eight months to writing the [Substrate Recipes](https://github.com/substrate-developer-hub/recipes), a collection of best practices for building modules and runtimes with substrate. He presented [Building DAOs on Substrate](https://www.youtube.com/watch?v=eguDIG11nW8) at Sub0 and, more recently, [presented at DOTcon](https://youtu.be/l9omXAWhWDM?t=101) with a [proposal for Polkadot's monetary policy](https://github.com/web3garden/monetary-futarchy). Amar will be designing and developing the modules and runtime. 
* [LinkedIn](https://www.linkedin.com/in/amar-singh-148043ba)
* [Github](https://github.com/4meta5)

Noah Gallant is the founder of [Sight](https://sight.design/) where he works with companies, non-profits, governments, and universities to innovate with empathy and sustainability in mind. He is interested in bringing accessible, human-centered design principles to blockchain technology. With this in mind, he will lead the user research pursued in milestone (1) to inform the design of the modules, runtime, and UI.
* [LinkedIn](https://www.linkedin.com/in/noah-gallant-9696078b)
* [Github](https://github.com/NoahGallant)

David Craven was a core developer at Parity. During his time at Parity, he made significant contributions to `substrate/core` and built [substrate-subxt](https://github.com/paritytech/substrate-subxt) before leaving the company to work on [rust-p2p](https://github.com/rust-p2p). David will be helping Amar build a command line tool for milestones (2) and (3) to test runtimes in the command line. This tool builds on [`substrate-subxt`](https://github.com/paritytech/substrate-subxt/) to construct extrinsics and send them to a running node via RPC.
* [LinkedIn](https://www.linkedin.com/in/dvc94ch)
* [Github](https://github.com/dvc94ch)

Jacob Chase-Lubitz is product strategist with five years of experience designing multi-sided platforms and business models, crafting product roadmaps, and managing development projects. He served as Director of Product Development at Everybill LLC, where he lead the design of an [award-winning concept for a healthcare payment platform](http://www.abillyoucanunderstand.com/winners-list/everybill). In his current role as Product Strategist at Artory GmbH, Jake is responsible for conducting customer research and forming go-to-market and pricing strategy. 
* [LinkedIn](https://www.linkedin.com/in/jchaselubitz/)
* [Github](https://github.com/jchaselubitz)

## <a href="https://github.com/web3garden/">Team Code Repos</a>

* [sunshine](https://github.com/web3garden/sunshine)
* [sunshine-docs](https://github.com/web3garden/sunshine-spec)
* [monetary-futarchy](https://github.com/web3garden/monetary-futarchy)

# Development Roadmap

## MILESTONE 1: Design and Document Specification
- user research report for fund coordination committees; the goal is to attain greater clarity as to "what governance mechanisms serve a useful purpose and what structure adds unnecessary complexity?" (Noah and Amar)
- **documentation** for required types for each module, their required functionality, and the required (new) type conversions between Polkadot-js and the substrate runtime (Noah and Amar)
- documentation will include a section for the research report to define prioritized features for a few use cases like open source funding, charity governance (liberal radicalism), and lending pools (Noah and Amar)

## MILESTONE 2: 2/4 Modules with Runtime and UI
- implementation of `vote` and `bank` modules (Amar)
- runtime with `vote` and `bank` modules configured (Amar)
- Polkadot-js libraries with types for interfaces that use `vote` and `bank` modules (Noah)
- start work on a local node RPC compatible with `substrate-subxt` for comprehensive testing of the modules (David and Amar)

## MILESTONE 3: Docs, Runtime, and CLI Tool for Runtime Testing
- `vote`, `bank`, `court`, `futarchy` modules (Amar)
- runtime with modules configured to support `sunshine` instances (Amar)
- command line tool for testing the runtime on a live node (David)
- Polkadot-js UI for `sunshine` instances configured and deployed on the runtime (Noah)
- *documentation for all the components*

# Additional Information

Each milestone will be completed within one month, starting in January 2020 and finishing all objectives under milestone 3 by the end of March 2020. All code will be delivered inside docker containers.

Work has been done so far
* mechanism design in [documentation](https://web3garden.github.io/sunshine-spec/) (which is now a bit outdated but contains the thoughts behind a previous iteration of the runtime, much of which will stay the same depending on feedback from user research during the first milestone)
* (Amar and David) already experienced with substrate development
* (David) already experienced with rust and substrate RPCs

### Have you applied to other grants so far?
No.

### Are there any projects similar to yours? If so, how is your project different?
Flowchain's innovative design seems to stem from nuanced governance of DeFi based stability protocols that require greater coordination of liquidity provision. Our modules may compliment these modules, but the focus of our work is not to innovate on the mechanism design. Instead, we would like to design usable and accessible interfaces with runtime module APIs designed to facilitate user interaction. The auxiliary tooling proposed for our second and third milestone will be used to more rigorously test the runtime and instill confidence in the underlying implementation.
