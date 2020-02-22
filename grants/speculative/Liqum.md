# Liqum

## Project Description

### A brief description of the project.

**Liqum** is a business process protocol that facilitates collaboration between decentralized services in the Polkadot ecosystem, as well as the outside world. It allows stakeholders to agree on the workflow, and ensure that its participants interact with each other according to the same rules.

The centerpiece is a process model in BPMN 2.0 standard that defines all the tasks to be performed by humans and machines. The flowchart is compiled into a dynamic data structure representing the process and its instances. Once published on-chain, it controls consistent, trustless, and real-time workflow execution.

The state changes with every piece of work performed. Smart contracts automatically assign the right jobs to the right resources. Permissioned visibility into transactions allows activity monitoring and reporting.

### An indication of why this project is good for the ecosystem.

Conventional centralized applications are disconnected, making interaction between them difficult. Services based on Polkadot should not repeat the same mistake and seek to capitalize on the native interoperability as the primary benefit of the emerging crypto economy. **Liqum** provides just that, an abstraction layer for structured and interconnected value chains that prioritizes process outcome over its ownership.

More specifically, each member of the ecosystem can perform a specific task in a process orchestrated across the network, e.g. confirm self-sovereign identity, issue a credit in stablecoin, or whatever utility they can provide. The main beneficiary is the end user though, profiting from increased operations efficiencies.

Think of it as a BPM system, but available globally to all the actors, as opposed to being siloed in a single organization.

### An indication of how you will integrate this project into Substrate / Polkadot.

We aim to create a process execution engine on top of Substrate. The key idea is to generate ink! smart contracts capable of interpreting a BPMN process model, represented as a space-optimized data structure, that can be dynamically modified at any time.

