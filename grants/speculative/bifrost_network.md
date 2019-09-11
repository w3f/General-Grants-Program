# Bifrost Network

## Project Description
Bifrost is a Polkadot parachain developed by Substrate that is perpendicular to the Stake ecosystem. The underlying is based on WebAssembly, LIBP2P and GRANDPA consensus, allowing users to complete Stake and acquire benefits while assets are chained.

Bifrost uses the cross-chain mode of the transfer bridge to access multiple PoS consensus chains. Through the cross-chain Stake assets, it has the advantages of no lock, automatic compounding, and Stake agent. Users can pass DOT, EOS, ATOM and other assets through the Bifrost transfer bridge. Mapping into the Bifrost parachain will result in the corresponding mapped assets (DOT-X, EOS-X, ATOM-X, etc.), and the user only needs to hold the mapped assets to obtain the corresponding Stake income based on the holding amount.

![bifrost-structure-chart](https://cdn.liebi.com/resource/images/bifrost-structure-chart.png)

## Team members
* Edwin Wang（Full Stack Engineer, CTO）
* Lurpis Wang (Full Stack Engineer)
* Jianping Deng (RUST & C++ Engineer)

## Team Website 
* https://bifrost.codes
* https://liebi.com

## Team's experience
Bifrost Network is a project developed by Liebi Technology based on Substrate. Bifrost Network technology prototype is the underlying technology of the Liebi Pool. The Liebi Pool will also be the first application built on the Bifrost Network. Bifrost Network is an open platform. We hope to provide more capabilities to the Stake Ecology.

Liebi team is made up of technical experts and experienced product designers who have been developing blockchain for many years. The mission is to make the blockchain simpler and lower the blockchain threshold so that more users can easily use the blockchain technology in their lives.Before the Liebi team also released a number of blockchain products, Liebi Pool, Liebi Lightning Rent, etc., core products mainly around Stake development, have extensive experience in Stake, and have multiple public blockchain development capabilities.

## Team Code Repos
* https://github.com/bifrost-codes

## Development Roadmap
#### 2019 Q3
##### Milestone 1 - Infrastructure Basic Modules - 1 month - $10k
- Infrastructure development
- Runtime module development
  - Support account
  - Support token: including create, issue, transfer, destroy, freeze functions;
  - Support staking: including stake, unstake functions;
  - Support realtime clearing/settlement on liquid balance
- Official Website development
- Web wallet development
- Support docker container
##### Milestone 2 - EOS Light Client & POC-1 - 1 month - $10k
- Runtime module development
  - Support DEX: pending/take/match orders
- EOS Bridge development
  - Light client for EOS
- DEX Website development
- Testnet: POC-1
  - About 10 validators online
  - Support account
  - Support staking
  - Support realtime clearing/settlement
- Document: 
  - Installment document
  - Usage document
  - Test document
  - Q&A
##### Milestone 3 - EOS Bridge & POC-2 - 1 month - $10k
- EOS Bridge development
  - Bridge contract on EOS
  - Multisig for bridge contract
  - Multisig transaction
  - Multisig notary
- Desktop wallet development
  - Key pair generate
  - Import mnemonic
- Testnet: POC-2
  - About 10 validators online
  - Installment & usage specification
  - Support DEX

## Additional Information
We will provide a full set of docker containers to facilitate milestone verification, and the EOS Bridge will be launched at POC-3. We hope to apply for the financial support of $30k USD, mainly used for early technical difficulties (Q3 quarter). We want to use DOT as a payment method, this is more helpful to us :)

##### What work has been done so far?
At present, the project's core module (Stake) has been verified on the smart contract. In order to make the project more open and universal, we decided to use Substrate to combine the cross-chain as the technical direction. 

##### Have you applied for other grants so far?
No, the team has invested in it and has not accepted external investment.
