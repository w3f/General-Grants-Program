# Archipel

## Project Description
We want to build a solution to resolve high availability problem of Validator nodes in PoS.
 This project will allow anyone to build its own highly available Validator setup.

The synchronization part for high availability orchestration will be based on the Substrate framework and will firstly target Polkadot validators, then fishermen and collators.


Moreover, this protocol can be used for other blockchain services that need high availability (parachains needs,  other PoS networks, storage, off chain computing and etc.). This will benefit the entire ecosystem.
We want to participate in building the new Web3 network. We want to simplify the access to blockchain technologies by removing the entry barrier with simple deployment tooling for everyone.
We want to integrate this high availability service in a one click mode at any decentralized personal hardware (dappnode hardware light infrastructure) using DAppNode package for the distribution. 
Everyone will be able to create his own Archipel federation or join existing federation and be engaged in Web3 movement.

Vision and details of the project can be found :
https://archipel.id/Archipel-Atoll-Paper.pdf



## Team members
* François Branciard
* Vladimir Ostapenco

## Team Website	
* https://archipel.id


## Team's experience


* Francois Branciard 

Sculpting clay, wood, stone, Open Source solution and Open
Execution through blockchain, I am a software engineer graduate from
Polytech Annecy. 

I have a strong backend experience on complex systems working
for around 10 years at Orange Information Systems. I started as a
developer, endorsed the role of technical leader, and then was in
charge of the Build Center Activation department for several business
critical projects. This experience brings me a lot, working with many
teams, production applications with high availability constraints,
performance and security.

After that, I then decide to follow my curiosity, new ideas and
intuition, and it leads me to naturally meet and dive into Ethereum
and learned its ropes. I work as Blockchain developer at iExec for 2
years now and I am always hunger to learn and explore new technologies
coming like Substrate and Polkadot.

I see computing as a science and science evolve thanks to shift.
We used to shift from mainframe to client/server architecture.
Client/client softwares and P2P economy is heading. On Board! I want
to shift, swing and grapple with this new playground with Archipel
Project.

* Vladimir Ostapenco

I am infrastructure, security and cloud engineer. After finishing my Master degree in Information Systems, Networks and Virtual Infrastructure Administration, I developed a deep interest in cybersecurity, AI and blockchain. 

During my university studies, I did a lot of research work that could be really useful for Archipel project. I worked on “Implementation and integration of a cluster of embedded systems” and “Comparative study of the performance of different distributed file systems”. I also studied the problem of electricity consumption by embedded systems. I finished my studies with a thesis in log mining and anomaly detection.

Having many years of experience with on premise and cloud infrastructure, I worked with the production environment of different sizes. Starting with a small infrastructure of several dozen users ending with a huge infrastructure of more than forty thousand users.

I am working as blockchain infrastructure engineer at iExec for 2 years. 
Now I am focused on developing with Rust using Substrate framework.

As a member of the Regional Information Systems Security Club and a certified Cisco Security, my goal is to create and maintain a highly secure, scalable and truly decentralized infrastructure.



## Team Code Repos
* https://github.com/branciard
* https://github.com/vladostp

## Team LinkedIn Profiles
* https://www.linkedin.com/in/francois-branciard/
* https://www.linkedin.com/in/vladostpro/

## Development Roadmap


### First Milestone	

* Description

The Polkadot validators liveness is monitored and supervised by
Archipel chain acting as a watchdog. If there is a problem with validator node, Archipel federation will coordinate through a
Substrate chain to take an action. It will ensure that one and only
one validator is active within the federation at the same time
(Active/Passive mode).
More details in the Archipel paper section PoC-1.

				
* Development timeline (2 months)

    * The development start - early November 2019. 
    * The milestone delivery - late December 2019.


* Delivery criteria 

The Archipel chain is based on Substrate framework and can be deployed on a DAppNode. The high availability is working in Active/Passive mode at Alexander Polkadot testnet. 
* Delivery Elements
    * Archipel node template source code
    * Docker image
    * DAppNode package
    * Documentation and Tutorials	 

### Second Milestone

* Description

In the second milestone, the Polkadot validator nodes will be in Active/Active mode. Each node is ready to validate and is connected to Archipel chain via an API. The validator have to check if it is
allowed to submit to the Polkadot network. In deed, it have to check
if it is currently the elected node within the Archipel federation.	
More details in the Archipel paper section PoC-2.	

* Development timeline (2 months)
    * The development start - early January 2020. 
    * The milestone delivery - late February 2020.

* Delivery criteria 

The Archipel chain is based on Substrate framework and can be deployed on a DAppNode. The high availability is working in Active/Active mode at Alexander Polkadot testnet. 

* Delivery Elements
    * Archipel node template source code
    * Docker image
    * DAppNode package
    * Documentation and Tutorials	


After completing the grant’s milestones we want to continue to develop toward the Web3 vision. Firstly, we plan to address other blockchain services that needs high availability. Then we want to experiment with other use cases ( data availability , key recovery ), decentralized infrastructure and federation system of DAppNodes using Substrate technologies.


## Additional Information

* What work has been done so far?
    * Writting this paper
        * https://archipel.id/Archipel-Atoll-Paper.pdf
    * Learning Rust 
    * Testing Substrate Framework
    * Trying Polkadot 
    * Creating DAppNode package
        * https://github.com/branciard/DAppNodePackage-polkadot-alexander
* Are there are any teams who have already contributed (financially) to the project?
    *   No
* Have you applied for other grants so far?
    * No
* Are there any other projects similar to yours? 


There are many PoS staking services that offer you to delegate your stake. Many of them are developing the high availability validator solutions internally.
* For example: 
    * Certus One High Availability for Cosmos Validator Nodes
        * https://kb.certus.one/validator_ha.html#active-active-validator


* How is your project different?

We want to democratise the PoS validation. Our solution will give the possibility to everybody to create a highly available validator infrastructure at home and be able to participate in network security (Polkadot or others).

To do this our project will be:

* Open Source
* Based on Substrate framework
* Developed for Polkadot Validators
