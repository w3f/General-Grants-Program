# Bifrost Network

## Project Description
Bifrost is a parachain designed to liberate staking's liquidity. based on Substrate development, users can convert PoS currency into Bifrost vToken via Bifrost interoperable bridge at any time to obtain staking revenue and liquidity. 

vToken can optimize transactions in multiple scenarios such as DEFI, DAPP, DEX, etc. If vToken is used as collateral for lending, its staking income can offset part of the interest and realize low-interest loans.

Bifrost needs to use a number of different public chain interoperable bridge to support the operation. In view of the early development and the lack of enough available interoperable bridges, we are currently developing a public EOS interoperable bridge and hope to apply for grant to promote the development of bridge. 

We expects that as the Polkadot and Substrate ecosystem matures, we will be able to use different public chain interoperable bridges developed by other teams.

![bifrost-structure-chart](https://cdn.liebi.com/resource/images/bifrost-structure-chart-v2.png)

## Team members
* Edwin Wang（Full Stack Engineer, CTO）
* Lurpis Wang (Full Stack Engineer)
* Jianping Deng (RUST & C++ Engineer)
* Alex Yu (RUST Engineer)

## Team experience
Bifrost is a project developed by Liebi technology based on substrate. Bifrost technology prototype is the underlying technology of the Liebi Pool. The Liebi Pool will also be the first application built on the Bifrost, Bifrost is also an open platform, we hope to provide more capabilities to the staking economy.

Liebi team consists of technical experts with years of experience in blockchain development. The mission is to make the blockchain simpler and lower the blockchain threshold so that more users can easily use the blockchain technology in their lives. our team’s products mainly around staking development, have extensive experience in staking, and have multiple public blockchain development capabilities.

## Team Website 
* https://bifrost.finance
* https://liebi.com

## Team repository
* https://github.com/bifrost-finance

## Bifrost EOS Bridge (Grant application)
The Bifrost EOS interoperable bridge is a substrate-developed project that combines SPV client and multi-signature mechanisms to build a secure, flexible, and scalable cross-chain without modifying the core functionality of the parent chain. We also envisioned a version in which the parent and side chains are SPV clients of each other. This version is more distributed and safer, but it is costly and difficult to implement. The current approach not only allows the user's assets to be chained, but also the staking benefits of the parent chain. In the future, it can also support any operation across the chain for true interoperability.

### Technical solutions
In this solution, the two sides participating in the cross-chain are the the **parent chain** and the **Bifrost sidechain**. The Bifrost sidechain actively collects and synchronizes transactions from the parent chain. The parent chain passively accepts and verifies transactions from users or sidechain.

#### Parent Chain
On the parent chain, we build a cross-chain contract as the entrance to Bifrost side chain, all transactions submit to the contract need to use multi-signature. The signer of the multi-signature must be the Bifrost’s notary node. Each notary node saves the private key of the parent chain account locally. The notary node is elected through the governance system and is rotated periodically. After the notary is rotated, the multi-signal configuration of the main chain side cross-chain contract is also required to be replaced. 

The user’s cross-chain assets are stored in cross-chain accounts or sub-accounts, and the security of user assets is maintained by multi-signature mechanism. The parent chain only passively accepts transactions submitted by the sidechain.

#### Bifrost Sidechain
**Bifrost sidechain** consists of the **SPV client** of parent chain and the **notary node multi-signature mechanism**, the SPV client is cross-chain entry for Bifrost, responsible for synchronizing parent chain block header data, verifying cross-chain transactions legitimacy. Notary node multi-signature is cross-chain export for Bifrost, responsible for signing parent chain transactions, and send transactions to the cross-chain contract on parent chain. After cross-chain contract detects that the multi-signature transaction meets the signature threshold, the subsequent operation will be performed.

#### Runtime modules
To implement the above mechanism, we will add the following modules to Substrate runtime:

##### 1. Bridge module
The Bridge module is a cross-chain core module that collects, validates, maps transactions from parent chain, and sends multi-sign transactions to parent chain. It contains the following features:

- **Parent Chain Registration**: Includes registration of the parent chain’s information, registration of each validator’s information, preventing receipt of data from forged sites.
- **Parent chain SPV client**: Includes parent chain block header information synchronization, cross-chain transaction verification.
- **Parent chain transaction mapping**: Verified transactions will be mapped to the Bifrost chain.
- **Parent chain transaction generation**: Transactions sent to the parent chain need to be generated on the sidechain first.
- **Signing for the parent chain transaction**: The parent chain transaction must be signed by each notary node before being sent.
- **Sending parent transaction**: Send the transaction to parent chain when collecting a sufficient number of signatures.
- **Parent transaction confirmation**: Update the original transaction status after confirming that the parent chain transaction has been received.

##### 2. Asset module
The creation, distribution, transfer, and destruction of user’s cross-chain assets. Cross-chain assets need to be created first through the governance system. Cross-chain assets need to be mapped by issue or destroy operations, accordingly.

#### Workflow
##### Parent chain to Bifrost sidechain
![bifrost-structure-chart](https://cdn.liebi.com/resource/images/parent-chain-to-bifrost.png)

##### Bifrost sidechain to parent chain
![bifrost-structure-chart](https://cdn.liebi.com/resource/images/bifrost-to-parent-chain.png)

#### Security
**SPV client sync forged block header information**: SPV client information is synchronized and jointly verified by each node. As long as the data provided by most nodes is correct, it can resist a few nodes to do evil.

**SPV client receives forged parent chain transaction**: Forged transactions cannot be verified by SPV, so it is safe as long as the SPV client’s data is ok.

**Generate forged parent chain transaction by evil nodes**: The premise of generating a parent chain transaction is that user to initiate a cross-chain transaction first, so this method cannot pass block verification.

**Forged multi-signed parent chain transactions**: Due to the trend of interest, there may be multiple nodes working together to do evil. The forged transaction can jump over Bifrost, directly signing and sending transactions to parent chain. Solution is that:
  
1. The number of participating nodes should be as many as possible, and the threshold of multi-sign should be as high as possible.
2. The candidate notary must be evaluated carefully based on factors such as user voting, reputation, and capabilities.
3. User assets on parent chain should be distributed to multiple sub-accounts. Each sub-account is signed by different set of notary, and the notary’s signature should be rotated periodically. (If you have a safer and more reasonable solution, please feel free to tell us :)

## Development Roadmap
##### Milestone 1 - RUST-EOS Development - 1 month - $10k
- EOS Primitive structs
    - Block
    - Transaction
    - Action
    - Name
    - Asset
    - Symbol
    - TimePoint
    - Checksum256
- EOS RPC interface
    - abi_json_to_bin
    - get_abi
    - get_account
    - get_currency_balance
    - get_currency_balance
    - get_block
    - get_info
    - get_raw_code_and_abi
    - push_transaction
- EOS P2P message protocol rewrite
    - Request message
    - Handshake message
    - Go away message
    - Notice message
    - Sync request message
    - Chain size message
    - Time message
- SECP256K1 crypto
    - Public key with EOS format
    - Secret key
    - Signature/Canonical Signature with EOS format
    - Keystore
- Custom subkey to support EOS
    -  SECP256K1 key generate/sign/verify
    -  Submit EOS transactions

##### Milestone 2 - SPV Client Development - 1.5 month - $15k
- P2P protocol for EOS
- Support EOS localnet/testnet/mainnet
- Block listener/verify
- Transaction listener/filter/verify
- Merkel tree verification
- Multisig transaction
- Bridge contract on EOS

##### Milestone 3 - Bridge Runtime Development - 0.5 month - $5k
- Offchain worker
    -  Comunicate with SPV client
    -  Sign transactions
    -  Submit transactions
- RPC module
    -  PRC for Bridge runtime
- Interoperability with eosio contracts
    -  Assets interoperability first
    -  Maybe contract interoperability
- Node docker image
    -  Bifrost node/tool image
    -  SPV client image
- Bridge interface protocol
- Custom command for cli

## Overview
##### Milestone 1
Use RUST to refactor the base component library of the EOS method, enabling the Substrate Runtime Module to build EOS Block, transaction, initiate RPC, rewrite P2P Message, generate public and private keys, and verify.

##### Milestone 2
Improve the SPV client, support Bifrost node and EOS node P2P protocol communication, EOS local network, test network, main network outbound block monitoring and filtering, complete the block header Merkel tree verification, and initiate multi-signal transactions from Bifrost to EOS network , complete the EOS network transfer bridge contract deployment.

##### Milestone 3
The interoperable bridge runtime module development enables the interoperable bridge to complete Bifrost and EOS bidirectional operation, package Bifrost EOS interoperable bridge node docker image, open interoperable bridge interface protocol, and complete custom interactive commands.
 
## Demo
##### Milestone 1
RUST-EOS is the Substrate component library, run the following command for environment testing and refer to the generated test case for development reference.

1. Install RUST
```
# curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

2. Clone rust-eos repository
```
# git clone https://github.com/bifrost-finance/rust-eos
```

3. Run Cargo test
```
# cargo test
# test result: SUCCESSED. 100 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out
```

##### Milestone 2
on the way…

##### Milestone 3
on the way…


## Additional Information
The Roadmap related code will be packaged into a docker container for verification, and the EOS interoperable bridge will be released at the Bifrost POC-3 stage. We hope to apply $30k of grant support to drive the development of a generic EOS interoperability transfer bridge. DOT and USDT We are happy to accept :)

##### What work has been done so far?
Currently we have open sourced Substrate supported RUST-EOS components and SPV Client developing and expect to open source in the future.
 
rest-eos repository: https://github.com/bifrost-finance/rust-eos

##### Have you applied for other grants so far?
We participated in the Substrate development hackathon organized by Polkaworld with the Bifrost project and won the competition. The rest was invested by the team and no other subsidies were applied.

*Bifrost EOS interoperable bridge is currently in the draft phase, more detailed design is still in progress. Any suggestions would be greatly appreciated.*
