# SR25519 Ports to C and C#

## Project Description

### Brief Description

Currently only one implementation of Sr25519 signing algorithm (a.k.a. Ritstretto255, a.k.a. Schnorrkel-Ristretto) is known and finished: Curve255-dalek in Rust. Also, a C implementation (curve255-donna) was stopped half done in April this year. Also, a Go implementation is mentioned in Ristretto website, but the last commit was done in May this year, and it looks less finished that C implementation.

We have researched portability of SR25519 into other mainstream languages such as C and C# and conclude that this is possible to do. 

We will deliver SR25519 library implemented in pure C as well as C# that is capable of producing a valid signature and validating a signature. The validity of signature can be verified with an existing Rust library. Also, the libraries should be capable to verify signatures produced by an existing Rust library.

### Why SR25519 Ports is Good for the Ecosystem

Having only one single Rust implementation presents two major portability problems:

* If Rust cross-compiler is not available (like for many embedded CPUs), linking or pinvoking of Rust library becomes impossible
* When Rust compiler or cross-compiler is available, pinvoking of Rust library is platform dependent and in many cases (e.g. with .NET) is not solved by finding an appropriate compiler: Some additional code tweaks are needed

Having multiple implementations of SR25519 will allow developers in multiple langauges to integrate with Substrate natively without Rust dependency.

### How SR25519 Ports Integrates into Substrate

SR25519 is one of the signing algorithms Substrate uses. Alexander testnet version uses SR25519 based on Schnorrkel 0.1.1 and Kusama and futher versions of network use SR25519 based on Schnorrkel v.0.8.5, both of which will be implemented within this grant application.  

### Why our Team is Interested

We've been working on several Client APIs for Substrate, noticed this portability problem and got interested. This is an exciting problem to solve, and we believe it will make jobs of many Substrate developers easier.

## Team members
* Alexander Mitrovich
* Greg Zaytsev
* Maksim Styrgin
* Mikhail Zaicev (professor of Higher Algebra, Moscow State University)

## Team Website
* http://usetech.com/blockchain.html

## Legal Structure
These details will be shared privately via our Google Form.

## Team's experience
Our team members each have more then 15 years of IT experience in managing projects and writing software for product companies and large enterprises alike. We created the Blockchain practice in 2016 and have done dozens of projects for clients across the globe on variety of blochchains, mostly on Ethereum.

## Team Code Repos
* https://github.com/usetech-llc/polkadot_api_dotnet
* https://github.com/usetech-llc/polkadot_api_cpp
* https://github.com/usetech-llc/multichain_airdrop
* https://github.com/usetech-llc/neupool
* https://github.com/gregzaitsev/platform-contracts
* https://github.com/gregzaitsev/wasmcharts_page
* https://github.com/gregzaitsev/platform-frontend
* https://github.com/usetech-llc/unicom
* https://github.com/usetech-llc/votingrelay
* https://github.com/usetech-llc/forever_coin
* https://github.com/usetech-llc/taklimakan-network

## Team LinkedIn Profiles
* https://www.linkedin.com/in/alexandermitrovich/
* https://www.linkedin.com/comm/in/gregory-zaitsev-95ba633

## Development Roadmap
Project roadmap and financial plan will be shared privately via Google Form.

Long term plans start with developing APIs for all mainstream languages as well as in-depth API improvement. As Polkadot community high level usecases evolve, API will adapt.

Also, our team plans to implement broader spectrum of applications such as

* Decentralized Non-Fungible Token Exchange
* Multi-chain token issuance
* Cross-chain Payment Gateways
* etc.

## Additional Information

### What work has been done so far?

C++ and C# APIs are delivered. Source code and documentation are available at these public repositories: 
* https://github.com/usetech-llc/polkadot_api_cpp
* https://github.com/usetech-llc/polkadot_api_dotnet

### Are there any other projects similar to yours? How is our project different?

1. Ristretto255 C Implementation by Frank Denis - does not cover SR25519
https://download.libsodium.org/doc/advanced/point-arithmetic/ristretto

2. C implementation by Isis Agora, unfinished and stopped (Isis kindly confirmed she does not have an intention to finish it):
https://github.com/isislovecruft/ristretto-donna

C# implementation is not covered by anyone yet.
