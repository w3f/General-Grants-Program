# Open Source Polkadot Stack [WIP!]

The goal of this page is to provide an overview of the open-source polkadot tech stack. At the moment it's far from complete. 

---

- [:clipboard: About](#clipboard-about)
- [:battery: Funding](#battery-funding)
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
## :battery: Funding

If you want to actively contribute to the polkadot stack and you are looking for funding, please make an application via the 
[General Grants Program](https://github.com/w3f/Web3-collaboration/blob/master/grants/grants.md) 
or [Open Grants Program](https://github.com/w3f/Open-Grants-Program). Keep in mind that we are generally interested in funding more than one solution for a specific field. Also, we have an interest in keeping existing technology up to date, in case older projects are no longer maintained. 

## :bookmark_tabs: Layers of Polkadot Stack

In the below sections you can find a list of different layers of the Polkadot Stack. 

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
| Polkadot RPC clients | [Go](https://github.com/centrifuge/go-substrate-rpc-client), [.Net](https://github.com/usetech-llc/polkadot_api_dotnet), [C++](https://github.com/usetech-llc/polkadot_api_cpp), [Haskell](https://github.com/Pixura), [Javascript](https://github.com/polkadot-js/api), [Ruby](https://github.com/itering/scale.rb), [Python](https://github.com/polkascan/substrate-interface-api), [Java](https://github.com/polkadot-java), [Rust](https://github.com/scs/substrate-api-client)
| Easy Runtime Development | [VS Plugin](https://github.com/everstake/vscode-plugin-substrate), [Atom Code Plugin](https://github.com/everstake/atom-plugin-substrate), [Substrate Playground](https://github.com/paritytech/substrate-playground) 
| Easy Smart Contract Development | [ink-playground](https://github.com/staketechnologies/ink-playground/tree/master), [Ink! Remix Plugin](https://github.com/blockchain-it-hr/ink-remix-plugin) 
| Runtime Security | [K specifications](https://github.com/kframework/wasm-semantics)
| Smart Contract Languages | [Solang](https://github.com/hyperledger-labs/solang), [Ink!](https://github.com/paritytech/ink), [Pact](https://github.com/kadena-io/)
| Smart Contract Security |   
| Easy integration testing |   
| Performance Testing |  

### :link: Chains and Modules

| Need | Existing Projects  
|-|-
| Scalable Transactions | [Plasm](https://github.com/staketechnologies/Plasm), [Celer](https://github.com/celer-network), [Gunclear](https://github.com/GunClear)
| Bridges|   [Ethereum by Centrifuge](https://github.com/centrifuge/), [EOS by Bifrost](https://github.com/bifrost-codes) 
| Privacy | [ZeroChain](https://github.com/LayerXcom/zero-chain), [pLibra](https://github.com/libra-china-org) 
| Off-Chain | [substraTEE](https://github.com/scs/substraTEE)
| Financial Chains | [Laminar Chain](https://github.com/laminar-protocol/laminar-chain), [Acala](https://acala.network/), [Centrifuge](https://github.com/centrifuge/), [Stafi](https://github.com/stafiprotocol/stafi-node), [Bandot](https://github.com/bandotorg/Bandot),  
| Smart contract chains | [Edgeware](https://github.com/hicommonwealth) 
| Access to real world data | [Oracle by Laminar](https://github.com/laminar-protocol/open-runtime-module-library/tree/master/oracle) 
| Identity | [Caelum Labs](https://gitlab.com/caelum-tech/lorena), [Litentry](https://github.com/litentry/litentry-runtime) 
| IoT | [Nodle](https://github.com/NodleCode/)
| Verifiable Claims | [KILT](https://github.com/KILTprotocol), [Dock](https://github.com/docknetwork) 
| Supply chain| [Wiv](https://github.com/wivtech/Substrate-SupplyChain)
| Social Networking | [SubSocial](https://github.com/dappforce/dappforce-subsocial)
| Messaging | [HOPR](https://github.com/validitylabs/HOPR-PL-Substrate), [Mailchain](https://github.com/mailchain)
| File Storage | [DatDot](https://github.com/playproject-io/datdot)
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
| High availability setup | [Archipel](https://github.com/luguslabs/archipel)
| Deployment Tools| [Polkadot Package Manager](https://github.com/Blockdaemon/bpm-sdk), [PolkaHub](https://github.com/akropolisio/polkahub-monorepo), [Avado](https://github.com/AvadoDServer/AVADO-DNP-Polkadot-custom) 
| Validator monitoring | [P.A.N.I.C.](https://github.com/SimplyVC/panic_polkadot), [Polkalert](https://github.com/galacticcouncil/polkalert), [B-Harvest](https://github.com/nodebreaker0-0/substrate/tree/prometheus_v0.3)   

### :black_nib: Signatures

| Need | Existing Projects 
|-|-
| SR25519 | [C](https://github.com/usetech-llc/sr25519), [C#](https://github.com/usetech-llc/sr25519_dotnet)
| Easy multisig scheme | 


## :construction_worker: Contributing

Pull requests, issues, or other contributions from the community are encouraged!  You can not only add specific projects but also potentially interesting fields/areas, which are currently missing in the tech stack. 

:heavy_exclamation_mark: All technologies listed above need to be open-source. Ideally, the links lead directly to the code. 

_Note: You will need a GitHub account to suggest changes or file issues. If you do not have a GitHub account, you may [sign up for one for free](https://github.com/join)._
