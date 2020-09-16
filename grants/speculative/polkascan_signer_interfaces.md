# Grant Application: Polkascan Signer Interfaces

## Project description
This project extends the Polkascan stack in general and extends Polkascan's Python libraries in particular with signing and signature verification capabilities by supporting two key methods for integrating with external signers.

1) Python Subkey Interface: for offline signing and signature verification.
2) Parity Signer Interface: for secure online signing.

Our organization is on an ongoing mission of building the Polkascan multi-chain explorer. Our fourth wave grant work left signing capabilities off-scope in our Python libraries. This project aims to provide full signing capabilities that can be used from within Python libraries and from user-facing Angular (web) applications.

### Why our project is good for the ecosystem
This project's deliverables provide Python-based signing and signature verification capabilities. Additionally this project's deliverables provide a fully independent Angular-based visual signer interface to Parity Signer. Both sets of deliverables provide signing and signature verification mechanisms which are fully independent of the currently dominant Javascript/Typescript mechanisms. Having fully independent implementations is good for the ecosystem as a whole. Needless to say, maturing and making available Python-based and Angular-based core components benefits the ecosystem.

### Why our team is interested
This work fits WEB3SCAN's (Polkascan's) short-term agenda of building its multi-chain explorer and its public instance at: https://polkascan.io.

## Organization & team
### Legal structure
Dutch BV (Limited Liability Company)

### Execution
Work of this grant will be contracted and executed by the legal structure, its employees or its subcontractors under direct supervision of the leadership team.

### Open-source license
All artifacts which result from this grant will be open-sourced under the GPLv3 license.

### Leadership team
* Emiel Sebastiaan (Emiel)
* David-Jan Hoogendoorn (Dave)
* Arjan Zijderveld (Arjan)

### Team's experience
Our team has worked together for over 10 years and is responsible for the Polkascan project, which provides the first and only multi-chain explorer for any Substrate-based blockchain. The team is also responsible for the Polkasource project, which provides ITSM services in the Polkadot ecosystem. 

### Team websites
#### WEB3SCAN
Company website: https://web3scan.com

#### Polkascan
* Live multi-chain explorer: https://polkascan.io
* Medium: https://medium.com/polkascan 
* Twitter: https://twitter.com/polkascan 

#### Polkasource
* Medium: https://medium.com/polkasource
* Twitter: https://twitter.com/polkasource
* DockerHub: https://hub.docker.com/u/polkasource

### Team code repositories
* openAware BV: https://github.com/openaware (internal repositories)
* Polkascan: https://github.com/polkascan (public open-source repositories)
* Polkasource: https://github.com/polkasource (public open-source repositories)
* Emiel: https://github.com/emielvanderhoek (personal GitHub account)
* Dave: https://github.com/dave4you (personal GitHub account)
* Arjan: https://github.com/arjanz (personal GitHub account)

### Team LinkedIn profiles
* Dave: https://nl.linkedin.com/in/dhoogendoorn
* Arjan: https://nl.linkedin.com/in/arjanzijderveld

## Development Roadmap
Please note the team also has other features and work items outside of this grant application (though all in relation to the Polkascan mission). This project extends prior artifacts and implements new artifacts:

1. Implement 'Py-Subkey':
    * a Python library that facilitates feature compatibility of Parity Technologies' Subkey application
2. Extend 'Py-Substrate-Interface':
    * new methods to facilitate signed transaction wrapping and submitting
3. Extend 'Substrate-Interface-API':
    * new methods to expose Python Substrate Interface library methods
4. Extend 'Substrate-Interface-GUI':
    * minimum functionality to demonstrate usage of all API-endpoints and methods
    * Various QR-interfaces to implement the Universal Offline Signature specification
5. Provide Docker support:
    * dockerfiles for independent repositories.
    * docker-compose setup for at least Kusama network.

## Funds Required Overall
30,000 USD. Willing to accept up to 70% of payment in vested DOTs.

### Timeline and Milestones
This project will be executed in two full months and can commence as soon as the grant application is approved.

#### Milestone 1: duration: 4 weeks
Milestone objectives: This milestone will result in `ed25519` and `sr25519` signing and signature verification capabilities for native Python applications. Its deliverables provide a basic library & application architecture that facilitates feature compatibility of Parity Technologies' Subkey CLI from within a Python library. In turn this provides signing and signature verification capabilities for native Python applications. Additionally these features will be made accessible through the Polkascan Substrate Interface API (a Python Falcon-application) and in turn though the Substrate Interface GUI (an Angular-application).

This milestone will cover work in the following artifacts:
- Artifact 1: `polkascan/py-subkey` repository on Github
- Artifact 3: `polkascan/substrate-interface-api` repository on Github
- Artifact 4: `polkascan/substrate-interface-gui` repository on Github
- Artifact 5: `polkascan/substrate-interface` repository on Github

