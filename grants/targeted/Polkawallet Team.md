# Polkawallet Team

 ## Project Description

 [Polkawallet](http://polkawallet.io) provide Cross-chain asset one-stop management, convenient staking and governance, the private key is self-owned. 

![_20190104141328](https://user-images.githubusercontent.com/34789555/50725634-2dc2e200-113b-11e9-8e9a-8f7d8a7cc6a3.png)

In order to give users a more humane and more convenient experience, as the entrance of the polkadot network, the user is provided with more intuitive visual data and status change display to guarantee the user's right to know and network participation.

![_20190104144252](https://user-images.githubusercontent.com/34789555/50725635-31eeff80-113b-11e9-959c-582a63b98418.png)

- Users can add assets, support Relaychain and Parachain to transfer, receive, and view the transfer history and state. Have the visual asset change analysis chart, make it easier for users to analyze assets. Users are notified when they receive the asset and can view the transfer details data.

  The private key is self-owned, and have the Gesture,Fingerprint, Facial recognition, Hot and cold wallet mechanism, users can set their own scheme. Our team is developing a new encryption scheme -- high - dimensional fractal encryption, will be used to safeguard the security of a user using the polkawallet.

![](https://qiniu.netsafe.org.cn/images/3.png)

![screen4-1546691772332](https://user-images.githubusercontent.com/34789555/50725645-66fb5200-113b-11e9-9e41-370d5c7092b9.png)

- Polkawallet makes it easier for validators and nominal ators to make their contributions, by making the charts more intuitive and having a detailed history of each validators, for better analysis and research.

![](https://qiniu.netsafe.org.cn/images/4.png)
![_ _20190105203945](https://user-images.githubusercontent.com/34789555/50725650-82fef380-113b-11e9-974f-55d5f7b1b1df.png)

- Polkawallet provides a more intuitive and convenient entry point for participating in governance. If there is a new referendum/proposals, the user is reminded and you can view the details. Users can governance directly from polkawallet and view the history governance records. So polkawallet also improves public Referenda engagement.

  ![](https://qiniu.netsafe.org.cn/images/5.png)

![screen3](https://user-images.githubusercontent.com/34789555/50725655-9ad67780-113b-11e9-96e3-31ac85f2f442.png)

- Polkawallet will follow in Polkadot footsteps and continue to expand the cross-chain ecosystem, which is a module for the near future. It will quickly integrate suitable cross-chain applications, and we believe that it will be a colorful page. Cross-chain asset exchange is just a side application.

![](https://qiniu.netsafe.org.cn/images/6.png)

- Available for all major mobile platforms. Currently react native is used as a cross-platform solution, which will be developed separately in the future.
- The Beta version has been released and you can experience it.


 ## Team members
* Fuyao Jiang | 0xthreebody

* Cheng fei Liu

* Jobn

* Yang Dong

* Song Wang

* Dianyu Kang

* Yanjie Yuan


## Team Website	

* https://polkawallet.io

## Legal Structure 
Beijing sanshan Internet technology co. LTD

## Team's experience
- Fuyao Jiang | 0xthreebody: Early Polkadot community members, continuous attention from the inception of the project. Chinese translator of polkadot wikipedia. One of the polkadot Chinese community groups, and participated in each version of the PoC test network.  Github: https://github.com/jiangfuyao
- Cheng fei Liu: 4 years development experience on React Native, graduated from WuHan university in China, has developed exchange App, mobile instant messaging App, short video App and shopping mall platform.
- Jobn: 7 years front-end development experience. Responsible for building the basic web architecture of the whole application, guiding and promoting the team to develop modules. Reduce coupling between front and back end projects by mocking out back-end interface definitions and data interactions. Github:https://github.com/jobn123
- Yang Dong,  8 years front-end development experience.3 years react native development experience  Encapsulates several front-end frameworks based on VUE and React. Core personnel of GemFrame front-end architecture.
- Song Wang, 3 years react native development experience,have experience in native development, developed mobile OA system, e-commerce platform and CRM system.
- Dianyu Kang, Graduated from university of jinan, China, 2 years react native development experience, core developer of polkawallet Beta version.
- Yanjie Yuan, 4 years UX/UI designer, 1 year user experience in blockchain industry.Have the experience in mobile wallet and exchange design.

## Team Code Repos
* https://github.com/polkawallet-io/polkawallet-RN

## Intended language of development
* JavaScript

Currently, there is only js version of the API, and my friends GemZhang is working on developing a Java version of the API. Will can be used for native development for better user experience.

## Development Roadmap

**Milestone One:** (plan: 2019.03.25)

- Improve extensibility:
  - Choose a more suitable architecture for this application.
  - Subcontracting according to architecture and business modules.
  - Divide the network layer and route layer according to the business module
  - The component package is re-screened, and the comprehensive optimization is selected to prepare for future updates.
  - Component packages need to be re-filtered for comprehensive optimization.
  - The code solution needs to be recalibrated for new business and multi-chain support.
- High coupling:
  - Page reusability.
  - Eliminate code accumulation.
  - Keep the structure uniform.
  - Move logic in the View layer or controller layer.
- Improve code quality:
  - Develop coding specifications.
  - Develop a code submission specification.
  - Add unit tests.
  - Eliminate file redundancy.
  - Eliminate code redundancy, unused code.
  - Extract method to remove duplicate code.
  - Clean up the code hierarchy.
  - Chinese and English bilingual annotation.
- Enhance the user experience:
  - Data caching, reducing user traffic consumption, and server performance consumption.
  - Reorganize the business logic to reduce redundant requests and redundant listening processes.
  - Constantly test, eliminate stuck, crash.

- Deliverables:  Public Github. https://github.com/polkawallet-io/polkawallet-RN
- Duration: 1 month.

**Milestone Two:**

- notifications function implementation. (plan: 03.31)
- referendums history function implementation. (plan: 04.03)
- Setting functions, include:Language/Gesture/Fingerprint/Facial recognition/Google Authenticator. (plan: 04.10)
- Redesign some processes to make them easier and easier to understand. (plan: 04.20)
- A new UI that gives users a convenient experience. Out of style before (plan:04.30)
- Deliverables:  Public Github. https://github.com/polkawallet-io/polkawallet-RN
- Duration: 1 month.

**Milestone Three:**

- Integrate Parity Signer to Polkawallet (plan: 05.10)
- Multi-chain support, including database and interface level. (plan: 05.20)
- Fix issue on github that should be fixed {optimize} (plan: 05.28)
- Prepare for release & github wiki for product description (plan: 05.30)
- Release 0.2.0 Beta version (plan: 05.31)
- Deliverables:  Public Github. https://github.com/polkawallet-io/polkawallet-RN & https://polkawallet.io
- Duration: 1 month.  

