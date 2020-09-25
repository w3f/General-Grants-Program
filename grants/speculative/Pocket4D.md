# Pocket4D

## Project Description
It's an embeddedApp/Dapp container, which runs Mini-Program inside existing iOS/Android/Desktop applications.
  
- Make `Mini-Program` distributed and can be another form of Dapp.
- Every app can be a super app using this framework.
- Decentralized application system using Decentralized Storage and blockchain
 

## What is Mini-Program and why it is powerful

### The costs of app development is too high

Making a website or a native app is not easy. Developers need to buy domain names, rent servers, provide Https authentication, run cloud programs, and finally spend money to promote apps in the market. Development costs are high, and they may only make a small profit in the advertising business.

And to develop a platform specific app , eg. Android App, requires more skills to developers. The web developers are many however who knowing how to build a native app are few. The tools and the stacks are different. Many of them may choose so-called "hybrid" stack to combine native and javascript, however, it is also hard to maintain.

### Native apps cannot dynamically update like a web

Native apps are pre-bundled and uploaded to AppStore. Even when they require a small update or fix, they have to submit another signed bundle and have to wait for a couple days or weeks for review. Unlike the web-app, updates can be done by changing url links.


### But current mobile apps markets are ruled by `Big Brothers`
Mobile apps, developed by enormous developers, are submitted to to these Apple's AppStore and Google play everyday. However, have been rigorously censoring and supervising the content and services of the applications, so when they believe that the content or the service violates the their policy and regulations, the App will be rejected and there is no room for bargaining.

