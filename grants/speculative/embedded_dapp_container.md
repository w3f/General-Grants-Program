# Embedded Dapp Container

## Project Description
Developing an embedded Dapp container for mobile(native) apps.

### Background and pain-points

  * There are a few mobile-native apps are crypto-related, like CEX and Wallet apps. However most Dapps are running on web browser, especially on Desktop PC. If the Dapp have a compatible version to mobile web, the Wallet apps are able to open a "webview" to run the Dapp.
  *  Most of the wallet apps are regulated by different governments. If the end-user is living in some country, for example China, he/she can't get the search results of crypto wallets on AppStore. Needless to say that Dapp comes the same.
  *  If we so much rely on Wallet Apps or Safari/Chrome browser to run the Dapp, we might not able to let massive users to get into the Web3 eco-system.

### Thinkings
   *  What if we can make Dapps even more decentralized? Or we say distributed?
   *  What if we can make Dapps running without browser or domain-based website?
   *  What if we can make Dapps exist everywhere without permission from AppStore(s) of Apple or Google?
   *  What if we can make Dapps run with or without Wallet Apps' help?

### Solutions

  Borrowing the idea of WeChat's mini-program, which the form of it is a javascript-bundle-app runs in a semi-browser enviorment. Even though the enviorment is WeChat app specific, and if we can migrate the enviorment to Web3.0's ecosystem, to Blockchain for example. We can come up with the solutions like the followings:
  
   *  To build an Dapp's frontend to a javascript bundle and deploy it to "Decentralized Storage" for example IPFS.
   *  To build a **Container** that can download and run the bundle just like WeChat does, but it's using the Web3's protocol. Provides all the Web3 apis that a Dapp needs to connect to blockchains. You might think of it as a MetaMask however it's form to be a **Container** not extension of browser.
   *  To build a set of tools that for Dapp developers to migrate their Dapps and deploy. Each Dapp has a DappID if it can deployed successfully(Maybe we need a new Infura-like service or Polka-Para-Chain here)
   *  Make the **Container** to be a mobile SDK and distribute it to Mobile App developers. The developers might run the SDK to their exsiting apps.
   *  Both the **Container** SDK and the JS Bundle should be cross-platform, running on Android/iOS and even more.
   *  When some mobile app developer successfully pull(or subscribe) some DappID deployed to the blockchain, the App should be able to open a non-browser but hybrid view to run the App, borrowing the power of the modern smart-phone, the Dapp will run like a native one. 
   *  The signing process is critical to Dapp, for now, we have seen smart-contract based wallet or WalletConnect solutions that can make it happen, the **Container** should also include one or more solutions from them.

### Substrate/Polkadot integration

   A blockchain defined backend is important, especially like this project. We need the backend to be permissioned-less, safe and cross-chain to maintain the massive requirement from different Dapps.

   * To build a POC-chain, we need Substrate to bootstrap a decentralized storage to host the javascript bundles. 
   * To make the Container running, we are hoping the apis can be solid and stable to major blockchains.
   * To make the project accepted by most mobile App developers(they are not crypto-fans by default), we need better economic-model than exiting advertising system that Apple and Google provides. We need a pre-designed eco-model inside the blockchain.

### Why we are interested?

#### The Experience

   The team have been building tools for pubic blockchains, and building apps for web2.0 companies. The more we do, the deeply we find that the barrier for major mobile users are too high, even they have already know that the benefits of blockchain/crypto, they can hardly find a way to use these fantastic stuff.

   To be honest, we really think the experience of current Dapps and Wallet sucks. Slow DNS resloving, bad browser compatibilities, different blockchain specific concepts and libraries , even worse user may have to run nodes using AWS or Firebase.

