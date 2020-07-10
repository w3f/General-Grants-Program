# Project name
List All Parachain Tokens on Ethereum DEX.

## Project Description
Through this project, we want to list all Parachain's tokens on Ethereum DEX. Listing tokens at a popular exchange is definitely necessary ,but it is expensive (Usually 8 BTC to $1M) and it takes long time. In addition, since all parachains are built not with Ethereum but with Substrate, user accessibility is still not good enough compared with the existing methods to get ERC20 tokens. (e.g. Uniswap, Bancor, Kyber) 

We will solve these problems by making a bridge between Ethereum and Substrate. The bridge we are going to build is trustless, secure, and cheaper gas costs.

If we could make the bridge, all parachain tokens could be traded through Ethereum DEX. This can bring many users from other blockchain platforms to Polkadot ecosystem.

As you may know, our team is building Plasm Network, a scalable smart contract platform which is compatible with Polkadot. One of the key milestones for us is to list the PLM token at a popular exchange in this year so that it is much more accessible for crypto enthusiasts to interact with Plasm Network. I guess other potential parachain projects will face this problem as well. Plasm Network is built with Substrate, so if you can make the bridge between them. This mechanism can be applied to other Substrate based Parachains.

### Specification
As a preparation, we have to deploy a Bridge Smart Contract. The Bridge Smart Contract on Ethereum stores the authorities(validators) list of grandpa. If the authorities change, we have to send a transaction to let Ethereum know the changes. (This transaction can be sent by anyone).

To claim the token, a user firstly has to lock the token on Substrate. After that, the user, or anyone else has to send the transaction on Ethereum with following data.

- Inclusion proof of transaction (or events, storage) in particular block on Substrate
- Justification of block
- GRANDPA authorities signature of that block.

### Difficulties
Grandpa, the finality gadget on Substrate uses ed25519 signature. But ed25519 is not natively supported on EVM. So, the gas cost will be around $10 to verify only single signature. Since there are many authorities in one round (around 100), it is impossible to verify signature one by one on the chain (It is still expensive if we use batch verification of ed25519 onchain).  To solve this Problem, we use *ZK-SNARKS* to verify the GRANDPA’s signature. Now we are planning to use *ZoKrates* library to create proof and verification.

ed25519 on substrate uses sha2-512 internally. However, sha2-512 is supported on neither ZoKrates nor Substrate. So we have to implement sha2-512 function on ZoKrates or Substrate. If we choose to implement sha2-512 on ZoKrates, offchain computation cost might be high. If we choose to implement sha2-512 on Substrate, onchain computation cost(gas cost) might be high.

## Team members
* Sota Watanabe
* Task Ohmori
* Yoshinobu Shijyo
* Masaharu Uno

Currently, we have 8 members in the team. The other 4 members are working on Plasm. And above 4 menmebers will be working on the DEX.

## Team Website	
* https://www.plasmnet.io/
* https://stake.cp.jp/en

## Legal Structure 
Incorporated in Japan

## Team's experience
Currently, Stake Technologies, a company behind of Plasm Network focus 100% on Polkadot and Substrate. We have been contributing to Polkadot and Substrate around 1.5 years. Below is the trucking record.

* Plasma implementation on Substrate
* ink! playground
* OVM implementation on Plasm Network
* Talked at Sub0 summit and DOT CON
* Participating in Web3 Bootcamp and UC Berkeley Xcelerator
* One of the first members of Substrate BUilders Program and Substrate Delivery Partner Program.
* etc

## Team LinkedIn Profiles
* https://www.linkedin.com/in/sota-watanabe-b962b3110/

## Project Roadmap (WIP)

TBA

## Additional Information
