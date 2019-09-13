# CCDEXChain
## Project Description
We are building a cross-chain bridge for Polkadot. 
The publickey algorithm used by the polkadot network is ed25519/sr25519, we want to design an algorithm based on MPC that can support distributed generation of EDDSA signature. Based on our previous work, the ECDSA distributed signature of the cross-chain bridging BTC and ETH networks has been implemented. Combined with the EDDSA algorithm, the nodes of the polkadot parallel chain can decentralized cross-chain with the BTC, ETH and other networks.

* The general approach to bridge design.

* Architecture on the issuing blockchain (Parachain architecture)

* Architecture on the backing blockchain (the external chain)

* How the process works to mint tokens on Polkadot

* How the process works to redeem tokens from Polkadot

You can find more details here:
https://ccdex.top/docs

## Team Members
* Dr. Chengshi Gao - Lead
* Leon
* eric
* booksxlee

## Team Website
https://ccdex.top/

## Legal Structure
No.

## Team's experience
Our team has implemented cross-chain and DEX testnet of mainstream cryptocurrencies such as BTC, ETH, XRP, ATOM, BNB, etc. See website: https://ccdex.top

Team’s works on blockchain space are following.
* https://ccdex.top/trade
* https://ccdex.top/explorer
* https://ccdex.top/wallet
    

## Team Code Repos
* ccdex: https://github.com/ccdex

## Team LinkedIn Profiles
* Chengshi Gao https://www.linkedin.com/in/%E6%89%BF%E5%AE%9E-%E9%AB%98-635ab5b1/
* Leon  https://github.com/jnxchang
* eric  https://github.com/erichu0722
* booksxlee https://github.com/booksxlee


## Development Roadmap
The milestones are spread out over a total of 3 months as following:
- M1 - 2 weeks: Algorithm design $30,000
  - Design Doc: Distributed EDDSA/ED25519 Signature Based on MPC Algorithm

- M2 - 3 weeks: Distributed signature implementation and polkadot transaction verification $20,000
  - Implement the EDDSA distributed signature algorithm on one node
  - Build the distributed signed polkadot transaction  
  - Guide: How to run the polkadot distributed signature transaction demo

- M3 - 2 weeks:  Cross-chain issue DOT on ccdexchain and DEX $20,000
  - Implement EDDSA distributed signature on multiple nodes
  - Deposit: Issue polkaBTC/ETH on ccdexchain when receiving tokens on BTC/ETH side
  - Withdraw: Burn polkaBTC/ETH on ccdexchain and send the tokens to the withdraw address on BTC/ETH side

- M4 - 5 weeks: Cross-chain issue BTC/ETH on substrate/polkadot $30,000
  - Deposit: Issue polkaBTC/ETH on Substrate/polkadot side when receiving tokens on BTC/ETH side
  - Withdraw: Burn polkaBTC/ETH on Substrate/polkadot side and send the tokens to the withdraw address on BTC/ETH side
  - Guide: How to deploy bridge and transfer token


## Additional Information
### What work has been done so far?
Implemented cross-chain and DEX testnet of BTC, ETH. But not on substrate/polkadot. 

### Have you applied for other grants so far?
No.

### Are there any other projects similar to yours?
Not found.
