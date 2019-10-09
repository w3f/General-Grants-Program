##
# Polkalert

**Project Description**

If this application is for a particular grant programme then please indicate that in the first line of this section.

- Please provide a brief description of the project here. This is likely more important for speculative applications, but also worth providing some description here of the team&#39;s intent with the project.

  - We are building a monitoring tool which alerts validators and their nominators if some malicious staking (in)activity occured. By decreasing their reaction time for fix or replacing their funds, Polkalert is an essential tool for every responsible validator and nominator.

- An indication of why this project is good for the ecosystem.
  - Polkalert is making validators field more transparent and secure for themselves and their nominators. By monitoring every validator and their track record, nominator can easily pick the most reliable validator and validators don&#39;t need to make their custom monitor themselves.
- An indication of how you will integrate this project into Substrate / Polkadot.
  - part of Portal [https://github.com/polkadot-js/apps](https://github.com/polkadot-js/apps) or standalone app
  - (optional) Lib for the node package (turn on, if the validation is activated), this could be working for every Substrate based nodes.
  - (optional) Lib for the wallets and nominators
- An indication of why your team is interested in creating this project.
  - Before we jump deeper for a more advanced problems, we want to provide some value for the initial community, help to stabilize early days of network, and fully understand roles of all agents in network
  - we&#39;d like to extend features for validators either within this project or other projects, as we are about to run validator node on Edgeware parachain

**Team members**

- Name of team leader
  - Peter Kris
- Names of team members
  - Gleb Urvanov - Backend
    - PhD dropout from Nuclear university Moscow - track record of mobile OS engineering, machine learning, smart contracts
  - Peter Kris - project management
    - generalist, full stack dev, crypto long timer since early days, leader of blockunison.com
  - Jakub Gregus - consulting product
    - industry researcher with wide product knowledge of crypto landscape
  - Andrej Mikulicka - Frontend
    - specialist React and Vue.js coder, quick iterator for prototyping

**Team Website**

 [www.blockunison.com](http://www.blockunison.com)

**Legal Structure**

Please provide name and registered address of the legal entity executing the project. These details can also be shared privately via our Google Form.

**Team&#39;s experience**

We&#39;re active engineers since beginning of Ethereum, developing Solidity smart contracts and adjacent backend / frontend software. We&#39;ve gathered quite diverse experience over the time and we would like to get more hands-on in Polkadot ecosystem and Rust eventually.

**Some of our projects:**

Etherem smart contract lottery platform (team of 8 people)

[www.playloteo.com](http://www.playloteo.com)

General Bytes ATM integration with DECENT cryptocurrency (team of 3 people)

[https://github.com/DECENTfoundation/DCore-ATM-integration](https://github.com/DECENTfoundation/DCore-ATM-integration)

Journaling app made for Blockstack (team of 3 people)

[https://www.mindtalk.app/](https://www.mindtalk.app/)

Biotron Android mobile app - ERC20 token rewarding for geo-location (team of 4 people)

[https://play.google.com/store/apps/details?id=io.biotron.app&amp;hl=en](https://play.google.com/store/apps/details?id=io.biotron.app&amp;hl=en)

**Team Github Profiles**

[https://github.com/gleb-urvanov](https://github.com/gleb-urvanov)

[https://github.com/PetoU](https://github.com/PetoU)

[https://github.com/Andkoo](https://github.com/Andkoo)

**Team LinkedIn Profiles**

- [https://www.linkedin.com/in/gleb-urvanov/](https://www.linkedin.com/in/gleb-urvanov/)
- [https://www.linkedin.com/in/peter-kris-a7274054/](https://www.linkedin.com/in/peter-kris-a7274054/)
- [https://www.linkedin.com/in/jakub-gregus-3025018a/](https://www.linkedin.com/in/jakub-gregus-3025018a/)
- [https://www.linkedin.com/in/andrejmikulicka/](https://www.linkedin.com/in/andrejmikulicka/)

**Development Roadmap**

Please add information setting into sufficient detail the following (usually two pages):

- The specifications of the software, delivered over a number of milestones. The detail must be such that after delivery we are able to examine whether the software meets the requirements agreed in the specifications, in order to be able to make any payments to you.

  **Phase 1 - the first ½ of funding - week 2-4:**
  
  (with respective documentation)
  License: Apache 2.0
  React frontend app integrated into polkadot UI/apps will show:
  
    - a) all validators and their stats
        - validator as a block producer of certain blockchain
      - weight
        - whole amount of stake that has been bonded from this validator and from his nominators
      - offline states
        - number of times the node has been caught offline
      - blocks for last 24h
        - numbers of blocks produced by this node
      - Reward comission
        - % of block rewards how much validator takes for his work (and how much nominators will eventually get)
      - sum of penalties
        - number of slashes with sum of stake that has been taken away as punishment
      
  **Phase 2 - the second ½ of funding - week 4-10:**
  
  (with respective documentation)
  License: Apache 2.0
  
    Alerting will be done:
    1. webhook, to allow programmatically any type of alert
    2. setup for external emailing service. User will be prompted while installation to optionally provide his email address
    
    Alerts:
    - a) Alert when some malicious validator activity occurred
      - double signing notification
        - when one validator produce 2 blocks with the same validator key
      - try to detect double spend attempts notification
        - where it’s possible to check
      - downtime notification
        - when my local node is not online
      - restart your node notification
        -  when node is offline for a particular time, send notification via webhook to allow you to restart the node 
       
       **Phase 1 and Phase 2 can be tested by connecting polkadot/apps interface to some node and see new app Polkalert there which shows real-time data**
       
  **Phase 3 (optional):**
    - choose your validator similar like in getstaker.com

**Architecture**

- Local running substrate node (Alexander testnet)

- React frontend (as part of polkadot/apps)

- Node.js backend application running on the same server as local substrate node

- external Node.js backend application - pings your own node automatically, to find out that your node is offline and send you an email about it (no manual setup required from node owner, automatic when local backend application set up)

- all data will be fetched through Polkadot JS API on Alexander testnet
https://polkadot.js.org/api/api/#api-selection
if not sufficient, then lower level RPC calls will be made


**Time schedule**

  - Phase 1:
    - 60 MDs
  - Phase 2:
    - 60 MDs
  - Phase 3 (optional):
    - To be determined from analysis after Phase 1 and Phase 2
- The required grant per milestone and the total amount requested. Grants can be in one of the fiat currencies CHF, EUR or USD or in DOTs or a combination of fiat and DOTs. Please reach out to grants@web3.foundation for discussing what amount in fiat and DOTs would be appropriate.
  - DOTs in equivalent of 40 000 EUR
- Note that we now have a preference to collect the financial information via our Google Form, or via a Google Document (paste the link into our Google Form).

Also helpful to know: what are the team&#39;s long-term plans and intentions after the grant has been awarded?

  - in the near future, we want to do more low-level engineering as we have strong math backgrounds, but before that we want to take lighter high level application as first peek. Rust is a must
  
**Licensing**

Apache 2.0 software license

**Additional Information**

Any additional information that you think is relevant to this application.

These bullet points won&#39;t be applicable to all projects. Some of the information may have already been included in the description section, if so then no need to state it again.

- What work has been done so far?
  - running Alexander and Kusama node
  - fetching the list of validators from node
- Are there are any teams who have already contributed (financially) to the project?
  - no
- Have you applied for other grants so far?
  - no
- Are there any other projects similar to yours?
  - not aware of any
- How is your project different?
  - it&#39;s a base for node management and automation of preventative actions
