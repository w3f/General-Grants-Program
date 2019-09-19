# Bullet-Substrate tool
## Project Description
This project is an privacy-protecting tool kit for parachain based on the Bullet-proof protocol. Bullet-Substrate tool is basically designed as a privacy tool for blockchain based on Substrate to impletement private transaction. 

The comparison of Bullet-proof and other privacy techniques can be found [Sonic: Zero-Knowledge SNARKs from Linear-Size Universal and Updatable Structured Reference Strings](https://eprint.iacr.org/2019/099.pdf) 


The outstanding features of Bullet-Substrate are as following:

* According to the features of Bullet-proof, we do not need any trusted party or MPC to do pre-setup

* According to the features of Bullet-proof, with shorted proof, the tool kit will be specially suitable for the  parachain where the the use of the resource (for example storage and code execution) may consume money

* The enhancement for time complexity in the Bullet-proof
    
* This project is the first privacy transaction impletementation for account module based on Bullet-proof protocol

* Customized development for Bullet-proof for substrate

The high level principle is as follows.

<div align="center">
<img src="https://user-images.githubusercontent.com/19221132/65102812-ec3f4200-d9fe-11e9-8f5d-0c4f1d3322ec.png" width="600px">
</div>


## Team Members

* Prof Yongge Wang[Consultant]
* Wenyao Hai
* Fei Zhou

## Team Website

http://sperax.io
## Legal Structure
incorporated

## Team's experience
[Consultant]

* Prof Yongge Wang : currently a full-time professor at the University of North Carolina at CharlotteProfessor. Wang's proposed post-quantum cryptographic algorithm RLCE has been selected as a candidate for the post-quantum standard of the NIST. In addition, Professor Wang has been actively involved in the development of a large number of protocol standards: for example, IETF, W3C XML protocol, IEEE 1363 protocol and SAN Internet Security Protocol.In this project, Prof Yongge Wang will serve as a consultant for the optimization for the Bullet-proof.


[Develpoer]

* Wenyao Hai : Familiar with common encryption and decryption algorithms for symmetric and asymmetric cryptosystems (AES, RSA, ECC), digital signatures such as ring signature aggregation signature, key management etc., proficient in the use of cryptographic algorithms and open source libraries, Familiar with PKI system, CA system and security protocol. Familiar with homomorphic encryption, zero knowledge proof/bullet-proof, lattice cryptography. Proficient in Go/C/C++ and other languages.[Wenyao Hai Github](https://github.com/Haysemonster)

* Fei Zhou : As a Java background developer for two years in Internet company, with rich experience in software background development. Engaged in blockchain development since 2017, master in exchange wallet and blockchain bottom layer development. Familiar with encryption algorithms（AES、RSA）, and proficient in using open cryptographic source libraries, and have rich experience in the development of cryptocurrency (ETH, BTC) and Dapp.[Fei Zhou Github](https://github.com/ronaldspeirs)


## Team LinkedIn Profiles
[Prof Yongge Wang](https://www.linkedin.com/in/yongge-wang-8680706/)

## Development Roadmap
The milestones are spread out over a total of 3 months as following:

* M1: Implementation of the optimization for the Bullet-proof protocol (4 weeks)
* M2: Construct blockchain called BulletChain based on substrate, and a simple wallet(2 week)
* M3: Implementation of balance privacy (4 weeks)
* M4: Implementation of a confidential contract assets (2 weeks)

## Additional Information
### What work has been done so far?
Complete the the theoretical research for the optimization for the Bullet-proof and some simulation of the optimization.

### Have you applied for other grants so far?
No.

### Are there any other projects similar to yours?
* In terms of Bulletproof : Menero, Mimblewimble

* In terms of privacy for substrate: [Substrate sgx proposal](https://github.com/w3f/Web3-collaboration/blob/master/grants/speculative/substrate_sgx_proposal.md)  [Zerochain](https://github.com/w3f/Web3-collaboration/blob/master/grants/speculative/zerochain.md)
