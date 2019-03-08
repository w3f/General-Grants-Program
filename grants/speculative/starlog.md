<img src="https://pact.online/dist/img/starlog_new.png" width="240">

## Project Description
The goal of Starlog is to research and develop an open source solo chain or potential parachain, which stores 
metadata for IPFS as non-fungible tokens as well as unavailability data (Programs: [New chains, Distributed File Storage](https://github.com/w3f/Web3-collaboration/blob/master/grants/grants.md#areas-of-interest)). The metadata will be signed by the uploaders and includes a price, a timestamp, owner(s), information about the uploaded file itself as well as the location/gateway of the initial upload.

Starlog provides, therefore, the following key benefits for IPFS uploads:

- Searchability via human-readable names
- Copyright system for IPFS uploads
- Marketplace for uploaded content
- Electronic identity based on personal IPFS uploads
- Faster initial loading of non-distributed IPFS content

Furthermore, the combination of IPFS as storage/hosting layer and Substrate as immutable database layer 
seems to be a potential scalable and relatively cheap solution for all kinds of distributed applications. 

The project will be based on our prototype [Dweb.page](https://github.com/PACTCare/Dweb.page), which is a Single-Page Application running on 
IPFS and currently using IOTA to store IPFS metadata and logs. Dweb.page was initially created to 
develop a fully distributed, transparent and easy to use file sharing application. During this process,
we encountered multiple issues with the current status of IPFS (e.g., readability of hashes, initial 
distribution time, availability of content, the speed of OrbitDB/IPNS and the setup of a distributed back-end), 
which led to the exploration of potential solutions. Based on IOTA and the Web Crypto API, we were able to 
develop a first concept that allows not only to make IPFS content searchable 
(see https://blog.florence.chat/a-distributed-search-engine-for-the-distributed-web-39c377dc700e) 
but also to develop almost free dapps (see https://blog.florence.chat/tutorial-how-to-build-a-completely-free-dapp-11a4ddf5959c). 
The picture below shows the first integration tests of Starlog into Dweb.page.

<img src="https://pact.online/dist/img/starlog_dweb.PNG" width="320px" alt="Dweb.page + Starlog">

Rather than trying to find one single truth directly on the blockchain (e.g., token-curated registry), 
the idea is to develop a subscription-based system (see image below). This means Publishers store 
immutable metadata and unavailability data on the chain. Consumers can decide which publishers (signatures) 
they trust and follow. In practice, this will be automatically archived by rules hard-coded into the 
interface (e.g., dweb.page). The benefit of the system is the immediate availability of information 
without the requirement of an additional voting system nor a filtering system, which takes individual preferences into account. 

<img src="https://pact.online/dist/img/sbs.png" width="650px" alt="subscription-based system ">

Since a slightly changed file (version) results in a completely new hash on IPFS but still might have the 
same metadata, it makes sense to store references to metadata objects to reduce the overall chain size. 
An off-chain storage of metadata is probably not a solution, because of the initial loading speed. 

We believe that based on Substrate we will be able to improve the current prototype further. On the one 
hand, the combination of non-fungible tokens based on IPFS hashes seems to be a promising solution for 
digital content creators since it offers them a unique opportunity to prove their ownership. On the other 
hand, we believe that using IPFS as the storage layer and Substrate as an application-specific blockchain 
(database/smart contract layer) is one of the most promising setups for future distributed applications, 
which we would like to explore. 

The ecosystem will profit from our research in the form of open source code, the respective documentation, and sharing of our work progress via Medium articles. We expect that the combination of IPFS and Substrate will be interesting for a lot of other Web3 projects. Furthermore, we will try to get additional attention on Hacker News, Reddit, and co. 


## Team members
* David Hawig
* André Fialho

## Team Website	
* https://pact.care
* https://dweb.page/

## Legal Structure 
PACT Care B.V. is a Dutch startup based in Amsterdam.

## Team's experience
The main development will be done by David Hawig. David developed Dweb.page as well as worked on multiple 
distributed ledger and IPFS projects for PACT Care. He also started to work on the Runtime 
Logic for [Starlog](https://github.com/PACTCare/Starlog) as well as the 
[UI integration](https://github.com/PACTCare/Dweb.page/tree/starlog). 

Andre Fialho will support with the background/state-of-the-art research as well 
as writing corresponding documentation, tutorials, and marketing materials.

## Team Code Repos
* https://github.com/PACTCare/Starlog
* https://github.com/PACTCare/Dweb.page/tree/starlog

## Team LinkedIn Profiles
* https://www.linkedin.com/in/david-hawig-206a44b1/
* https://www.linkedin.com/in/andre-s-fialho-baa69413/

## Development Roadmap

### Phase 1 Preliminary research phase (4 weeks, parallel to phase 2): 

Summary: In this phase, we will focus on additional research regarding the runtime and the integration of the subscription-based system. Potential questions are: 
*	How to optimize the storage of metadata to improve the loading as well as reduce the chain size (e.g., ERC-1155 or storing on IPFS)?
*	How to deal with users uploading content illegally?
*	How does a subscription-based system compare to existing solutions like token-curated registry for this use-case?
*	How to trade and value ownership rights without generating just another token? 
*	How to implement a multi-signature/-owner system?

Funding: 6.000 $

Milestones: Medium Idea article

### Phase 2 Development phase (10 weeks): 

Summary: We will further develop and test the existing open source runtime and use Dweb.page as a UI, which handles the subscription-based system according to the use-behavior.

Funding: 18.000 $

Milestones: 
*	Open source runtime
*	Dweb.page integration
*	Substrate runtime tutorial
*	Tutorial on creating a JavaScript UI.  

### Phase 3 Documentation phase (2 weeks):

Summary: We will improve the documentation of the project, write a final medium article about our findings as well as potential next steps and other use-cases for the Substrate framework. 

Funding: 4.000 $

Milestones: 
*	Documentation
*	Medium article including next steps

Starlog is for us a pure research project. We currently don’t have any plans to monetize on the project itself. 
In the long-term, we plan to apply this technology in multiple healthcare related projects. We are open-minded regarding receiving the grant in a combination of fiat and DOTs.    

## Licensing

Dweb.page is currently published under the GNU General Public License v3.0. The project Starlog is published under the MIT License. 

## Additional Information
Starlog is based on our research and development work for our project [Dweb.page](https://github.com/PACTCare/Dweb.page). 
You can read more about it on our [Medium blog](https://blog.florence.chat/). We also already implanted a basic 
[substrate runtime](https://github.com/PACTCare/Starlog).

So far, we haven’t applied for other grants with this project and all our development work for this project is financed 
by ourselves. We received a grant by the IOTA Foundation for our healthcare project 
[Untangle Care](https://blog.iota.org/the-second-cohort-of-ecosystem-development-fund-grantees-b4349ab01f7c). Dweb.page 
and all related work mentioned in this proposal aren’t part of this IOTA grant. 
We are currently not aware of any similar projects. 

