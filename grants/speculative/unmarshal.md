# General Grant Proposal for Unmarshal

* **Project:** Unmarshal

## Project Overview :page_facing_up:
 Unmarshal: Chain agnostic DeFi Data Protocol that Indexes data from mutiple chains and extracts the information required by clients and serves the data in multiple formats.

### Overview

- Unmarshal is a Decentralized network of blockchain data indexers and transforming tools to power your DeFi applications on any chain.
  We are starting Polkadot, Stafi and Edgeware.
- Unmarshal will index the entire blockchain for Polkadot, Stafi and Edgeware and more other chains and provide data in the form of
    * Rich API
    * Push Notifications
    * Websockets

 - Ecosystem
     * Rich APIs
     * Notification Engine
     * Defi state Engine
     * Profit & Loss
     * Tax Engine
     * Insights and analytics

- Defi Applications can focus on their Business & Application logic by leaving on-chain data access requirements to us.
- In our consulting days, we came across lot of Defi applications that need the on-chain data and were finding it hard.
to find any reliable source. one, there are not many providers in this space. second, there are no providers that provide customised data in required format.

### Project Details

Unmarshal is MVP includes a single node that serves
    * APIs for wallet balances, transactions, Defi protocol positions.
    * Notification Engine: Clients can subscribe to notification engine.
    * Defi Protocol Positions
    * Profit and Loss calculator
    * Tax Engine
    * Analytics and Insights

* Overall functionality
    * https://unmarshal.io/#about-us
    * https://unmarshal.io/#features

* Tech:
    * Golang monorepo with micro service architecture.
    * MySql/RocksDB for Cold storage
    * Redis for caching and hot storage
    * Graphql, GRPC and REST APIs
    * Elastic search for dashboards
    * Kafka for internal/external data streaming


### Ecosystem Fit
* While there are few products such as The graph, Covalent, BitQuery etc. We differ from them as follow.
    * Few of them support just one or few chains. No support for polkadot from majority of them. We will be multichain start from Polkadot ecosystem.
    * No support for multi format data. They just provide APIs. Web3 needs beyond that, and Unmarshal is dedicated towards it.
    * Most of them provide raw data. Unmarshal's APIs include rich data with token rate, decoded transactions, logos etc.
    * Most of them are centralized providers, Unmarshal will be a network of Indexers and data curators.
    * Support for Notifications. Unmarshal is the first data provider to provide data inform of notifications.
    * Support for websockets. Unmarshal will be the first in class.

## Team :busts_in_silhouette:
### Team members
#### Manohara K.
* Founder and CEO
* Grab, Gojek, Kernel Fellow
* https://www.linkedin.com/in/manoharak/


#### Nishanth Sankar Ram
* Operations & Product
* GAVS, Impartus
* https://www.linkedin.com/in/nishanth-sankarram/


#### H. G. Shiva Kumar
* Engineering
* Navi, Gojek
* https://www.linkedin.com/in/shivhg/


#### Yogesh Talurmath
* Sales & Marketing
* Imanage, Infinity research
* https://www.linkedin.com/in/yogeshtm/

#### Santhosh K. S.
* Engineering
* LTI
* https://www.linkedin.com/in/santhosh-k-s-875a96163/

### Team Website
* https://unmarshal.io

### Legal Structure
EUCRYPT GLOBAL PTE. LTD, 3 FRASER STREET, #05-25, DUO TOWER, SINGAPORE 189352

### Team's experience
* Manohara K(Kernel Fellow):
    * Manohara has 7years of software development experience and 2 years of Web3 development.
    * Worked as Engineer owner at major ride hailing platforms such as Grab, Gojek.
    * Built complex projects like Advance booking, Cancellation Policy and arrear collection

* Shivakumar
    * Shivakumar has 7 years of software development experience and 1 year of web3

* Nishanth Sankar Ram:
    * Nishanth has 13 years of IT experience in various roles such as product owner, Business Analyst, etc.
* Yogesh Talurmath:
    * Yogesh has 6 years of Business development experience

### Team Code Repos
* https://github.com/eucrypt
* https://github.com/manoharaksh
* https://github.com/shivhg
* https://github.com/manoharkshetty

