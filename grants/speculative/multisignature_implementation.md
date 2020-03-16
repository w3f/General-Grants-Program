# Project Name  

Multisignature Implementation  

## Project Description  

This is an application for development of multisignature implementation for Polkadot. Multisignature (multisig) refers to requiring more than one key to authorize a transaction.  
It is generally used to divide up responsibility for possession of assets. By using a multisig wallet, users are able to prevent the problems caused by the loss or theft of a private key.  
So even if one of the keys are compromised, the funds are still safe.There are couple of methods to implement Multisignature: Shamir's Secret Sharing Scheme, m of n signature and n of n signature.  

We investigated all these approaches, noted their advantages and disadvantages and stand on the next ways to implement multi signature for Polkadot:  
- using multisignature runtime module  
- using threshold Schnorr signature for ed25519
- using Schnorr multi signature n of n sr25519  
We are providing for your consideration the roadmap for all 3 approaches.
## Team members  
- Vitalii Parkhomenko – team leader/researcher/tech writer  
- Aleksei Korobeinikov – developer  
## Team Website  
- https://everstake.one & https://atticlab.net  
## Legal Structure  
ATTIC LAB, Limited Liability Company. 89, Kazimir Malevich str., Kyiv, 03150, Ukraine  
## Team's experience  
Everstake is an affiliate company of Attic Lab, so members from both teams are going to participate in the project. Everstake has developed an online IDE for the IOST blockchain. Attic Lab’s development experience includes the following projects: Crypto exchange Codex. View Here Cassandra history plugin. View Here Munin plugins. View Here OpenBankIT. Open-source banking software. View Here EOS History API running on Elasticsearch cluster. View Here My EOS Wallet. View Here My EOS Wallet mobile version. View Here1. View Here2. EOS Book. View Here My Telos Wallet. View Here My BOS Wallet. View Here
Besides, we have successfully developed VSCode & Atom plugins for Web3Foundation previously  
## Team Code Repos  
- https://github.com/everstake  
- https://github.com/atticlab  
## Team LinkedIn Profiles  
- https://www.linkedin.com/in/vitalii-parkhomenko-493561187/  
- https://www.linkedin.com/in/aleksei-korobeinikov/  
## Development Roadmap  
### Onchain implementation:  
1. Library for multisig (wrapper to polkadot-js) 30h  
1. Blockchain(Runtime Module) 60h  
   1. Wallet setup  
   1. Multisignature wallet logic  
   1. Daily limit management  
   1. Signers managements  
   1. Unit-tests  
1. Integration testing 16h  
1. Documentation, tutorials 10h  
  
Total for Onchain implementation: 126 hours  
Budget: 8,000 USD  
  
### Onchain implementation (reusing F3Joule):  
1. Library for multisig (wrapper to polkadot-js) 30h  
1. Blockchain(Runtime Module) 24h  
   1. Refactoring  
   1. Daily limit management  
   1. Unit-tests  
1. Integration testing 16h  
1. Documentation, tutorials 10h  
  
Total for Onchain (reusing F3Joule) implementation: 80 hours  
Budget: 5,200 USD  
  
### Worker implementation (using Schnorr signatures)  
1. Library(wrapper to polkadot-js) 70h  
1. Client(ui) 48h  
1. Blockchain(Runtime Module) 104h  
   1. Multisignature transaction logic  
   1. Submit transaction logic  
   1. Events  
   1. Unit-tests  
1. Worker 140h  
   1. Multisignature transaction logic  
   1. Verification and collecting all signatures logic  
   1. Signature aggregation logic  
   1. Send extrinsic to Module logic  
1. Integration testing 24h  
  
Total for worker implementation: 386 hours  
Budget: 25,000 USD  
## Long-term plans  
We would like to continue developing tools and products for Polkadot, and not only in the area of editors and IDE’s.  
## Additional Information  
What work has been done so far? Getting familiar with the Substrate codebase and researching possible ways to do it.
Have you applied for other grants so far? We have finished one project with Web3 so far.
Are there any other projects similar to yours? Not to our knowledge.  

