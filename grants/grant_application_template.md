# Project name

Triplecheck Network

## Project Description
If this application is for a particular grant programme then please indicate that in the first line of this section.

W3F Grant

* Please provide a brief description of the project here. This is likely more important for speculative applications, but also worth providing some description here of the team's intent with the project.

Triplecheck is a proxy re-encryption network for private content publishing, origination and verification. We are creating a triplecheck runtime module for substrate blockchains. We originally created to project to combat deepfakes and other types of faked content on the web. 

* An indication of why this project is good for the ecosystem.

Blockchain runtimes will need a way to verify content and provide re-encryption keys to other member's of the blockchain network. We are going to allow different substrate users to provide policys to re-encrypt data that is published on any Substrate blockchain. 

* An indication of how you will integrate this project into Substrate / Polkadot.

We will create a runtime module that allows a user to upload data to the blockchain with a policy. This policy is associated with a substrate account. The user can the share this policy with another substrate account which will re-encrypt the data that is on chain with their key. They can the decrypt the data that is on-chain and see the content. 

* An indication of why your team is interested in creating this project.

We believe that we are moving into a world where privacy and content verification is going to be a massive problem. By combining Triplecheck network with Substrate chains, we can solve this issue for the Polkadot ecosystem. Blockchain developers will be able to use proxy re-encryption on substrate based blockchains for their own private content publishing use cases. 

## Team members
* Name of team leader
  Dominic Steil
* Names of team members
  Harish Prasanna
  

## Team Website	
* https://triplecheck.network

## Legal Structure 
Please provide name and registered address of the legal entity executing the project. These details can also be shared privately via our Google Form.

## Team's experience
Please describe the team's relevant experience

Distributed systems, blockchain networks, cyber security and anti-virus networks. Expirience developing ethereum applications, front-end (React, Angular), node / express middlewares, Python Flask servers.

## Team Code Repos
* https://github.com/harishperfect/triplecheck
* https://github.com/domsteil/c-chain

## Team LinkedIn Profiles
* https://www.linkedin.com/in/dominic-steil-b6092553
* https://www.linkedin.com/in/harishprasanna

## Development Roadmap
Please add information setting into sufficient detail the following (usually two pages):

* The specifications of the software, delivered over a number of milestones. The detail must be such that after delivery we are able to examine whether the software meets the requirements agreed in the specifications, in order to be able to make any payments to you.

* A time schedule on when each milestone will be achieved.

SCRUM Methodoligy with standups for all team members bi-weekly. 

8/17/2019 - Project begin: Scoping based on Rust / Substrate / Polkadot / WASM / Libp2p.

8/28/2019 Milestone 0: Following web3 conference in Berlin we kick off Triplecheck Runtime Project.

9/8/2019 - Milestone 1: Runtime module development in Rust for policy creation.

9/17/2019 - Milestone 2: Runtime module development for proxy re-encryption on the runtime storage.

9/28/2019 - Milestone 3: Runtime module development for verify module.

10/8/2019 - Milestone 4: Runtime module development for decrypt module. 

10/17/2019 - Milestone 5: Runtime module development for substrate account decryption of runtime storage. 

10/28/2019 - Milestone 6: Begin UI development for leveraging secret store bond with triplecheck module. Begin documentation for the Triplecheck runtime module. 

11/8/2019 - Milestone 7: Component UI development for interacting with Substrate and the Triplecheck module.

11/17/2019 - Milestone 8: Complete Project. 

* The required grant per milestone and the total amount requested. Grants can be in one of the fiat currencies CHF, EUR or USD or in DOTs or a combination of fiat and DOTs. Please reach out to grants@web3.foundation for discussing what amount in fiat and DOTs would be appropriate. 
* Note that we now have a preference to collect the financial information via our Google Form, or via a Google Document (paste the link into our Google Form).


Note: It should be clear how the project will be working towards deployment on Substrate / Polkadot.

Also helpful to know: what are the team’s long-term plans and intentions after the grant has been awarded?


## Additional Information
Any additional information that you think is relevant to this application.

These bullet points won't be applicable to all projects. Some of the information may have already been included in the description section, if so then no need to state it again.

* What work has been done so far?

We have a working product that allows users to upload and encrypt data on the network. Users can then provide the policy to another user to re-encrypt the data using their key for decryption. 

* Are there are any teams who have already contributed (financially) to the project?
No

* Have you applied for other grants so far?
No

* Are there any other projects similar to yours?
No

* How is your project different?
It is leveraging proxy re-encryption
