# DeepBrain Chain

This application is (select one):

- [x] Speculative (use this by default)
- [ ] an RFP response

This application is (select one):

- [ ] Public (fully)
- [x] Public with private finances
Speculative

## Project Description

DeepBrain Chains' aim has always been to deliver a decentralized cloud compute network for AI development (note that AI development is the focus and does not mean the compute can not be used for other purposes). Currently, this core feature is already available for use. However it still requires further integration within the blockchain framework to fulfill it's full purpose and functionality.

Our goals for this project are outlined within [Phase 1](#phase-1). However the extent of our plans extend further than the first phase and as such, while this application only targets our initial phase, we will still provide details of our future developments outside of our first application.  

 [Phase 1](#phase-1) -
The aim of our project as a whole is to switch from the current NEP-5 chain to a native substrate token with decentralized governance. Develop a base service within the Substrate/Polkadot ecosystem to provide resources as a whole, as well as our product to end users.

 [Phase 2](#phase-2) -
Expand on initial infrastructure to develop easy to understand documentation for utilization of DBC services to build further applications within the ecosystem. Outline Polkadot parachain connectivity.

DeepBrain Chain will be good for the ecosystem as it provides a platform for decentralized compute, something that has dramatically reduced the costs when compared with centralized cloud services. This has large potential for any number of reasons. One of the more specific purposes being backup services to any chains that require it. New features could be implemented and expanded on by developers within the Substrate/Polkadot ecosystem, including other successful grantees.

Streamlined services for developers within the ecosystem, would mean less time working with third party platforms and instead could utilize a service directly provided through Substrate/Polkadot, with better support and documentation for their needs.

Completing this project directly falls in line with our teams needs both in the short and long term. It's just not something that is feasible within the NEP-5 ecosystem. We've seen great interest surrounding Susbstrate/Polkadot and believe that becoming early adopters of it's development could provide significant improvements in our goal of decentralizing the governance of our utility token.

## Team Member

DeepBrain Chain consists of the following two teams:

- DeepBrain Chain Core Team

  - Feng He, CEO
  - Chuangfeng Li, CMO
  - Zhou Yu, Lead Market and Partner Development
  - Johnny Ma, Director of Sales
  - Kuang Jian Min, Dev R&D
  - Jeason Y, Dev R&D
  - Joya Lin, Assistant/ Operations Contract
  - Haisong Gu, VisionX CEO, AI implementation advisor
  - Jenny Wu, Financial Officer

- DeepBrain Chain Community Team

  - Rhyan, Project Organizer - Team Leader
  - Luke Penrod, Lead Developer & Owner of Deep In Thought, LLC
  - Jack Seaton, Front-end Developer
  - Sehab Veljacic, Software Engineer & Owner of [Webenology, LLC](https://www.linkedin.com/company/webenology-llc?trk=public_profile_experience-item_result-card_subtitle-click)

## Team Website

- DeepBrain Chain Core Team
  - [https://www.deepbrainchain.org/](https://www.deepbrainchain.org/) (Informational/ Chinese users. Servers in China)
  - [https://www.dbchain.ai/](https://www.dbchain.ai/) (Chinese product services)
- DeepBrain Chain Community Team
  - [https://dbc.team/](https://dbc.team/) (Informational, will host governance/staking and portal to western products.)

## Team's Experience

- The DeepBrain Chain core team hold a vast amount of prior experience within the early days of AI in China. Including the development and marketing of Smart 360 voice assistant which gained more than 17 million users.
- Outlined research and development for decentralized cloud service platform. Have already released MVP August 2018. With our core Chinese platform already beginning to gain traction with developers.
- Launched API and website for cloud providers to copy, already in use by universities within China.
  - Shanghai Jiao Tong University, University of Chinese Academy of Sciences, Institute of Electrics, Chinese Academy of Sciences, University of Electronic Science and Technology of China, Hangzhou Dianzi University, Liaoning Technical University, Ocean University of China, Athlone Institute of Technology, Fuzhou University and more.
- One of the first AI projects launched, global marketing at various conferences within AI / Cloud computing and blockchain.

## Team Code Repos

- Community Team: <https://github.com/dbc-community>
- Core Team: <https://github.com/DeepBrainChain>
- Luke Penrod: <https://github.com/DeepInThought>
- Sehab Veljacic: <https://github.com/abivelj>

## Team LinkedIn Profiles

- Feng He: <https://www.linkedin.com/in/yong-he-2a3a5614b/>
- Joya Lin: <https://www.linkedin.com/in/joya-lin/>
- Haisong Gu: <https://www.linkedin.com/in/haisong-gu-17296929/>
- Chuangfeng Li: <https://www.linkedin.com/in/chuanfeng-li-23b846152/>
- Jenny Wu: [https://www.linkedin.com/in/%E6%8B%A5%E7%8F%8D-%E6%AD%A6-317b5210a/](https://www.linkedin.com/in/拥珍-武-317b5210a/)
- Jeason Y: <https://www.linkedin.com/in/jeason-y-383952154/>
- Rhyan Cook: <https://www.linkedin.com/in/rhyan-cook-b90739145/>
- Luke Penrod: <https://www.linkedin.com/in/luke-penrod-deepinthought>
- Sehab Veljacic: <https://www.linkedin.com/in/sehabveljacic>

## Development Roadmap

We have chosen to use [GNU General Public License v3.0](https://choosealicense.com/licenses/gpl-3.0/) as our preferred license, as Substrate already utilizes this.

## Phase 1

- **Milestone 1 — Core focus on infrastructure setup — 1 month**
  - [ ] Our first major objective is to successfully launch the DeepBrain Chain Mainchain which is constructed from the Substrate blockchain framework.
    * The basic functions of this chain will be released in Milestone 1, simply as groundwork to the Milestone 2 expansion. 
    - [ ] Treasury
    - [ ] Governance
    - [ ] Articles of this process will be documented for future projects looking to migrate to a Substrate/Polkadot blockchain.  We will be focused on moving away from the [NEO](https://neo.org/) platform ([NEP-5 Token](https://docs.neo.org/tutorial/en-us/9-smartContract/What_is_nep5.html)).  At a later date documents on migrating from [Ethereum](https://ethereum.org/) ([ERC-20 Token Standard](https://eips.ethereum.org/EIPS/eip-20)) to the DeepBrain Chain Mainchain will be produced too. 
     * The [VisionX](https://www.visionx.org/) project, which is an incubation from the DeepBrain Chain foundation, is currently using an ERC-20 token.  The date on the latter is undetermined and probably out of this scope of these drafted milestones.
    
    - [ ] We will provide docker images, docker-compose and helm charts to execute nodes and ease the development process going forward.  Also, any custom shell or PowerShell scripts produced will be made readily available.  Most of these are already constructed and will be accessible to the general public soon.
  - [ ] Deploy a native Substrate or ERC-20 based token, via [Ink!](https://substrate.dev/docs/en/ecosystem/contracts/ink), as an integration method for end-users and exchanges to swap new tokens over.
      - [ ] [Subkey](https://substrate.dev/docs/en/ecosystem/subkey) with `--network dbc-mainchain` to create wallets via cli.
      - [ ] Web wallet that creates accounts on the mainchain.
      - [ ] JSON-RPC access to create and interact with wallets.
      - [ ] A runtime module that will save to the chain itself.  This will record a NEP-5 address inputed by end-users to IPFS on the chain, with the newly created Substrate based wallet address.  This will happen after the NEP-5 token has been verified by sending a randomized amount to an issued wallet address.
  - [ ] Complete a successful token swap of the DBC token for the foundation, mining and teams pre-allocated budgets already set forth.
  - [ ] Open token swap to the general public via the DeepBrain Chain website.
- [ ] Deliver a guide on usage, which will include instructions on how to  compile, download and run the code successfully.  Including deploying the chain, transferring and testing tokens, swapping current tokens.
  
- **Milestone 2 — Core focus on community integration — 1 month**
  - [ ] We will build a custom runtime module, that will serve as a supernode, which is a collective of at least 9 staked nodes with a minimum of 20 million DBC Tokens and a max stake of 50 million on each node. (This can be increased when all community nodes, excluding dev/team, hit their cap and once proposal has been passed by supernodes) - this will not be accessible publicly until Milestone 3. 
  * Node types:
    * 1 x community low stakes node (no minimum stake, max 500k stake) 
    * 1 x team/community dev node (only can be staked by community devs and team) 
    * 7 x standard community nodes (can be hosted via community site, or hosted privately if verification/KYC/proof of intent and capability all checks out)
        * Minimum individual stake: 1m
        * Max stake: 12.5m (25% initial total node cap)
    
    - [ ] Staking Rewards
  - [ ] Launch a beta Governance dashboard for public testing with a native Substrate token.  Create base template for use by any project to utilize going forward.
      The dashboard is a web application for decentralized collaboration and governance. 
    - [ ] Proposal submission for use of treasury tokens, change of core mechanics such as chain fees, reward rates, supernode max caps etc.
    - [ ] Proposals will include submission criteria and outline expected targets of each goal. Comment section under each proposal for feedback and direct discussions. 
    - [ ] Live chat and forum for discussion of proposals and project. 
    - [ ] Governance - voting deadlines for each submitted proposal
  - [ ] Expand on governance features within staking ecosystem to ensure complete automation of network from outside attacks.
  - [ ] Benchmarking tools for overall block performance and node election via web application. 
      - [ ] Integrated node election within web dashboard
      - [ ] Telemetry integration for node performance to gauge block production, uptime, number of votes cast per each node/node activity. 
          - Users should be able to access this dashboard to elect and stake on community nodes. Telemetry should provide users information on node activity, such as which nodes put forth the most proposals, which nodes have the most individual users, which nodes are the most active with voting. 
  - [ ] Deliver a guide on usage, which will include instructions on how to  compile, download and run the code successfully. 
    - [ ] This will include a custom Web3 account with dev privileges. Community proposals will be active at this time and you can fully take part in live governance. 
  
- **Milestone 3 — Core focus on product integration — 1 month**
  - [ ] Launch beta dashboard for AI developers to utilize compute through western website (via [dbc.team](https://dbc.team) portal)
      - [ ] Main feature of this dashboard will initially be for AI developers to rent compute directly from suppliers using the DBC API.
      - [ ] Filter and search function to find the best node (geolocation, stats, reputation, hardware specifications)
      - [ ] Wallet to store tokens and make payments for compute. 
  - [ ] Smart contract development for renting via DBC cloud compute API (replacing NEP5 Payment streams)
      - [ ] Smart contract for automatic payment from consumer to provider. We will therefore not act as a middle man in the payment structure. Tokens will go directly from User A to Provider A. 
      - [ ] Contracts will determine refund schedules for nodes that do not supply exact hours of use/go off-line. 
  - [ ] Introduce public supernodes into the project.  The governance will be used for node election usage.
  - [ ] Launch incentive service for Substrate/Polkadot developers to build out DApps (both AI specific or non specific). Ideally to use DBC network for the benefit of Substrate/Polkadot or their project as a whole.
  - [ ] Deliver a guide on usage, which will include instructions on how to  compile, download and run the code successfully.

## Phase 2 - Long term

After successful deployment and completion of Phase 1, we plan to continue development of the network and it's accessibility regardless of any future grants or funding.
    
This will include research and development of connecting with Polkadot services.

Developing dashboard with DBC API for Substrate/Polkadot developers to utilize DBC compute or AI services.

Further incentive programs for Substrate/Polkadot developers to get started with the network through DBC.

The main focus after Phase 1 will still be:

- The development of our English cloud product, including a full release of the AI developer dashboard. 

- The security and smooth operation of community governance, voting/proposal applications to ensure no bad actors can manipulate the network.

However many of these goals also fit within smaller development targets within Substrate/Polkadot field for integration.

Long term targets include overall connectivity within the Substrate/Polkadot ecosystem so that DBC may be considered a core tool or infrastructure utility for newer projects to rely on.

### Additional information

What work has been done so far?

- Substrate module node setup, node web explorer, staking module testing.
- Decentralized AI cloud training network and client already developed using NEP-5 as payment service.
- API plug-in and [dbchain.ai](https://dbchain.ai) dashboard means anyone can set up a service for utilizing the cloud compute. (with more than 20 already running, including universities)
- Community governance group with more than 120 members ready to participate on native substrate governance.

### Have you applied for other grants so far?

- [ ] Yes
- [x] No

### Are there any projects similar to yours?

In terms of cloud compute, there are Golem, Iexec, Sonm and perhaps others. However none targeted the AI field from the beginning. With most offering services for cloud mining, DApps or video rendering. They now begin to move in to the machine learning field as they see the vast potential.

### Other noteworthy mentions

- Signed strategic cooperation and ongoing collaboration with ASUS and Qinghai Mobile IDC Oct 2019 regarding crypto mining and AI field.

- More than 1500 users on our Chinese [dbchain.ai](https://www.dbchain.ai) platform within 2 months of launch
- DeepBrain Chain Advised by Robert Bosch venture capital and GOBI investment.