# Project name

## Project Description
IOV's mission is simple — to facilitate blockchain adoption by making it simple, secure and easily accessible to anyone.
 
More than a name service, IOV is an open source technology, a gateway for users to access and interact seamlessly on multiple chains. 
 
We would love to make it simple for people that build multi-chain applications to be able to interact with Polkadot blockchain easily, making Polkadot chains accessible by anyone.
 
We would love to use this grant to fund the integration of Polkadot into the multi-chain ecosystem of blockchains.
 
IOV-Core is an open source library that facilitates standard access to all chains. IOV-Core connects assets and users across all chains, and gives access to a multi-chain name service. Any multi-chain application built with IOV-Core will naturally evolve as more chains and digital assets are plugging in, without additional work from the application side. Standard multi-chain operations like atomic swap is an additional feature that chains integrated into IOV-Core can benefit from. 
 
By integrating with IOV Core, Polkadot could benefit from:
* Immediate integration in multi-chain applications built with IOV-Core, bringing users and transactions to Polkadot
* Ability to easily build multi-chain applications on top of Polkadot
* With integrated name service, Polkadot will provide a user interface that allows to associate multiple crypto addresses to a unique name. This feature could drastically improve user experience for any Polkadot dApp.
* Atomic swap can enable transfer of assets between Polkadot and other chains for its users, generating more transactions and usability.

IOV is aimed to help create an interconnected blockchain ecosystem that removes risk, complexity, and inconvenience of sending and receiving tokens and NFTs across every blockchain.

## Team members
* Benjamin Simatos
* Antoine Herzog, Dave Puchyr, Orkun Kulce

## Team Website	
* https://iov.one

## Legal Structure 
IOV SAS, 55 rue la Boetie, 75008 Paris, France
83784901700012 R.C.S Paris

## Team's experience
already launched IOV blockchain and integrated Cosmos, Ethereum, Lisk chains into IOV Core

## Team Code Repos
* https://github.com/iov-one/iov-core
* https://github.com/iov-one/


## Team LinkedIn Profiles
* https://www.linkedin.com/in/davepuchyr/
* https://www.linkedin.com/in/antoine-herzog-65aa7257/
* https://www.linkedin.com/in/benjamin-s-76b2621/

## Development Roadmap
This document put into word the budget submitted in google doc.

Here is a reminder of the main criteria of our grants:
* We are focusing on making Polkadot/Substrate chains more accessible.
* Total grant EUR 60k.
* Timeframe: around 4 months for 1 dev, with several milestones
* Open source license Apache 2.0

##Milestone 1 — Connecting to Polkadot/Substrate chain — 1 month — EUR 15,000
* We will create a Substrate module that will connect to Polkadot chains to get data in the generic way.
* 20 functions:
establish(baseUrl, options): PolkadotConnection
constructor(baseUrl, chainId)
disconnect(): void
chainId(baseUrl): ChainId
height(): number
getToken(TokenTicker): Token
getAllTokens(): Token[]
getAccount(AccountQuery): Account
getNonce(address|pubkey): Nonce
postTx(bytes)
getBlockHeader(height): BlockHeader
watchBlockHeaders
watchAccount
getTx(TransactionId) : Transaction[]
searchTx(TransactionQuery) : Transaction[]
listenTx
liveTx
getFeeQuote(transaction): Fee
withDefaultFee(UnsignedTransaction): UT
searchTransactionsById(TransactionId): Transaction[]
 
* We will deliver the first module for Polkadot/Substrate compatibility with IOV Core multichain library. This is going to be an RPC client in JS. We would be wrapping your existing API client into IOV's abstraction layer.
* The code will have proper unit-test coverage to ensure functionality and robustness.
* The testing will be possible though CLI.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

##Milestone 2 — Derive new addresses and sign transactions — 1 month — EUR 15,000
* We will create the functions to create addresses and send assets and sign messages on Substrate in a generic way.
* 10 functions:
 
bytesToSign(UnsignedTransaction, Nonce): SigningJob
bytesToPost(SignedTransaction): PostableBytes
identifier(SignedTransaction): TransactionId
parseBytes(PostableBytes, ChainId): SignedTransaction
identityToAddress(Identity): Address
isValidAddress(string): boolean
Total 6 functions

decodePolkadotAddress
decodePolkadotPubkey
isValidAddress
pubkeyToAddress(PubkeyBundle, prefix): Address
total 4 functions

* We will deliver the modules signing transactions for open source access and the integration into Neuma, a multichain chrome extension, and access to Polkadot assets into neuma based wallets and apps. We wrap the existing API into an abstract interface to simplify integration for our wallet partners which wants to connect to multiple chains, Polkadot, Eth, Cosmos, Tezos, and also to connect to our multi chain name service the IOV Name Service.
* The code will have proper unit-test coverage to ensure functionality and robustness. The testing will be possible through CLI.
* We will build a Docker image with (e.g.) our Substrate chain, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

##Milestone 3 — Cross chain atomic swap — 2 months — EUR 30,000
* We will create a smart contract for atomic swap leg compatible with other chains atomic swap to facilitate cross chain atomic swap with Substrate chains.
* 23 functions:
 
decodeSwapProcessState(data): SwapProcessState
decodeEventSignature(data): SwapContractEvent
SCReaderTotalSupply(contractAddress): BN
SCReaderBalanceOf(contractAddress): BN
createSCSwapId(): SwapId
buildSCTransferCall(unsigned: SendTransaction): Uint8Array
buildErc20ApproveCall(unsigned: SCApproveTransaction): Uint8Array
buildAtomicSwapOfferPolkadotCall(unsigned: SwapOfferTransaction): Uint8Array
buildAtomicSwapClaimCall(unsigned: SwapClaimTransaction): Uint8Array
buildAtomicSwapAbortCall(unsigned: SwapAbortTransaction): Uint8Array
parseOpenedEventBytes(bytes, SwapId): OpenSwap
updateSwapInList(AtomicSwap[], AtomicSwapUpdate, SwapIdPrefix): AtomicSwap[]
balancesFromSC(): Amount[]
getSwaps(AtomicSwapQuery): AtomicSwap[]
searchSCTransfers(sender, recipient, minHeight, maxHeight): Trasaction[]
getSwapLogs(contractAddress, minHeight, maxHeight): PolkadotLog[]
serializeUnsignedSwapOfferTransaction(SwapOfferTransaction, UnsignedSerializationOptions): Uint8Array
decodeSwapProcessState(data): SwapProcessState
decodeEventSignature(data): SwapContractEvent
SCReaderTotalSupply(contractAddress): BN
SCReaderBalanceOf(contractAddress): BN
createSCSwapId(): SwapId
buildSCTransferCall(unsigned: SendTransaction): Uint8Array
buildErc20ApproveCall(unsigned: SCApproveTransaction): Uint8Array
* We will deliver a functional cross chain atomic swap protocol compatible with Polkadot. The intentions would be to provide atomic swap between 2 Substrate based chains. This will be a Substrate module (so written in Rust) as well as the wrapping into IOV Core.
* The code will have proper unit-test coverage to ensure functionality and robustness. The testing will be possible through CLI.
* We will build a Docker image with (e.g.) our Substrate chain, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

## Future Plans
* IOV's mission is simple — to facilitate blockchain adoption by making it simple, secure and easily accessible to anyone. 
