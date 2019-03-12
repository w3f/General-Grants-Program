<img src="https://pact.online/dist/img/starlog_new.png" width="240">

## Project Description
The goal of Starlog is to research and develop an open source solo chain or potential parachain, which stores metadata for the next generation of the world wide web as non-fungible tokens as well as availability data (Programs: [New chains, Distributed File Storage](https://github.com/w3f/Web3-collaboration/blob/master/grants/grants.md#areas-of-interest)). For this project, we will focus on IPFS as the distributed storage layer for the web3. The metadata will be signed by the uploaders and includes a unique hash, a price, a timestamp, a license, information about the uploaded file itself as the location of the initial upload or pinning gateway.

Starlog provides, therefore, the following key benefits for the next generation of the world wide web:

- Distributed searchability via human-readable names
- Copyright system 
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

The goal of our roadmap is to develop and document a metadata chain for IPFS based on Substrate. The signed metadata will include a unique hash, a price, a timestamp, a license, information about the uploaded file itself as well as the location of the initial upload or pinning gateway. In addition to that, we will develop a basic interface for this runtime based on our project dweb.page. The overall project will take 12 weeks and include documentation, articles, and tutorials.

Starlog is for us a pure research project. We currently don’t have any plans to monetize on the project itself. 
In the long-term, we plan to apply this technology in multiple healthcare related projects. We are open-minded regarding receiving the grant in a combination of fiat and DOTs.  

### Phase 1 Preliminary research phase (4 weeks, parallel to phase 2): 

Summary: In this phase, we will focus on the design and additional research of a metadata runtime and the implementation of this system based on Substrate. Potential questions are: 
*	How to optimize the storage of metadata to improve the loading as well as reduce the chain size (e.g., ERC-1155 or storing on IPFS)?
*	How to deal with users uploading content illegally?
*	How does a subscription-based system compare to existing solutions like token-curated registry for this use-case?
*	How to trade and value ownership rights without generating just another token? 
*	How to implement a multi-signature/-owner system?

Milestones: 
* Design: Medium article and whitepaper draft describing a distributed metadata system based on Substrate

Funding: 6.000 $

### Phase 2 Development phase (10 weeks): 

Summary: We will further develop and test the existing open source runtime and use Dweb.page as a UI, which handles the subscription-based system according to the use-behavior. The goal is to create a fast and scalable runtime so that users can request metadata and availability information almost instantly. To archive this, we also investigate potential additional off-chain solutions. 

Milestones: 

* Implementation: We will create and test multiple Substrate modules that implement the described metadata system. Starlog will probably consist of three modules: 
  1. a metadata combination module, which contains and handles the IPFS hash, a metadata hash, a price, a license number, and a gateway,
  1. an availability module, which stores and update the availability information of IPFS files, and
  1. a module containing the actual metadata. This module might either be integrated off-chain or focus on reducing the required on-chain storage size.
*	Interface: Dweb.page will be the interface for our runtime. Therefore, we need to write the necessary JavaScript code. We will try to structure the code in a way that it can easily be reused for other projects.  
*	Tutorials: We will write a tutorial that demonstrates how to integrate Substrate into an existing web project based on the @polkadot/api npm package. Furthermore, we will write a tutorial on how to write and test a Substrate runtime similar to our solution. The focus will be specifically on the aspects we encounter during the development process, which are missing in other tutorials. 

Funding: 18.000 $

### Phase 3 Documentation phase (2 weeks):

Summary: We will improve the documentation of the project, write a final medium article about our findings as well as potential next steps and other use-cases for the Substrate framework. 

Milestones: 
*	Documentation: We will use Read the Docs to create the documentation for the project. This will include a summary, a couple of tutorials and the specification of the project.
*	Marketing: We will write a medium article, which discusses the potential next steps and other use-cases for the project. Additionally, we will share our work on different forums/networks (e.g., Reddit, Hacker News, Twitter, etc.).

Funding: 4.000 $  

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

