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

## Team's experience
Bifrost Network is a project developed by Liebi Technology based on Substrate. Bifrost Network technology prototype is the underlying technology of the Liebi Pool. The Liebi Pool will also be the first application built on the Bifrost Network. Bifrost Network is an open platform. We hope to provide more capabilities to the Stake Ecology.

Liebi team is made up of technical experts and experienced product designers who have been developing blockchain for many years. The mission is to make the blockchain simpler and lower the blockchain threshold so that more users can easily use the blockchain technology in their lives.Our core products mainly around Stake development, have extensive experience in Stake, and have multiple public blockchain development capabilities.

## Team Code Repos
* https://github.com/bifrost-codes

## Development Roadmap
##### Milestone 1 - RUST-EOS Development - 1 month - $10k
    Primitive structs
    P2P message protocol rewrite
    SECP256K1 keystore
    Test case
    https://github.com/bifrost-codes/rust-eos

##### Milestone 2 - SPV Client Development - 1.5 month - $15k
    EOS testnet node
    Block listener
    Transcation listener
    Transcation verify
    Transcation filter
    Multiple signature
    Bridge contract on EOS

##### Milestone 3 - Runtime Moudle Development - 0.5 month - $5k
    Offchain worker
    RPC moudle
    Interoperability with eosio contracts
    Dockerfile
    Bridge interface protocol

## Additional Information
We will provide a full set of docker containers to facilitate milestone verification, and the EOS Bridge will be launched at POC-3. We hope to apply for the financial support of $30k USD, mainly used for early technical difficulties (Q3 quarter). We want to use DOT as a payment method, this is more helpful to us :)

##### What work has been done so far?
At present, the project's core module (Stake) has been verified on the smart contract. In order to make the project more open and universal, we decided to use Substrate to combine the cross-chain as the technical direction. 

##### Have you applied for other grants so far?
No, the team has invested in it and has not accepted external investment.
