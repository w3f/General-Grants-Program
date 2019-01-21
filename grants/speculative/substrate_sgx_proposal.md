# Substrate Transaction Privacy using Intel SGX

## Project Description

SCS suggests an extension to Substrate allowing to call the runtime modules inside an Intel SGX enclave. This would allow modules to read and modify an encrypted state that can't be accessed outside a set of provisioned enclaves. Use cases demanding transaction privacy could be implemented on Substrate.

### Why Trusted Execution Environments?

TEEs claim to provide computation integrity and confidentiality. Nowadays, two systems are widely available: Intel SGX and ARM TrustZone. We hope to see TEEs from open source designs like [OpenPower](https://openpowerfoundation.org/) soon. We focus first on Intel SGX for this proposal because SDK support is more mature than for TrustZone. However, we should make sure to give the user a choice and move to hardware abstractions like [openenclave](https://github.com/Microsoft/openenclave) or [Asylo](https://cloud.google.com/blog/products/gcp/introducing-asylo-an-open-source-framework-for-confidential-computing) once they reach stable releases for different TEEs.
Trusting Intel SGX means trusting the Intel Attestation Service (IAS) to truthfully report about their hardware and to keep their signing keys secure. Moreover, it means trusting Intel's hardware design to do what it claims. Various attack vectors have been suspected (e.g. by the thorough work [Intel SGX explained](https://eprint.iacr.org/2016/086.pdf)). Side-channel attacks are likely to be feasible.

While we should take these attack vectors as well as concerns about Intel's integrity and capabilites seriously, one should keep in mind that all our software runs on hardware provided by a set of very few manufacturers. If we compare confidentiality guarantees for TEEs and zk-SNARKS for example, we should bear in mind that zk-SNARKS will be computed on clients, many of them running on the same Intel CPUs as well, subject to trust in Intel.

### Why not (yet) Zero-Knowledge Proofs?

Intel SGX is available today with stable SDKs. Moreover, SGX allows for generic computation of high complexity, mainly limited by SGX memory (i.e. limiting the size of the state). Zero-knowledge protocols for generic computation like [ZEXE](https://eprint.iacr.org/2018/962.pdf) are very interesting, but also very new. Moreover, they are computation-heavy (2+ min) and transaction sizes are significantly higher (~1KB) than they could be with SGX. High tx-volume applications are more efficiently tackled with TEEs. Embedded applications are more likely possible with ARM TrustZone than with ZEXE in the medium-term.

### Benefits for the Ecosystem

We would open the Substrate platform to a whole new field of applications requiring some confidentiality along with scalability.

### Technical Approach

The modular architecture of Substrate should allow to modify the runtime executor to run WASMI within a SGX enclave without major refactoring. Baidu has already released a [Rust SDK for Intel SGX](https://github.com/baidu/rust-sgx-sdk) together with a code sample running the parity WASMI within an enclave. This shall serve as a starting point.

Then, an enclave provisioning solution needs to be implemented that allows multiple enclaves to access and modify the encrypted state with a shared secret (unknown to anyone outside the enclave). We intend to use a multi-party key exchange procedure for this. The runtime state could be distributed in encrypted form over IPFS with only its hash being written to the blockchain.
While the Intel team for [Hyperledger Sawtooth Private Data Objects](https://github.com/hyperledger-labs/private-data-objects) (as of writing) has implemented a simple provisioning procedure where enclaves need to be provisioned in advance, the secret key being split among multiple provisioning services (PS), ??risks?? collusion attacks among PSes among other vulnerabilities. We think the set of provisioned enclaves needs to be mutable. For this purpose we'd still have to investigate a suitable key agreement protocol that can be ??taken out?? whenever the set of provisioned enclaves changes.

### Motivation

Our team is interested in this project because we develop blockchain solutions for our industry partners and we think that Substrate could be a very good tool to base our projects on. However, Substrate currently doesn't offer transaction-level privacy. Our customers need to tune the transparency/confidentiality trade-off for their specific use cases. While there are plans to use zk-SNARKS for that purpose, there currently isn't any production-ready solution out there to implement such proofs for generic problems. Trusted Execution Environments like Intel SGX or ARM trustzone are designed to provide confidence and integrity guarantees for code remote execution. Even if side-channel attack vulnerabilities have been reported, such attacks are very expensive. Our customers may be willing to take the risk of such attacks in return for a production-ready solution. They also might accept the dependency on Intel Attestation Services.
Moreover, the Rust language is of strategic interest for SCS and the company would cover the efforts necessary for introducing more of our staff to Rust.

## Team Members

Supercomputing Systems AG (SCS) employs ~130 engineers. The following people are relevant for this proposal (although the implementation would be done by 1-2 people mainly, others are available to contribute their expertise on demand):

* Alain Brenzikofer, Department Head Decentralized Systems
* Noa Melchior
* Christian Langenbacher
* Marcel Frei
* Sabine Proll
* Armin Häberling
* Sascha Montellese
* Juraj Skripsky

## Team Website

* https://www.scs.ch/en/about-scs/departments/decentralized-systems/

## Legal Structure

Swiss AG

## Team's Experience

As an engineering services company SCS AG has more than 25 years of experience in the fields of electronics, software and system design. Profound know-how, solid methodological competence as well as efficient project management are the foundation of our success.

Most programming experience in the following languages: C/C++, C#, Java, Python and VHDL.

Alain Brenzikofer follows Blockchain developments since 2011. He works for SCS since 2012 where he started working on blockchain projects in 2016 and was appointed to lead a new department for "decentralized systems" in summer 2018. As a private initiative, he designed a new cryptocurrency ecosystem [encointer - An Ecological, Egalitarian and Private Cryptocurrency and Self-Sovereign Identity System](https://encointer.org) . A project he currently intends to realize based on Substrate (including this privacy extension).

Our team is part of the [Quartierstrom project](https://quartier-strom.ch), implementing and currently field-testing a decentralized P2P energy market in Switzerland together with ETHZ, Bosch IoT Lab, HSLU and others.
SCS is in charge of the development of a dynamic grid usage-tariff smart contract as well as privacy-by-design concepts for the decentralized energy auction, thereby investigating and evaluating Zero-Knowledge Proofs, Linkable Ring Signatures, Multi-Party Computation as well as Trusted Execution Environments.

Moreover, we've developed a PoC for Electric Vehicle charging process on blockchain based on Parity Ethereum: https://youtu.be/xJUKNlV79pg

For trusted sensor oracles, Alain wrote a [whitepaper on decentralized trusted timestmping](https://www.scs.ch/wp-content/uploads/2017/01/trusted-sensor-whitepaper.pdf).

A few further blockchain projects are subject to NDAs.

## Team Code Repos

* https://github.com/scs
  * https://github.com/scs/leanXcam/wiki

### Private Endeavours by our Team Members

Sascha Montellese

* https://github.com/Montellese/xbmc/graphs/contributors
* https://github.com/Montellese/cpp-signal
* https://github.com/Montellese/cpp-cache

Armin Häberling (Rust)

* https://github.com/arminha?utf8=%E2%9C%93&tab=repositories&q=&type=&language=rust

Alain Brenzikofer

* https://github.com/encointer/simulations

Juraj Skripsky

* https://github.com/mono/mono/commits?author=jskripsky

## Team LinkedIn Profiles

https://www.linkedin.com/in/alain-brenzikofer-9a4480165/

https://www.linkedin.com/in/noa-melchior-674501173/

https://www.linkedin.com/in/sabine-proll-5a7118153/

## Development Roadmap

As Substrate has no stable release yet, we'd start from what is there (the beta2 release at time of writing). Changes to Substrate might cause refactorings delaying the plan.

* Start: within 3 weeks after grant awarding
* **M1** (4 weeks): Substrate SGX PoC1. Docker container running a Substrate node with a simple native demo runtime inside an SGX enclave.
* **M2** (3 weeks): Substrate SGX PoC2. Running WASMI inside enclave.
* **M3** (2 weeks): *simple* a-priori enclave provisioning V1.0 using the approach suggested by Hyperledger Sawtooth PDO
* **M4** (4 weeks): enclave provisioning V2.0 using multi-party key agreement among enclaves
* starting after M3 we'd put the platform to use for one of our existing customers
* [encointer](https://encointer.org) Blockchain PoC would be built on M4
* further plans / new grant?: implement POET consensus for Substrate (based on [Hyperledger Sawtooth POET](https://sawtooth.hyperledger.org/docs/core/releases/1.0/architecture/poet.html))

## Additional Information

### What work has been done so far?

Getting familiar with Substrate's code base.

### Have you applied for other grants so far?

No.

### Are there any other projects similar to yours?

Not to our knowledge.
