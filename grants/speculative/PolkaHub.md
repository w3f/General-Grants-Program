# PolkaHub. Scalable Blockchain Infrastructure


## Introduction
This proposal features “Platform-as-a-Service (PaaS) for Substrate Nodes”: inspired by [Heroku](https://heroku.com), aiming to create a managed container system, with one-click services for deploying and running different parachain. 
The proposed system enables automatic updates and resource management for running nodes, additionally providing templates for launching parachains. 


## What is PolkaHub

1. Polkahub is a fast, scalable blockchain infrastructure component for Substrate parachains.

2. Polkahub provides parachain developers with the ability to launch and manage network infrastructure using our command line utility and the ability to provide public node access 

3. PolkaHub gives users the opportunity to get free cloud access to the diverse Polkadot ecosystem

4. The Polkahub Explorer (list of parachains) provides comprehensive information about each parachain, how it can be used (how to make transactions and other operations in it). Additionally, it provides information on how to use the public parachain’s API to create decentralized applications.

5. Polkahub provides developers with a uniform standard for packaging and deploying applications to cloud infrastructure. 

6. Polkahub provides the functionality to track and control of the parachain’s versions. So in the event of critical bugs arising, developers can update or roll back the version of the parachain using simple commands (via running specific commands in a command line). 

7. Polkahub supports Node deployment to remote servers or cloud infrastructure via git. 

8. Polkahub infrastructure is based on buildpacks (industry standard for managing containers in the cloud).

9. Buildpacks provides high-level interfaces for isolated environments within the node's execution. Easily scaled, managed and updated.

10. No need to rely on DevOps and System Administration for managing parachain’s infrastructure - thanks to PolkaHub. You only git, command line and a simpleweb-interface. 

11. Sample basic scenario - node deployment infrastructure using PolkaHub: 
   * Download PolkaHub utility
   
   * Get deployment token via PolkaHub utility
   
   * Insert in command line “git push https://token.polkadhub.io master: development”, where master:development is an active branch of code. 
   
   * PolkaHub automatically creates buildpacks, installs all dependencies, sets needed settings and deploys application. 
   
   * When the process is completed the parachain will be accessible through a link https://testchain.polkahub.io/
   
   * wss://testchain.polkahub.io
   
   * Also, the developer can publish his parachain on the PolkaHub Explorer. The description and documentation for the project will be automatically sourced from the Readme and Docs folder. 


12. Basic scenario for dapp developer: 

    * Visit https://explorer.polkahub.io

    * Select parachain, read its documentation. 

    * Copy RPC / Websocket links

    * Build apps for this parachain


## Why the Polkadot ecosystem needs Polkahub

New languages, frameworks, version control systems, databases, architectures, and other bleeding-edge technologies are gaining ground in the space. Especially in fast changing environments as Web3. You need containers, microservices to support infrastructure work  All of this should be updated regularly too.
We want to create a platform like Heroku for Web3. IT teams can manage this platform instead of building everything from scratch. 

Any developer of a decentralized application will be able to install the node he needs through our service in a command line. Our PaaS will not require any knowledge of DevOps from dApp developers. 

For example, you have 2 nodes in your parachain. And you want to launch other 8 nodes. You run a command with parameters - parachain / number of nodes etc. The PaaS infrastructure ensures that everything will launch and work correctly. 


## Feature list

**Buildpacks (smart container)**

* Provide a balance of control that reduces the operational burden on developers and supports enterprise operators who manage apps at scale.

* Ensures that apps meet security and compliance requirements without developer intervention.

* Provides automated delivery of both OS-level and application-level dependency upgrades, efficiently handling day-2-day operations that are often difficult to manage with Dockerfiles.

**Runtime**

Your apps run inside smart containers in a fully managed runtime environment.

**Scale**

PaaS scales in an instant, both vertically and horizontally (look for an example above). You can elegantly run everything from dApps to parachains, manage the number of nodes in your network, and so on. 

**Sets of pre-built nodes**

PaaS keeps buildpacks of different parachain nodes. You can select which node you need and install it. 


## Ecosystem benefits

Having launched our own [parachain](https://telemetry.polkadot.io/#/Akropolis) since February 2019 and seeing how rapidly the web3 infrastructure is changing - new versions / updates / patches are frequently being released - made us reach the following conclusion: 

Keeping the infrastructure up to date becomes time-consuming and constantly requires attention. This delays the development. Creating this PaaS solution will allow developers to fully focus on the development of their own parachains or applications, rather than setting up and maintaining infrastructure.


## Legal Structure

Akropolis Decentralised Ltd , Suite 23 Portland House, Glacis Road, Gibraltar, GX11 1AA, company number: 116430


## Team Website

Akropolis.io


## Team's experience

Recent team updates:

* IBM MoU signed, co-development partnership confirmed [press-release pending]

* Winner of a 0x+Coinlist DeFi Hackathon. Developed a new economic primitive ["Committments to Future Cashflows"](http://cashflowrelay.com/)

* [C2FC Implementation on Substrate](https://github.com/akropolisio/akropolis-polkadot), [it’s telemetry](https://telemetry.polkadot.io/#/Akropolis) and [video screencast](https://www.dropbox.com/s/svcbp4f62myfxfd/C2FC.mp4?dl=0).

* [Partnership](https://medium.com/akropolis/empowering-informal-economies-via-defi-poa-network-and-akropolis-announce-their-partnership-d8abe8bd0c74) with POA Network (xDAI chain), towards better UX standards for end-user adoption.

* [Latest development update](https://medium.com/akropolis/akropolis-development-update-82aaee0f5ee2) featuring work up-to-date, future plans and sneak peek of MVP (out until the end of June)


**Alex Maz (CTO)**:

Blockchain engineer, educator and an active founding member of St.Petersburg Blockchain Association, Alex graduated with BSc Applied Mathematics and Computing Sciences and is a PhD (cand.) Machine Learning. Blockchain developer and miner since 2012, he has 16 scientific publications focussing on natural language recognition and 10 commercially implemented applications to his name. Alex has shipped products in fintech, banking, and gaming, and is passionate about educating the new generation of blockchain developers. Full-stack developer with over 15 years experience (C#/.NET, Golang,  Java, Solidity).

**Alex Koz (Blockchain R&D)**

Software Engineer, Consultant, Game Developer & reverse-engineering enthusiast. OSS enthusiast, active contributor of DDG, Haxe. Over 15 years of development of real-world applications since 2000. Worked for many companies such as SmartGames, Dulton Media, Games.Mail.ru, Leo Burnett, Rambler, Clickberry, and others.

**Dmitriy Serdcev (Senior Frontend Developer)**

Dmitriy is an experienced frontend developer with MSc in Computer Science and over 15 years experience, having shipped over 8 commercial projects, including those using DLT technology. Active participant of open-source projects and all things web3.0.


## Team Github

https://github.com/akropolisio
https://github.com/akropolisio/akropolis-polkadot

## Team Code Repos

https://github.com/AlexanderMazaletskiy
https://github.com/fzzr-
https://github.com/in19farkt

## Team LinkedIn Profiles

https://www.linkedin.com/in/alexander-mazaletskiy/
https://www.linkedin.com/in/akozlovskij
https://www.linkedin.com/in/dmitriy-serdtsev-8307b617b/

## Target Programming Language

Golang, Rust, Javascript (nodejs)

## Development Roadmap

1 month: research and creation of the buildpacks API for Substrate Nodes. Technical Polkahub functionalities for this stage:: 

   * Creation of images for different Substrate nodes. 

   * Updating Substrate Nodes using buildpacks’ high-level abstraction

   * Using buildpacks for launching Substrate-based networks.

2 month: building Hub / web-portal for buildpacks. We will be working on the creation of buildpacks for main projects in the Polkadot ecosystem and on the deployment of clusters for managing bulidpacks using [dokku](http://dokku.viewdocs.io) and [Flynn](https://flynn.io).  We  will create the specification on how to create buildpacks. Developers will be able to do it following our specification and will be able to upload their buildpacks to the portal. Other developers/users will be able to download different buildpacks. 

As a result it will be a web portal like https://thegraph.com with a set of builpacks. 

3 month: testing and launching


## Milestones / Deliverables

T+1: Full documentation of Polkahub PaaS the alongside technical design description. 

T+3: Ready to use Functionalities : 

* Creation of buildpacks of existing parachains. 

* Uploading buildpacks to our PaaS (polkahub.io)

* Installing buildpacks to your servers works through a command line. 

* Tutorial / FAQ uploaded to github / web-portal. 


## Additional Information

**Are there any other projects similar to yours?** 

There is a project https://developers.validators.io/ that has some similarities, but they provide API services for dApp developers. To provide this service, they need to support scalable cloud infrastructure  in cases of highload. Our solution can make it easier to support and maintain services like Validators.io. 

Another one is https://github.com/w3f/polkadot-deployer that helps  deploying Polkadot nodes. But this solution still requires knowledge of DevOps to do that. 

**How to check our deliverables** 

We provide the Polkahub PaaS infrastructure. Therefore, to test the functionalities of the solution, you do not need to compile or install anything. Anyone can deploy a node from any supported by PolkaHub parachains to our cloud. 

Then you can check on http://telemetry.polkadot.io that a new node has appeared on the network and is working correctly. 

**Is it open source?** 

Our code will be fully open source. Anyone can independently install our solution on their server following our tutorial and provide PaaS to Web3. 
