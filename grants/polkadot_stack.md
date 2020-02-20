# Open Source Polkadot Stack

> The goal of this page is to provide an overview of the open-source polkadot tech stack. At the moment it's far from complete. 

If you want to actively contribute to the polkadot stack and you are looking for funding, please make an application via the 
[General Grants Program](https://github.com/w3f/Web3-collaboration/blob/master/grants/grants.md) 
or [Open Grants Program](https://github.com/w3f/Open-Grants-Program). 
Feel free to also take a look at the [accepted grant applications](https://github.com/w3f/Web3-collaboration/blob/master/grants/accepted_grant_applications.md).

---

- [:clipboard: About](#clipboard-about)
- [:bookmark_tabs: Layers of Polkadot Stack](#bookmark_tabs-layers-of-polkadot-stack)
  - [:iphone: Explorer and Wallets](#iphone-explorer-and-wallets)
  - [:wrench: Tools, APIs and Languages](#wrench-tools-apis-and-languages)
  - [:link: Chains and Modules](#link-chains-and-modules)
  - [:black_circle: Host](#black_circle-host)
  - [:electric_plug: Network Maintenance Tools](#electric_plug-network-maintenance-tools)
  - [:black_nib: Signatures](#black_nib-signatures)
- [:construction_worker: Contributing](#construction_worker-contributing)

## :clipboard: About 

Polkadot Stack is a subset of the Web3 Stack, which consists of **open-source** technologies contributing to [Polkadot](https://polkadot.network/), [Kusama](https://kusama.network/) or [Substrate](https://substrate.dev/) (below in stack) or rely on it (above in stack).

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

In the below sections you can find a list of different layers of the Polkadot Stack. Keep in mind that we are generally interested in funding more than one solution for a specific field. Also, we have an interest in keeping existing technology up to date, in case older projects are no longer maintained.  

### :iphone: Explorer and Wallets

| Need | Existing Projects 
|-|-
| Desktop Wallets | [AirGap](https://github.com/airgap-it/airgap-wallet)
| Browser Extensions | [Polkadot{.js}](https://github.com/polkadot-js/extension), [Enzyme](https://getenzyme.dev/), [Speckle OS](https://www.speckleos.io/)  
| Mobile Wallets| [Lunie](http://lunie.io/), [Polkawallet](https://polkawallet.io/), [Parity Signer](https://github.com/paritytech/parity-signer)  
| Web (burner) Wallets| 
| Multisignature Wallets| 
| Hardware Wallets | [Ledger](https://github.com/ZondaX/ledger-polkadot), [NGRAVE](https://ngrave.io/) 
| Explorer | [Polkascan](https://github.com/polkascan), [Polkastats](https://polkastats.io/)
| Validator Dashboard | [DotHub](https://github.com/figment-networks/dothub), [Polkacube](https://github.com/hashquark-io)

### :wrench: Tools APIs and Languages

| Need | Existing Projects  
|-|-
| Parachain Dev Kits | [Gantree](https://github.com/flex-dapps)| 
| Polkadot RPC clients | [Go](https://github.com/centrifuge/go-substrate-rpc-client), [.Net](https://github.com/usetech-llc/polkadot_api_dotnet), [C++](https://github.com/usetech-llc/polkadot_api_cpp), [Haskell](https://github.com/Pixura), [Javascript](https://github.com/polkadot-js/api), [Ruby](https://github.com/itering/scale.rb), [Python](https://github.com/polkascan/substrate-interface-api), [Java](https://github.com/polkadot-java)
| Easy Runtime Development | [VS Plugin](https://github.com/everstake/vscode-plugin-substrate), [Atom Code Plugin](https://github.com/everstake/atom-plugin-substrate), [Substrate Playground](https://github.com/paritytech/substrate-playground) 
| Easy Smart Contract Development | [ink-playground](https://github.com/staketechnologies/ink-playground/tree/master), [Ink! Remix Plugin](https://github.com/blockchain-it-hr/ink-remix-plugin) 
| Runtime Security | [K specifications](https://github.com/kframework/wasm-semantics)
| Smart Contract Languages | [Solang](https://github.com/hyperledger-labs/solang), [Ink!](https://github.com/paritytech/ink)
| Smart Contract Security |   
| Easy integration testing |   
| File Storage | 
| Performance Testing |  

### :link: Chains and Modules

| Need | Existing Projects  
|-|-
| Scalable Transactions | [Plasm](https://github.com/staketechnologies/Plasm), [Celer](https://github.com/celer-network), [Gunclear](https://github.com/GunClear)
| Bridges|   [Ethereum](https://github.com/centrifuge/) 
| Privacy | [ZeroChain](https://github.com/LayerXcom/zero-chain), [pLibra](https://github.com/libra-china-org) 
| Off-Chain | [substraTEE](https://github.com/scs/substraTEE)
| Financial Chains | [Laminar Chain](https://github.com/laminar-protocol/laminar-chain), [Acala](https://acala.network/) 
| Smart contract chains | [Edgeware](https://github.com/hicommonwealth) 
| Access to real world data | [Oracle by Laminar](https://github.com/laminar-protocol/open-runtime-module-library/tree/master/oracle) 
| Identity | [Caelum Labs](https://gitlab.com/caelum-tech/lorena) 
| Verifiable Claims | [KILT](https://github.com/KILTprotocol) 
| Supply chain| [Wiv](https://github.com/wivtech/Substrate-SupplyChain)
| Social Networking | [SubSocial](https://github.com/dappforce/dappforce-subsocial)
| Computation | 
| Enable specific use-cases | [Robonomics](https://github.com/airalab/substrate-node-robonomics)

### :black_circle: Host

| Need | Existing Projects 
|-|-
| Rust | [Substrate](https://github.com/paritytech/substrate)
| C++ | [Kagome](https://github.com/soramitsu/kagome)
| Go | [Gossamer](https://github.com/ChainSafe/gossamer)
| AssemblyScript | 

### :electric_plug: Network Maintenance Tools

| Need | Existing Projects 
|-|- 
| Secure validator setup | [Trutzone-based HSM](https://github.com/ZondaX)  
| Validator Deployment Tools| [Polkadot Package Manager](https://github.com/Blockdaemon/bpm-sdk) 
| Validator explorer/monitoring | [P.A.N.I.C.](https://github.com/SimplyVC/panic_polkadot), [Polkalert](https://github.com/galacticcouncil/polkalert)   

### :black_nib: Signatures

| Need | Existing Projects 
|-|-
| Ecosystem around a single version of crypto | 
| Easy multisig scheme | 


## :construction_worker: Contributing

Pull requests, issues, or other contributions from the community are encouraged!  You can not only add specific projects but also potentially interesting fields/areas, which are currently missing in the tech stack. 

:heavy_exclamation_mark: All technologies listed above need to be open-source. Ideally, the links lead directly to the code. 

_Note: You will need a GitHub account to suggest changes or file issues. If you do not have a GitHub account, you may [sign up for one for free](https://github.com/join)._
