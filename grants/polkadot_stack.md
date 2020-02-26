# Open Source Polkadot Stack [WIP!]

The goal of this page is to provide an overview of the open-source Polkadot Tech Stack. At the moment it's a work-in-progress, 

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

The Polkadot Tech Stack is a subset of the Web 3.0 Tech Stack, which consists of the **open-source** technologies contributing to and relying on [Polkadot](https://polkadot.network/), [Kusama](https://kusama.network/) and [Substrate](https://substrate.dev/). It is meant to be used for decentralized application (Dapp) development within many possible verticals including DeFi, Gaming, Provenance and many others not pictured below.

```
|------|--------|------------|
| DeFi | Gaming | Provenance |
|______|________|____________|
            Dapps
|--------------------------/-|
| Explorers, Wallets      /  |
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

The Web3 Foundation's [General Grants Program](https://github.com/w3f/Web3-collaboration/blob/master/grants/grants.md) 
and [Open Grants Program](https://github.com/w3f/Open-Grants-Program) are focused on funding development work to build out all layers of the Polkadot Tech Stack. Please use the preceding links to apply for funding for relevant projects.

To get a better understanding of the projects we consider most relevant you can explore a detailed breakdown of the various layers of stack, below. We divide each of the layers into the various *components* which we feel are most important. We then highlight some of the *exisiting projects* that address these components as well as *some specific projects we would like to fund*.

We typically like to fund more than one project for each component so if you see a component with 1 or 0 exisiting projects then it's likely that we would consider an application in this area. In order to consider funding a proposal that addresses a component with many existing projects then we would need to be persuaded that this proposal brought unique value to the ecosystem. Such value could be in many forms including but not limited to differentiated functionality, better user experience, the attraction of new users to the ecosystem or a high-likelihood that the technology would be maintained for a long period of time.

By describing our areas of priority in detail we do not wish to preclude grant applications that address different areas that we may not have thought of. We would like to fund all projects that bring value to the ecosystem. If you are considering applying for a project and are not sure if it falls within our areas of interest then please get in touch with us to discuss it.

## :bookmark_tabs: Layers of Polkadot Stack

In the below sections you can find a list of different layers of the Polkadot Stack. 

### :iphone: Explorer and Wallets

| Components | Existing projects | Some specific projects we would like to fund
|-|-|-
| Desktop Wallets | [AirGap](https://github.com/airgap-it/airgap-wallet)
| Browser Extensions | [Polkadot{.js}](https://github.com/polkadot-js/extension), [Enzyme](https://getenzyme.dev/), [Speckle OS](https://www.speckleos.io/)  
| Mobile Wallets| [Lunie](http://lunie.io/), [Polkawallet](https://polkawallet.io/), [Parity Signer](https://github.com/paritytech/parity-signer)  
| Web (burner) Wallets| 
| Multisignature Wallets| 
| Hardware Wallets | [Ledger](https://github.com/ZondaX/ledger-polkadot), [NGRAVE](https://ngrave.io/) 
| Explorer | [Polkascan](https://github.com/polkascan), [Polkastats](https://polkastats.io/)
| Validator Dashboard | [DotHub](https://github.com/figment-networks/dothub), [Polkacube](https://github.com/hashquark-io)

### :wrench: Tools APIs and Languages

| Components | Existing projects | Some specific projects we would like to fund 
|-|-|-
| Parachain Dev Kits | [Gantree](https://github.com/flex-dapps)| [Minimal Parachain Dev Kit](https://github.com/w3f/General-Grants-Program/issues/204) |
| Polkadot RPC clients | [Go](https://github.com/centrifuge/go-substrate-rpc-client), [.Net](https://github.com/usetech-llc/polkadot_api_dotnet), [C++](https://github.com/usetech-llc/polkadot_api_cpp), [Haskell](https://github.com/Pixura), [Javascript](https://github.com/polkadot-js/api), [Ruby](https://github.com/itering/scale.rb), [Python](https://github.com/polkascan/substrate-interface-api), [Java](https://github.com/polkadot-java), [Rust](https://github.com/scs/substrate-api-client) | [Web3 Compatible API for Substate EVM Chains](https://docs.google.com/document/u/1/d/1LL_uXGvhihaC7928WmWT7yYlThN8c8HI_0u7h-JKlk0/edit?usp=drive_fs&ouid=113079615530164190769)|
| Easy Runtime Development | [VS Plugin](https://github.com/everstake/vscode-plugin-substrate), [Atom Code Plugin](https://github.com/everstake/atom-plugin-substrate), [Substrate Playground](https://github.com/paritytech/substrate-playground) | [AssemblyScript Runtime Generation](https://github.com/w3f/General-Grants-Program/issues/159)|
| Easy Smart Contract Development | [ink-playground](https://github.com/staketechnologies/ink-playground/tree/master), [Ink! Remix Plugin](https://github.com/blockchain-it-hr/ink-remix-plugin) 
| Runtime Security | [K specifications](https://github.com/kframework/wasm-semantics)
| Smart Contract Languages | [Solang](https://github.com/hyperledger-labs/solang), [Ink!](https://github.com/paritytech/ink), [Pact](https://github.com/kadena-io/)| AssemblyScript, Functional Programming Languages |
| Smart Contract Security |   
| Easy integration testing |   
| Performance Testing |  

### :link: Chains and Modules

| Components | Existing projects | Some specific projects we would like to fund
|-|-|-
| Scalable Transactions | [Plasm](https://github.com/staketechnologies/Plasm), [Celer](https://github.com/celer-network), [Gunclear](https://github.com/GunClear)| Roll-ups, DAG-based consensus mechanisms, |
| Bridges|   [Ethereum by Centrifuge](https://github.com/centrifuge/), [EOS by Bifrost](https://github.com/bifrost-codes)| ZCash, Ethereum, Tendermint | 
| Privacy | [ZeroChain](https://github.com/LayerXcom/zero-chain), [pLibra](https://github.com/libra-china-org) 
| Off-Chain | [substraTEE](https://github.com/scs/substraTEE)
| Financial Chains | [Katal Chain](https://github.com/katalchain), [Laminar Chain](https://github.com/laminar-protocol/laminar-chain), [Acala](https://acala.network/), [Centrifuge](https://github.com/centrifuge/), [Stafi](https://github.com/stafiprotocol/stafi-node), [Bandot](https://github.com/bandotorg/Bandot),  
| Smart contract chains | [Edgeware](https://github.com/hicommonwealth) 
| Access to real world data | [Oracle by Laminar](https://github.com/laminar-protocol/open-runtime-module-library/tree/master/oracle), [Oracle by Katal Chain](https://github.com/katalchain/blockchain/tree/master/modules/oracle) 
| Identity | [Caelum Labs](https://gitlab.com/caelum-tech/lorena), [Litentry](https://github.com/litentry/litentry-runtime) 
| IoT | [Nodle](https://github.com/NodleCode/)
| Verifiable Claims | [KILT](https://github.com/KILTprotocol), [Dock](https://github.com/docknetwork) 
| Supply chain| [Wiv](https://github.com/wivtech/Substrate-SupplyChain)
| Social Networking | [SubSocial](https://github.com/dappforce/dappforce-subsocial)
| Messaging | [HOPR](https://github.com/validitylabs/HOPR-PL-Substrate), [Mailchain](https://github.com/mailchain)
| File Storage | [DatDot](https://github.com/playproject-io/datdot)
| Name Service| [Substrate Names](https://github.com/xaya/substrate-names)
| Computation | 
| Enable specific use-cases | [Robonomics](https://github.com/airalab/substrate-node-robonomics)
| Secret store |
| Universal Naming Service |

### :black_circle: Host

| Components | Existing projects | Some specific projects we would like to fund 
|-|-|-
| Rust | [Substrate](https://github.com/paritytech/substrate)
| C++ | [Kagome](https://github.com/soramitsu/kagome)
| Go | [Gossamer](https://github.com/ChainSafe/gossamer)
| AssemblyScript | 

### :electric_plug: Network Maintenance Tools

| Components | Existing projects | Some specific projects we would like to fund
|-|-|-
| Secure validator setup | [Trutzone-based HSM](https://github.com/ZondaX)  
| High availability setup | [Archipel](https://github.com/luguslabs/archipel)
| Deployment Tools| [Polkadot Package Manager](https://github.com/Blockdaemon/bpm-sdk), [PolkaHub](https://github.com/akropolisio/polkahub-monorepo), [Avado](https://github.com/AvadoDServer/AVADO-DNP-Polkadot-custom) 
| Validator monitoring | [P.A.N.I.C.](https://github.com/SimplyVC/panic_polkadot), [Polkalert](https://github.com/galacticcouncil/polkalert), [B-Harvest](https://github.com/nodebreaker0-0/substrate/tree/prometheus_v0.3)   

### :black_nib: Signatures

| Components | Existing projects | Some specific projects we would like to fund
|-|-|-
| SR25519 | [C](https://github.com/usetech-llc/sr25519), [C#](https://github.com/usetech-llc/sr25519_dotnet)
| Easy multisig scheme | 
| Validator HSMs| |
| Validator HSM-like solutions|


## :construction_worker: Contributing

Pull requests, issues, or other contributions from the community are encouraged!  You can not only add specific projects but also potentially interesting fields/areas, which are currently missing in the tech stack. 

:heavy_exclamation_mark: All technologies listed above need to be open-source. Ideally, the links lead directly to the code. 

_Note: You will need a GitHub account to suggest changes or file issues. If you do not have a GitHub account, you may [sign up for one for free](https://github.com/join)._
