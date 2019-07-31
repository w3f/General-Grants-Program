# Project name

Triplecheck Network

## Project Description

**Triplecheck** is a Substrate runtime module (SRLM) that uses proxy re-encryption for private content publishing, origination and verification. We are creating the Triplecheck runtime module for substrate blockchains. We originally created to project to combat deepfakes and other types of faked content on the web. 

* An indication of why this project is good for the ecosystem.

Blockchain runtimes will need a way to verify content and provide re-encryption keys to other member's of the blockchain network. We are going to allow different substrate users to provide policys to re-encrypt data that is published on any Substrate blockchain. 

* An indication of how you will integrate this project into Substrate / Polkadot.

We will create a runtime module that allows a user to upload data to the blockchain with a policy. This policy is associated with a substrate account. The user can the share this policy with another substrate account which will re-encrypt the data that is on chain with their key. They can the decrypt the data that is on-chain and see the content. 

* An indication of why your team is interested in creating this project.

We believe that we are moving into a world where privacy and content verification is going to be a massive problem. By combining Triplecheck network with Substrate chains, we can solve this issue for the Polkadot ecosystem. Blockchain developers will be able to use proxy re-encryption on substrate based blockchains for their own private content publishing use cases. 

## Team members

  Dominic Steil
  
  Harish Prasanna
  

## Team Website	
* https://triplecheck.network


## Team's experience
Please describe the team's relevant experience

Distributed systems, blockchain networks, cyber security and anti-virus networks. Expirience developing ethereum applications, front-end (React, Angular), node / express middlewares, Python Flask servers.

## Team Code Repos
* https://github.com/triplecheck
* https://github.com/domsteil/c-chain

## Team LinkedIn Profiles
* https://www.linkedin.com/domsteil
* https://www.linkedin.com/harishprasana

## Development Roadmap
Please add information setting into sufficient detail the following (usually two pages):

Month 1: 
8/17/2019 - 9/17/2019
Implement Upload Substrate Modules

We will create a Substrate module that will create a proxy re-encryption policy.
Development of a working module to upload data encrypted with the policy to the substrate runtime storage.
UI developed for leveraging secret store bond with Triplecheck module.
Documentation on how to upload Policies and link to Substrate Accounts.
Docker Container for Testing.



Month 2:
9/18/2019 - 10/17/2019
Implement Verify and Decrypt Substrate Modules

We will create a Substrate module that will verify uploaded data and decrypt the data using the re-encrypted key.
Development of a working module to verify the encrypted data that is uploaded using the policy module.
Development of a working module to decrypt the encrypted data that is uploaded using the policy module.
Complete UI development for interacting with Substrate and the Triplecheck module.
Documentation on how to decrypt and verify policies. 
Example Tutorial of verifying uploaded data using the Triplecheck Runtime Module. 
Example Tutorial  to use the Triplecheck runtime module for uploading data to the runtime storage and decrypting using policy.
Docker Container for Testing


Month 3:
10/18/2019 - 11/17/2019
Complete Substrate Modules, UI, Documentation

Runtime module development for substrate account decryption of runtime storage.
Completion of Triplecheck Runtime Module.
Completion of Documentation
Example Tutorials of uploading, verifying, and decrypting data using the Triplecheck Runtime Module.
Docker Container for Testing and Deployment.


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
