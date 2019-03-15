# Web3 Foundation Grants

As part of our commitment to promoting the Web3 ecosystem, we are providing a comprehensive grants initiative. This means that successful applicants will be able to receive funding for their efforts to improve the Web3 ecosystem.

* **For technical development grants** [apply here](https://docs.google.com/forms/d/e/1FAIpQLSfMfjiRmDQDRk-4OhNASM6BAKii7rz_B1jWtbCPkUh6N7M2ww/viewform). To help with your application, follow and complete the [5 step process](https://github.com/w3f/Web3-collaboration/blob/master/grants/grants.md#process) and view the areas of interest below.
* **For community related grants** [apply here](https://docs.google.com/forms/d/e/1FAIpQLSetcOWe18KQ2E2CkrlEclZ0jkUypw5N5iX1erVcF8TJJxizmQ/viewform). Community grants are intended for community members with long-term (1+ year) commitment to hosting meetups or workshops. To host a single event, visit the [issues section of this repo](https://github.com/w3f/Web3-collaboration/labels/Meetup) to find collaborators in your city. For blog posts and videos please view the [open bounties](https://github.com/w3f/Web3-collaboration/labels/Bounty).

Primarily, we are interested in projects that can be completed in 3 months or less. It is possible that further funding can occur, but we prefer projects to be smaller in nature and hence a more manageable risk. With Polkadot genesis approaching, we would like to have many projects funded and delivered in advance.

## Guidelines
The funding maximum for grants is $100,000 per project. Teams shouldn’t seek to cover 100% of their early-stage funding via W3F Grants alone.

Any project requesting :
* **$30k or less** will receive approval the fastest.
* **$31 - 100k** will need to wait longer for a decision.

Teams can apply for grants more than once, but they need to complete the previous project (as described in their application) before receiving additional funds. 

## Licensing
In order to successfully receive grant funding for your application it is necessary for the project to have **open source** code. We prefer to use Apache 2.0 but it is also fine to use the GNU GPL v3 license.

## Documentation
To ensure ease-of-use we require all projects to create documentation that explains how their project works. For example, creating a tutorial will help new users to understand how to use the product. Video is also a good way to demonstrate how something works; however, written documentation is a minimum requirement for funding.

## Areas of interest
The Web3 Foundation is interested in providing grants in the different areas of interest shown below. If any of these topics are of interest to you then please make a speculative application and request funding for your project. Our focus is to support projects building around **Substrate** or **Polkadot**.

For projects related to Ethereum, please apply for funding through [ECF](https://ecf.network/), which Web3 Foundation is a founding contributor of. The Web3 Foundation's commitment to Ethereum includes the funding we have given to both ECF and Eth Prize.

* **Software Development**
  * Development and deployment tooling
    * IDEs
    * Dependency management
    * Testing frameworks
    * Scalable cluster
    * Tools for easy deployment
    * Parachain development kits
  * New languages and libraries
    * Targeting deterministic Wasm
  * New chains
    * Interesting new blockchains that can act as parachains
      * Chains with succinct state transition proofs (i.e. zk-SNARKs or zk-STARKs based)
      * Application specific parachains with a good product story
    * Adaptations of existing blockchains as parachains
  * Protocol integrations
    * Bridges to other blockchains
      * Ethereum
      * Bitcoin
      * Tezos
      * Cosmos
      * Consortium chains
    * Distributed File Storage (e.g. IPFS)
    * Transient P2P messaging (e.g. Whisper)
    * New protocols that are useful for Web3 stack
  * Second layer protocols
    * State channels (runtime modules, dedicated parachains)
    * Key server networks
  * Monitoring
    * Block explorers
    * Node explorers
    * Statistical analytics
  * UI
    * Wallets
    * Libraries
    * Mobile integration
  * ~~Alternative Polkadot Runtime Environment implementation~~ ([Link](https://github.com/w3f/Web3-collaboration/issues/12))
  * Hardware wallet integration / HSMs
    * Users, validators and collators
  * Polkadot Runtime Modules and corresponding UIs
    * Governance
    * Interoperability
    * Stable coins
    * Oracles
    * Identity
    * General app modules, see [Ethereum paper](https://github.com/ethereum/wiki/wiki/White-Paper#applications) for inspiration
  * Benchmarking tools
  * Core implementation testing tools
* **Education and Documentation**
  * Software Documentation
  * Technical education material
    * Courses
    * Tutorials
    * Guides
* **Research**
  * Benchmarking
  * New primitives
    * Technical and economical
  * Analysis of existing protocols and implementations
  * Security testing
* **Community Development**
  * Meetups (check out our [meetup kit](https://github.com/w3f/Web3-collaboration/blob/master/meetups.md) with how-tos and materials)
  * Workshops (e.g. setting up a Polkadot node or writing a Substrate Runtime Module)
  
## Who are we interested in?
  We provide funding to the aforementioned areas of interest to the following parties:

* Individuals
  * Developers, anyone in the community
* Companies/Teams
  * Established teams with a track record
* Researchers
  * Universities/Professors
  
## Process
The grant application can be seen as a 5-step process. Below is an outline of these 5 steps.
  
1. **Communication**
   * See the list or our [Areas of Interest](https://github.com/w3f/Web3-collaboration/blob/master/grants/grants.md#areas-of-interest).
   * If your idea isn&rsquo;t listed, but you think it&rsquo;s cool, you can send us an email or get in touch via Riot.
1. **Application**
   * Applications should be made via a pull request into this repo. We appreciate that not all teams will want to make the financial details public, so there is a Google Form to collect such information. Bare in mind that we are looking for projects with timeframes of less than 3 months.
   * Example application: [Application](https://github.com/w3f/Web3-collaboration/pull/49/files), [Pull Request](https://github.com/w3f/Web3-collaboration/pull/49)
   * Steps for applying: 
     1. We would like **all** teams to start by adding a few details to one of our grant applications forms ([development](https://docs.google.com/forms/d/e/1FAIpQLSfMfjiRmDQDRk-4OhNASM6BAKii7rz_B1jWtbCPkUh6N7M2ww/viewform), [community](https://docs.google.com/forms/d/e/1FAIpQLSetcOWe18KQ2E2CkrlEclZ0jkUypw5N5iX1erVcF8TJJxizmQ/viewform)). This makes it easy for us to manage all applications in one place. Afterwards, please continue to fill out the appropriate GitHub templates.
        * This Google Form also allows teams to send any private financial information to supplement their public application, or for teams to make a fully private application. Note that priority will be given to public applications.
     1. For public applications, with or without public financial information, the next step is to fork this repository.
     1. In the newly created fork, create a copy of the **application template** ([Link](https://github.com/w3f/Web3-collaboration/blob/master/grants/grant_application_template.md)), and make sure to add it to the [Speculative](https://github.com/w3f/Web3-collaboration/tree/master/grants/speculative) sub-folder. Most applications will be into the speculative folder, in the few cases where we have issued an RfP then the response will be into the [Targeted](https://github.com/w3f/Web3-collaboration/tree/master/grants/targeted) sub-folder.
     1. Label the file as "project_name.md".
     1. Fill out the template with the details of your project.
     1. Once you have filled out the template, and are happy that it is complete, click on "create new pull request".
     1. The body of the pull request will show a template that requests an abstract of the project and the completion of a checklist. Please complete as appropriate. The **pull request template** can be viewed here: [Link](https://github.com/w3f/Web3-collaboration/blob/master/.github/PULL_REQUEST_TEMPLATE.md)
   * Please take care to include all necessary information!
1. **Review**
   * W3F will review the applications received and determine if more information is required and potentially schedule a call with the team.
1. **Decision**
   * W3F will notify the applicants of whether their proposal has been accepted for grant funding or not.
   * If a team is successful, there will be further conversation required to figure out specific details around timelines and payment schedules.
1. **Follow up**
   * Once progress has started, W3F will want to have follow up conversations to see how the project is developing.