# Substrate Explorer

## Project Overview
A suitable substrate Explorer, with strong expansibility, easy construction, and easy interface

![playground](https://s1.ax1x.com/2020/08/30/dbzQ0I.png)

The features to be implemented:
  * Connect substrate nodes and synchronize data in real time,Persist data with PostgreSQL(or Mysql).
  * Establish associations between the underlying data,and provides the GraphQL Query query interface.
  * Provides a WebSocket interface to the outside world based on GraphQL Subscription as a middleware.
  * Set up the module table, realize the optimization query of staking, treasury, council and other data
  
## Project Details

This project will be divided into two parts, one is the service of data import and data query, and the other is the front end of displaying data to users.

* Explorer Service API
  - Project [substrate-explorer-api](!https://github.com/jyopen/substrate-explorer-api)    
  - Technology stack
    - TypeScript
    - Node
    - GraphQL(apollo-server)
    - Sequelize
    - PostgreSQL (or Mysql)
    - Express(or Koa)
    - @polkadot/api   
    
    
The basic functionality of this section is complete, importing basic blocks, transactions, events, logs, metadata, and completing the GraphQL interface.
Later, the data of the modules such as account, staking, treasury, council and other sections will be collected and constructed separately.

* Explorer Front
  - Project [substrate-explorer-front](!https://github.com/jyopen/substrate-explorer-front)    
  - Technology stack
     - Vue
     - TypeScript
     - apollo-client
     
This part is still in its infancy. The plan is to develop single or list queries for blocks, transactions, events, logs, and so on along the chain, and to design pages for accounts, staking, treasury, council and other sections.

     
## Ecosystem Fit
 
We project is similar to the two projects [subscan](!https://www.subscan.io/), [polkascan](!https://polkascan.io)
However, these two project node request clients are developed by themselves, lacking documentation and poor scalability.我们将用使用已有的 @polkadot/api 客户端进行开发，它具有比较好理解的api还有良好的文档。
We will be working with the existing @polkadot/ API client, which has a well understood API and is well documented.
And the server USES the GraphQL framework for its external interface, allowing anyone to assemble their own data at will.

## Team members
- **Guoquan Xie** - Founder, Full-Stack Developer.
- **Yinjie Cai** - Product Designer.	

## Team Website	

Content design...
[https://jyopen.com](https://jyopen.com)

## Legal Structure 
Shanghai Jieyuan Technology Co., LTD, China.

## Team's experience

**Guoquan Xie**   
Full stack developers,mainly responsible for the code development of this project. Have rich development experience in Node, Web and APP development. The last two years in the block chain direction on the special study,
Researched Substrate, Ethereum and Cardano, and developed several wallets and browsers based on them.
**Yinjie Cai**  
Excellent product designer with rich experience in design, responsible for page function design.

## Team Code Repos
* [https://github.com/jyopen/substrate-explorer-api](!https://github.com/jyopen/substrate-explorer-api)
* [https://github.com/jyopen/substrate-explorer-front](!https://github.com/jyopen/substrate-explorer-front)

## Team LinkedIn Profiles

## Development Roadmap

### Milestone 1 — Explorer Service API — 1 month — $10,000
* We will develop a program that can import the substrate's historical data, and provide a query interface to that data.
* Unit tests are added to ensure the stability and robustness of the program.
* Add documentation to teach users how to use this project to import data from chains developed within the Substrate framework.
### Milestone 2 — Explorer Client — 1 month — $10,000
* Design of relevant interface.
* Encapsulate the interface client,as simple and easy to use as `api.block.one.query({number:8888}).then(console.log)`。
* The interface requests the documentation for the tool.
* Front-end project development.
### Milestone 3 — Bug Fixing & Documentation — 1 month — $10,000
* Test the support of Polkadot, Kusama, etc.
* Get the Docker image ready for deployment.
* Server erection, explorer website construction.
* Optimization of related documents.
## Future Plans
The polkadot ecology is very optimistic, will continue to optimize the project.
There was a Demo that developed a wallet before [substrateWallet](!https://github.com/puti94/substrate-wallet),
We will continue to develop it if there is an opportunity.


## Additional Information

* What work has been done so far?

Previously, We have opened some projects related to the ecosystem of substrate in [https://github.com/jyopen](!https://github.com/jyopen),
But because of the energy and financial problems did not continue, I hope to get a grant can be full-time to do.

* Have you applied for other grants so far?
No.
* Are there are any teams who have already contributed (financially) to the project?
No.
