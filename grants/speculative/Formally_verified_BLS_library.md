# Formally Verified BLS12-381 Signature Library

## Project Description
This proposal seeks to extend language support of the `blst` BLS signature library and help fund formal verification of the library. BLS signatures are being adopted by a variety of blockchain protocols due to their [efficient aggregation properties](https://wiki.polkadot.network/docs/en/learn-keys#are-bls-signatures-used-in-polkadot). We have recently implemented a fast MIT-licensed BLS signature library called [blst](https://github.com/supranational/blst). The library is the fastest known implementation and is compliant with the draft [IETF specification](https://tools.ietf.org/html/draft-irtf-cfrg-bls-signature-02). The library is also focused on security (e.g. constant time) and is about to begin formal verification. This goal of this library is to be a performant and secure building block for the ecosystem, as `libsecp256k1` was for 'Blockchain 1.0'. The library has been adopted by both [Eth2](https://twitter.com/paulhauner/status/1280760605373161472) and [Filecoin](https://twitter.com/Whyrusleeping/status/1287866736230842368) clients.

## Team members
* Simon Peffers
* Sean Gulley
* Kelly Olson
* Andy Polyakov

## Team Website	
* https://supranational.net

## Legal Structure 
See Google Form submission

## Team's Experience
* Sean Gulley and Simon Peffers are former Principal Engineers at Intel’s Data Center Innovation Group. They have worked for over two decades on algorithmic acceleration, including cryptography.
* Kelly Olson is a former director in the Security Division at Intel Corporation and has served on the Technical Steering Committee and Governing Board of the Linux Foundation's Hyperledger project.
* Andy Polyakov has been implementing open source cryptography for over two decades. He is currently a maintainer and a top 5 contributor by commits to the OpenSSL library.

### Example Repositories

* [blst BLS Signature Library](https://github.com/supranational/blst)

* [CRYPTOGAMS](https://github.com/dot-asm/cryptogams)

## Team Code Repos
* https://github.com/supranational

## Development Roadmap

### Milestone 1 — Batch Operation Performance Optimizations — 1 months
* Implement affine point addition and montgomery batch inversion techniques to improve batch operation performance
* Implement use of endomorphisms to improve [scalar multiplication performance](https://eprint.iacr.org/2013/158.pdf)
* Develop inline documentation of the code

### Milestone 2 — C++, Java, and Python Bindings — 2 month
* Implement C++ bindings for the `blst` library to complement the existing Rust and Go bindings
* Leverage C++ bindings to provide object oriented bindings for Java and Python use
* Release a basic tutorial documenting how to use the C++, Java, and Python APIs for signature operations

### Milestone 3 — Documentation — 1 month
* Document the theory of operation of the library that connects the basics of pairing-based cryptography with the interface provided by the library
* Develop documentation for each bindings APIs
* Provide examples of applications that are leveraging the `blst` library and its bindings

### Milestone 4 — Formal Verification Complete and Released — 5 months
* Complete formal verification of the `blst` implementation in C by ensuring the implementation matches the formal specification
* Open Source the [Cryptol](https://github.com/GaloisInc/cryptol) implementation of the IETF specification that the library will be verified against
* Release a brief report documenting the findings of the formal verification activities

### Milestone 5 — Integration Support for Polkadot — 1 month
* Collaborate directly with Polkadot/Substrate developers to assist them in integrating the `blst` BLS12-381 signature library

## Future Plans
* We intend to extend the compatibility and functionality of the library by supporting more platforms (as proposed in this grant), as well as by adding new functionality. One area we are particularly excited about is extending the library beyond signature operations to support other cryptographic primitives using the BLS12-381 curve such as vector commitmentments and SNARKs. Other future activities include maintenance of the library and further performance optimizations.

## Additional Information
### What work has been done so far?
The `blst` library currently supports x86 and ARM64 platforms, as well as Linux, Windows, and Mac. The library currently has both Rust and Go bindings, and we intend to develop additional bindings directly and through SWIG. Both the Rust and Go bindings have already been integrated into blockchain client software.

### Are there any teams who have already contributed (financially) to the project?
Both the Ethereum Foundation and Protocol Labs have provided support for this library.

### Are there any other projects similar to yours? If so, how is your project different?  
There are a number of other BLS12-381 libraries available under an open source license. Our library is faster than all other implementations which is critical when verifying large aggregate signatures. Our library is also focused on security and is the only BLS library we know of that is planning to be formally verified.