### Team LinkedIn Profiles
* https://www.linkedin.com/in/manoharak
* https://www.linkedin.com/in/shivhg/
* https://www.linkedin.com/in/yogeshtm/
* https://www.linkedin.com/in/nishanth-sankarram/
* https://www.linkedin.com/in/santhosh-k-s-875a96163/

## Development Roadmap :nut_and_bolt:
### Overview
* **Total Estimated Duration:** 4 months
* **Full-time equivalent (FTE):**  5
* **Total Costs:** $72,000

### Milestone 1 - Decoding API layer for Polkadot, stafi, Edgeware.
* **Estimated Duration:** 4 weeks
* **FTE:**  3
* **Costs:** $18,000
* Deliverables:
    * Setup Unmarshal Project, Deployment Pipeline, CI-CD
    * Integrate with Subscan for Polkadot
    * Develop decoder to decode blockchain data
    * Integrate with Price feed(CoinGecko, CoinMarketPlace)
    * Cost includes $3,000 infrastructure cost

### Milestone 2 Indexing and Notification support
* **Estimated Duration:** 4 weeks
* **FTE:**  3
* **Costs:** $18,000
* Deliverables:
    * Index polkadot to remove dependency
    * Develop generic Indexing framework to index multiple chain in future
    * Notifications support for all major chains
    * Support for websockets and GraphQL
    * Cost includes $3,000 infrastructure cost


### Milestone 3 Defi protocol positions
* **Estimated Duration:** 4 weeks
* **FTE:**  3
* **Costs:** $18,000
* Deliverables:
    * Index stafi, edgeware and any other major chain that client require
    * Defi Protocol tracking support for protocols such as polkaswap, Mantra, Akropolis.
    * Framework for automated Defi protocol Indexing
    * Cost includes $3,000 infrastructure cost

### Milestone 4 P&L, Tax, Analytics
* **Estimated Duration:** 4 weeks
* **FTE:**  3
* **Costs:** $18,000
* Deliverables:
    * Profit & Loss engine for all 3 protocols
    * Tax engine to provide statements for taxable events
    * Support for Insights and Analytics
    * Cost includes $3,000 infrastructure cost


### Community engagement
Manohara, our CEO is a passionate blogger who likes to write about his learning and experiences.
Some of his blogs can be found at https://medium.com/@manoharshetty96

## Future Plans
Unmarshal Network: A decentralized network consisting of Blockchain Indexer, Data curators, Validators, and Consumers.
We have to remove the centralized entity which can become a single point of failure.
We believe decentralized network can get handle the increasing load with much needed stability and reliability.

## Following will be the network roles

####  Defi applications:
* Access data from any blockchains in any format to power your applications. Unmarshal’s data is rich, detailed, decoded, and Informative.
* Enjoy the stability and reliability of a decentralized network and yet access rich data without writing a single line of data extraction code.

####  Node operators:
* Run the indexer node for any supported blockchain to earn incentives. No need to implement complex soft contracts to run the node.
* Implement support for new blockchains and change requests from network users to earn rewards.
* Build insights and analytic dashboards using unmarshal data and host it in Unmarshal’s network to earn fees from users.

####  Data Extractors:
* Extract information out of Indexed blockchain data.
* Implement client's custom requests

####  Validators:
* Become node validators to validate the accuracy, response time, and health of nodes to earn incentives.
* Earn incentives by delegating the staking power to indexers to run the unmarshal nodes.


## Additional Information :heavy_plus_sign:
#### What work has been done so far?
* We have start building basic API layer with the support of subscan APIs.
    * https://api.unmarshal.io/v1/polkadot/address/13GkDCmf2pxLW1mDCTkSezQF541Ksy6MsZfAEhw5vfTdPsxE/assets?auth_key=VGVtcEtleQ==
    * https://api.unmarshal.io/v1/stafi/address/34Ya35ZRSjKiMkACU1kKBgyeA3ftmrR1jBMTR8BVd9chK4nD/assets?auth_key=VGVtcEtleQ==
    * https://api.unmarshal.io/v1/edgeware/address/jUFFyyPNDehrfs4MkmrTMJKDunYQS3EnGz1BSCy9Ppeecnd/assets?auth_key=VGVtcEtleQ==

- Are there are any teams who have already contributed (financially) to the project?
    * We have funded the project so far using our savings.

- Have you applied for other grants so far?
    * No