#### Why Wechat's idea? and why is it important for real bussiness?

   Wechat's mini-programs are prooven successful, though we know WeChat is a web2.0 product. However the main idea behind the mini-program is "Decentralized" according to its designer Allan Zhang. [See how he thinks](https://www.tmtpost.com/2551266.html). Dapp should be able to use inside every app like a website but faster and safer, and target oriented.
   
   Here we think of that if the Dapp can really gain the abillities to become distributed to every capable mobile Apps without Wechat or FAANG Apps. End users should be able to use the app they like, and App developers can benefit from the revenue when they host the **Container** service, and they won't worry about that their users' data will be sold to tech giant via AD pages, which the way the App developers have no choice because most apps are lack of bussiness model.
   
   In the meantime, we really think multiple Dapps could complete a series of tasks using smart-contracts just like the "Lego" modules, without jumping around and signing all around. That is important for blockchain to get massive expanded to real world bussiness. For example, reserving airplane tickets, booking hotel rooms, and pre-call a taxi-ride from airport to hotel, all can be done via smart-contract interface, and most importantly, just inside a single small Dapp that connects different services. Currently, these process and integration can only be done by bigger companies like Bookings and others, what if the Dapp can go beyond that? 
   
   But first we have to make it out of the framework.


#### The Big Brothers

   The AppStore of App has banned 882k+ apps in the year 2019, who knows if someday we cannot download Binance due to some regulation? And recently Apple also ban cookies on Safari due to it's ITP policies, and clean the localstorage in 7 days by force. Who knows what's coming to browser in the future?

   The adoptions for Dapps and cryptos are critical. For a long time, those good things are living inside the browser and PC, we need better solution for them, and get more users on board.

   We think this project is on the edge of Web2.x and to become the one of the entrance to Web3.0 world.


## Team members
* Michael So
* Tyler Yu
* Shaoqin Zhu
* other team members from firestack-lab

## Team Website	
* https://firestack.one

## Legal Structure 
Shanghai Niepan Technology Co,.ltd

## Team's experience
* Building toolings for Zilliqa's blockchain.
* Building toolings for Harmony's blockchain.
* A mobile gaming project running


## Team Code Repos
* https://github.com/FireStack-Lab

## Team LinkedIn Profiles
 Sorry we don't use LinkedIn

## Development Roadmap

### Milestone 1 — Container and Storage — 1 month — $10,000
* We will create a "Cross-platform" **Container** for App hoster, using google's Flutter.
* We will create a javascript bundle tool and a javascript framework for Dapp, using vue/react-like technology.
* We will create a Substrate module that will run a decentralized storage system for Dapp bundle.
* Full-Time Employees: 3

### Milestone 2 — Test runs — 1 month — $10,000
* We will migrate a Dapp such as Dex or BlockExplorer using our framework.
* We will create a example App that can runs the Container and the Container will run the Dapp.
* We will deliver a working module, along with a simple tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to deploy the dapp to the storage.
* We will write up a tutorial for developing the Dapp.
* Full-Time Employees: 4

### Milestone 3 — SDKs and POC-chain — 1 month — $10,000
* We will make the container to mobile SDKs, and publish to maven(Android),CocoaPods(iOS) and pub.dev(dart and flutter)
* We will publish a npm package for bundling tools and provide a complete guide and documentation for Dapp developers.
* We will build a Docker image with our Substrate chain, demostrating it's functionality. 
* Full-Time Employees: 5

## Future Plans
* Complete Blockchain Side toolings, such as infura-like node services.
* Continue upgrading the Dapp tools and Container SDK to implement more apis from Web3
* Co-operate with more ecosystems like wallet providers and node providers
* Using more advancing technologies like wallet-connect solutions for Dapp
* Economic model design for App hoster, Dapp developers and node validators.
* Hire more people if we can revenue from the project or financing.

## Additional Information
Any additional information that you think is relevant to this application that hasn't already been included.

* The work has started for a month or-so, the POC-client Container is done by flutter?
* Only our team members are devoted to the project. 
* Previously, we have applied Zilliqa and Harmony's grant for toolings.
* Michael So personally is running another start-up project, which is distributing the mobile games. When developing the App itself, the App will also using similar technology that used in the project for specific features.