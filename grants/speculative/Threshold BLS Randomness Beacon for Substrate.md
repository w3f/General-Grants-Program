# Threshold BLS Randomness Beacon for Substrate

## Project Description

The goal of the project is to construct a Substrate pallet implementing a randomness beacon based on the well-known idea of extracting randomness from threshold signatures [[1]](https://link.springer.com/article/10.1007/s00145-005-0318-0), specifically, using the BLS signature scheme [[2](https://www.iacr.org/archive/pkc2003/25670031/25670031.pdf), [3](https://arxiv.org/pdf/1908.05156.pdf), [4](https://arxiv.org/pdf/1805.04548.pdf)]. The main idea of such a randomness beacon is that a committee of N nodes holds keys for threshold (⅔N) BLS signatures and periodically signs specific nonces -- randomness then comes from the unique signatures that are created in this process. Importantly, the obtained randomness cannot be biased unless an adversary controls more than (⅔N) nodes and stays live unless an adversary controls more than (⅓N) nodes. 
To run such a randomness beacon along a blockchain there are essentially two options for the choice of a committee:
1. In case when this blockchain’s consensus protocol is committee-based (i.e. has either a fixed, or infrequently changing set of block authors) the consensus committee can be used to run the beacon.
2. Otherwise, for instance when PoW or some form of permissionless PoS is used for consensus, a trusted committee of nodes needs to be selected (by some means) to run the beacon chain.

Thus, in other words, such a beacon in the setting with committee-based consensus has no additional requirements, and in the “permissionless” setting requires a “trusted” committee to be selected.
While the overall idea of using threshold signatures as a randomness source is indeed quite simple and seemingly easy to implement, the true challenge lies in the setup phase during which the threshold keys of the nodes are generated. Such a setup is called Distributed Key Generation (DKG) in the literature and has been subject of extensive research. Several solutions have been proposed for DKG, adapted to various assumptions on the network and the adversary [[1](https://link.springer.com/article/10.1007/s00145-005-0318-0), [5](https://link.springer.com/chapter/10.1007/3-540-46416-6_47), [6](https://link.springer.com/chapter/10.1007/3-540-36563-X_26), [7](https://cypherpunks.ca/~iang/pubs/DKG.pdf)], including the recent work of the authors of this grant proposal [[3]](https://arxiv.org/pdf/1908.05156.pdf) that achieves DKG in the fully asynchronous BFT setting. 

In the specific setting of implementing DKG within a Substrate module, we believe that one can take advantage of having access to a blockchain and use it as a broadcast channel, in order to obtain a robust DKG protocol that does not suffer from issues related to synchronization. More specifically, we believe that a design akin to the protocol proposed by  Schindler et. al. [[8]](https://eprint.iacr.org/2019/985), with certain minor adjustments would be the best fit for this setting.

##### Why is this project good for the ecosystem:

Fair randomness plays an important role in any blockchain ecosystem. Not only can it serve as a useful primitive for smart contracts in a variety of contexts such as: lotteries, producing unpredictable challenges, or instantiating random protocol parameters, but it also enables a much richer class of blockchain governance models by allowing randomly rotating committees. At this point there are two ways available to produce randomness in substrate chains:
- Collective Coin Flipping via pallet_randomness_collective_flip
- Randomness from VRF (via pallet_babe) as a byproduct of the BABE consensus 

Neither of these options offers a generic, safe source of randomness for blockchain use -- Collective Coin Flipping is relatively weak, and can be biased by the adversary, and the second option can be used only on chains with BABE consensus. We would like to implement an alternative that uses a state-of-the-art technique based on extracting randomness from threshold BLS signatures. Given our expertise in designing randomness sources, both at the theoretical layer, as well as, at implementing them, we believe that we can create a developer-friendly pallet that realizes this idea, consistent with the vision of Substrate as a modular, highly customizable framework for building blockchains. 

One particular application of our implementation would be to deploy a standalone parachain whose sole purpose is to produce safe randomness for the use in the entire Polkadot ecosystem. 


##### An indication of how you will integrate this project into Substrate / Polkadot.

We would like to build the randomness beacon as a Substrate pallet.


##### An indication of why your team is interested in creating this project.

After learning about Substrate our team members became great fans of the framework, especially because the design choices within Substrate make it elegant, future-proof and highly flexible. We see great potential in Substrate as a universal tool, not only for fast prototyping of MVPs, but also as a default tech stack for rapidly deploying modern blockchain systems. 

To stimulate further growth of Substrate, we would like to offer our expertise in distributed randomness generation and contribute an important piece: a randomness beacon pallet that would allow for robust generation of unbiased randomness.


##### Team members:
* [Adam Gągol](https://www.linkedin.com/in/adam-g%C4%85gol-b07904154/)
* [Damian Straszak](https://www.linkedin.com/in/damian-straszak-98a2601a5/)
* [Michał Świętek](https://www.linkedin.com/in/micha%C5%82-%C5%9Bwi%C4%99tek-40720b168/)

##### Team Website	
* https://cardinals.cc


##### Team's experience
* We designed and implemented the first efficient asynchronous BFT randomness beacon allowing for high-scale deployment (https://arxiv.org/abs/1908.05156, independent work with [Kokoris-Spiegelman-Malkhi-Abraham](https://eprint.iacr.org/2019/1015.pdf)). 
* We designed and implemented an efficient [DAG-based consensus protocol](https://arxiv.org/abs/1908.05156).
* We designed and implemented a new [threshold ECDSA signature protocol](https://eprint.iacr.org/2020/498) with attributable faults.
* While we have implemented these protocols using Golang (see our repos) due to its relative simplicity and speed of development, we feel confident in Rust as well and are eager to code our next project using it as the main language. During the past weeks we got familiar with Substrate through substrate.dev tutorials and recipes. 


##### Team Code Repos
* [Consensus and randomness beacon](https://gitlab.com/alephledger/consensus-go)
* [threshold ECDSA](https://gitlab.com/cardinals1/threshold-ecdsa)


## Development Roadmap

* Total Estimated Duration: 12 weeks
* Full-time equivalent (FTE): 2.5

##### Milestone 1
We create a Substrate pallet implementing the functionality of a Randomness Beacon based on threshold BLS signatures, provided that the nodes forming the beacon committee already hold threshold BLS keys. In other words, we implement a Randomness Beacon leaving out the DKG part for now.
* Total Estimated Duration: 4 weeks
* Full-time equivalent (FTE): 2.5

| Deliverable  | Specification                                                                                                                                          | 
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| Repository   | A git repository containing source code and a README that describes the work done during this milestone and how to use the pallet at the current stage |
| Tests        | The code will have proper unit-test coverage to ensure functionality and robustness                                                                    | 
| Docker       | Docker image with a Substrate chain using our module, demonstrating its functionality                                                                  | 

##### Milestone 2
We will enrich our module with a Distributed Key Generation protocol, allowing a committee to run the randomness beacon without preconstructed keys. We plan to build this part using a top-down approach, thus the main objective would be to complete a high-level skeleton of the protocol, including what messages are sent and when, and the logic of how these messages impact the state of a node. For this milestone, we will likely leave out some independent details such as verifying correctness and consistency of the messages, dealing with zero-knowledge proofs.

* Total Estimated Duration: 4 weeks
* Full-time equivalent (FTE): 2.5

| Deliverable  | Specification                                                                                                                                          | 
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| Repository   | A git repository containing source code and a README that describes the work done during this milestone and how to use the pallet at the current stage |
| Tests        | The code will have proper unit-test coverage to ensure functionality and robustness                                                                    | 
| Docker       | Docker image with a Substrate chain using our module, demonstrating its functionality                                                                  | 


##### Milestone 3
We complete the details of the DKG protocol that have been left out at the previous Milestone. We complement the code with extensive documentation and write a tutorial. We run experiments in a distributed environment (AWS) and include the results in a report.

* Total Estimated Duration: 4 weeks
* Full-time equivalent (FTE): 2.5

| Deliverable        | Specification                                                                                                                                        |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Repository         | git repository including full code and README that fully describes the work done during the milestone and how to use the pallet at the current stage |
| Tests              | The code will have proper unit-test coverage to ensure functionality and robustness                                                                  |
| Docker             | Docker image with Substrate chain using our module, demonstrating its functionality                                                                  |
| Documentation      | Full documentation for the pallet                                                                                                                    |
| Tutorial           | Simple tutorial showing deployment of the pallet in PoS and PoW scenarios                                                                            |
| Experiments report | A report on the performance of the substrate generated on a distributed environment using AWS                                                        |