1. Deliverables: Python Subkey architecture
The deliverables in this section will enable a basic library & application architecture that facilitates feature compatibility of Parity Technologies' Subkey application from within a Python library.
```
D1.1. New `polkascan/py-subkey` repository on Github.
D1.2. Basic `py-subkey` library architecture // Refer to the scope paragraph for implementation considerations.
D1.3. Setup of release and deployment workflows to the PyPi Package Index.
```

2. Deliverables: Feature compatibility with native Subkey
The deliverables in this section provide feature compatibility from within a Python library for Parity Technologies' Subkey application and its subcommands.

```
D2.1. Support for command `subkey` // Basic command support.
D2.1.a. Support for flag: '--help'/'-h' // Prints help information.
D2.1.b. Support for flag: '--version'/'-V' // Prints version information.
D2.2. Support for subcommand: `generate` // Generate a random account.
D2.2.a. Support for flag: '--ed25519'/'-e' // Use Ed25519/BIP39 cryptography.
D2.2.b. Support for flag: '--sr25519'/'-e' // Use Schnorr/Ristretto x25519/BIP39 cryptography.
D2.2.c. Support for option: '--network'/'-n' <network> // Specify a network. One of substrate (default), polkadot and kusama.
D2.2.d. Support for option: '--password'/'-p' <password> // The password for the key.
D2.2.e. Support for option:  '-w'/'--words' <words> // The number of words in the phrase to generate. One of 12 (default), 15, 18, 21 and 24.
D2.3. Support for subcommand: `inspect` // Gets a public key and a SS58 address from the provided input.
D2.3.a. Support for argument: 'secret seed' // Secret seed.
D2.3.b. Support for argument: 'secret URI' // Secret URI (with derivation paths and password).
D2.3.c. Support for argument: 'SS58' // SS58 address.
D2.3.d. Support for argument: 'public URI' // Public URI.
D2.4. Support for subcommand: `sign` // Sign a message, provided input, with a given (secret) key.
D2.4.a. Support for flag: '-h'/'--hex' // The message on input is hex-encoded data.
D2.4.b. Support for argument: 'message' // The message.
D2.4.c. Support for argument: 'suri' // The secret key URI.
D2.5. Support for subcommand: `verify` // Verify a signature for a message, provided on input, with a given (public or secret) key.
D2.5.a. Support for flag: '-h'/'--hex' // The message on input is hex-encoded data.
D2.5.b. Support for argument: 'message' // the message to verify.
D2.5.c. Support for argument: 'sig' // Signature, hex-encoded.
D2.5.d. Support for argument: 'uri' // The public or secret key URI.
D2.6. Support for subcommand: `vanity` // Generate a seed that provides a vanity address.
D2.6.a. Support for option: '--number'/'-n' <number> // Number of keys to generate [default: 1].
D2.6.b. Support for argument: 'pattern' // Desired pattern.
```

3. Deliverables: Unit tests for Python Subkey
The deliverables in this section will provide unit tests for the `py-subkey` library to show intended use and conformity of the deliverables in section 2.
```
D3.1. Key-pair lifecycle: generate key-pair.
D3.2. Key-pair lifecycle: inspect generated key-pair.
D3.3. Key-pair lifecycle: sign message with generated key-pair.
D3.4. Key-pair lifecycle: verify message with generated key-pair.
D3.5. Permutations of D3.1, D3.2, D3.3 & D3.4 to cover various (sub)command options & flags.
```

4. Deliverables: Feature compatibility of `py-subkey` in `substrate-interface-api`
The deliverables in this section will enable feature compatibility of the Python Subkey library (`py-subkey`) from within the Substrate Interface API's JSON-RPC API. The primary objective of this deliverable is to showcase conformity of the deliverables in section 1 & 2 in a user friendly way (i.e. use of a JSON-RPC API through Postman).
```
D4.1. JSON-RPC API method: subkey_generate([arguments/options/flags]) // Generate a random account.
D4.2. JSON-RPC API method: subkey_inspect([arguments/options/flags]) // Gets a public key and a SS58 address from the provided input.
D4.3. JSON-RPC API method: subkey_sign([arguments/options/flags]) // Sign a message, provided input, with a given (secret) key.
D4.4. JSON-RPC API method: subkey_vanity([arguments/options/flags]) // Generate a seed that provides a vanity address.
D4.5. JSON-RPC API method: subkey_verify([arguments/options/flags]) // Verify a signature for a message, provided on input, with a given (public or secret) key.
```

5. Deliverables: Feature compatibility of `substrate-interface-api` (and in turn `py-subkey`) in `substrate-interface-gui`. The primary objective of this deliverable is to showcase conformity of the deliverables in section 1, 2 & 3 in a user friendly way (i.e. listing the JSON-RPC API methods of deliverable 4 in a user interface).
```
D5.1. Availablility of JSON-RPC API methods of deliverables in section 4 in the RPC section.
```
Documentation
- README.md: Getting started with the Python Subkey library
- SECURITY.md: Security considerations the Python Subkey library
- PDOC: Auto-generate API documentation for Python projects for the Python Subkey library

