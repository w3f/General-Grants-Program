# Project Name
Polkadot-Solana bridge

## Project Description
This is an application for development of the Polkadot-Solana bridge.

There are currently a few approaches to build a decentralized bridge between two blockchains. Two of them are XClaim bridge and PoA Bridge (modernized Parity bridge). However, the only working bridge that exists in production (mainnet) is PoA Bridge. Security provided by PoA Bridge is authority of an administrator who manages a list of trusted validators.
XClaim bridge is trying to overcome centralization and authority mechanism with relayChain. Security is based on a proof that a TX happened on the backing (foreign) chain. This approach has not been implemented in a secure way yet (XClaim relays on code of BTC-Relay which is not even in the MVP phase yet).

We are going to introduce a bridge model where we try to resolve the problems of PoA Bridge and centralization without involving expensive operations of relay chains design of XClaim bridge.
It is more robust and secure to built up an incentive game over PoA Bridge, but instead of an authoritarian list of validators we implement the mechanics which integrates dependency on stake required for being a validator. Therefore bridge maintainers should be validators and be economically interested in supporting bridge and behaving fairly. Such interest is based on the concept that malicious actions of validators on Foreign chain will lead to decreasing price of Home tokens which results in lowering economical value of validators stakes.

## Team members
* Vitalii Parkhomenko – team lead/researcher/tech writer
* Aleksei Korobeinikov – developer
* Olexiy Buyanskyy – developer

## Team Website
* https://everstake.one & https://atticlab.net

## Legal Structure
ATTIC LAB, Limited Liability Company. 89, Kazimir Malevich str., Kyiv, 03150, Ukraine

## Team's experience

Everstake is an affiliate company of Attic Lab, so members from both teams are going to participate in the project. We have developed VSCode and Atom plugins for Substrate. We have also created a PSP for this project.

Our prior projects and experience include: Crypto exchange Codex. Cassandra history plugin, Munin plugins, OpenBankIT open-source banking software, EOS History API running on Elasticsearch cluster, My EOS Wallet. (web and mobile), NEO IDE, Teztracker (Tezos blockchain explorer).

## Team Code Repos
* https://github.com/everstake
* https://github.com/atticlab

## Team LinkedIn Profiles
* https://www.linkedin.com/in/vitalii-parkhomenko-493561187/
* https://www.linkedin.com/in/aleksei-korobeinikov/
* https://www.linkedin.com/in/olexiy-buyanskyy-2111795/

## Development Roadmap
1. M1 - Asset Bridge
At this point the bridge is able to send messages with the given number of validator signatures from Solana to the Polkadot chain. No error reporting, no exactly-once-delivery guarantee, no token transfer. Polkadot part of the bridge could be upgraded with newer version.
   * Listener (watcher in terms of PoA) (80h)
      * Implement and integrate Solana chain client with oracle software
      * Listens to Polkadot events
      * Keeps tracks of last processed block (part of exactly once delivery)
      * Submits signatures to Solana bridge contract
   * Worker (sender in terms of PoA) (60h)
      * Listens to Solana events
      * Sends TX to specified method on Polkadot bridge module/contract
      * Stores unprocessed TXes in persistent storage
   * Polkadot modules/contracts (30h)
      * Bridge modules/contract
         * Stores message in specified contract
         * Unpack methods signature and do call
      * Store modules/contract 
         * Store given data received from specified address
   * Solana contracts (60h)
      * Bridge contract
         * Receives data and emits event with the `bytes32 bundledHash`
         * Collects signatures  from validators
         * Validates signatures issued for Polkadot
         * Emit event to worker upon reaching a signatures threshold
      * Validator contract
         * Manages list of validators (add, remove)
         * Manages number of signatures
   * Setup and deployment (24)
      * Deploy Solana contracts
      * Deploy Polkadot modules/contracts
      * Setup Listeners and worker
      * Check integrity
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Total hours for M1: 254

2. M2 - tokens->Native Bridge. At this point the bridge is able to transfer tokens from Polkadot to Solana. Keeps track of TX status.
   * Polkadot modules/contracts (60h)
      * Bridge modules/contract
         * Validates signatures issued for Solana
   * Solana contracts (50h)
      * Bridge contracts
         * Extracts and validates signatures
         * Limits on daily operations
         * Able to unlock locked native tokens backed by Polkadot tokens in amount 1-to-1 upon receiving corresponding TX and sends them to the given address
   * Listener (20h)
      * Could submit signature readable by Solana chain
   * Worker (50h)
      * Sends TX to specified method on Solana bridge contract
      * Able to execute `mint` functionality on Solana chain
      * Keeps track of `tokens->Native transactions` from receiving to executing (error reporting)
   * Deployment (12h)
      * Update Solana contracts and Polkadot modules/contracts
      * Check integrity
   * Reserve (30h)
   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Total hours for M2: 202

3. M3 - Native->tokens Bridge. At this point bridge implements Native <---> tokens functionality; has fault tolerance to worker crashes; has error reporting improvements.
   * Polkadot modules/contracts (30h)
      * Bridge modules/contract
         * Able to unlock locked tokens upon receiving corresponding TX
   * Solana contracts (30h)
      * Bridge contract
         * Allows to lock native tokens in exchange of Polkadot tokens backing tokens and emits corresponding event
   * Listeners (8h)
      * Listens to Solana `Native->Polkadot tokens` events
   * Worker (40h)
      * Containerize worker with additional replicas (fault tolerance improvement)
      * Worker has notifications(email/messenger) in case of insufficient funds 
   * Deployment (8h)
      * Update Solana contracts and Polkadot modules/contracts
      * Check integrity
   * Reserve (30h)
   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Total hours for M3: 146

4. M4 - NFTs Bridge. At this point the bridge could mint, lock, unlock NFT tokens approved by validators.
   * Polkadot modules/contracts (40h)
      * Bridge modules/contract
         * Able to validate that given token is NFT token
         * Able to lock/unlock any NFT tokens and emit corresponding events
         * Manages list of trusted NFT token issuers
   * Solana contracts (60h)
      * Bridge contract
         * Able to lock/unlock any NFT tokens and emit corresponding events
         * Manages list of trusted NFT token issuers
      * NFT Token module/contract
         * Able to mint token with permission
         * Could be deployed by different accounts 
   * Listeners (8h)
      * Listens to `NFT` events
   * Worker (20h)
      * Able to execute `lock\unlock` functionality on both chains
   * Deployment (8h)
      * Update Solana contracts and Polkadot modules/contracts
      * Check integrity
   * Reserve (35h)
   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Total hours for M4: 191

**Total timeline: 3.5 actual months or 793h**
