# Threshold Signature Validator Client Specification

## Project Description
We intend to create the specification and design of a threshold signature validator client for Substrate blockchains. As hot session keys used for validation are currently stored directly in the client, more secure solutions are critical to the long term security of validators and thus the network.

This project will specify how validators will be able to run multiple remote signers, each storing a key share, the signatures of which will be aggregated by a validator client and propagated to the network. We’ll define the validator client’s changes, a remote signer, communication between them, and describe how this arrangement maximizes security and availability while protecting against double signing. Our recommendations will be submitted as a Polkadot Standards Proposal ([PSP](https://github.com/w3f/PSPs)) at the conclusion of this grant.

The need for this solution is well known and has been discussed in the context of [adding remote signing to the Substrate client](https://github.com/paritytech/substrate/issues/4689) and [adding threshold signatures to Schnorrkel](https://github.com/w3f/schnorrkel/issues/11). The staking industry at large has been working towards these types of solutions, and [a production implementation exists today for Tendermint chains](https://blog.polychainlabs.com/tendermint/2020/03/26/threshold-validator-for-tendermint.html). We don’t present these solutions as being particularly new or novel, rather the value of this grant is in its succinct and complete presentation specific to Substrate blockchains and the coordination that allows.

Our team has been providing secure solutions for Proof of Stake validators for several years. We’re excited about the future for Polkadot, Substrate chains at large, and we’re eager to make technical contributions to this ecosystem.

## Team members
Obsidian Systems was founded in 2014 by Ali Abrar and Ryan Trinkle, who continue to serve as its managing partners today. Today it consists of approximately 39 software developers, quality assurance engineers, management professionals, and other staff.

## Team Website
https://obsidian.systems/

## Legal Structure

Obsidian Systems LLC is a Delaware limited liability company.

Our legal address is P.O. Box 1206, New York, NY 10159. Our office address is 19 W 21st St, Suite 503, New York, NY 1001.

## Team's experience
Obsidian Systems designs and develops high quality software solutions to pressing business problems. Our experienced team has delivered mission-critical solutions to a variety of high-profile clients, including several Fortune 500 companies and national retail firms, and blockchains such as Tezos and Kadena. These solutions secure millions of dollars in cryptographic assets ([Tezos Baking/Wallet Ledger applications](https://github.com/obsidiansystems/ledger-app-tezos)), lower the technical barrier to participation in consensus ([Kiln](https://gitlab.com/obsidian.systems/kiln)), and facilitate the development of smart contracts (Pact and [Chainweaver](https://www.kadena.io/chainweaver)).

Our solutions are currently used by thousands of employees and tens of thousands of consumers every day.

Most relevant to this project, we designed and developed the first block validating application for a consumer hardware wallet (Tezos Baking for the Ledger Nano S), used by a significant portion of the Tezos baking community. We also have a track record of producing secure solutions across other industries used by government agencies, research institutions, and private companies. 

You can find us on [Github](https://github.com/obsidiansystems), [Gitlab](https://gitlab.com/obsidian.systems), [Medium](https://medium.com/@obsidian.systems), and [Twitter](https://twitter.com/obsidian_llc).

## Team Code Repos
https://github.com/obsidiansystems?tab=repositories. Additionally/Relevantly:
- Tezos Ledger Applications - https://github.com/obsidiansystems/ledger-app-tezos
- Nervos Ledger Application - https://github.com/obsidiansystems/ledger-app-nervos
- Kiln, the Node/Baking GUI for Tezos - https://gitlab.com/obsidian.systems/kiln
- Obelisk - https://github.com/obsidiansystems/obelisk/
- Reflex Platform - https://github.com/reflex-frp/reflex-platform
- Kadena’s Pact Smart Contract Language (Contributors) - https://github.com/kadena-io/pact

## Team LinkedIn Profiles
- https://www.linkedin.com/in/ryantrinkle/
- https://www.linkedin.com/in/aliabrar/
- https://www.linkedin.com/in/reinhartmichael/

## Project Roadmap
We recommend a timeline of 3-5 weeks to complete this project. Our team will include developers, Project Manager, and a Product Owner, with an average staffing of 2 FTE across these roles. Ideally payment would be received after the completion of each phase, with ½ received after Phase 1 and ½ received at the completion of Phase 2.

### Phase 1: High-level Specification
Most of the requirement gathering for this project is already complete and a preliminary specification is included in this proposal below. Before we consider Phase 1 complete, we’d review our high level plans with the Web3 Foundation to confirm the solutions we have in mind align well with their goals.

In particular, these specifications will cover remote signers, supported key storage solutions, communication between remote signers and the validator client, threshold key generation and signature aggregation, double signing protection and availability.

Milestone Notes:
- Deliverable: High level summary of inputs and changes
- Estimated Timeline: 1-2 weeks
- Payment: 1/2 total grant allocation

### Phase 2: Formal Proposal
After the Web3 Foundation agrees our direction is satisfactory, we’ll produce our detailed final recommendations in the form of a PSP. This distilled, comprehensive format can be reviewed by the general public, security auditors, and additional interested stakeholders like validators and hardware providers.

The PSP will include adequate information for teams, whether they be our own or 3rd parties, to begin implementing portions of the specification with confidence that their work contributes to a larger goal. This PSP will include but is not limited to:

- API/RPC specifications
- Command line interface specifications
- Detailed descriptions of new repositories or changes to existing repositories
- Documentation on how core requirements are guaranteed
- Lists of supported hardware and integration plans for each
- Positions on why stylistic choices have been made

Milestone Notes:
- Deliverable: PSP Submission
- Estimated Timeline: 2-3 weeks
- Payment: 1/2 total grant allocation

## Preliminary Specification
The specifications produced by this grant covers the **validator client**, **remote signing servers**, how they work together, and additional considerations such as protection from double signing and ensuring high availability.

### Validator Client
The validator client will be responsible for generating key shares, aggregating partial signatures into full signatures, and propagating the full signature to the network.

The addition of an **RPC agent** to the client codebase opens the client to communication with multiple remote signers. Important topics we’ll cover include endpoint discovery, identification, and authentication, versioning, and data formats for transportation and serialization.

The agent should be optionally run via CLI-flag passed to the Substrate client at startup and listen for incoming reverse communications from remote servers authenticated via secret handshake. Once authenticated, the agent can begin sharing requests with multiple remote signing servers. These requests will need to be distinguished according to which key signature is being requested (BABE, GRANDPA, parachain, “I’m Online”) and each must take the specifics of each protocol into consideration. These particulars make the application of a single format across all key requests questionable.

### Remote Signing Server
Remote signing server will be a separate repository run independently from the client. In addition to storing the key share generated by the validator client, it listens for RPC requests, creates the signature/payload, and returns the response through an encrypted connection.

The remote signer should have a **command-line interface** sufficient enough to add, rotate, and test keys. Key shares generated in the client should only be added locally through this command line interface and not via RPC. Configuration should otherwise be set using a config file specifying:

- **Validator data**, such as the substrate chain being validated and the name of the validator(s) for which the signer is validating
- **Validator client data**, such as its location and secrets used to authenticate the connection with the client
- **Key data**, such as which keys are stored and their purpose (BABE, GRANDPA, etc), their location (hardware, encrypted file), and curve (sr25519, ed25519, etc)

**Key solutions** within scope include:
- YubiHSM2
- USB Armory MkII
- Ledger devices
- CloudHSMs
- TEE (such as [SubstraTEE](https://github.com/scs/substraTEE))
- Keyfile storage

### Additional Considerations

**Double Signing Protection** - While key storage solutions are effective at protecting the secret key from theft, an attacker could still have the validator slashed by convincing it to sign the same operation twice. Some key solutions (such as Ledger devices) can have built-in application logic with double signing protection, but this isn’t universally supported. The remote signing server should have sufficient capability to protect against such attacks regardless of where the key is stored. This should be done for each protocol’s key in use separately since the considerations may vary per protocol. 

**High Availability / Threshold Signing Schemes** - Validators can be slashed if their infrastructure lacks the availability expected from a block producer. The introduction of remote signing alone with a single remote signer can negatively impact availability, however remote signing with threshold signatures is robust and mitigates this risk very well. Each remote signer is asked to sign a block, confirms signing the block won’t violate its double signing mechanisms, and produces a partial signature which is sent to the validator client. The client aggregates signatures from several signers according to the m of n conditions set during key generation, and propagates the full signature it has assembled. The validator can continue to produce blocks as long as m remote signers are online with minimal risk of being slashed. The increase to the margin of safety this affords validators makes this an ideal arrangement for block validators providing critical security to the network. Work already being done to [add threshold multi-signatures to Schnorrkel](https://github.com/w3f/schnorrkel/issues/11) is a key component to actualizing this arrangement and will be incorporated in our specifications.

## Additional Information
Obsidian Systems has been discussing these types of improvements to validator key management with the Web3 Foundation, large validators on several blockchains, and hardware providers for several months. We’d be delighted to implement the specifications produced by this grant proposal and continue to improve the security of staking.

Additional interesting directions we’d like to take this after this proposal has been completed include:
- Actualizing support for HSMs and other key storage solutions not yet supported
- Multi-party computation and shared secrets
- Integrations for other projects
- Well documented example configurations
- Demonstrations of advanced configurations validating on multiple chains with diverse hardware
