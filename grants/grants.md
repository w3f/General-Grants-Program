# Web3 Foundation Grants

As part of our commitment to promoting the Web3 ecosystem, we offer a comprehensive grants program focused on funding software development, research, technical education and community engagement efforts related to **Polkadot** and **Substrate**. 

## Process
If you are considering applying for a grant, please follow the process below.
  
1. **Determine the scope of your project**
   * Review the appropriate areas of interest:
     * [Areas of interest for technical grants](#areas-of-interest-for-technical-grants)
     * [Areas of interest for community engagement grants](#areas-of-interest-for-community-engagement-grants)
     
     If your idea isn&rsquo;t listed, but you think it&rsquo;s cool, you can send us an [email](mailto:grants@web3.foundation) and tell us about it.
   * Ensure the scope of your project falls within the appropriate guidelines
     * [Guidelines for technical grants](#Guidelines-for-technical-grants)
     * [Guidelines for community engagement grants](#Guidelines-for-community-engagement-grants)
     
   Once you determine that your project falls within the areas of interest and corresponds to the guidelines above, proceed to the next step.
   
1. **Application**

    We recommend checking out the "[How successfully apply](https://medium.com/web3foundation/web3-foundation-grants-wave-two-recipients-16d9b996501d)" section at the end of the Wave 2 grant winners blog post. It gives an indication of what a good roadmap should look like, plus it outlines the criteria of what we look for in an application.
       
    1. Fill out the appropriate Google form for your grant application:
    
        Partially public applications that limit financial information (e.g. funding amount requested) to the Google form are preferred. However, teams are free to make fully public applications as well as fully private applications. 
    
        * [technical grant application](https://docs.google.com/forms/d/e/1FAIpQLSfMfjiRmDQDRk-4OhNASM6BAKii7rz_B1jWtbCPkUh6N7M2ww/viewform)  
       * [community engagement grant application](https://docs.google.com/forms/d/e/1FAIpQLSetcOWe18KQ2E2CkrlEclZ0jkUypw5N5iX1erVcF8TJJxizmQ/viewform)
       
        Teams that chose to make a fully private application are done. Teams that have chosen to make a fully or partially public application should proceed to the next step.
       
    1. Fully or partially public applications should be made via a pull request to this repo by following the steps below.
       1. Fork this repository.
       1. In the newly created fork, create a copy of the [technical grant template](https://github.com/w3f/Web3-collaboration/blob/master/grants/grant_application_template.md) or the [community engagament grant template](https://github.com/w3f/Web3-collaboration/blob/master/grants/grant_application_template_community.md).
           * Most applications should go into the [speculative](https://github.com/w3f/Web3-collaboration/tree/master/grants/speculative) sub-folder.
           * In the few cases where the application is a response to specific RFP then the application should go into the [targeted](https://github.com/w3f/Web3-collaboration/tree/master/grants/targeted) sub-folder.
       1. Label the file as "project_name.md".
       1. Fill out the template with the details of your project.
       1. Once you have completed the application, click on "create new pull request".
       1. The body of the pull request will show a template that requests an abstract of the project and the completion of a checklist. Please complete as appropriate and take care to include all necessary information. The **pull request template** can be viewed [here](https://github.com/w3f/Web3-collaboration/blob/master/.github/PULL_REQUEST_TEMPLATE.md).
       
1. **Review**
   * The W3F will review the applications received, determine if more information is required and potentially schedule a call with the team.
   * Parity Technologies may also assist in the review of some applications.
   
1. **Decision**
   * The W3F will notify the applicants of whether their proposal has been accepted for grant funding or not.
   * If a team is successful, further communication will be required to determine specific details around timelines and payment schedules.
   
1. **Follow up**
   * Once progress has started, the W3F will want to have follow up conversations to see how the project is progressing.

## Guidelines for technical grants
Technical grants are intended to fund:
* software development
* research
* the production of software documentation and technical education material

For more specific information on our funding priorities, please view our [areas of interest section](#areas-of-interest-for-technical-grants) below.

The funding maximum for technical grants is $100,000 per project. Teams shouldn’t seek to cover 100% of their early-stage funding via W3F Grants alone.

Any project requesting :
* **$30k or less** will receive approval the fastest.
* **$31 - 100k** will need to wait longer for a decision.

Teams can apply for grants more than once, but they need to complete the previous project (as described in their application) before receiving additional funds. 

We are primarily interested in projects that can be completed in 3 months or less.

### Licensing
In order to successfully receive grant funding for your application it is necessary for the project to have **open source** code. We prefer Apache 2.0 but the GNU GPL v3 license is also acceptable.

### Documentation
To ensure ease-of-use we require all projects to create documentation that explains how their project works. At a minimum, written documentation is required for funding. Tutorials or videos are also helpful for new users to understand how to use the product.

### Areas of interest for technical grants
The W3F is interested in providing grants within the following areas of interest. If any of these topics are of interest to you then please make a speculative application to request funding for your project. 

* **Software development**
  * Development and deployment tooling
    * IDEs
    * Dependency management
    * Testing frameworks
    * Scalable cluster
    * Tools for easy deployment
    * Parachain development kits
    * Off-chain worker tooling
  * New languages and libraries
    * Targeting deterministic Wasm in Runtime
    * Node API bindings (Besides JS and Java at moment!)
  * New chains
    * Interesting new blockchains that can act as parachains
      * Chains with succinct state transition proofs (i.e. zk-SNARKs or zk-STARKs based)
      * Application specific parachains with a good product story
    * Adaptations of existing blockchains as parachains
  * Protocol integrations
    * Bridges to other blockchains ([Link](https://github.com/w3f/Web3-collaboration/issues/155))
      * Ethereum
      * Bitcoin
      * ZCash
      * Tezos
      * Cosmos
      * Consortium chains
    * Distributed File Storage (e.g. IPFS)
    * ~~Transient P2P messaging (e.g. Whisper)~~
    * New protocols that are useful for Web3 stack
  * Second layer protocols (runtime modules, dedicated parachains)
    * State channels
    * ~~Plasma~~
    * Key server networks
  * Monitoring
    * ~~Block explorers~~
    * Node explorers
    * Statistical analytics
  * UI
    * Wallets (including Metamask-like wallets)
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
* **Research**
  * Benchmarking
  * New primitives
    * Technical and economical
  * Analysis of existing protocols and implementations
  * Security testing
* **Education and documentation**
  * Software Documentation
  * Technical education material
    * Courses
    * Tutorials
    * Guides
    
### Who we are interested in funding

* Individuals
  * Developers, anyone in the community
* Companies/Teams
  * Established teams with a track record
* Researchers
  * Universities/Professors
 
## Guidelines for community engagement grants
Community engagement grants are intended to fund high-quality community engagement efforts such as meetups, workshops and hackathons.

The degree of financial support for each applicant is likely to be within the $3,000 to $10,000 range. The maximum funding for a single grant is $30,000.

### Areas of interest for community engagement grants
Funding is available for any short-term strategy that promotes community engagement. This statement is purposefully vague as we wish to be open to applications that promote community engagement in creative ways. However, we believe the majority of approved applications will be for events such as:

  * Meetups (check out our [meetup kit](https://github.com/w3f/Web3-collaboration/blob/master/meetups.md) with how-to's and materials)
  * Workshops (e.g. setting up a Polkadot node or writing a Substrate Runtime Module)
  * Hackathons
  
If any of these areas are of interest to you then please make a speculative application to request funding for your project. 
  
### Who we are interested in funding
The community engagement program will only consider funding companies and teams with an established track record of successful community engagement work. Grant funding for this category is not available to individuals.
    
