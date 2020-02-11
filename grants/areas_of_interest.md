# Areas of Interest [DRAFT]

If any of these topics below are of interest to you then please make an application via the 
[General Grants Program](https://github.com/w3f/Web3-collaboration/blob/master/grants/grants.md) 
or [Open Grants Program](https://github.com/w3f/Open-Grants-Program). 
Feel free to also take a look at the [accepted grant applications](https://github.com/w3f/Web3-collaboration/blob/master/grants/accepted_grant_applications.md).

- [:clipboard: Polkadot Stack](#clipboard-polkadot-stack)
- [:pencil: Layers of Polkadot Stack](#layers-of-polkadot-stack)

## :clipboard: Polkadot Stack 

The Grants Programs seeks to allocate resources to projects that are beneficial to the advancement of the Polkadot Stack.
Polkadot Stack is a subset of Web3 Stack, which consists of technologies contributing to Polkadot implementation (below in stack) or rely on Polkadot protocol (above in stack).
Polkadot Stack is meant to be used for decentralised application (Dapp) development within many possible verticals.

## :pencil: Layers of Polkadot Stack

In the below sections you can find a list of different layers of the Polkadot Stack.

### Parachains and Bridges

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

### Standards

| Need | Existing Projects | Priority 
|-|-|- 
|Token Standards| | NFTs for in-game assets E1155, Security tokens, fungible and non-fungible tokens|
| Cross Chain Standards | | SPREE
| Contract Wallet Standards || Multisig Interface

### Tools, APIs and Languages

| Need | Existing Projects | Priority  
|-|-|- 
|Development of Specific Chains | Substrate + Cumulus | Parachain dev kits
| Polkadot RPC clients | Go, .Net, C++, Rust, Javascript, Python, Java, | Web3 Compatible API for Substate EVM Chains
| Runtime writing from different languages | Rust (Substrate), Go , C++ | AssemblyScript
| Easy Runtime Development | IDE (VS/Atom Code Plugin), Playground | 
| Runtime Security | K specifications for the SRML (Runtime Verification) |
| Smart Contract Languages | Solidity, Ink!| AssemblyScript, Functional Programming Languages
| Easy Smart Contract Development | Playground | IDE
| Smart Contract Security | Security Framework  |
| Easy integration testing | Benchmarking | 
| File Storage | | tools integrating Polkadot and file storage protocols
| Clear performance expectations | TODO | Transaction throughput, networking performance testing

### Browsers and Wallets

| Need | Existing Projects | Priority
|-|-|- 
| Desktop Wallets | Browser Extensions | Desktop wallet, Web (burner) wallets + Faucet, Multisignature wallet
| Mobile Wallets| Mobile Wallets | Web (burner) wallets + faucet, Multisignature wallet
| Hardware Wallets | Ledger, NGRAVE |Trezor
| Governance participation | Polkawallet, Enzyme |Governance interface

### Network Maintenance Tools

| Need | Existing Projects | Priority
|-|-|- 
| Secure validator setup | Trutzone-based HSM | 
| Validator Deployment Tools| Polkadot Package Manager, Hardware Node Deployment |
| Validator explorer/monitoring | Validator tracker , Alert Focus | 
| Block explorer| Polkascan | Lightweight (IoT) block explorer?

### Libp2p

| Need | Existing Projects | Priority | 
|-|-|-
| |

### Signatures (ed25519, sr25519, BLS)

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

