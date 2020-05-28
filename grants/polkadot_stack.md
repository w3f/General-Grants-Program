# Open Source Polkadot Stack [WIP!]

The goal of this page is to provide an overview of the open-source Polkadot/Kusama Tech Stack. At the moment it's a work-in-progress.

This is a living document and we are relying on our community to contribute to this and help maintain it. Please feel free to make edits and additions via pull requests. We apologize if we missed your project!

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
  - [:satellite: Networking](#satellite-networking)
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

To get a better understanding of the projects we consider most relevant you can explore a detailed breakdown of the various layers of stack, below. We divide each of the layers into the various *components* which we feel are most important. We then highlight some of the *exisiting projects* that address these components as well as some *potentially interesting projects* that we would like to fund.

We typically like to fund more than one project for each component so if you see a component with 1 or 0 exisiting projects then it's likely that we would consider an application in this area. In order to consider funding a proposal that addresses a component with many existing projects then we would need to be persuaded that this proposal brought unique value to the ecosystem. Such value could be in many forms including but not limited to differentiated functionality, better user experience, the attraction of new users to the ecosystem or a high-likelihood that the technology would be maintained for a long period of time.

By describing our areas of priority in detail we do not wish to preclude grant applications that address different areas that we may not have thought of. We would like to fund all projects that bring value to the ecosystem. If you are considering applying for a project and are not sure if it falls within our areas of interest then please get in touch with us to discuss it.

## :bookmark_tabs: Layers of Polkadot Stack

In the below sections you can find a list of different layers of the Polkadot Stack. 

### :iphone: Explorer and Wallets

| Components | Existing projects | Potentially interesting projects
|-|-|-
| Desktop Wallets | [AirGap](https://github.com/airgap-it/airgap-wallet), [Sakura](https://github.com/w3finance/sakura)
| Browser Extensions | [Polkadot{.js}](https://github.com/polkadot-js/extension), [Enzyme](https://getenzyme.dev/), [Speckle OS](https://www.speckleos.io/)  
| Mobile Wallets| [KodaDot](https://twitter.com/KodaDot), [Lunie](http://lunie.io/), [Polkawallet](https://polkawallet.io/), [Parity Signer](https://github.com/paritytech/parity-signer)  
| Web (burner) Wallets| [KodaDot](https://twitter.com/KodaDot)
| Multisignature Wallets| 
| Hardware Wallets | [Ledger](https://github.com/ZondaX/ledger-polkadot), [NGRAVE](https://ngrave.io/) 
| Block Explorers | [Polkascan](https://github.com/polkascan), [Polkastats](https://polkastats.io/), [Subscan](https://github.com/itering/subscan)
| Validator Dashboards | [DotHub](https://github.com/figment-networks/dothub), [Polkacube](https://github.com/hashquark-io), [YieldScan](https://github.com/buidl-labs/YieldScan)
| Node Explorers | [Polkadot Node Explorer](https://github.com/protos-research/polkadot-node-explorer)
| Governance Dashboards | [Polkassembly](https://github.com/paritytech/polkassembly)

### :wrench: Tools APIs and Languages

| Components | Existing projects | Potentially interesting projects 
|-|-|-
| Parachain Dev Kits | [Gantree](https://github.com/flex-dapps)| [Minimal Parachain Dev Kit](https://github.com/w3f/General-Grants-Program/issues/204), tools to create parachains from frameworks used in other ecosystems |
| Polkadot RPC clients | [Go](https://github.com/centrifuge/go-substrate-rpc-client), [.Net](https://github.com/usetech-llc/polkadot_api_dotnet), [C++](https://github.com/usetech-llc/polkadot_api_cpp), [C](https://github.com/finoabanking/substrate-c-tool), [Haskell](https://github.com/Pixura), [Javascript](https://github.com/polkadot-js/api), [Ruby](https://github.com/itering/scale.rb), [Python](https://github.com/polkascan/substrate-interface-api), [Java](https://github.com/polkadot-java)*(old)*, [Java](https://github.com/emeraldpay/polkaj)*(new)*, [Rust](https://github.com/scs/substrate-api-client) | [Web3 Compatible API for Substate EVM Chains](https://docs.google.com/document/u/1/d/1LL_uXGvhihaC7928WmWT7yYlThN8c8HI_0u7h-JKlk0/edit?usp=drive_fs&ouid=113079615530164190769)|
| Easy Runtime Development | [VS Plugin](https://github.com/everstake/vscode-plugin-substrate), [Atom Code Plugin](https://github.com/everstake/atom-plugin-substrate), [Substrate Playground](https://github.com/paritytech/substrate-playground) | [AssemblyScript Runtime Generation](https://github.com/w3f/General-Grants-Program/issues/159)|
| Easy Smart Contract Development | [ink-playground](https://github.com/staketechnologies/ink-playground/tree/master), [Ink! Remix Plugin](https://github.com/blockchain-it-hr/ink-remix-plugin) 
| Runtime Security | [K specifications](https://github.com/kframework/wasm-semantics)
| Smart Contract Languages | [Solang](https://github.com/hyperledger-labs/solang), [Ink!](https://github.com/paritytech/ink), [Pact](https://github.com/kadena-io/)| AssemblyScript, Functional Programming Languages, other languages with developed toolchains |
| Smart Contract Security |   
| Easy integration testing |   
| Performance Testing |  [MixBytes Tank](https://github.com/mixbytes/tank)
| Chaos/Fuzz Testing |

### :link: Chains and Modules

| Components | Existing projects | Potentially interesting projects
|-|-|-
| Scalable Transactions | [Plasm](https://github.com/staketechnologies/Plasm), [Celer](https://github.com/celer-network), [Gunclear](https://github.com/GunClear)| roll-ups, DAG-based consensus mechanisms, side chains |
| Bridges |   [Ethereum by Centrifuge](https://github.com/centrifuge/), [EOS by Bifrost](https://github.com/bifrost-codes), [POA <> Substrate](https://github.com/paritytech/parity-bridge), [Substrate <> Ethereum DAI Bridge](https://github.com/akropolisio/POC-polkadai-bridge), [Substrate <> Substrate Bridge](https://github.com/paritytech/substrate-bridge-relay), [BTC by ChainX](https://github.com/chainx-org/ChainX)| ZCash, Ethereum, Tendermint | 
| Privacy | [ZeroChain](https://github.com/LayerXcom/zero-chain), [pLibra (Phala Network)](https://github.com/phala-network) 
| Off-Chain | [substraTEE](https://github.com/scs/substraTEE)
| Financial Chains | [Katal Chain](https://github.com/katalchain), [Laminar Chain](https://github.com/laminar-protocol/laminar-chain), [Acala](https://acala.network/), [Centrifuge](https://github.com/centrifuge/), [Stafi](https://github.com/stafiprotocol/stafi-node), [Bandot](https://github.com/bandotorg/Bandot), [Definex](https://github.com/y2labs-0sh) 
| DEXs | [OAX Foundation](https://github.com/OAXFoundation), [Cybex](https://github.com/alexxuyang/substrate-dex) | DEX with privacy and confidentiality features such as those found in a [dark pool](https://en.wikipedia.org/wiki/Dark_pool) 
| Smart contract chains | [Edgeware](https://github.com/hicommonwealth), [EVM Module](https://substrate.dev/docs/en/next/conceptual/runtime/contracts/evm_module) | sharded smart contract chains, smart contract chains with novel security approaches, smart contract chains based on exisiting toolchains|
| Access to real world data | [Oracle by Laminar](https://github.com/laminar-protocol/open-runtime-module-library/tree/master/oracle), [Oracle by Katal Chain](https://github.com/katalchain/blockchain/tree/master/modules/oracle) 
| Identity | [Caelum Labs](https://gitlab.com/caelum-tech/lorena), [Litentry](https://github.com/litentry/litentry-runtime) 
| IoT | [Nodle](https://github.com/NodleCode/), [MXC/DataHighway](https://github.com/DataHighway-DHX/node)
| Verifiable Claims | [KILT](https://github.com/KILTprotocol), [Dock](https://github.com/docknetwork) 
| Supply chain| [Wiv](https://github.com/wivtech/Substrate-SupplyChain)
| Social Networking | [SubSocial](https://github.com/dappforce/dappforce-subsocial)
| Public Voting System | | [Consul](https://github.com/consul/consul) - Open Government and E-Participation Web Software
| Messaging | [HOPR](https://github.com/validitylabs/HOPR-PL-Substrate), [Mailchain](https://github.com/mailchain)
| File Storage | [DatDot](https://github.com/playproject-io/datdot)
| Name Service| [Substrate Names](https://github.com/xaya/substrate-names)
| Gaming | | [Amethyst](https://amethyst.rs/) + [Substrate](https://substrate.dev/)
| Computation | 
| Enable specific use-cases | [Robonomics](https://github.com/airalab/substrate-node-robonomics)
| Secret store |
| Licensing |

### :black_circle: Host

| Components | Existing projects | Potentially interesting projects
|-|-|-
| Rust | [Substrate](https://github.com/paritytech/substrate)
| C++ | [Kagome](https://github.com/soramitsu/kagome)
| Go | [Gossamer](https://github.com/ChainSafe/gossamer)
| AssemblyScript | 

### :electric_plug: Network Maintenance Tools

| Components | Existing projects | Potentially interesting projects
|-|-|-
| Secure validator setup | [Trutzone-based HSM](https://github.com/ZondaX)  
| High availability setup | [Archipel](https://github.com/luguslabs/archipel)
| Deployment Tools| [Polkadot Package Manager](https://github.com/Blockdaemon/bpm-sdk), [PolkaHub](https://github.com/akropolisio/polkahub-monorepo), [Avado](https://github.com/AvadoDServer/AVADO-DNP-Polkadot-custom) 
| Validator monitoring | [P.A.N.I.C.](https://github.com/SimplyVC/panic_polkadot), [Polkalert](https://github.com/galacticcouncil/polkalert), [B-Harvest](https://github.com/nodebreaker0-0/substrate/tree/prometheus_v0.3)   
| Validator payout management | | [Bäckerei](https://github.com/cryptiumlabs/backerei) - Automated reward payment & account management for Tezos bakers

### :black_nib: Signatures

| Components | Existing projects | Potentially interesting projects
|-|-|-
| SR25519 | [C](https://github.com/usetech-llc/sr25519), [C#](https://github.com/usetech-llc/sr25519_dotnet)
| Easy multisig scheme | 
| Validator HSMs| |
| Validator HSM-like solutions|

### :satellite: Networking

| Components | Existing projects | Potentially interesting projects
|-|-|-
| DHT crawler | [Go](https://github.com/atredispartners/dht-crawler-polkadot), [Kotlin](https://github.com/emeraldpay/polkabot)

## :construction_worker: Contributing

Pull requests, issues, or other contributions from the community are encouraged!  You can not only add specific projects but also potentially interesting fields/areas, which are currently missing in the tech stack. 

:heavy_exclamation_mark: All technologies listed above need to be open-source. Ideally, the links lead directly to the code. 

_Note: You will need a GitHub account to suggest changes or file issues. If you do not have a GitHub account, you may [sign up for one for free](https://github.com/join)._
