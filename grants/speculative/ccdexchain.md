# CCDEXChain
## Project Description
We are building a cross-chain bridge for Polkadot. 
The publickey algorithm used by the polkadot network is ed25519/sr25519, we want to design an algorithm based on MPC that can support distributed generation of EDDSA signature. Based on our previous work, the ECDSA distributed signature of the cross-chain bridging BTC and ETH networks has been implemented. Combined with the EDDSA algorithm, the nodes of the polkadot parallel chain can decentralized cross-chain with the BTC, ETH and other networks.

* The general approach to bridge design.

We implementing the decentralization of private key control assets through the MPC algorithm. This means that a private key controlled account(MPC Account) can be controlled by multiple keys. These keys are generated cooperatively by multiple p2p network nodes through the MPC algorithm.  

After the user deposit BTC/ETH to the MPC account, the cross-chain bridge verifies the deposit transaction then issues the corresponding assets on the substrate/polkadot contract which also controlled by the same MPC nodes. These assets theoretically include all ECDSA and EDDSA assets. Applications such as exchange can be completed through smart contracts.

* Architecture on the issuing blockchain (Parachain architecture)

On the substrate/polkadot side, ccdexchain create a MPC account on bitcoin/ethereum which controlled by decentralized nodes. Create a MPC contract on substrate/polkadot which used for issues the corresponding assets.

* Architecture on the backing blockchain (the external chain)

On the bitcoin/ethereum side,  Bitcoin/ethereum does not need to be modified.

* How the process works to mint tokens on Polkadot

The ccdexchain monitors the user's MPC account, if a new deposit transaction occurs, after several blocks are confirmed, the corresponding assets are issued in the corresponding MPC contract. The operation of issuing assets transaction requires MPC nodes to reach consensus and collaborative distributed signatures, which can ensure the security of asset deposit and issuance.

* How the process works to redeem tokens from Polkadot

After user send the withdrawal transaction on the MPC contract of the substitute/polkadot, contract burn the polkaBTC/ETH, and the ccdexchain is triggered to generate a corresponding withdrawal transaction. This transaction also requires MPC nodes to reach consensus and collaborative distributed signatures,  which can ensure the security of withdrawal and burn assets. 

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
  - Guide: How to run the distributed signature transaction demo


- M3 - 2 weeks:  EDDSA DKG protocol implementation $20,000
  - Implement EDDSA distributed key generation and signature protocol on multiple nodes
  - Implement cross-chain bridge which veirfy the BTC/ETH deposit/withdraw transaction
  - Guide: How to run the multiple nodes network and send distributed signature transaction


- M4 - 5 weeks: Issue PolkaBTC/ETH on substrate/polkadot $30,000
  - Implement the polkadot contract which controlled by distributed nodes, the contract mapping and the cross-chain assets.
  - Deposit: Issue polkaBTC/ETH on Substrate/polkadot side when receiving tokens on BTC/ETH side
  - Withdraw: Burn polkaBTC/ETH on Substrate/polkadot side and send the tokens to the withdraw address on BTC/ETH side
  - Guide: How to deploy contract, bridge, and cross-chain transfer token


## Additional Information
### What work has been done so far?
Implemented cross-chain and DEX testnet of BTC, ETH(Not on substrate/polkadot). 

### Have you applied for other grants so far?
No.

### Are there any other projects similar to yours?
Not found.
