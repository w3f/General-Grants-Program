# Project name

Java implementation of Schnorr signature scheme on Ristretto version of Ed25519.

## Project Description

We propose implementing the SR25519 signature Scheme in Java, with full test suite and documentation.

We believe broadening Polkadot's technology stack to a popular and performanant language like Java will improve visibility and adoption.

This library can then be used by other Java elements in Polkadot's stack for signature generation/verification.

As experienced Java engineers who are looking to get more involved in the Polkadot ecosystem, we this project as a good entrypoint.


## Team members

Ankur Shah and Andrew Dickson

## Team Website	

https://www.mathshop.io

## Team's experience

In addition to extensive closed-source client-based software development, we have been consulting in the blockchain space for the last three years, both in product, mechanism design, blockchain architecture, and implementation.
While our recent work has focused more on research than code, recent software projects include an implementation of [Osrank in Java](https://github.com/oscoin/osrank-java) (for Radicle) and a proof of concept for a [simple libsnark/ZKP use case](https://github.com/stratumn/pequin/commits?author=ankurdelight) (for Stratumn).


## Team Code Repos
* https://github.com/ankurdelight
* https://github.com/andrewpdickson

## Team LinkedIn Profiles
* https://www.linkedin.com/in/ankurdelight/
* https://www.linkedin.com/in/andrew-p-dickson/

## Development Roadmap

* Total Time: 5 weeks
* Each week includes each applicant working part-time, for a totlal of 40 human-hours / week
* Code will be licensed with Apache 2.0

### Milestone 1 — Implement SR25519 Signatures — 4 weeks
* We will provide a well-documented Java implementation for SR25519 signatures, including any necessary mathematical libraries (ie Ristretto)
* The code will have proper unit-test coverage to ensure functionality and robustness.

### Milestone 2 — Tutorial and Docker Image — 1 week
* We will write a user-friendly tutorial for signing and verifying signatures.
* We will build a Docker image for ease of testing/deployment.

## Future Plans
* We would be interested in getting more involved with cryptographic implementations (multi-sigs? HD?) at Polkadot. We are also interested in building infrastructure for performance testing for hosts, RPC-clients, and network topologies.

## Additional Information

### Relevant work

We have looked at [existing C# implementation](https://github.com/usetech-llc/sr25519_dotnet), dalek [ristretoo specs](https://ristretto.group/) and [implementation](https://github.com/dalek-cryptography/curve25519-dalek) of SR25519, and Java implementation of [Ristretto](https://github.com/cryptography-cafe/curve25519-elisabeth) and [ed25519](https://github.com/str4d/ed25519-java).
