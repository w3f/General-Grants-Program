# Vue.js ui utilities, components and libraries

## Project Description

Reimplement [React components](https://github.com/polkadot-js/ui) into [Vue.js](https://vuejs.org/) for broader ecosystem. Vue.js is mostly adopted in Asia. It will enable access for Vue.js developers to build Polkadot/Substrate apps [[1]](https://polkadot.js.org/ui/)[[2]](https://github.com/polkadot-js/apps/) on top of Vue.js. 

We are interested in UI components (ordered by interest)
* [polkadot-js/ui](https://github.com/polkadot-js/ui/tree/master/packages/)
* [polkadot-js/apps](https://github.com/polkadot-js/apps/tree/master/packages/) app-*
* [ui-signer](https://github.com/polkadot-js/apps/tree/master/packages/ui-signer)
* [ui-app](https://github.com/polkadot-js/apps/tree/master/packages/ui-app)

### Reasons
Vue.js has easier learning curve to get productive and less head scratching even for backend engineers used to write code in Node.js. 
Vue.js aims to be easier for onboarding for engineers to build frontend tooling.
We've made [web-based Subkey in Vue.js](https://subkey.netlify.com) and it took a long while to go through all required utils and we gained experience that for developers experience we need lower entry barrier. [We wrote article about experience we gained.](https://medium.com/@yangWao/how-accounts-on-polkadot-and-substrate-are-created-9f9d80a57ae1)

### Intended language of development
Implementation would be in Vue.js 2.6.x, Typescript 3.5.3 in modern way using ES6/7/8 covered with tests up to 60% with [A maintainability by codeclimate](https://codeclimate.com/github/polkadot-js/ui).

## Why our Team is Interested
We want to be part of community and Polkadot ecosystem by building solid basestone for further projects. We also made [article how web-based Subkey was made in Vue.js](https://medium.com/@yangWao/how-accounts-on-polkadot-and-substrate-are-created-9f9d80a57ae1)

Nowadays [polkadot-js/apps](polkadot-js/apps) repository have 510 closed various issues and 48 open. 
Frontend is emerging component for decentralization ecosystem and probably looking forward to support repository as well in future.

## Team members
* Matej Nemček - [twitter.com/yangwao](https://twitter.com/yangwao) - Typescript, Vue.js - full stack engineer, founder & leader of [blockchain cowork Progressbar](https://cowork.progressbar) in Bratislava, Slovakia, [personal website](https://hypersignal.xyz), Substrate experience with SRML module. Recently built web-based [“Subkey” keyring tool in Vue.js](https://subkey.netlify.com/) [repository](https://github.com/yangwao/offline-polkadot-keygen)
* Viktor Valastin - [twitter.com/vikiival](https://twitter.com/vikiival) - Typescript, Vue.js - student in the Faculty of Informatics and Information Technologies at Slovak Technical University, doing academic research about blockchain technology, full stack engineer (NodeJS, React)

## Team website
* Matej Nemček - [hypersignal.xyz](https://hypersignal.xyz)

## Legal Structure
These details will be shared privately via our Google Form.

## Team’s experience
Previously worked as Ethereum developers in various Solidity projects, counting on few ICOs, distribution mechanism for airdrops, working on dApp for renting cars on Ethereum
* Matej - experience with bitcoin apps in the past (2014), engineering cryptography in password manager ([Saferpass](https://saferpass.net/), 2015) and doing backend code mostly. Worked for blockchain company ([Decent.ch](https://decent.ch/)) where he was responsible for code in ICO department team. Leading R&D research and distribution mechanism for Decent. Did few experimental ERC223 & ERC721 and hardware hackinig.

* Viki - [Experience in creating car sharing dApp on top of Ethereum blockchain](https://opac.crzp.sk/?fn=detailBiblioForm&sid=BCA102CB6C4CA54D4CEAA875C35B&seo=CRZP-detail-kniha) using ERC721 token composition, whitepaper was successfully submitted to academic conference. Worked for Danish company (CN Group) and was responsible for UX/UI in security business web applications (Vue.js, Angular and React). Now working for a company which is creating car-management software(React, Spring) and blockchain based car sharing platform.

## Team Code Repos
* [github.com/yangwao](https://github.com/yangwao)
* [github.com/yangwao/offline-polkadot-keygen](https://github.com/yangwao/offline-polkadot-keygen)
* [github.com/viktorko99](https://github.com/viktorko99/)

## Team LinkedIn Profiles
* [linkedin.com/in/mnemcek](https://linkedin.com/in/mnemcek)
* [linkedin.com/in/vikival/](https://www.linkedin.com/in/vikival/)

## Development Roadmap

### Milestone 1 - week 2-4 - ⅓ of requested funding

Reimplement following React components into Vue.js to reflect today functionality at date of accepting grant: 

* [ui-assets](https://github.com/polkadot-js/ui/tree/master/packages/ui-assets)
* [ui-identicon](https://github.com/polkadot-js/ui/tree/master/packages/ui-identicon)
* [ui-keyring](https://github.com/polkadot-js/ui/tree/master/packages/ui-keyring)
* [ui-settings](https://github.com/polkadot-js/ui/tree/master/packages/ui-settings)
* Write technical documentation for each component, [similar to](https://polkadot.js.org/ui/) [this one](https://polkadot.js.org/common/)

### Milestone 2 - week 4-8 - ⅓ of requested funding

[Build reusable components into Vue.js namely:](https://github.com/polkadot-js/apps)
* Accounts (app-accounts)
* Address book (app-address-book)
* Democracy (app-democracy)
* Extrinsics (app-extrinsics)
* Transfer (app-transfer)
* Settings (app-settings)
* Write technical documentation for each component, [similar to](https://polkadot.js.org/ui/) [this one](https://polkadot.js.org/common/)

### Milestone 3 - week 8-12 - ⅓ of requested funding 
* Write wallet-boilerplate with app-accounts, app-address-book, app-transfer

[Build reusable components into Vue.js, namely](https://github.com/polkadot-js/apps): 
* Staking (app-staking)
* Storage (app-storage)
* ToolBox (app-toolbox)
* Explorer (app-explorer)
* ToolBox (app-toolbox)
* Treasury (app-treasury)
* Write technical documentation for each component, [similar to](https://polkadot.js.org/ui/) [this one](https://polkadot.js.org/common/)

### Milestone 4 - week 12+ 
* Partially implement dashboard in Vue.js with app-account, app-explorer, app-transfer (extend wallet-boilerplate)
* Resolve Pull Requests from community. 
* Run public Vue.js dashboard interface through Netlify as demonstration for other developers.
* Build small mvp application on top of Polkadot or Substrate, support repository issues.

We prefer to receive the payment in FIAT, but would be willing to consider part payment in DOTs, up to 33%.

## Licensing
All Vue.js components will be open sourced under the MIT software license.

## Additional Information

* What work has been done so far?
We have reimplement keyring into Vue.js & Typescript https://subkey.netlify.com/ to proof hands on experience with https://polkadot.js.org/common/ utilities. https://github.com/yangwao/offline-polkadot-keygen
 
* Are there are any teams who have already contributed (financially) to the project?
No.

* Have you applied for other grants so far?
No.

* Are there any other projects similar to yours? 
Just found one relevant mention https://github.com/polkadot-js/ui/issues/109 prior date 17/7/2019.

* How is your project different?
Comparing to React frontend framework, there will be polkadot-ui available for largest front-end market by star-gazers on Github 143931 Vue.js vs 132789 React
Source https://github.com/collections/front-end-javascript-frameworks
