# MPC signing and homomorphic encryption primitives

## Project Description

### Brief description

MPC (multi-party computation) signing is a mechanism which allows the owners of several "key shards" to engage in a zero knowledge protocol in order to produce a single digital signature. This achieves essentially the same goals as multisignature, yet without any assumptions from the underlying layer, and additional benefits like the ability of implementing shard issuance, revocation, and rotation.

Homomorphic encryption is a primary mechanism which enables MPC signing, but it is usable on its own for performing limited computation over sensitive data.

There is also a number of non-interactive zero knowledge proofs that power MPC signing, but are interesting on their own.

### Why this project is good for the ecosystem

These building blocks are quite orthogonal to each other and may prove valuable in various blockchain deployments, to name a few:
  * Distributed custody of assets that are accessed in automatic way (so called "hot wallets")
  * Simple smart contracts - token swaps, escrows
  * Private voting

### How this integrates into Substrate

Our deliverables are Rust libraries implementing aforementioned primitives.

### Why our team is interested

## Team members
* Nikita Lesnikov
* Alexey Dziadziuk

## Team Website
* [Shard X](https://shardx.io/)

## Legal Structure
These details will be shared privately.

## Team's experience
Our team members have experience in distributed systems engineering, network protocol design & implementation, Ethereum development (smart contracts, most notably DEX). We share several notable competitive programming awards.

## Team Code Repos
Unfortunately, most of our code is not open-source yet.

## Team LinkedIn Profiles
  * [Nikita Lesnikov](https://www.linkedin.com/in/nikita-lesnikov-63136948/)
  * [Alexey Dziadziuk](https://www.linkedin.com/in/aliaksei-dziadziuk-116a3113a/)

## Development Roadmap

Milestone 1 — Substrate modules for MPC signing - 1 month
  * We create a Substrate module showcasing MPC threshold signatures over Curve25519/SR25519.
  * Functionality is demonstrated by the ability to transfer assets authorized with a single signature, yet said signature is produced over an MPC protocol completely off-chain.
  * Deliverable is a set of Rust modules implementing said functionality to be used within Substrate.

Milestone 2 — Shard issuance, revocation, rotation — 1 month
  * We extend the MPC signing framework with said functionality.
  * Functionality is demonstrated by the ability to manage the set of signers for a single public key without affecting the said public key.
  * Deliverable is a set of Rust modules implementing said functionality to be used within Substrate.

Milestone 3 — ECDSA support — 1 month
  * ECDSA is an important legacy digital signature scheme, and supporting it is useful in the context of building inter-chain bridges
  * We extend the MPC signing framework to support MPC threshold signatures over secp256k1 ECDSA.
  * Functionality is demonstrated by supporting all of the above on Ethereum.
  * Deliverable is once again a set of Rust modules implementing said functionality to be used within Substrate.

## Additional Information

### What work have been done so far?

We have a functional implementation of MPC signing for Ethereum & Bitcoin ([API docs](https://api.shardx.io/docs)).

### Are there any other projects similar to yours?

 * [KZen Research repository](https://github.com/KZen-networks) - Rust, research implementations of MPC ceremonies
 * [Unbound MPC libraries](https://github.com/unbound-tech/blockchain-crypto-mpc/blob/master/docs/Unbound_Cryptocurrency_Wallet_Library_White_Paper.md) - C++ implementation of a 2-of-2 MPC signing & key derivation using garbled circuits
 * [Binance TSS](https://github.com/binance-chain/tss-lib#how-to-use-this-securely]) - Go implementation of threshold MPC signing

### How is your project different?

Our project aims to fulfill those goals which we believe have not received enough attention so far:
  * Offline signing - we prefer to minimize the number of rounds rather than communication amount, to make airgapped usage easier for custody
  * HSM targeting - we optimize specifically for resource-constrained environments like TEEs
  * Permissive licensing - our code does not have GPL/LGPL dependencies
