# t3rn

## Project Description
3rn is a protocol for interoperable code execution between multiple blockchains, which makes it safe and simple by following the implementation of the execution circuit. 

t3rn consists out of framework & tools to write interoperable code (both as contracts and runtime logic), the execution platform of that code and reusable packages registry - blocks of interoperable logic maintained by decentralised network. 

t3rn emphasizes the existent decentralised-solutions interoperability and allows multiple blockchains to collaborate. By re-using the whole decentralised application blocks, fosters building the decentralised solutions with the freedom to operate on multiple chains.

## Team members
* Maciej Baj, director, maciej@maciejbaj.com.

## Team Website	
* https://github.com/t3rn

## Team's experience
Maciej Baj - >3 years experience as a blockchain developer, project manager & head of development. 

## Team Code Repos
* https://github.com/MaciejBaj
* https://github.com/t3rn

## Team LinkedIn Profiles
* https://www.linkedin.com/in/maciej-baj/

## Development Roadmap 

#### Milestone 1: Design & Initial Structure — 0.5 Month
##### Design 
- Document and standardise the entities - package, standard, gateway, blockchain. 
- Document and standardise Circuit API, interfaces, contexts.
- Document and standardise Gateway Standards, Engine, API.
- Document and standardise the initial base package - transfer manual.
- Design and document an example Package - SEA (Service Execution Agreement), where a consumer gets to buy a service registered on another chain. That package uses the previously documented base packages - transfers manual.
##### Initial Structure
- Create initial Substrate modules that cover implement the documented 
Requirements:
- Package, Standard, Blockchain all have their API defined.
- Gateway Circuit has defined API & context.
- Gateway Stanards, Engine, API have defined API & context.
- SEA Example is documented and supported with a graphic.
- Create initial modules for t3rn SRML leaving the functions empty for now.
- Following Substrate modules are created with full API but empty functions: Blockchain, Package, Standard, Gateway, Gateway Circuit.

#### Milestone 2: Gateway — 1 Month 
##### Engine
- Implement the Gateway Engine that executes WASM Binaries (for Contracts) and native Rust functions (for Modules).
- Implement Escrow Account with an overlay in Gateway, that:
    - Adds the authorisation layer on top of changes to Escrow Accounts granting the write access only to given accounts (eventually t3rn validators).
    - Calculates the merkle path out of state transitions to Escrow Accounts as execution proofs.
- Implement the inclusion proofs in Gateway Engine.
##### Standards
- Implement Gateway Standards.
- Integrate Gateway with Balances Pallet. 
- Integrate Gateway with Contracts Pallet. 
##### API
- Implement simulated Gateway API that passes massages to and from the Gateway.
- Create an example that sends the compiled WASM Contract.

#### Milestone 3: Gateway Circuit & Registry — 1 Month 
##### Registry
- Implement the registry that stores Packages, Standards, Blockchains and Gateways. 
- Provide the Registry API module to post and get the entities to and from the registry.
- Register two example blockchians in the registry. 
##### Circuit
- Implement Gateway Circuit that sends and receives the messages to and from a gateway.  
- Implement the Circuit execution that processes the transaction on all affected gateways.
    - Validate the proofs received from a gateway and store them in the execution context. 
- Implement the execution phases into the circuit. 
- Implement the customizable execution order into the phases.
- Implement the accounts and balances for t3rn packages executioners.
- Provide Circuit API that receives the singed interoperable transactions and stores them as packages in the registry.

#### Milestone 4: Transfers & Tools — 1 Month 
- Create the compilation tool that translates the t3rn contracts into the interoperable transactions (WASM Binaries + Metadata).
- Create the tool for signing and sending the interoperable transactions to the Gateway Circuit.
- Demonstrate the customizable execution order by implementing a contract using the promise-like behaviour.
- Implement & Demonstrate the transfer manual package.

#### Milestone 5: Consensus & Network — 1 Month 
- Implement consensus and validation system over the Gateway Circuit interoperable execution and proofs.
- Introduce network validators that form the consensus and host the interoperable execution provided by Gateway Circuit.
- Introduce the fee model for interoperable execution.
- Release a test network of t3rn hosting the platform for interoperable execution.

#### Milestone 5: Additional Packages — 1 Month 
- Implement the swap package, allowing placing and the swap orders for a limited and market price.
- Implement the SEA package, that consumes the service registered on a different parachain using the swap package. 
- Demonstrate the SEA package usage by deploying the SEA & swap packages into the testnet network and creating a simple GUI.

## Future Steps 
- Implement Gateway with XCMP API. 
- (Optional) Implement Gateway with Bridge API. 
- Release t3rn as a cryptocurrency and integrate with a 3rd party decentralised exchange. 
- Implement the transfer auto package that seamlessly exchanges the cryptocurrencies between parachains affected in the interoperable execution.
- Implement gov module that governs t3rn Registry.