Recently, a well-known mobile game was removed from the App Store and Google Play simply because its developer wanted to use their own payment method. And a few companies which previously being rejected stood up and formed a line called [AppFairness](https://appfairness.org/), to advocate for freedom of choice and fair competition across the app ecosystem.

The war between developers and market rulers won't stop, until the fairness is settled.

### Mini-Programs
In late 2016, Allen Zhang, one of the founders of Wechat, initiated the idea of [Mini-Program](https://en.wikipedia.org/wiki/WeChat#WeChat_Mini_Program). At that time, WeChat already had more than 1 billion users around the world, and the `Mini-Program` were only allowed to run in WeChat. He believed that the `Mini-Program` should be `Get when wanted, Leave when finished`("唾手可得，用完即走"). When the idea landed in WeChat, its development was unstoppable. Very soon, Baidu, ByteDance, and Alibaba followed Wechat's lead and developed their own `Mini-Program` system. As of June 2020, the total number of users of `Mini-Program` has exceeded 400 million, while more than 600,000 `Mini-program` have been running online.

The `Mini-Program` combines Javascript, which is very close to what front-end developers are used to, and native apps, which provide a high-performance rendering engine and a powerful API that web browsers don't. Smartphone users, meanwhile, rely more on the convenience of mobile phones and app-based internet services. App developers prefer to be able to enhance their native apps independently, rather than having to upgrade their app versions and be censored by the App Store or Google Play every time. Thus, the `Mini-Program` becomes the lightweight optimal solution for these companies.

However, these giant companies that develop `Mini-Program` are reluctant to open source their software, as it is difficult to completely separate it from the services they offer in actual business. But the strategies of these companies have indeed attracted many other companies and individual developers to join their ecosystem.


## Why we want to introduce `Mini-Program` to for Web3.0's Dapp

We hope that the Web 3.0 ecosystem becomes strong and everyone can benefit from it. However, there are still many pain points.

### Most `Dapps` are web-apps, they might hard to get mobile users.
The vast majority of Web 3.0 projects are `back-end` projects that need to redevelop the `client-side` to interface with them. However, many `client-side` apps are rejected by the App Store and Google Play, or the experience of the `client-side` projects is so poor that they have to rely on wallet apps to be of value.

The vast majority of Web 3.0 `front-end` projects are browser-based. Therefore, users have to open a desktop or mobile browser to run these web applications. However, these web applications rely to some extent on browser extensions, which makes them very difficult to reach mobile users.

Current wallet apps provide interfaces for web applications through Webview and `Web3`. However, the qualities of web applications is uneven, which is prone to slow loading and compatibility issues, resulting in poor user experience. Once the Wallet App is rejected by the App Store and Google Play, users can only look for other alternatives.

The web today is domain-based and it's hard to completely decentralize it. Apart from the back-end part, even if AWS cloud storage or Google cloud is used, the client still needs an http/https domain name to resolve the front-end resources. So this creates some operational risk that the app service may be inaccessible due to server-side issues.

In conclusions, to get mobile users:
1. Dapps should escape from browser, and use hybrid development stack on mobile phone.
2. Dapps should use hash address to resolve, not domain, or else it would be blocked by some country authorities.
3. Dapps should be looking for decentralized storage to store their front-end assests and the bundle


### `Mini-Program` is powerful if it is combined with blockchain
`Mini-Program` runs inside mobile app, just like a web-app. However, it has more advanced capabilities than web.

1. The host(native mobile app) provides the apis from mobile system and better rendering methods than web. Most mobile phone os are designed and optimized for rendering and interacting, eg. face-recoginizing, finger-print recoginizing, camera,.etc. Which are more powerful than browser can provide.
2. The crypto libraries and standard protocol interface like `web3` can be embedded by native-side, that the frontend(javascript) is more light-weight without downloading from remote server. 
3. The `Mini-program` bundle can be sent/push and resolved dynamicaly, just like webapp using url. And when the bundle is stored in decentralized storage eg. using IPFS protocal. It would be much agnostic and decentralized than using `domain-based` storage system like `Firebase Storage`.
4. Because `Mini-program` have the abilities to dynamicaly and decentralized update the front-end, we don't worry about the `Big-Brother` may reject the application.
5. More over, if we have a blockchain with economic model running and host those `bundles`, we might create another eco-system for mobile app better than Apple's appstore and Google play. The free market can be governed by communities not tech-giant, and both mobile app host and front-end `Mini-program` developers can be benifit from it.


In conclusions, if dapps are made to be `Mini-Program` and use blockchain:
1. Dapps can be run inside mobile app, without worrying rejected by `Big-Brothers`.
2. Dapps gains the power of native app(host), without losing the abilities of dynamic updating.
3. Dapps can be running very fast and provides rich apis that web-app can't.
4. Dapps can be governed by greater communities using blockchain stacks.



## The Pocket4D solution
Here, we propose a solution to the above pain point: in considering the application of the `Mini-Program` to a decentralized system, we found that it has the potential to become an important piece of the puzzle in scaling users in the current Web 3.0 phase.

1. Client side, be a container, and run for Dapp
   Pocket4D will act as a container, not just an app. This container, like WeChat hosting the `Mini-program` ecosystem, will provide:
   - An embedded Javascript engine for the sandbox enviorment, to run javascript of front-end
   - A standard rendering protocols (e.g. `xml`), extraded from `Mini-program` bundle, and transcript for native rendering engine.
   - Common APIs (e.g. `navigation`, `deviceInfo`, etc.), and interfaces such as `Web3` objects and crypto libraries to end users. 
   - Use google's flutter as standard rendering engine to provide quality-assured service capabilities, and can be easily integrated into the host app.
   - Fully open sourced, unlike other `Mini-Program` solution eg. wechat/alibaba/bytedance, that every app host can use it for free.

   We have finished the client design, please refer to [Technical Design](https://github.com/Pocket4D/Pocket4D-Wiki/blob/master/technical-design.md)

2. An eco-system driven by blockchain
   In theory, Pocket4D doesn't need a blockchain, however, our goal is to build a decentralized system, a blockchain is needed to:
   - Host the bundle and assets eg. videos/images/other files.
   - A token economic model that `Mini-Program` can be distributed between app hosts, in the meantime, tokens can be used as reward when `Mini-Program` is distributed.
   - A eco-system for `Mini-Program` that can be governed by communities(eg. app hosts, validators and so on)
  
   We will try using Substrate to start building the blockchain with the decentralized storage system, or to co-operate with the storage solution inside the ecosystem of Polkadot, eg. Crust.

   The blockchain design is not done yet, because it is not immenent for current stage. We will update our stacks and progress further.


## Team members
* Wei Su (Michael So): Project Manager and iOS/Android/Flutter/Javascript developement
* Ian Tan: Front-end and Mini-Program Framework developement
* Lulu Ren: Blockchain and SmartContract developement
* Yaolong Cui: Product Manager
* Bruce Huang: Adviser and Business Development

The development will be mainly done by 2-3 full-time and one part-time engineer. The remaining people will provide necessary support to the development.

## Team Website	
* https://pocket4d.io (In progress)
* https://firestack.one
  

## Legal Structure 
SHANGHAI NIEPAN INFORMATION TECHNOLOGY CO., LTD., a startup company focusing on blockchain development in China.

## Team's experience

Team FireStack was founded in late 2018 focusing toolings for blockchain and smart-contract developers.

In 2018 to 2020, we've made several SDK tooling project for Zilliqa, Harmony. We also did solutions for DEXs, CEXs and DEFI projects.

We have different technical and bussiness background, some of them are working for famous Blockchain project, and some of them are in famous internet companies.

We love open-source project and the engineers all love commiting and helping others. The team mainly write C/C++, Javascript, Kotlin, Swift, Java, Rust, and Go. We are also familiar with Solidity and some other "SmartContract Script" languages

* Wei Su(Michael So): Founder and Lead Developer of Pocket4D.
* Ian Tan: Senior fullstack and blockchain developer, who is working in some famous internet company globaly, and former Zilliqa team member.
* Lulu Ren: Senior back-end and smart-contract engineer, who is working for Zilliqa
* Yaolong Cui(Ken Cui): Product manager, who is working for some famous fin-tech company in China.
* Bruce Huang: Founder and Adviser to FireStack, former CEO of Madalicai.com, former Director of Alibaba Cloud Computing.


## Team Code Repos

- Pocket4D: https://github.com/Pocket4D
- FireStack: https://github.com/FireStack-Lab


## Team LinkedIn Profiles
* Bruce Huang: https://www.linkedin.com/in/the-bruce-huang/

## Development Roadmap
https://github.com/Pocket4D/Pocket4D-Wiki

## Technical Design
https://github.com/Pocket4D/Pocket4D-Wiki/blob/master/technical-design.md

## Additional Information

* What work has been done so far?
  * A experimental JSEngine with QuickJS and DartLang 
  * A simple Mini-Program compiler
  * A simple Test Server hosting js/html/css bundle
* Are there are any teams who have already contributed (financially) to the project?
  * No.
* Have you applied for other grants so far?
  * No.
* Are there any other projects similar to yours?
  * No.
* How is your project different?
  * Open-source `Mini-Program` full stack solution 
  * Decentralized Storage for `Mini-Program` frontend bundle.
  * More design and updates are in [Pocket4D Wiki](https://github.com/Pocket4D/Pocket4D-Wiki)
