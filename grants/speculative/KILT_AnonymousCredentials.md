# Substrate Anonymous Credentials

## Project Description

Anonymous Credentials enable entities to obtain revocable credentials from trusted attesters (issuers) and show these credentials to multiple verifiers without revealing any identifiable information. The anonymisation ensures that multiple verifiers are unable to track a specific credential presenter entity by correlating the presenter's identity through colluding (sharing data) with each other.

Idemix is one of the already existing attribute based anonymous credential systems (originally developed by IBM Research, currently integrated in [Hyperledger Fabric](https://hyperledger-fabric.readthedocs.io/en/release-1.4/idemix.html)).
This anonymous credential suite has the following privacy properties:
- Unforgeability: no claim presenter can prove possession of attributes that were not issued to him by the attester.
- Multi-show unlinkability: if a verifier is presented the same credential twice, it is impossible for her to tell whether both presentations originated from the same credential or from two different ones.
- Decoupled attesters and verifiers: the attester is not involved in the verification of credentials.
- Selective disclosure: any subset of attributes contained in a credential can be disclosed.

Idemix credentials by default do not use a blockchain, as they were rather intended for industry usecases when this scheme was conceived (issuer being a central entity). Here we try to open up this scheme for general use in a decentralized way. The issuer is the individual attester (and not the blockchain eg. KILT) in our model. The huge advantage of the Gabi approach is that the claimer can randomize the signatures for each presentation of the credential (enabling the privacy feature for the claimer), while the special revocation accumulators preserve the anonymity of the credentials.


The [Gabi](https://github.com/privacybydesign/gabi) is an open-source Go implementation of the primitives based on the [Idemix specification](https://domino.research.ibm.com/library/cyberdig.nsf/1e4115aea78b6e7c85256b360066f0d4/eeb54ff3b91c1d648525759b004fbbb1?OpenDocument). 
* The credentials are **signed** using the ***Camenisch-Lysyanskaya (CL) Signature Scheme*** which is described [here](https://groups.csail.mit.edu/cis/pubs/lysyanskaya/cl02b.pdf) and in 4.4 of the spec. 
* The **issuance** of a credential is described in section 6.1.1 of the spec. Implementation (e.g. [build credential](https://github.com/privacybydesign/gabi/blob/ce779395f4c98898f21f8c49f71f4b3353995127/builder.go#L119), [issuer](https://github.com/privacybydesign/gabi/blob/ce779395f4c98898f21f8c49f71f4b3353995127/issuer.go#L29)) does not precisely follow the specification, some features are not implemented by Gabi (e.g. range proofs on attributes).
* The credential **presentation** to a verifier is described in spec 6.2.3 ([disclose attributes](https://github.com/privacybydesign/gabi/blob/ce779395f4c98898f21f8c49f71f4b3353995127/credential.go#L101)) & 6.2.11 ([verify](https://github.com/privacybydesign/gabi/blob/ce779395f4c98898f21f8c49f71f4b3353995127/proofs.go#L187))
* **Revocation** is [accomplished](https://github.com/privacybydesign/gabi/blob/revocation/revocation/api.go) using [RSA-B Accumulators](https://link.springer.com/content/pdf/10.1007%2F3-540-45708-9_5.pdf). 

The goal of this project is to extend the set of tools that enable privacy in the Polkadot ecosystem and web3 by developing the necessary integrations of the Gabi library into the Substrate/Polkadot API stack. Completing this endeavor will enable the Polkaverse (including our Substrate based KILT Protocol) to effortlessly use attribute based Anonymous Credentials. Any project that handles personal identities/attributes will be able to benefit form integrating the software components (Portable Gabi Library, Revocations SRML) created during this project.

## Team members
* Timo Welde (Team Lead)
* Marton Csernai (Research Lead)
* William Freudenberger (Software Developer)
* Albrecht Weiche (Software Developer)
* Maud Nalpas (Software Developer)
* Dudley Needham (Software Developer)
* Leon Wenzel (Software Developer)

## Team Website
https://www.kilt.io

## Legal Structure
BOTLabs GmbH, Keithstraße 2-4, D-10787 Berlin
AG Charlottenburg HRB 193450 B

## Team's experience
We are a diverse team with 30+ years experience in software development, mathematics and research in computer science.

* **Timo** is a Full Stack Developer, working in Blockchain Technology since 2016. He has a proven track record in Open Source development and was part of the [Thunder](https://thunder.org) Core Team. Timo graduated in Computer Science at the Berlin University of Technology.
[JS/TS, Rust, Python C, C#, Objective-C]

* **Marton** is a Research Scientist with experience in telecommunications, network science and neuroscience. He holds a master’s degree in electrical engineering and PhD in computer science from Budapest University of Technology and Economics.
[Python, Matlab, C]

* **William** is a Software Developer with a focus on cryptography and zero-knowledge protocols. He studied Mathematics at the Technical University of Berlin, his hometown.
[JS/TS, Rust, C]

* **Albrecht** is a developer who concentrates on idemix and the Gabi library. He graduated from the Karlsruhe Institute of Technology with a Master’s degree in Computer Science.
[Go, Rust, Python, Security]

* **Maud** is a software developer with a sweet spot for developer communities. She works on KILT Protocol’s software and with the community. She is an open web, open source, new technologies and data privacy enthusiast. Maud studied engineering.
[JS/TS, C++, UX/UI Design]

* **Dudley** is a Full-stack developer with a background in Engineering.
[JS/TS]

* **Leon** is a Computer Science and Integrated Systems student at the Technical University of Berlin. He has previously worked as developer and technical consultant at multiple blockchain startups.
[JS/TS, Rust]

## Team Code Repos
* https://github.com/KILTprotocol/

## Team LinkedIn Profiles
* https://www.linkedin.com/in/timo-welde-5012397b/
* https://www.linkedin.com/in/martoncsernai/
* https://www.linkedin.com/in/william-freudenberger/
* https://www.linkedin.com/in/maudnalpas/
* https://www.linkedin.com/in/dudley-needham-56b115189/
* https://www.linkedin.com/in/albrecht-weiche-7a4a1914b/

## Development Roadmap

- **Milestone 1 - Creating Anonymous Credentials with Gabi** (4 weeks):  
*Goal:* Wrap the Gabi Go library into a WASM component to make it compatible with JavaScript (client side).
    - Converting existing Go Gabi Library into WASM (*done*)
    - Exposing functionality as JavaScript API (*done*)
    - Add unit and functional tests (*in progress*)

- **Milestone 2 - Revocation SRML** (4 weeks):  
*Goal:* Build the necessary components to handle revocations on the blockchain side.
  - Research and refine concept
  - Add functionality into portable Gabi library and JavaScript API
  - Create SRML for Gabi revocation
    - Store accumulator per attester
    - Remove witness from accumulator
    - Add unit tests
  - Create JavaScript module for the SRML
    - JavaScript API for accumulator handling
    - Add integration tests

- **Milestone 3 - Documentation** (2 weeks)  
*Goal:* Make our solution easily accessible for the developer community.
  - Write documentation for features of Substrate Anonymous Credentials (Portable Gabi Library and Revocations SRML)
  - Write tutorial on how to use the the Substrate Anonymous Credentials
  - Write medium article to explain the concepts
  - Publicise our solution on social networks

Time effort estimation is provided in a way that 2 developers are working on the project full time and the rest of the team has a supportive role.

## Additional Information

* *What work has been done so far?*
    - Portable Gabi library, including some tests (in Milestone 1)

* *Have you applied for other grants so far?*
   - We haven’t applied for any other grants with this project. The work detailed in this grant application is financially covered.

* *Are there any other projects similar to yours? If so, how is your project different?*
   - [SSI Layer for a Polkadot](https://github.com/w3f/Web3-collaboration/blob/master/grants/speculative/Self%20Sovereign%20Identity%20layer%20as%20a%20Polkadot%20runtime.md) by Caelum Labs
      - Verifiable Credential and DID stack for Substrate. However, the proposed Merkle-tree based credential anchoring scheme most probably does not solve the privacy issue.

   - [ZeroKnowledge Identity](https://github.com/w3f/Web3-collaboration/pull/168/files#diff-b301d2acf19e9e0c3ef70ab1dcd1cd8c) by Commonwealth
      - Anonymous identity system with a specific use case of linking web2 <-> web3 identities. For them, a web3 identity is a single pseudonym for multiple web2 identities. However, in our case, we would need multiple target identities (ideally one randomized target identity for every verification) so that multiple verifiers cannot know they communicated with the same person.

   - [IRMA](https://privacybydesign.foundation/irma-en/) by Privacy by Design Foundation
      - Privacy-friendly identity platform for authentication and signing attributes with open source go codebase using the Gabi library.
      - In contrast to their solution, where it is the attester’s responsibility to always keep her accumulator database online, our solution writes and maintains the accumulators of attesters on the blockchain. Thus we enable a wider range of end users to become attesters in an effortless way that is more aligned to the principles of web3.
      - Moreover, in IRMA when someone requests revocation but the accumulator witness is out of date, it [needs to be updated before a revocation](https://irma.app/docs/revocation/#revocation-updates) can go through. If the age of the witness has passed a certain threshold the credential holder has to contact the attester’s IRMA server to download updates, and this might harm the user’s privacy towards the attester. By writing the accumulators on chain we might be able to mitigate such a privacy issue.

    - [Sovrin](https://sovrin.org/) by Evernym
        - An open source self-sovereign identity project based on IBM Hyperledger. They also use the CL Signature scheme with revocations, but their system is anchored on a permissioned blockchain network and it is incompatible with the Polkaverse.


    - [W3C Verifiable Credentials (VC) Specification](https://w3c.github.io/vc-data-model/#zero-knowledge-proofs)

        - The latest version of the VC spec supports implementing CL Signatures in Verifiable Credentials ([example](https://w3c.github.io/vc-data-model/#example-24-a-verifiable-credential-that-supports-cl-signatures)).

