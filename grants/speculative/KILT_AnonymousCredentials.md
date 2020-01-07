# KILT Anonymous Credentials

## Project Description

Anonymous Credentials enable entities to obtain revocable credentials from trusted attesters (issuers) and show (some properties of) these credentials to multiple verifiers. The anonymisation ensures that multiple verifiers are unable to track a specific credential presenter entity by correlating the presenter's identity through colluding (sharing data) with each other.

The [Gabi](https://github.com/privacybydesign/gabi) is an open-source Go implementation of the Idemix attribute based anonymous credential system (originally developed by IBM Research, currently integrated in [Hyperledger Fabric](https://hyperledger-fabric.readthedocs.io/en/release-1.4/idemix.html)).
This anonymous credential suite has the following privacy properties:
- Unforgeability: no claim presenter can prove possession of attributes that were not issued to him by the attester.
- Multi-show unlinkability: if a verifier is presented the same credential twice, it is impossible for her to tell whether both presentations originated from the same credential or from two different ones.
- Decoupled attesters and verifiers: the attester is not involved in the verification of credentials.
- Selective disclosure: any subset of attributes contained in a credential can be disclosed.

The goal of the project is to extend the set of tools that enable privacy in the Polkadot ecosystem and web3 by developing the necessary integrations of the Gabi library into the KILT/Substrate/Polkadot API stack. Completing this endeavor will enable the Substrate/Polkadot ecosystem to effortlessly use Idemix type Anonymous Credentials. Any project that handles personal identities/attributes will be able to benefit form integrating the KILT SDK in their project, or they can include the software components underlying our SDK (portable Gabi Library, Revocations SRML).

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

* **Timo** is a Full Stack Developer, working in Blockchain Technology since 2016. He has a proven track record in Open Source development and was part of the Thunder Core Team (thunder.org). Timo graduated in Computer Science at the Berlin University of Technology.
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

- **Milestone 1 - Creating Credentials** (6 weeks):
Goal: wrap the Gabi Go library into a WASM component to make it compatible with the JavaScript based stack (client side).
  - Portable Gabi library (without credential revocation)
    - Converting existing Go Gabi Library into WASM (*done*)
    - Exposing functionality as JavaScript API (*done*)
    - Add unit and functional tests (*in progress*)
  - Integration into KILT SDK
    - Add integration tests

- **Milestone 2 - Revocation** (4 weeks):
Goal: build the necessary components to handle revocations on the blockchain side.
  - Research and refine concept
  - Add functionality into portable Gabi library and JavaScript API
  - Create SRML for Gabi revocation
    - Store accumulator per attester
    - Remove witness from accumulator
    - Add unit tests
  - Create JavaScript module for the SRML
    - JavaScript API for accumulator handling
    - Add integration tests
  - Integration into KILT SDK

- **Milestone 3 - Documentation** (2 weeks)
Goal: make our solution easily accessible for the developer community
  - Write documentation for new features in the KILT SDK Docs
  - Write tutorial on how to use the the KILT Anonymous Credential Suite
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