Scope
- The Subkey subcommand `transfer` will not be supported by `py-subkey`. The `transfer`-subcommand is a higher level signing feature that will be supported in milestone 2.
- The Subkey subcommand `sign-transaction` will not be supported by `py-subkey`. Correspondence with Parity Technologies taught is that this subcommand is deprecated. Additionally the `sign-transaction`-subcommand is a higher level signing feature that will be supported in milestone 2.
- There is a timeboxing constraint for implementing Subkey feature compatibility. Please refer to our note below.

Implementation considerations for Subkey feature compatibility: We have considered a number of different implementation to provide Subkey feature compatibility within the Python Subkey library. 
1) External `ed25519` and `sr25519` Python libraries
2) RUST-bindings for the Python interpreter 
3) CLI-wrapper subprocesses. 

The first option will currently not provide a viable solution. Although some work has been done to create a sr25519 Python Library (https://gitlab.com/kauriid/schnorrpy/), this project is not considered active and mature enough to use in our project. This argument alone is sufficient to not go down this pat. That said, there are a number of other concerns not to choose for this approach which we won't document here.

Both the second and third option are considered viable solutions with some security and uncertainty trade-offs. Our preference goes to the second option for it allows us to directly utilize native RUST-code via bindings. We will timebox our implementation efforts to deal with the implementation uncertainty and default to the third option of the CLI-wrapper subsprocesses implementation of Subkey.

Milestone Payout: 15,000 USD


#### Milestone 2: duration: 4 weeks
Milestone objectives: This milestone will result in generalized Substrate offline and secure online transaction-signing capabilities for any Substrate-based network.

This milestone will cover work in the following artifacts:
- Artifact 2: `polkascan/py-substrate-interface` repository on Github
- Artifact 3: `polkascan/substrate-interface-api` repository on Github
- Artifact 4: `polkascan/substrate-interface-gui` repository on Github
- Artifact 5: `polkascan/substrate-interface` repository on Github

6. Deliverables: Python Substrate Interface library extensions
The deliverables in this section will enable feature compatibility of Parity Technologies' 'TxWrapper' in the Python Substrate Interface library. This will in turn enable wrapping and submitting transactions to Substrate-based networks. The Python Substrate Interface library itself is agnostic regarding the signature origin. External signers such as Python Subkey and Parity Signer can be used as signers.
```
D6.1. Library method: createSigningPayload(UnsignedTransaction, <Options>) // Construct the signing payload from an unsigned transaction.
D6.2. Library method: createSignedTransaction(UnsignedTransaction, Signature, <Options>) // Wrap a signed transaction in a format in an envelop that can be submitted over the Substrate Interface once serialized.
D6.3. Library method: submitSignedTransaction(SignedTransaction) // Submit a signed transaction over the Substrate Interface.
```

7. Deliverables: Substrate Interface API extensions
The deliverables in this section will extend Substrate Interface API with the new Python Substrate Interface library methods. The primary objective of this deliverable is to showcase conformity of the deliverables in section 6 in a user friendly way (i.e. use of a JSON-RPC API through Postman).
```
D7.1. JSON-RPC API method: runtime_createSigningPayload(UnsignedTransaction, <Options>) // Construct the signing payload from an unsigned transaction.
D7.2. JSON-RPC API method: runtime_createSignedTransaction(UnsignedTransaction, Signature, <Options>) // Wrap a signed transaction in a format in an envelop that can be submitted over the Substrate Interface once serialized.
D7.3. JSON-RPC API method: runtime_submitSignedTransaction(SignedTransaction) // Submit a signed transaction over the Substrate Interface.
```

8. Deliverables: Substrate Interface GUI extensions
The deliverables in this section will enable feature compatibility of the Substrate Interface with external signers following the Universal Offline Signature specification. This methods provides a two-way interface between a hot wallet and cold signer for the purpose of securely signing and broadcasting transactions and data on current and future decentralized networks. This interface will enable Parity Signer compatibility.
```
D8.1. QR-interface: Introduction // Network identification and address from cold to hot in binary format.
D8.2. QR-interface: Payload // Data to sign prefixed with metadata from hot to cold in binary format.
D8.3. QR-interface: Signature // Signature for payload in binary format from cold to hot.
```

Documentation
- PDOC: Auto-generate API documentation for Python projects for the Python Substrate Interface
- Documentation and usage of all RPC-methods for use with Postman
- Medium article: Development Update 7: Polkascan Signer Interfaces

Milestone Payout: 15,000 USD

## Outlook
This project should lead to the go-to libraries/applications for any Python application developers that require signing and signature verification capabilities. Additionally this project should lead to secure user-facing signing capabilities on Polkascan.io.

## Additional Information
### Are there any other projects similar to yours?
The following projects are referenced in this project:
* Polkadot JS: https://polkadot.js.org/
* TX Wrapper: https://github.com/paritytech/txwrapper
* Universal Offline Signatures: https://github.com/maciejhirsz/uos
* Parity Signer: https://github.com/paritytech/parity-signer

### How is our project different?
Currently no signing and signature verification mechanisms are available to use from within Python and Angular applications. This project's deliverables provide Python libraries for a general audience.