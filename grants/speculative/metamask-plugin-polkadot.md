# Metamask plugin for Polkadot

## Project Description
This project includes the development of Polkadot wallet for simple interaction with Polkadot dapps. Considering the whole ecosystem, we propose implementing wallet as a MetaMask plugin (in future references “snap”) to enable all MetaMask users interaction with Polkadot dapps. This will enable simple and easy onboarding of existing Ethereum users into Polkadot.

Snap would be able to generate Polkadot account keys from dapp’s unique MetaMask key and enable those keys to receive/send units (assets), sign messages and interact with dapps. This means that users will automatically get Polkadot wallet generated.

Please note, we won’t be able to change Metamask UI but instead dapps should use injected API to display relevant information and trigger transactions (some will require MetaMask prompts). This is a new feature in MetaMask and will require extra research and following up with the development updates to continuously make UX better.

## Team members
* [Marin Petrunić](https://github.com/mpetrunic)
* [Belma Gutlić](https://github.com/morrigan)
* [Mak Muftić](https://github.com/MakMuftic)
* [Ivan Rubido](https://github.com/irubido)
* [Nikola Mlinarić](https://github.com/nmlinaric)


## Team Website	
* https://www.nodefactory.io/

## Legal Structure 
Company in the Republic of Croatia

## Team's experience
We are a blockchain research and development company but also a group of friends and developers working from an office in Zagreb. Being mostly fullstack developers and blockchain developers for the last 3 years, we are successfully providing services such as dapp development, infrastructure and tooling.

We are already working on some grant sponsored projects like:
* **ChainGuardian** - Eth2 validator desktop application 
* **js-libp2p-noise** - libp2p stream security transport to be used in eth2 mainnet
* **Hactar** - a Filecoin miner analyzer
    * https://github.com/NodeFactoryIo/hactar-daemon
    * https://github.com/NodeFactoryIo/hactar-frontend
    * https://github.com/NodeFactoryIo/hactar-backend

Some of the other projects that we have been working on can be found on our [website portfolio](https://www.nodefactory.io/portfolio/).

## Team Code Repos
* https://github.com/NodeFactoryIo

## Team LinkedIn Profiles
* https://www.linkedin.com/in/belmagutlic/
* https://www.linkedin.com/in/mpetrunic/
* https://www.linkedin.com/in/mak-muftic/
* https://www.linkedin.com/in/nikola-mlinari%C4%87-6159b1168/
* https://www.linkedin.com/in/ivan-rubido-917169151/


## Development Roadmap

#### Milestone 1: Generating Polkadot compatible keys and read-only actions (3 weeks - 2 persons full time):
* Prepare Metamask snap package and installation
* Generate `ed25519` keys using `@polkadot/keyring` and Metamask App Key as seed
* List DOT token asset
* Provide following read-only actions:
    * get public key `ed25519`
    * get balance
    * get blocks by hash/number
    * get transactions
    * export private key
* Simple web dapp demonstrating snap functionality

#### Milestone 2: Enable sending transactions and signing messages (2 weeks - 2 persons full time):
* Send units to other account
* Notification of successful or failed transaction
* Notification of incoming transactions
* Signing custom messages
* Making snap compatible with [Polkadot extension api](https://github.com/polkadot-js/extension#api-interface)
* Demonstrating functionality on simple web dapp


#### Milestone 3: Integrate and documentation (2 weeks - 1 person full time):
* Create documentation on how to integrate snap into your dapp
* Create PR integrating snap into https://github.com/polkadot-js/apps/tree/master/packages/app-accounts dapp

We'll keep this plugin updated in case of Metamask API breaking changes. We hope Metamask will expose API to allow UI modification
in which case we plan to apply for additional grants to enhance Metamask experience in Polkadot space.

## Additional Information
* **What work has been done so far?**

Mostly just researching API, snap documentation and similar projects.

* **Are there are any teams who have already contributed (financially) to the project?**

No.

* **Have you applied for other grants so far?**

No.

* **Are there any other projects similar to yours? If so, how is your project different?**

[MetaMask Agoric Plugin](https://github.com/danfinlay/metamask-agoric-plugin) - Metamask snap for non-Ethereum blockchain.

[Polkadot{.js} extension](https://github.com/polkadot-js/extension#api-interface) - Browser extension for interacting with Polkadot dapps

This project aims to combine those two previously mentioned projects to enable hassle-free onboarding of Ethereum users to Polkadot Dapps by providing the same API as Polkadot browser extension.