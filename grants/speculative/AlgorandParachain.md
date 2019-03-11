# Algorand Parachain
## Project Description
This grant application supports research and development of a Polkadot parachain with Algorand consensus protocol. 

Algorand defines a cryptographic sortition-based algorithm for choosing a random subset of validators in each round of the protocol. A custom BFT-like gossip protocol is then used to agree on canonical network state for the next round (i.e., agree on the next block). Algorand's current security model assumes that an adversary may corrupt validators instantly, which entails melding the sortition participation commitment with making the validating decision.

While this model is reasonably suited for block consensus, a lot of real-life applications require delays between these two parts, e.g., in legal dispute resolution a committee of legal specialists will want to participate in the sortition and verify that they have won before considering the provided materials, as otherwise they will likely be doing redundant work that will not be rewarded.

We propose an extension to the base Algorand protocol that will allow the committee to respond with a delay after winning the sortition, based on a cryptographic key derivation scheme. Such protocol would allow to form decentralized committees for various services in other Polkadot parachains.

With this grant we will be able to focus on this project full-time for 3 months, during which the following scope of work will be performed:
* Formal documentation for a Substrate runtime that adheres to specification of Algorand by (Micali et al., 2017).
* Implementation of documented runtime on Substrate.
* R&D concerning extension of Algorand protocol in order to support delayed response for a decentralized committee protocol.
* Formal documentation of a decentralized committee protocol.
* Extending the existing runtime with the documented protocol.
## Team members
* Alexander Bokhenek - Lead
* Ivan Kamakin
## Team Website
https://moderntoken.com 
## Legal Structure
TBD, the exact structure is currently considered.
## Team's experience
Modern Token is a blockchain business and technology consultancy firm established in April 2017. Members of our technical staff has 3 years of experience in blockchain industry on average. Our team performs various R&D services regarding consensus algorithms, platform economics (design and modelling) and platform architecture. For an overview of our previous work see https://moderntoken.com/works.
## Team Code Repos
* https://github.com/Van0k
* https://github.com/SirFrancisDrake
## Team LinkedIn Profiles
* https://www.linkedin.com/in/ivan-kamakin-55951b152/ 
* https://www.linkedin.com/in/alexander-bokhenek-9701a2176/ 
## Intended language of development
* Rust
* Python or Haskell for PoC
While Rust will be used for development of the resulting parachain, Python or Haskell may be used in some cases for fast prototyping.
## Development Roadmap
The milestones are spread out over a total of 3 months as following:
* **Milestone 1: Algorand Parachain R&D**
  * Develop a specification of Algorand runtime for Substrate
  * Create first PoC specification
  * Deliverables: A paper with a formal specification released publicly
  * Duration: 1 month
  * Funding: EUR 10’000
* **Milestone 2: Implementation of Algorand Parachain**
  * Stable implementation of Algorand runtime in Rust (node client)
  * CI/CD tools
  * Tests
  * Deliverables: A public repository on Github with a node client
  * Duration: 2 weeks
  * Funding: EUR 5’000
* **Milestone 3: Decentralized committee R&D**
  * Specification of a key derivation scheme for a decentralized committee protocol
  * Proofs of security
  * Overview of possible applications
  * Deliverables:  A paper with a formal specification released publicly
  * Duration: 1 month
  * Funding: EUR 10’000
* **Milestone 4: Implementation of decentralized committee protocol**
  * A runtime module for a decentralized committee protocol
  * Deliverables: A public release on Github in a separate pull request/branch.
  * Duration: 2 weeks
  * Funding: EUR 5’000
  
The total funding amount is EUR 30’000. Currently the project is funded by Modern Token internally. Modern Token will release the parachain software publicly under a permissive license and will possibly monetize it through consultancy and integration services.
## Additional Information
[Algorand Theoretical Paper](https://www.algorand.com/sites/default/files/2018-11/Theoretical.pdf)
