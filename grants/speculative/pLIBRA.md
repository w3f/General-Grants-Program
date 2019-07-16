# Project name

## Project Description
pLIBRA is a privacy-preserving Libra powered by Private Contract on Polkadot. We aim to protect the privacy of Libra users. More specifically we will create:

- A bridge connecting Polkadot and Libra
- A privacy-preserving token on Polkadot for Libra users
- A privacy-preserving DApp ecosystem better than Calibra

### Why Libra

Started by Facebook, a company with 2.7B users, Libra may be the first blockchain to achieve massive adoption. LibraCoin may become the stable coin with the most liquidity and consensus.

Though Libra aims to become a permissionless blockchain in long term, Calibra, the source of its user base is a completely centralised wallet:

1. Calibra stores the full history of user activities. Even if they promise to keep it secretly, the wallet service, 3rd parties, and even Facebook can get your identity.
2. Your private information could be used or distributed when Calibra considers it necessary.

We don’t think users should be watched or controlled by a company. Libra should be freely used on all the blockchains.

### Why Polkadot

Polkadot offers flexible cross-chain interoperation functionality. As the high users base and volume expectation, Polkadot can bring Libra to other blockchains business to release its full power for Libra users.

### Privacy Contract

The core technology of pLIBRA is Privacy Contract. It brings trutless and privacy preserving Turing-Complete smart contract to Polkadot ecosystem and make pLIBRA possible.

From late 2018, our team started to work on Turing-Complete Privacy Contract baded on trusted execution environment (TEE). It guarantees the security without compromising data privacy. The pLIBRA Privacy Contract runs a Libra light client inside the enclave. Thanks to Privacy Contract, on the one hand, the client can manage privkeys and sign transactions without utilising cpu intensive cryptographic. On the other hand, it gets privacy preserving token like Monero for free.

The PoC is now based on Intel SGX, already supported by the mainstream servers. However the special hardware are only required by miners, not users.

## Team members
* Hang Yin: Blockchain & Smart Contract system design
* Jun Jiang: Privacy Smart Contract and SGX Kernel development
* XiaoXuan Tang: Bridge Client development
* Marvin Tong: Project Manager
* Zhe Wang: Business Development

The development will be mainly done by 2-3 full-time and one part-time engineer. The remaining people will provide necessary support to the development.

## Team Website	
* https://libra-china.org

## Legal Structure 
HashForests (Wuhan) co. LTD, a startup company focusing on blockchain development in China.

## Team's experience

HashForests was founded in late 2018 focusing on off-chain scaling and trusted execution environment technologies. We have developed a prototype of Intel SGX based smart contract and plugged it into a Graphene based blockchain. We have also developed a few DApps as proof of concept.

In June 2019 we started [LibraChina](https://libra-china.org), a communtiy focusing on promoting blockchain massive adoption and Libra technology. Since then we have developed a Libra testnet explorer [LibraBlock](https://librablock.io) and an online wallet is currently a work in progress.

Before the team was founded, our team members has been worked in Google, DiDi Chuxing, Dji, and Liwoshuo, a famous China startup. We have blockchain experts who initiated Bitcoin Gold, a fork of Bitcoin and now its market cap is ranked around 25th. The team mainly write C++, Js, Rust, Ruby, and Python.

* Hang Yin: Founder and Lead Developer of Bitcoin Gold. Senior Developer of Google. 10 years coding experience.
* Marvin Tong: Senior Product Manager with 3 years experience . Worked in Tencent and Didi which both are the biggest Internet Companies in China. Good at Product Design and Business Development.
* Zhe Wang: Hardware Engineer. Core member of Bitcoin Gold in China.
* Jun Jiang: CTO of KnewOne and Senior Software Architect in Dji. Lead of RubyChina community.
* XiaoXuan Tang: CTO of Liwushuo. Senior iOS developer and System Architect.


## Team Code Repos

- Private projects by team members
  - Bitcoin Gold (Hang Yin): https://github.com/BTCGPU/BTCGPU
  - Rails Engine (Jun Jiang): https://github.com/rails-engine

## Team LinkedIn Profiles
* Hang Yin: https://www.linkedin.com/in/hang-yin-167012a7/
* Marvin Tong: https://www.linkedin.com/in/林-佟-0131b292/
* Zhe Wang: https://www.linkedin.com/in/喆-王-0a99a038/
* Jun Jiang: https://www.linkedin.com/in/jun-jiang-5b9b4153/
* Xiaoxuan Tang: https://www.linkedin.com/in/xiaoxuan-tang-26628784/

## Development Roadmap

- [pLIBRA One Pager](https://docs.google.com/document/d/e/2PACX-1vRpkf-xvEwDSglNHMKI2J8qC7F4JiB7kLv5kOwO_mJzg-bYRL545_3JxWaM-0rCX_iyHDb68zk3Sw75/pub)
- M1 - 1 weeks Release the Technical Whitepaper
  - $500
- M2 - 4 weeks: Privacy Contract infrastructure on Substrate as a Polkadot Parachain
  - Script to launch Substrate and deploy a ERC-20 like token contract inside the enclave
  - Run confidencial transaction tests with the test token
  - $12,500
- M3 - 2 weeks: Libra cross-chain bridge as a Privacy Contract
  - Script to launch the bridge node
  - Issue pLIBRA on Substrate side when receiving money on Libra side
  - Brun pLIBRA on Substrate side and send the token to the withdraw address on Libra side
  - $6,000
- M4 - 3 weeks: Final product with user interfaces
  - Fully working cross-chain transferring
  - Fully working Privacy Coin pLIBRA
  - Cross-chain transferring function in our online Libra wallet
  - $11,000

### Long Term Plan
pLIBRA is based on Privacy Contract. We intend to extend the underlying infrastructure to a generic Turing-Complete contract platform as a Parachain called Phala Network. It will support:

- Async privacy contract
- Permissionless computing power market
- Deploy cross-parachain bridge
- Bridge for trusted IoT devices
- More TEE in addition to Intel SGX


## Additional Information

* What work has been done so far?
  * Libra blockchain explorer: [librablock.io](https://librablock.io)
  * PoC of SGX based Privacy Contract
  * Get familiar with the Libra light client
* Are there are any teams who have already contributed (financially) to the project?
  * No.
* Have you applied for other grants so far?
  * No.
* Are there any other projects similar to yours?
  * [Substrate SGX](https://github.com/libra-china-org/Web3-collaboration/blob/master/grants/speculative/substrate_sgx_proposal.md) is similar to our Private Contract implementation.
* How is your project different?
  * We focus on brining Libra ecosystem to Polkadot with privacy-preservation in a novel way while Substrate SGX is a specific SGX extension implementation.
