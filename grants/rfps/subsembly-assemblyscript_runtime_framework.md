# Subsembly
##### AssemblyScript Runtime Framework Proposal

## Project Description
*In response to the Alternative Polkadot Runtime Generation (AssemblyScript) RFP.*

The goal of the project is to develop a framework for AssemblyScript runtime development. This proposal is a follow-up on the previous PoC Account-based Runtime developed in AssemblyScript. As always the goal of the prototype AssemblyScript runtime was to serve as a proof-of-concept. Now that we have managed to deliver it, we would like to refactor it and extend it in such a way, so that developers will be able to build Runtimes in AssemblyScript relatively easily. Our approach would be similar to Substrate as it serves as a perfect example of such a framework.

The goal would be to:
- Make the code more abstract and reusable. Refactor the code so that is more structured and developers can fairly easily build something on top.
- Provide CLI tool for bootstrapping and compiling AssemblyScript Runtimes.
- Implement more Substrate Modules, because as of now, the only ones supported are: Timestamp, Aura and Balances.
- Add extensive documentation and recipes, hosted on Gitbook or similar.

## Team Members
- Daniel Ivanov, Christian Veselinov (leads)
- Dastanbek Samatov
- Kristiyan Srebrev
## Team Website
- https://limechain.tech
## Legal Structure
- LimeLabs Ltd., incorporated in Bulgaria, Dragan Tsankov 23A, 1113, Sofia, Bulgaria
## Team's experience
LimeChain is a blockchain development company with offices in London, UK and Sofia, Bulgaria. Since 2017, LimeChain has worked on 70+ blockchain projects, including a strong track record of building developer tools for different protocols such as Ethereum, EOS, Aeternity and Corda. Some of the companies LimeChain has worked with are Celo, P&G, Raiffeisenbank, Status, Dapper Labs, Hedera and Maker among others. LimeChain is also embedded into the Polkadot developer ecosystem, particularly with building AssemblyScript developer tools. The team has built a SCALE Codec implementation and an Account-based AssemblyScript Runtime PoC.

Current Polkadot related projects:
- https://github.com/LimeChain/as-scale-codec
- https://github.com/LimeChain/as-substrate-runtime

## Team Code Repos
- https://github.com/LimeChain
- https://github.com/Daniel-K-Ivanov
- https://github.com/dastanbeksamatov
- https://github.com/thcrnk

## Team LinkedIn Profiles
- https://www.linkedin.com/in/daniel-k-ivanov/
- https://www.linkedin.com/in/dastanbek-samatov-30ab71128/
- https://www.linkedin.com/in/chris-veselinov/
- https://www.linkedin.com/in/kristiyan-srebrev-30087229/

## Development Roadmap
Based on our past experience from building Developer tools and the expertise we gained while building the PoC Account-Based Runtime we think that there is a spectrum of tasks that will contribute to the success of Subsembly.
- **Interface**: We want for builders to easily test and use the Runtimes that they are building, that’s why we think that implementing the Metadata API will be beneficial.
- **Config**: One of the most important architectural drivers of the framework will be the ease of configuration. We will keep Runtime configuration as one of the top priorities when it comes to design decisions. 
- **Features**: Support for new pallets. Providing the most used components as components off-the-shelf will be beneficial to developers.
- **Docs**: Gitbook Documentation & Recipes
- **Optimisations**: We see a big potential on optimising the already existing operations in SCALE Codec and Runtime. Now that the library is gaining traction and developers will be using it, we think that it will be important to refactor some of the logic in order to increase the read/write/memory performance. 

The code will be released with Apache 2.0 license.

**Important**:<br>
Although security will be one of the top priorities along with modifiability while building Subsembly, we must acknowledge that the framework, as it will be delivered at the end of the proposed milestones, will not be production ready. In order for that to happen, in our opinion, community reviews as well as formal audit will be required.

We want to keep in mind that although Subsembly will follow Substrate’s approach, AssemblyScript is not mature. A lot of libraries do not exist yet and most of those that already exist are not production ready. To add on top of that, AssemblyScript does not have support for powerful language features such as macros which are heavily used in Substrate. That being said, we will do our best and keep the developer experience and security as top priority.

