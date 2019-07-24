# Zabo

## Project Description
* We connect application developers and users with existing crypto wallets and infrastructure using a single interface. Users bring their own custodial or non-custodial wallet, not Zabo’s, and we connect it. Developers work with a single API to connect with any wallet.
* We feel much of the ecosystem has developed fragmented solutions to common problems, especially when it comes to cryptocurrency itself and the wallets that hold it. Today, as a user, when you connect to a new application, you generally use the target application's new wallet, while we have dozens of wallet options already available. Additionally, there are numerous exchanges globally, each with their api to access custodial wallets. Rather than provide another wallet, we aim to bring existing wallets and networks together through a standard pipeline via a familiar interface.
* Zabo will facilitate sending transactions to parachains on the Polkadot network by integrating wallet providers that support these transactions. Additionally, we will offer data endpoints to receive information from these parachains.
* Our team has been building blockchain solutions together for a few years now. We noticed this issue of fragmented wallets and wallet interfaces as we developed for the financial industry and decided this was an important issue to solve. Better developer experience leads to better user experience because developers can offload non-core technical issues.

## Team members
* Christopher Brown - Team Co-Lead and full stack dev
* William Dias - Team Co-Lead and full stack dev
* Davi Reinke - Front-end dev
* Fred Furas - Back-end dev
* Alex Treece - Product Lead

## Team Website	
* https://zabo.com - Product website
* https://github.com/modular-network - Team github

## Legal Structure 
Modular Inc. - Address shared in Google Form.

## Team's experience
Christopher Brown is a 10+ year software engineer with experience in Golang, JavaScript, Solidity, Swift, Java, PHP, and C++. He's worked on various open source projects including [EthPM](https://github.com/ethpm/ethpm-go) and [Ethereum Libraries](https://github.com/modular-network/ethereum-libraries), as well as holds White Hat Group tokens at [0x475ded3e48d0182fd684e3f78a1ee17659482c3b](https://etherscan.io/address/0x475ded3e48d0182fd684e3f78a1ee17659482c3b). William Dias is a 10 year software engineer with experience in Nodejs, JavaScript, and Golang. Davi Reinke is a 10 year software engineer with experience in Reactjs, JavaScript, and Golang. Fred Furas is a 5+ year software enginner with experience in C#, .NET, Golang, Java, JavaScript, and Swift. Alex has 10+ years experience in private equity and product management.

## Team Code Repos
* https://github.com/modular-network
* https://github.com/diaswrd
* https://github.com/Hackdom
* https://github.com/dreinke
* https://github.com/FredFuras
* https://github.com/alextreece

## Team LinkedIn Profiles
* https://www.linkedin.com/in/christopherbrown12/
* https://www.linkedin.com/in/alextreece1/
* https://www.linkedin.com/in/diaswrd/
* https://www.linkedin.com/in/davireinke/
* https://www.linkedin.com/in/fred-furas/

## Development Roadmap
We currently have a baseline MVP version published as v0.1.0 and will require 6 months to complete v1.0. For the Polkadot grant portion, we will require 2 months to complete. We intend on having 5 working full-time on this project. Total cost estimate shared in Google Form.

### Milestone 1 - Research and Design - 1 month - $0
We will research polkadot-js api and the polkadot-js extension, as well as current implementations in polkadot-ui and at polkadot.js.org/apps to design an easy interface capable of communicating with a locally hosted and remotely hosted node connected to the Alexander testnet (or its equivalent at the time of implementation). We will also design a proof of concept which shows how a web application can leverage a mobile wallet, such as Polkawallet, for account information and transaction signing through HTTP and deep linking.   

  * Research the current Polkadot API's
  * Design the following default substrate functions into the Zabo Client API:
    - `query.balances.freeBalance()`
    - `rpc.state.queryStorage()` to obtain historical storage entries for the connected wallet
    - `tx.staking.bond()`
    - `tx.staking.nominate()`
    - `tx.staking.chill()`
    - `tx.staking.unbond()`
    - `tx.staking.withdrawUnbonded()`
    - `tx.balances.transfer()`
  * Design protocol to leverage mobile wallets from a web app.   

We will deliver a fully documented Zabo interface at the end of this milestone.

### Milestone 2 - Implement Design - 1 month - $12.5k
We will implement the designed interface within the Zabo sandbox environment and make it available via the Zabo Client API. We will allow application users to select a local keystore, a polkadot-js extension managed keystore, or an address only connection to utilize the application powered by Zabo's Polkadot interface.

We will deliver a simple web app capable of interacting with the Alexander testnet utilizing the developed API and make this application, as well as the Zabo Client API, available via a Docker image. The Zabo Client API will be open sourced and made available on Github.

### Milestone 3 - Implement Mobile Wallet Protocol - 1 month - $12.5k
We will build out the proof-of-concept protocol designed to allow a Zabo powered web application to leverage a mobile wallet keystore by using Polkawallet as an example target. We will fork the polkawallet-io React Native repository and allow extrinsic data to be sent to, signed, and sent back from the mobile wallet to the web application.

We will deliver a Docker image containing a Polkawallet capable of signing a transfer request built in the Zabo powered web application and submitting it to the Alexander testnet.

### Payment Type
We would be willing to take 100% payment in DOTs.

### Ongoing Support
We intend to continue building out and supporting the Zabo API into the future as an ongoing concern. We plan on active engagment in the developer and user communities so that we can receive accurate feedback on development priorities.

## Additional Information
Any additional information that you think is relevant to this application.

These bullet points won't be applicable to all projects. Some of the information may have already been included in the description section, if so then no need to state it again.   

* We have accepted VC funding for the company   
* We have also recently applied with the Ethereum Foundation   
