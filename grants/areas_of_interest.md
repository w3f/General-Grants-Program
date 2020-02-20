# Polkadot Stack

If any of these topics below are of interest to you then please make an application via the 
[General Grants Program](https://github.com/w3f/Web3-collaboration/blob/master/grants/grants.md) 
or [Open Grants Program](https://github.com/w3f/Open-Grants-Program). 
Feel free to also take a look at the [accepted grant applications](https://github.com/w3f/Web3-collaboration/blob/master/grants/accepted_grant_applications.md).

---

- [:clipboard: About](#clipboard-about)
- [:bookmark_tabs: Layers of Polkadot Stack](#bookmark_tabs-layers-of-polkadot-stack)
  - [:iphone: Explorer and Wallets](#iphone-explorer-and-wallets)
  - [:wrench: Tools, APIs and Languages](#wrench-tools-apis-and-languages)
  - [:link: Parachains and Bridges](#link-parachains-and-bridges)
  - [:electric_plug: Network Maintenance Tools](#electric_plug-network-maintenance-tools)
  - [:black_nib: Signatures](#black_nib-signatures)
  - [WASM](#wasm)
  - [Rust](#rust)

## :clipboard: About 

The Grants Programs seeks to allocate resources to projects that are beneficial to the advancement of the Polkadot Stack.
Polkadot Stack is a subset of the Web3 Stack, which consists of technologies contributing to Polkadot or Kusama implementation (below in stack) or rely on the Polkadot or Kusama protocol (above in stack).

```
|------|--------|------------|
| DeFi | Gaming | Provenance |
|______|________|____________|
            Dapps
|--------------------------/-|
| Browsers, Wallets       /  |
|------------------------/---|
| Tools, Apis, Languages/    |
|----------------------/-----|
| 2nd layer protocols /      |
|--------------------/-------|
| Chains            /  other |
|------------------/---    --|
| *Polkadot*      |   tech   |
|------------------\---------|
| P2P, Crypto, Wasm \        |
|--------------------\-------|
```

## :bookmark_tabs: Layers of Polkadot Stack

In the below sections you can find a list of different layers of the Polkadot Stack. Keep in mind that we are generally interested in funding more than one solution for a specific field. Also, we have an interest in keeping existing technology up to date. In case older projects are no longer maintained.  

### :iphone: Explorer and Wallets

| Need | Existing Projects 
|-|-
| Desktop Wallets | 
| Browser Extensions | [Polkadot{.js}](https://github.com/polkadot-js/extension), [Enzyme](https://getenzyme.dev/), [Speckle OS](https://www.speckleos.io/)  
| Mobile Wallets| [Polkawallet](https://polkawallet.io/)  
| Web (burner) Wallets| 
| Multisignature Wallets| 
| Hardware Wallets | Ledger, NGRAVE 
| Explorer | 
| Governance participation | 

### :wrench: Tools APIs and Languages

| Need | Existing Projects | Priority  
|-|-|- 
|Development of Specific Chains | Substrate + Cumulus | Parachain dev kits
| Polkadot RPC clients | [Go](https://github.com/centrifuge/go-substrate-rpc-client), [.Net](https://github.com/usetech-llc/polkadot_api_dotnet), [C++](https://github.com/usetech-llc/polkadot_api_cpp), Rust, Javascript, [Ruby](https://github.com/itering/scale.rb), [Python](https://github.com/polkascan/substrate-interface-api), [Java](https://github.com/polkadot-java), | Web3 Compatible API for Substate EVM Chains
| Runtime writing from different languages | Rust (Substrate), Go , C++ | AssemblyScript
| Easy Runtime Development | IDE (VS/Atom Code Plugin), Playground | 
| Runtime Security | K specifications for the SRML (Runtime Verification) |
| Smart Contract Languages | Solidity, Ink!| AssemblyScript, Functional Programming Languages
| Easy Smart Contract Development | Playground | IDE
| Smart Contract Security | Security Framework  |
| Easy integration testing | Benchmarking | 
| File Storage | | tools integrating Polkadot and file storage protocols
| Clear performance expectations |  | Transaction throughput, networking performance testing

### :link: Parachains and Bridges

| Need | Existing Projects | Priority  
|-|-|-
|Scalable Transactions | Plasma, State Channel Network| DAG parachains, Roll-up, Second Order Relay Chains, Other Side Chains
| Bridges|  Ethereum, Bitcoin, Libra | Bridge Hub , Zcash, Ethereum 
| Privacy | zk-SNARKs+obfuscation , pLibra | zk-SNARKs
| Off-Chain | TEE  |
| Financial Chains | Stablecoin , Trading Parachain  | Stablecoin, Decentralised exchanges
| Smart contract chains | ink! | smart contract chains based on existing toolchains, chains with novel security approaches, sharded smart contract chains
| Access to real world data | Oracle | Oracle Parachain
| Identity | Decentralised Identity , Zero Knowledge Identity  | 
| Verifiable Claims | Attestation |
| Computation | | Golem, Truebit or similar integrations
| Enable specific use-cases | Robotic parachain , SRML for social networks , SRML for supply chain , SLA SRML | Application-specific parachains with good product stories (e.g file storage, name resolution chain)

### :electric_plug: Network Maintenance Tools

| Need | Existing Projects | Priority
|-|-|- 
| Secure validator setup | Trutzone-based HSM | 
| Validator Deployment Tools| Polkadot Package Manager, Hardware Node Deployment |
| Validator explorer/monitoring | Validator tracker , Alert Focus | 
| Block explorer| Polkascan | Lightweight (IoT) block explorer?

### :black_nib: Signatures

| Need | Existing Projects | Priority
|-|-|-
| Ecosystem around a single version of crypto | | standardise and promote
| Easy multisig scheme | | research and implement

### Wasm

| Need | Existing Projects | Priority
|-|-|-
| ecosystem around a single version of DWasm | | standardise and promote

### Rust

| Need | Existing Projects| Priority
|-|-|-
| More convenient development |  | decrease compilation times
| Reproducable Runtime build | | allow for deterministic builds
| Small Runtimes | | decrease compiled binary size