![subsembly-wbs](https://raw.githubusercontent.com/LimeChain/General-Grants-Program/images-branch/grants/rfps/images/subsembly-wbs-diagram.png)

## Milestone 1 — Foundation — 15 days
This milestone will lay out the project’s foundations. For the successful completion of this milestone we can define the following criteria:
1. Create a new repository and use the current AS Runtime Modules and core modules in the Subsembly framework.
2. Explore possible design implementation and refactor the code structure so that it is easy for someone to configure the properties of his Runtime or the modules that he uses. The goal would be to produce a design that provides high modifiability by having low coupling and high cohesion. This is one of the most important aspects of the framework and we would like to do it properly while keeping in mind the nature of the AssemblyScript language.
    - Being able to easily configure runtime version and block time.
    - Being able to easily add new custom pallets/modules.

3. Provide inline documentation and a README file documenting the Subsembly project.
4. Optimise the performance of AS SCALE Codec encoding/decoding (one of the most frequently used operations in the Runtime. We can achieve more than 2x optimisation).

Note: Branding materials will be created although they will be outside the grant scope and will be funded by LimeChain.

**Full-Time Employees: 2**<br>
**Days: 15**

## Milestone 2 — Metadata and Fees — 15 days
For the successful completion of this milestone we can define the following criteria:
1. Implement Metadata and its API for the already built modules (System, Aura, Balances, Timestamp). Add internal documentation, Unit and Integration tests. The Metadata module enables anyone to easily interact with the Runtime using the https://polkadot.js.org/apps/ interface.
2. Implement Transaction Payment module along with unit and integration tests. Will be used to enforce fees on transactions.

**Full-Time Employees: 2**<br>
**Days: 15**

## Milestone 3 — Subsembly CLI — 14 days
In this milestone, we are planning to introduce the Subsembly CLI, a npm library that will help developers get started with Subsembly. For the successful completion of this milestone we can define the following criteria:
1. Create the Subsembly CLI and publish it as a NPM package.
2. `subsembly init`  - Once executed, it will create the appropriate folder structure (runtime, tests). The core modules of Subsembly will be placed in the “/runtime” folder, along with the core functionality such as the Runtime API, serialisation and deserialisation. This command will be used to bootstrap new Subsembly Runtimes. We will explore the different module packaging options as-well.
3. `subsembly compile` - Once executed, the command will compile the AS Runtime and produce the WASM binary.
4. `subsembly build-spec` - Once executed, the command will build the RAW genesis specification from a provided (non-raw) spec file.
5. Implement integration tests for the CLI functionality.
6. Provide inline documentation and a README file documenting the Subsembly CLI.

**Full-Time Employees: 2**<br>
**Days: 14**

## Milestone 4 — Documentation & Recipes — 12 days
In this milestone, we are planning to create a Gitbook documentation for Subsembly and the CLI. At this point, developers will be able to use Subsembly to build runtimes. It is important not to neglect the documentation, guides and recipes as they are going to be the most important resource for builders. For the successful completion of this milestone we can define the following criteria:
1. Create a Gitbook (or similar) hosted website for Subsembly.
2. Provide extensive documentation about the framework and its components.
3. Provide documentation about Subsembly CLI.
4. Create Recipes/Guides section and describe how someone can use Subsembly to:
    -  Develop his own pallets
    - Create and run Account-Based Runtime on a Substrate node

**Full-Time Employees: 1.5**<br>
**Days: 12**

While building the PoC Runtime, we always kept modularity as an important property of the design, thus we implemented the modules as separate packages and as decoupled as possible. Because of that we would be able to easily introduce new pallets/modules in Subsembly. There is already a big list of pallets implemented in Substrate, that can be added in Subsembly as-well, however we decided that it might be best to start with the ones that might seem most complex for developers to implement themselves (Milestones 5 and 6) though widely used.

## Milestone 5 — Session and BABE — 23 days
For the successful completion of this milestone we can define the following criteria:
1. Implement and test Session pallet. Will be required by BABE and GRANDPA.
2. Implement and test BABE pallet. Users must be able to produce Subsembly
3. Runtime and run it on a Substrate node that uses BABE.
The new pallets will be added in the Docs website of Subsembly along with recipes on how someone can use them.

**Full-Time Employees: 2**<br>
**Days: 23**

## Milestone 6 — GRANDPA — 14 days
For the successful completion of this milestone we can define the following criteria:
1. Implement and test GRANDPA pallet. Users must be able to produce Subsembly Runtime and run it on a Substrate node that uses GRANDPA.
2. The new pallet will be added in the Docs website of Subsembly along with a recipe on how someone can run AS Runtime with GRANDPA configured.

**Full-Time Employees: 2**<br>
**Days: 14**

## Future Plans
LimeChain will be resolving any critical bugs that may arise.

We would like to extend the framework by adding new pallets in the future. The list of pallets that can be implemented is a big one though. We can tailor them to the ones that Web3 Foundation sees as most important or valuable from their observations. Here is a list of the possible pallets that can be added to the framework as of the current state of AssemblyScript, if the Web3 Foundation is interested in that:
1. Assets
2. Atomic Swaps
3. Authority Discovery
4. Authorship
5. Democracy
6. Elections Phragmen
7. Finality Tracker
8. I’m Online
9. Indices
10. Nicks
11. Offences
12. Proxy
13. Randomness Collective Flip
14. Recovery (utilises Proxy)
15. Scheduler

After the delivery of Milestone 3, Subsembly can be used by builders and after Milestone 4 (docs), builders will have the necessary resources to do so. We would like to help out developers who want to use the framework and share our knowledge developing AssemblyScript Runtimes. We will share as much information as possible in the documentation & recipes website. LimeChain views the project as not only another way of building Runtimes for Substrate, but as a foundational knowledge base for AssemblyScript <> Substrate/Polkadot related projects as-well.

In mid to long term, LimeChain hopes to continuously add value to the Polkadot development community with further implementations, SDKs and libraries, such as Smart Contract related tooling.
