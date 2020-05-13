# AssemblyScript Runtime Proposal

## Project Description

*In response to the Alternative Polkadot Runtime Generation (AssemblyScript) RFP.*

Polkadot has the ability to load, swap or upgrade it’s Blockchain features by having a decoupled design. The two main components are the Polkadot Host and the supplied Wasm code that is executed in the Polkadot Runtime Environment using a Wasm Interpreter.

Currently the most matured way of generating Runtimes is using Rust and Parity-built tools. The end goal of this project is to deliver the tools necessary to build Runtimes in AS, however in this initial project we will define, prioritise and deliver an Account-Based PoC AS Runtime. In order to do that, we need to develop utils and modules in AssemblyScript first.

Some of the deliverables listed in this proposal are the utilities that will accommodate the calls between a Polkadot Runtime and AS Wasm Runtime blob.

The main benefit of delivering those utilities is that everyone building AS Wasm Runtimes will have to use them, otherwise they must implement them themselves. Having such libraries available will help anyone who wants to develop their runtime in AS.

The other part of the deliverables is the Account-based PoC AS Runtime. We think that it will be beneficial because it will provide a better understanding of the work required for developing AS Runtime Generation tool and it would be the first step towards that goal. 

LimeChain is a blockchain-agnostic development company with a strong passion for developer tooling. We see Polkadot as an exciting technology and we hope to be able to help the developer community through various dev tools and implementations.


## Team members
* Daniel Ivanov, Christian Vesselinov (leads)
* Lyubomir Kiprov


## Team Website	
* https://limechain.tech

## Legal Structure

* LimeLabs Ltd., incorporated in Bulgaria, Dragan Tsankov 23A, 1113, Sofia, Bulgaria

## Team's experience
LimeChain is a blockchain development company with offices in London, UK and Sofia, Bulgaria. Since 2017, LimeChain has worked on 50+ blockchain projects, including a strong track record of building developer tools for different protocols such as Ethereum, EOS, Aeternity and Corda. Some of the companies LimeChain has worked with are Celo, P&G, Raiffeisenbank, Status, Dapper Labs and Maker among others. The proposed developer team in particular also has experience with Substrate.

The team is currently working on a AssemblyScript implementation of the SCALE codec:
- https://github.com/LimeChain/assemblyscript-scale-codec

A few Interesting commits:
- https://github.com/aeternity/aepp-aeproject-js
- https://github.com/LimeChain/etherlime
- https://github.com/LimeChain/eoslime


## Team Code Repos
* https://github.com/LimeChain
* https://github.com/Daniel-K-Ivanov
* https://github.com/bakasura980
* https://github.com/thcrnk

## Team LinkedIn Profiles
* https://www.linkedin.com/in/daniel-k-ivanov/;
* https://www.linkedin.com/in/lyubomir-kiprov/;
* https://www.linkedin.com/in/chris-veselinov/

## Development Roadmap

Based on our research we have concluded that there are 3 major components that will be reused in any AssemblyScript Runtime. The three components are:
- AssemblyScript SCALE Codec
- Polkadot WASM API
- Runtime Interface Client
In addition to the ones listed above, anyone who wants to build AS runtime will have to implement Primitives and Modules depending on their use case. Most of the Primitives and Modules will be required in every Runtime (f.e Balances).


Below we provide an **example roadmap**. In the descriptions it should be clear how the project is related to Substrate and/or Polkadot. We recommend that the scope of the work can fit within a 3 month period and that teams structure their roadmap as 1 month = 1 milestone. It is always best to describe the functionality we should expect, plus how we can check that such functionality exists in the product.

For each milestone:
* Please be sure to include a specification of the software. The level of detail must be enough so that we are able to test that the software meets the specification.
* Please include total amount of funding requested per milestone. Funding can be in fiat (CHF, EUR or USD) or in DOTs. It can also be in a combination of fiat and DOTs. Please reach out to grants@web3.foundation to discuss what amount in fiat and DOTs would be appropriate for your project.
* Please note that we require documentation (e.g. tutorials) in each milestone. This ensures that the code can be widely used by the community.
* Please commit to providing a docker container for the delivery of your project. 
* Please indicate the number of Full-Time Employees working on each milestone, and include the number of days along with their cost per day.

### Milestone 1 — Implement Substrate Modules — 1 month — $10,000
* We will create a Substrate module that will... (Please list the functions that will be coded for the first milestone).
* We will deliver a working module, along with a simple tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works.
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will build a Docker image with (e.g.) our Substrate chain, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

### Milestone 2 — Additional features — 1 month — $10,000
* We will create a... (Describe the next round of features and functions that will be added).
* We will deliver... (Explain how you will demonstrate that the functionality you built will work as intended).
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will build a Docker image with (e.g.) our Substrate chain, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

### Milestone 3 — Additional features — 1 month — $10,000
* We will create a... (Describe the next round of features and functions that will be added).
* We will deliver... (Explain how you will demonstrate that the functionality you built will work as intended).
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will build a Docker image with (e.g.) our Substrate chain, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

## Future Plans
* Please include the team's long-term plans and intentions.

## Additional Information
Any additional information that you think is relevant to this application that hasn't already been included.

Possible additional information to include:
* What work has been done so far?
* Are there are any teams who have already contributed (financially) to the project?
* Have you applied for other grants so far?
* Are there any other projects similar to yours? If so, how is your project different?  
