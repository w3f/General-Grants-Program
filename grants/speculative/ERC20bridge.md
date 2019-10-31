# [PoC] ERC20 – Polkadot Bridge




## Abstract

*In order to implement an ERC20 bridge we created a special Substrate-based chain (SubstrateDAI). The bridge validator nodes are launched together with the oracles of the token bridge and are separate software modules. The oracles listen to one of the chains (Ethereum or SubstrateDAI) and register bridge-related events, perform actions to approve relay requests from validators by collecting signatures, and send confirmation of approval to the other side of the bridge. The Ethereum to SubstrateDAI transfer will result in the creation of a newly minted token on SubstrateDAI chain known as sDAI.*

*SubstrateDAI which will work independently for now, and aims to participate in the auction after the Polkadot launch to become a parachain in the network. Therefore SubstrateDAI (sDAI for short) has the possibility of being one of the first (if not the only) stablecoin chain on Polkadot, and could be leveraged by other parachains for DeFi or other applications.*


## Reference Documentation

In preparation of this specification, the following documents have been considered:

1. [Polkadot Bridges RFP](https://github.com/w3f/Web3-collaboration/issues/155)

2. [https://docs.google.com/document/d/1yMpiSAAvGeRebLlzl5fmcq_LloIViperTw4UUEuQYzM/edit](https://docs.google.com/document/d/1yMpiSAAvGeRebLlzl5fmcq_LloIViperTw4UUEuQYzM/edit)

3. [Polkadot Bridges: Design Considerations for Bridging to PoW Chains](https://hackmd.io/UVzp6Z-bRAOo9Ny531yhmA)

4. [XCLAIM: Trustless, Interoperable, Cryptocurrency-Backed Assets](https://eprint.iacr.org/2018/643.pdf)

PoC Demonstration

1. [https://polkadai-bridge.akropolis.io](https://polkadai-bridge.akropolis.io)

2. [https://github.com/akropolisio/POC-polkadai-bridge](https://github.com/akropolisio/POC-polkadai-bridge)

3. [Demo video](https://www.dropbox.com/s/8nic1r7932e5iyj/Screen%20Recording%202019-09-27%20at%2018.01.30.mov?dl=0)


## Dependencies

1. Production-ready bridge can’t be launched before Polkadot launches;

2. Audit of solution (Substrate side) cannot be carried out before an audit of stable version of Substrate has been concluded;

3. Approximate timeline for the production-ready and audited sDAI chain and bridge - 4-5 months. 



## Limitations

- PoC works only with DAI tokens (Kovan testnet)

- PoC doesn’t have limitations for daily volume which are necessary from a security point of view

- Bridge validators are a trusted set of validators. This limitation will be removed post-PoC stage



## Specification

Ethereum chain: 

1. Token bridge contract

2. the contract receives requests from the user to relay assets (tokens) to the SubstrateDAI, the corresponding amount of tokens is locked on the contract

3. the contract allows to limit bridge operations: minimum/maximum amount of tokens per one transaction and maximum amount of tokens per day

4. the contract provides a permanent address for the bridge operations

5. the contract manages the list of bridge validators, a bridge validator can be added or removed from the list

6. the contract collects confirmation calls from the bridge validators, checks if enough confirmations collected and releases the tokens

SubstrateDAI chain: 

1. SubstrateDAI has SRML module for minting and burning SubstrateDAI tokens. 

2. Bridge validators can send to SRML module messages to mint/burn tokens. 


## Process Flow
Ethereum to SubstrateDAI: 

1. Alice calls approve method for an ERC20 token linked with the bridge. The bridge contract address is pointed out as the spender

2. Alice calls a method from the bridge contract. The arguments of this method: value and recipient. The method transfer value of associated tokens to itself and emits an event for the token bridge oracle. As a result, the tokens are locked on the bridge account.

3. Every bridge validator node catches the event and sends relay request as a transaction to SubstrateDAI. The signed message contains value and recipient. Recipient is the address of tokens in SubstrateDAI chain. 

4. As soon as the needed number of relay request is generated , one of the validators sends a transaction to mint SubstrateDAI tokens and sends it to the recipient address. 

Detailed process flow is described in Appendices: Exhibit A.

SubstrateDAI to Ethereum: 

1. Alice calls method of SubstrateDAI’s SRML module. The argument of this method: value and recipient. The recipient is an Ethereum address. The method burns value of SubstrateDAI tokens. 

2. Every bridge validator node catches the event and sends a relay request to Ethereum RPC. The signed message contains value and recipient. 

3. As soon as the needed number of relay request is generated( M of N), one of the bridge validators calls the method and Ethereum bridge contract. This method unlocks DAI and sends it to the recipient address. 

Detailed process flow is described in Appendices: Exhibit B.

## Satisfaction of Requirements
**Security:**

- Tokens can be issued in the Substrate-chain only after the ERC20 tokens are locked on the bridge contract [implemented in PoC];

- Unlocking tokens is possible only upon the burning of tokens in the Substrate-chain [implemented in PoC];

- When launching a bridge, you can configure the required number of block confirmations to achieve finality [implementation is ongoing];

- The bridge supports the ability to manage a set of validators (exclude / add validators, slash validator’s stake) [implementation is ongoing];

- The bridge supports setting daily limits to reduce damage in the event of an attack [implementation is ongoing]
 
**Liveness**
the bridge supports any ERC20 token and any address pairs <Ethereum, Substrate> for both Ethereum to Substrate Chain and Substrate Chain to Ethereum [PoC for DAI token]

**Redemption option**: implemented without any restriction in PoC

**Consistency:** tokens can be issued in the Substrate-chain only after the ERC20 tokens are locked on the bridge contract. [PoC]

**Auditability:** all bridge transactions can be tracked using the block explorer (etherscan and polkadot-js). 

**Scalability:** the bridge has a restriction related to Ethereum throughput (since all validators send transaction confirmation to Ethereum). No other scalability restrictions. 


## Legal Structure

Akropolis Decentralised Ltd , Suite 23 Portland House, Glacis Road, Gibraltar, GX11 1AA, company number: 116430


## Team Website

[Akropolis.io](https://akropolis.io)


## Team's experience
Recent team updates:

- IBM MoU signed, co-development partnership confirmed [press-release pending]

- Winner of a 0x+Coinlist DeFi Hackathon. Developed a new economic primitive ["Committments to Future Cashflows"](http://cashflowrelay.com/)

- [C2FC Implementation on Substrate](https://github.com/akropolisio/akropolis-polkadot) and its [telemetry](https://telemetry.polkadot.io/#/Akropolis).
POC implementation of [Ethereum-Polkadot bridge](https://github.com/akropolisio/POC-polkadai-bridge). 
Last development updates include launch [DAO module with DeFi integrations](https://medium.com/akropolis/akropolis-launches-the-first-testnet-afo-governance-module-9fbde56ce33f) and [tools for Polkadot ecosystem](https://medium.com/akropolis/akropolis-development-update-august-2019-2b54318566a1) (Browser extension and Staking Portal). 


**Alex Maz (CTO)**

Blockchain engineer, educator and an active founding member of St.Petersburg Blockchain Association, Alex graduated with BSc Applied Mathematics and Computing Sciences and is a PhD (cand.) Machine Learning. Blockchain developer and miner since 2012, he has 16 scientific publications focussing on natural language recognition and 10 commercially implemented applications to his name. Alex has shipped products in fintech, banking, and gaming, and is passionate about educating the new generation of blockchain developers. Full-stack developer with over 15 years experience (C#/.NET, Golang,  Java, Solidity).

https://github.com/AlexanderMazaletskiy

https://www.linkedin.com/in/alexander-mazaletskiy/

**Dmitriy Serdcev (Senior Frontend Developer)**

Dmitriy is an experienced frontend developer with MSc in Computer Science. He has15 years of experience in the field,  and has shipped over 8 commercial projects, including those using DLT technology. 

https://github.com/in19farkt

https://www.linkedin.com/in/dmitriy-serdtsev-8307b617b/
 
**Andrew Orlov**

Andrew is a MSc Computer Systems. His skills include Rust, Erlang, Elixir, Python, Haskell, WASM, Polkadot/Substrate. He has 13+ years in commercial software development.

https://github.com/andor0 
 
**Alex Gnatovskyi**

Alex is a BSc Electrical Engineering and Electrotechnologies. His skills include Rust, NodeJs, Python, React, Polkadot/Substrate. Alex has 2.5+ years of commercial development experience.

https://github.com/alekspickle 

## Team Github

[https://github.com/akropolisio](https://github.com/akropolisio)

[https://github.com/akropolisio/akropolisOS-chain-node](https://github.com/akropolisio/akropolisOS-chain-node)

[https://github.com/akropolisio/polkadai-bridge](https://github.com/akropolisio/polkadai-bridge)


## Team Code Repos

[https://github.com/in19farkt](https://github.com/in19farkt)

[https://github.com/AlexanderMazaletskiy](https://github.com/AlexanderMazaletskiy)

[https://github.com/andor0](https://github.com/andor0)

[https://github.com/alekspickle](https://github.com/alekspickle)

## Team LinkedIn Profiles

[https://www.linkedin.com/in/alexander-mazaletskiy/](https://www.linkedin.com/in/alexander-mazaletskiy/)

[https://www.linkedin.com/in/dmitriy-serdtsev-8307b617b/](https://www.linkedin.com/in/dmitriy-serdtsev-8307b617b/)


## Target Programming Language

Rust, Javascript/Typescript, Solidity

## License

Apache 2.0

## Development Roadmap

**1 Milestone - full specification (1 month)**

- Technical and design specs delivery 

- Basic documentation of the PoC functionality

- PoC: 
	- Multi-sig smart contract on Solidity
	- Substrate module for bridge validators
	- Simple UI/UX. 
 

**2 Milestone - implementation (2nd-3rd month)**

- Technical and design Specs delivery 

- Bridge Monitoring tool

- Validators managing functionality (ability to add/remove validator, finality options, etc)

- Managing daily limits and other options in order to minimize possible damage in case of attacks

- Validator nodes incentivization (bridge fee, slashing, etc)
 
**3 Milestone - security audit & launch (4rd-5th month)**

- Define bridge validators set (3-4 well-known blockchain companies)

- Report from security auditor


## Appendices

### Exhibit A. Ethereum to Substrate Transfers

<img src="/images/bridge1.png" alt="drawing" />

1. Sender calls **setTransfer**(amount, recipient) function and gets messageID - unique identifier of bridge transfer.

2. Funds are transferred to bridge smart contract. Bridge smart contract issues event *RelayMessage*(messageID, sender, recipient, amount).

3. Bridge validators listen to *RelayMessage*(...) event. When bridge validator registers RelayMessage(...) event, it calls approveTransfer(messageID, sender,  recipient, amount) function of Bridge Ethereum Smart contract. 

4. Bridge smart contract collects **approveMessage** calls. If smart contract gets approveTransfer from N validators 
(M - number of approves from bridge validators,
 N - number of bridge validators, M<=N),
 it locks funds and issues ApprovedRelayMessage(messageID, sender,  recipient, amount)

5. Bridge validators listen *ApprovedRelayMessage*(messageID, sender,  recipient, amount) event. When bridge validators get it, bridge validator calls **multi_signed_mint**(message_id, from, to, amount) function of Bridge SRML. 

6. Bridge SRML module collects **multi_signed_mint** calls from validators. 

7. If it gets N approves from bridge validators, Bridge SRML mints sDAI tokens and issues event *MintedMessage*(message_id). 

8. Bridge validators listen *MintedMessage*(message_id) event. When validator register it, validator calls **confirmTransfer**(messageID) function of Bridge Ethereum Smart contract. 

Types:

1. Substrate:
	- message_id - H256

	- from - H160

	- to - AccountId 
	- amount - Balance (uint128)

2. Ethereum:
	-	messageID - bytes32
	-	sender - address
	- 	recipient - bytes32
	-	amount - uint256


### Exhibit B:  Substrate to Ethereum transfers

<img src="/images/bridge2.png" alt="drawing" />

1. Sender calls **set_transfer**(recipient, amount) function and gets messageID - unique identifier of bridge transfer.

2. SRML bridge issues the RelayMessage(messageID) event.

3. Bridge validators listen to *RelayMessage* event. When bridge validator registers it, validator calls **approve_transfer**(messageID) function of Bridge SRML 

4. Bridge SRML collects **approve_transfer** calls. If it gets approve_transfer from M validators 
(M - number of approves from bridge validators, 
N - number of bridge validators, M<=N), 
it locks funds and issues ApprovedRelayMessage(messageID, sender,  recipient, amount)

5. Bridge validators listen ApprovedRelayMessage(messageID, sender,  recipient, amount) event. When bridge validators get it, bridge validator calls **withdrawTransfer**(message_id, from, to, amount) function of Bridge Smart Contract. 

6. Bridge Smart Contract collects **withdrawTransfer** calls from validators. If it gets N approves from bridge validators, Bridge Smart Contract unlocks DAI tokens and transfers them to Recipient. 

7. Bridge Smart Contract issues event *withdrawMessage*(message_id). 

8. Bridge validators listen withdrawMessage event. When validator register it, validator unlocks the funds and calls **confirm_transfer**(messageID) function of Bridge SRML. As soon as the needed number of relay request is generated (M of N) SRML module burnes sDAI tokens, and emits *BurnedMessage*(Hash, AccountId, H160, TokenBalance) event
