# Standalone t3rn Gateway 

## Project Description
t3rn is designed to be a protocol for interoperable code execution between multiple blockchains, which makes it safe and simple by following the implementation of the execution circuit.

Within this initial developement phase the work will continue on framework & tools to write interoperable code (both as contracts and runtime logic) and the standalone Gateway responsible for executing packages on a single parachain.

The standalone Gateway brings additional phases over the regular runtime execution - commit and revert, due to which effects of the execution can be reverted and never committed to the target accounts. This is possible, as after the execution phase the changes are made only to the child storage of dedicated on that parachain Escrow Account, which acts as a regular account from the perspective of a parachain, therefore all of the changes to its storage are secured by the consensus effective in that parachain and can be relied on by already integrated services. 

### Standalone Gateway vs Interoperable Circuit
Creating the standalone Gateway constitutes the first phase of work on the interoperable t3rn protocol. As a result of that phase, Gateway comes as the pallet which can be included in parachains as an additional utility that brings multiple phases and reversibility into execution. Using the standalone Gateway, developers can create the reversible logic within the context of a single parachain.

The appropriate tools for the compilation of contracts and modules that work on the multiple phases environment operated by the Gateway are also the result of the initial development phase.  

The system automatically overseeing and ordering the execution of the phases over multiple registered parachains - Gateways Circuit will become the result of the next development phases of the interoperable t3rn protocol. 

More information about can be found in the dedicated [Gateway readme](https://github.com/t3rn/t3rn/blob/master/gateway_standalone.md).

## Team members
* Maciej Baj, director, maciej@maciejbaj.com.

## Team Website	
* https://github.com/t3rn

## Team's experience
Maciej Baj - I am passionate about blockchain with more than 3 years of experience as a blockchain developer, project manager & head of development. Academic background fed my natural joy to deeply research and analyze technical challenges and opportunities that the industry faces.

## Team Code Repos
* https://github.com/MaciejBaj
* https://github.com/t3rn
* https://github.com/t3rn/t3rn/blob/master/gateway_standalone.md

## Team LinkedIn Profiles
* https://www.linkedin.com/in/maciej-baj/

## Development Roadmap 

#### Milestone 1: Initial Structure & Gateway API — 2 Weeks
##### Initial Structure
- Document and standardise Gateway Standards, Engine, API.
- Create initial Substrate modules & structure for Gateway Standards, Engine, API filled with mocked functions.
- Create the structure for the multi-step transaction. 
##### Gateway API
- Implement `multistep_call` RPC endpoint that receives the multi-step transctions, validates them and passes into Gateway Engine.
- Implement the `rent_projection` function that passes the query about the execution projection to Gateway Engine. 
- Create an example, already compiled, package and demonstrating sending Gateway API. Update the documentation and readme files accordingly.

#### Milestone 2: Gateway Engine — 6 weeks
- Execute received from Gateway API packages and pass the current execution results back to the API. 
- Implement Escrow Accounts:
    - Implement Escrow Account submodule that holds the multi-step transaction executed on that parachain within its storage.
    - Adds the authorization layer on top of changes to Escrow Accounts granting the write access only to authorized accounts (eventually t3rn validators, in the meantime to trusted parties).
    - Calculates the merkle path out of storage transitions to Escrow Accounts as execution proofs of the `Execution` phase.
- Implement the `Revert` and `Commit` phases handlers, that either move the state out of Escrow Account into the target accounts or invalidate the operation. Validate whether the accounts were mutated and provide convenient configuration to deal with this special case.
- Present the proofs of execution and inclusion that accesses the state of a parachain to calculate merkle paths out of state and extrinsic tree.
- Integrate the Engine with Parachains supporting both Balance and Contract pallet. Adhere to the operative fee strategy.
- Prepare functional tests checking validity of execution results and their proofs for a few example packages.
- Update the documentation and readme files to ensure they're aligned with implementation. 

#### Milestone 3: Gateway Standards — 4 Weeks
- Prepare Standards - the equivalent of Contract pallet external execution context to work in multiple phases with the use of Escrow Account.
- Allow modules to be executed via Gateway as host functions, in order to support non-standard functionalities hosted by parachains that do not include Contracts pallet.
- Update the documentation and readme files to ensure they're aligned with implementation. 
- Write integration test checking the functionality of standalone Gateway as a whole.
- Provide a Docker image with standalone Gateway.

#### Milestone 4: Package Compilation Tools — 4 Weeks
- Create the compilation tool that translates the contracts and modules into the packages, as described in details in "Package, Contract, Module" subsection. 
The compiler divides the business logic into several chunks which can be executed separately on gateways, but make sense as a whole in the context of overall multi-step transaction execution.
- Create the tool for signing and sending the interoperable transactions to the Gateway.
- Demonstrate the execution on standalone gateway by preparing a few examples, which will be included in the documentation.
- Create the docker image with preloaded modules and the example of sending packages into the Gateway.

## Future Steps 
#### Please refer to the following development phases highighted in [Development Roadmap of t3rn protocol](https://github.com/t3rn/t3rn#development-roadmap).