Each set of smart contracts embodies control flow logic, data structure state, and specific external user defined tasks & scripts, that are compiled directly from a BPMN model. Then, we extract compilation artifacts, such as element indexes, their respective encoded types, and condition tables. Smart contracts are initialized through Polkadot apps api and linked together by their respective AccountId`s. Together, they form an executable process representation.

At this stage we are building an on-chain part of the project, but you can learn more about the next steps in the Future Plans section below.

### An indication of why your team is interested in creating this project.

Denis has been discovering and automating business processes for the last 5 years. One of the most common problems is a technological disconnect between different companies trying to collaborate. It is currently solved with forcing one party into the infrastructure of the other; or by custom and direct integration; or via trigger-event services like Zapier. None of this is scalable.

Blockchain environment removes the need for a middleman, while processes can be defined in universally understood notation as autonomously functioning models. Together these facts create an enormous opportunity to make interaction and coordination between distributed parties more efficient.

## Team members

* **Denis Igin**, Business Development
* **Aleksey Gnatovskyi**, Software Engineer
* **Arsen Kondratiev**, Software Engineer

## Team Website	

https://liqum.io

## Legal Structure 

The business is registered as Sole Proprietorship. We might change the incorporation structure and jurisdiction with the first institutional investor.

## Team's experience

[Aleksey](https://github.com/alekspickle) is a software engineer with hands-on experience building on Substrate. Additionally, he specializes in Rust, NodeJs, Python, and React, with over two years of development experience with these technologies.

Some examples of the work include:

* Dothereum project development (porting runtime block producing [from babe to aura](https://github.com/dothereum/dothereum/tree/aura)) when it was active.
* One of core developers of [PolkaHub](https://github.com/akropolisio/polkahub-monorepo) hosting for easier parachain/substrate-based node deployment ([CLI](https://github.com/akropolisio/polkahub-cli), [backend](https://github.com/akropolisio/polkahub-backend)).

[Arsen](https://github.com/iorveth) is a Rust developer with over a year of experience in blockchain & backend domains. 

One of the recent projects involved successful requirements definition, architecture design, and code of Cost per Action and Statistic Collector infrastructure backends in Rust for cluster of DAPs, based on Tron and EOS platforms. The actual commits and the name of the project cannot be disclosed due to NDA restrictions.

An examples of the work:

* Utxo based, bitcoin-like blockchain, implemented in Rust - [ritcoin](https://github.com/iorveth/ritcoin) (purely for educational purposes)

Denis has 20+ years of entrepreneurial and management experience: 2 companies and 3 startups launched, had 1 exit, hundreds of websites / systems developed, active member of local venture and blockchain community.

## Team Code Repos

https://github.com/Liqum/rust-onchain-execution-engine/

## Team LinkedIn Profiles

* [Denis Igin](https://www.linkedin.com/in/denisigin/)
* [Aleksey Gnatovskyi](https://www.linkedin.com/in/aleksey-gnatovskyi-31b15a131/)
* [Arsen Kondratiev](https://www.linkedin.com/in/arsen-kondratiev-031801172/)

## Development Roadmap

The core of the system is a set of smart contracts based on BPMN standard that implement common operations in any process model. They are decoupled for the sake of reusability:

**BPMN Interpreter**: Encodes the semantics of the BPMN language and controls that the execution adheres to the standard. It is implemented as a single process-agnostic contract that interprets the logic of the process models by querying / updating process perspectives from / into Interpreter Flow and Interpreter Data structures.

**Interpreter Flow**:  Describes the control-flow perspective of the workflows, i.e. an order in which instructions are executed. It contains process model structures, as well as their elements (task, event, gateway, etc.) and relations. Supports sub-processes.

**Interpreter Data**: A hierarchy of smart contracts formed from the nodes for each process / sub-process instance, that store its state and keep a reference to the related Interpreter Flow node.

**Data Factories**: Handles smart contracts’ instantiation. The Data Factories, linked to a sub-process in the Interpreter Flow hierarchy, must define how to instantiate the smart contract of the corresponding Interpreter Data node.

Process specific business rules defined in the models:

**Data & Scripts**: Describes the data management perspective of the workflows, i.e. information created, manipulated, and used while performing the work. It contains data and operations from a particular process model, while the values are conditioned and scoped to its instance. It extends Interpreter Data and is used by external actors to access data and execute tasks. Actor permissions are verified via Resource Access Control, and if he can perform the task, the process data and state are updated. For that, the corresponding Interpreter Data node invokes the BPMN Interpreter, that in turn interacts with the related Interpreter Flow nodes.

**Resource Access Control**: Describes the resource perspective of the workflows, i.e. entities capable of doing the work. Handles the user access control and resource allocation for a task. Supports dynamic role assignment to process actors, that can be extended to restrict not only the execution of tasks, but also to control the operations / updates on the Interpreter Flow and Interpreter Data structures, as an authorization mechanism for process modification.

Components to interact with workflow participants include:

**Event Log**: Manages interactions with external applications and actors, as specified by the process model, and validates the data they provide. Enables interaction with off-chain monitors that listen for events, such as change of state in a process.

**Interchain Bridge**: Implements interactions with other applications in Polkadot network, that are exposed as services.

### Milestone 1

Duration: 1 month

Deliverables: Common process operations, i.e.

* BPMN Interpreter
* Interpreter Flow
* Interpreter Data
* Data Factories

### Milestone 2

Duration: 1 month

Deliverables: Process specific rules, i.e.

* Data & Scripts
* Resource Access Control

### Milestone 3

Duration: 1 month

Deliverables: On-chain and off-chain communication, i.e.

* Event Log
* Interchain Bridge

Each milestone will be delivered together with documentation, tutorials, examples, and a Docker container, that allow checking that the code functions as described above.

## Future Plans

The immediate goal is to gain traction with Polkadot based projects, in parallel with development. We will discover opportunities to automate repeated activities, preferably those happening often, involving end users, and following the same steps every time.

Once the on-chain process execution logic is tested on real-life use cases, we will write our own pallet to be shared and re-used by the community. We also aim to become a parachain, subject to Polkadot mainnet launch and DOT tokens availability.

Further steps to become a fully-fledged business process management system:

Worklist handler: Makes sure that work items are enabled, started, and completed by users or services off-chain

Task panel: End user interface for workers to carry out specific process tasks, e.g. fill out a web form as a result of the work performed

Process activity: Monitoring, reporting, and visualization of the transactions, according to access permissions

Process modelling and setup: End user interface for administrators to model a business process and automatically compile it into a dynamic data structure to be deployed on the execution engine

Process repository: Stores compilation artifacts and addition metadata in a decentralized storage

Far-reaching plans:

Tokenization: Utility token to pay for the service, e.g. a small fee for each update of process status / data.

On-chain governance: Process stakeholders form a council to discuss and agree on business logic and data confidentiality

## Additional Information

We researched the subject matter and conducted a feasibility study to shape the system architecture. The development work has been under way for some time too, but it turned out to take extensive time and effort, hence the need for financial support.

Initial project development is self-funded. We have not applied for other grants. We are open to collaborate with early stage investors though, and might take advantage of various opportunities in the future, such as Substrate Builders Program, Open Grants Program, Polkadot Ecosystem Fund.

There are several other projects that aim to build workflow engines:

[LTO Network](https://lto.network)

* Pros: Mainnet launched, several production customers, 20k daily transactions
* Cons: Workflow engine is under development, not fully decentralized (uses own fork of Waves, NXT for anchoring, keeps data in MongoDB)

[Statebox](https://statebox.org)

* Pros: Advanced workflow engine based on Petri Nets that can be converted from BPMN, production project integrated with GET protocol sold 123k tickets
* Cons: Deployed as a centralized service, can only be used in conjunction with external blockchain

[Caterpillar](https://arxiv.org/abs/1808.03517)

* Pros: Based on BPMN and Ethereum, capable of both compiling and interpreting processes
* Cons: More of a set of academic works, not published on public blockchain yet

[Unibright](https://unibright.io)

* Pros: Based on Ethereum, live PoC exists
* Cons: Only supports basic processes, not BPMN

[Monax](https://monax.io)

* Pros: Fully functional service based on blockchain with a BPMN workflow engine
* Cons: Optimized to handle digital contracts, and not other work

[Agreements Network](https://agreements.network)

* Pros: Fully functional service based on blockchain with a workflow engine
* Cons: Optimized to handle legal agreements, and not other work

[Quanopt](http://quanopt.com)

* Pros: PoC tool for translating BPMN in Hyperledger Composer
* Cons: Early stage

Kudos go to @siman who introduced us to the Substrate and Polkadot ecosystem!
