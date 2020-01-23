# Zerochain
## Project Description
We are building a privacy-protecting parachain for Polkadot using zero-knowledge proofs. Zerochain is basically designed as a blockchain for storing the encrypted data. As usual, all data on blockchain is public and everyone can see it, but the data on Zerochain is encrypted so anyone can not see the data without the key for decryption.

In addition, Zerochain is the first implementation of account-based blockchain for privacy-preserving  and the first substrate node applied zero-knowledge proofs. The zk-SNARKs implementation for Substrate would be reusable for other projects on Substrate.

The three features of Zerochain are following:
* The optimization for the zero-knowledge proving cost
    * 18,278 constraints comparing to 106,604 constraints in Zcash(Sapling). (w/o address anonymity)
* The optimization for the on-chain storage cost
    * The encrypted balances are just overwritten unlike UTXO-based.
* The flexibility for the privacy-preserving applications
    * Designed to be easy to add some functionalities like confidential whitelists for assets and anonymous voting

Here is a high-level overview of the Zerochain scheme.
<div align="center">
<img src="https://user-images.githubusercontent.com/20852667/54922583-d4a16800-4f4b-11e9-8615-4a14d45206b8.png" width="600px">
</div>

You can find more details here:
https://medium.com/layerx/announcing-zerochain-5b08e158355d

## Team Members
* Osuke Sudo - Lead
* Ozaki Yoichi

## Team Website
https://layerx.co.jp/

## Legal Structure
incorporated in Japan

## Team's experience
LayerX is a blockchain company which has some separeted teams and projects. Zerochain is one of the focusing R&D project. The lead enginner Osuke has been working as an Ethereum smart contract developer and zero-knowledege proofs developer total for 2 years.

Osuke’s works on blockchain space are following.
* The first implementation of Plasma in Vyper
    * https://github.com/LayerXcom/plasma-mvp-vyper

* A 64bit-TinyRAM simulator in Go lang (The TinyRAM architecture is a random-access machine designed to be a convenient tool for expressing the correctness of nondeterministic computations like zk-SNARKs.)
    * https://github.com/LayerXcom/gram

* A Solidity implementation of the zk-STARKs verifier for a MiMC calculation (incomplete)
    * https://github.com/LayerXcom/stark-sol

* A zk-STARK implementation for fibonacci sequence in C++ and executing in Rust (using libstark)
    * C++: https://github.com/LayerXcom/libSTARK/tree/macOS/fibonacchiseq
    * Rust: https://github.com/osuketh/stark-rust

## Team Code Repos
* Zerochain: https://github.com/LayerXcom/zero-chain
* A UI for Zerochain: https://github.com/LayerXcom/zero-chain-ui

## Team LinkedIn Profiles
We are not on LinkedIn.

## Development Roadmap
The milestones are spread out over a total of 3 months as following:
* M1: Generating transaction on a browser as a (kind of) wasm wallet (2 weeks)
* M2: Implementation of a runtime module for confidential transfer fees (2 weeks)
* M3: Protecting from front running attacks (2 weeks)
* M4: Implementation of a runtime module for confidential fungible assets (2 weeks)
* M5: Implementation of anonymous transactions (4 weeks)

In addition, we will research and implement the small PoC for the new zero-knowledge proofs like SONICs, zkSTARKs and Bulletproof for eliminating the trusted setup problem of the current zk-SNARKs. 
We don’t include, however, these into the above milestones because it would take more time and not fix the specification yet.

## Additional Information
### What work has been done so far?
Implementing the MVP for confidential payment on Substrate.

### Have you applied for other grants so far?
No.

### Are there any other projects similar to yours?
* In terms of zero-knowlege proofs: Zcash, Monero, Grin

* In terms of privacy for substrate: [Substrate sgx proposal](https://github.com/w3f/Web3-collaboration/blob/master/grants/speculative/substrate_sgx_proposal.md)
