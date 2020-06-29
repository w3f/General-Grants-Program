# Generic Asset Gateway

## Project Description
Generic Asset Gateway is a Substrate Runtime Module that provides a generic process to make cross-chain asset transfer very easy. All kinds of assets can be transferred to the Substrate-based Chain ecosystem by using a process work like traditional centralized exchange deposit / withdrawal service. 

### Why Generic Asset Gateway

Generic Asset Gateway will make cross-chain transfer very easily and the user can transfer the cross-chain asset just like they are using the centralized exchange service.

Generic Asset Gateway is composed of `Generic Deposit Gateway` and `Generic Withdrawal Gateway`. To make it work, `Generic Asset Gateway` will rely on some centralzied 3rd-party or federation. 

#### The Design of Generic Deposit Gateway
By integrating the BIP-32 mechanism, Generic Deposit Gateway implements an open, auditable Generic Deposit Gateway mechanism. Through this mechanism, users will get a unique deposit address corresponding to their substrate based blockchain address, and the deposit address generation process is open and transparent. The deposited assets are securely held in insured cold storage multi-signature wallets. The whole deposit process does not touch the network.

The implementation process is as follows:

1. For a blockchain that requires access to a deposit gateway, The blockchain generates a public-private key pair. The private key is securely stored offline, and the public key is used as the xpub key to generate the deposit address.

2. Using BIP-32 derivation rules and an xpub key to derive the deposit address of the corresponding index user, the calculation method is as follows: `CKDpub((Kpar, cpar), I) → (Ki, ci)`. i is index, starting at 0, increasing by the number of users. The blockchain only store the value of the xpub key and the index. 

3. User initiates a deposit transaction on the blockchain by sending the original asset to the derived deposit address; this automatically binds the relationship between the corresponding asset deposit address and the user’s address that’s generated on the chain.


#### The Design of the Generic Withdrawal Gateway
The withdrawal gateway is designed to implement an on-chain review process based on permission control, with a gateway design similar to an exchange’s withdrawal process. The withdrawal process is as follows:

1. User initiates a withdrawal request.

2. The blockchain deducts the corresponding funds from the user’s mapped the blockchain 
asset balance in advance and enters the approval process.

3. The user with admin permission  reviews and checks the information.

4. If the approval is successful, the original asset withdrawal process is initiated,
    and the related admin user signs the transaction using a hardware wallet to broadcast the transaction to the original chain’s network. When there are enough confirmations, the transaction is marked as completed.

5. Once the original asset is successfully withdrawn, the blockchain automatically burns the mapped asset. If the review process fails, the refund process is initiated, returning the pre- deducted funds to the user and marking the withdrawal as a failure.


### Open Source

This is an open source project under Apache License 2.0. All the defined milestones will be available to the open source community.

## Team members

* Jamie Cheng: Former BTCChina Developer, Blockchain Developer
* Terence Ge: Fronend Developer

The development will be mainly done by 2-3 full-time and one part-time engineer. The remaining people will provide necessary support to the development.

## Team Website	
* https://www.riochain.io

## Legal Structure 
RioDefi INC. in HongKong, China

## Team's experience

Rio DeFi is a Blockchain technology company. Our mission is to accelerate the mass adoption of digital assets by bridging traditional and decentralized finance.

Our vision is a world in which everyone has access to decentralized financial (DeFi) services. To that end, we develop applications that connect people to digital assets, mobile payments, and DeFi services such as savings and lending. Our solutions enable lower transaction fees, faster confirmations, energy efficiency, secure storage, and global reach.

## Team Code Repos
- RioChain: https://github.com/riodefi

## Team LinkedIn Profiles
* Jamie Cheng: https://www.linkedin.com/in/starit/
* Terence Ge: https://www.linkedin.com/in/terence-ge-4a146185/


## Development Roadmap

- Milestone 1 — Implement Basic Substrate Modules — 1 month — $10,000
  - We will create a Substrate module that will provide function related to deposit process
We will deliver a working javascript example. It will allow the user to generate deposit address according to the seed and index onchain.
  - The code will have proper unit-test coverage to ensure functionality and robustness.
  - We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

- Milestone 2 — Implement Withdrawal Substrate Modules  — 1 month — $10,000
  - We will create a Substrate module that will provide function related to withdrawal process.
The code will have proper unit-test coverage to ensure functionality and robustness.
  - We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.


- Milestone 3 — Additional features — 1 month — $10,000
  - We will create a web admin panel to work with the generic asset gateway, it will allow the user with related permissions to approve or reject the withdrawal request. Also, it will integrate with the blockchain explorer to show related data including deposit history, withdrawal history and some other stats.
  - We will deliver a working blockchain explorer based on Polkascan. It can collect generic asset related data including deposit history, withdrawal history, asset type and some other stats..
  - The code will have proper unit-test coverage to ensure functionality and robustness.
  - We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

All the deliveriables for each milestone will be published in the open source repositories.

### Long Term Plan

- Add some rick control mechanism to help the user with admin permissions to show the system health stats.
- Give setting up examples to the some popular blockchains: BTC, ETH, EOS…
- Security Improvement

## Additional Information
