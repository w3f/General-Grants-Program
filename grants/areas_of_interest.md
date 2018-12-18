# Areas of Interest

## Software Development

* Development and deployment tooling
  * IDEs
  * Dependency management
  * Testing frameworks
  * Scalable cluster
    * We would like a scalable RPC service for Polkadot. This would be a service that is elastic and can scale with the number of requests.
    * Features: Super stable RPC end point, Distribute requests appropriately, Spin up new resources as need.
  * Tools for easy deployment
  * Parachain development kits
* New languages and libraries
  * Targeting deterministic Wasm
* New chains
  * Interesting new blockchains that can act as parachains
    * Examples: oracle chains, rapid transactions, DEX parachains.
  * Adaptations of existing blockchains as parachains
    * Examples: smart contract chains, private transactions (e.g. zk-snark, ring ct)
* Protocol integrations
  * Bridges to other blockchains (link to wiki)
    * Solo chains, with their own consensus mechanisms, have ecosystems which exist in isolation (ex: ETH, BTC). Through bridges, solo chains will be able to connect their blockchain ecosystems with Polkadot and share features and users.
    * We require an open source block explorer that can read basic Substrate blocks (e.g. Relay chain blocks, or Edgware blocks) but is generic enough that it can be extended by community input.
  * Distributed File Storage (e.g. IPFS)
  * Transient P2P messaging (e.g. Whisper)
    * Integrate these messaging protocols to Substrate.
  * New protocols that are useful for [Web3 stack](https://wiki.web3.foundation)
    * The vision of Web3 requires a fully integrated tech stack. We need teams to integrate each of the technologies in the stack into Polkadot.
* Second layer protocols
  * State channels (runtime modules, dedicated parachains)
    * Implement state channels as runtime modules (can be reused across parachains) or in a dedicated parachain.
  * Key server networks
* Monitoring
  * Block explorers
    * We require an open source block explorer that can read basic Substrate blocks (e.g. Relay chain blocks, or Edgware blocks) but is generic enough that it can be extended by community input. The idea is to provide a block explorer for any parachain.
  * Node explorers
    * We require an open source node explorer. Useful info: Client types, client versions, locations and any other info. This will require node crawling to figure out what&rsquo;s going on.
  * Statistical analytics
* UI
  * Wallets
    * Build a UI that allows users to send transactions (and ideally other extrinsics).
  * Libraries
  * Mobile integration
    * Mobile apps that allows users to interact with the Polkadot platform (this includes mobile wallets).
* Alternative Polkadot Runtime Environment implementation ([Link](https://github.com/w3f/Web3-collaboration/issues/12))
* Hardware wallet integration / HSMs
  * Users, validators and collators
    * Validators require a signing key that resides on the validation node. This requires keeping the key in an HSM or a hardware wallet.
    * Users should have the option to have a hardware wallet for transactions. This requires being able to write firmware for popular hardware wallets.
    * Further consideration is required for other types of extrinsics: such as enabling users to participate in governance.
* Polkadot Runtime Modules
  * Governance
    * Polkadot is taking a lead in active governance. The relay chain, which is the backbone of Polkadot, enables token holders to have voting power and help decide how the platform evolves. However, each parachain will be able to have its own governance and thus we we are interested in developing further governance modules that parachain builders can reuse.
  * Interoperability
  * Interesting new modules
* Benchmarking tools
* Core implementation testing tools

## Community Development

* Blog posts
* Meetups
* Conferences
* Software documentation
* Educational content
  * Blog posts
  * Videos
  * Courses

## Research

* Benchmarking
* New primitives
  * Technical and economical
* Analysis of existing protocols and implementations
* Security testing
  * Tools to find vulnerabilities in runtime modules and smart contracts
  * Examples: static code scanners, fuzzers.
