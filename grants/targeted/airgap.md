# AirGap

## Project Description

AirGap is a blockchain agnostic mobile crypto wallet with a two-device approach and a focus on security and usability. Your old smartphone is your new ‘hardware wallet’

### The Status Quo

Interaction with any protocol is still tedious for users, they have to think about security which is usually cumbersome to understand. A secure and usable gateway to decentralized applications and features of these protocols is needed. Loss of funds by losing access to a private key either malicious or just out of neglection is encountered every day in the crypto space.

With our open source project AirGap, we’re solving this problem by providing a solution which allows to completely sign transactions offline thus having the secret of the user newer exposed to any network. Thanks to the agnostic approach multiple protocols can be conveniently and securely managed with only one secret.

### Our Motivation

With our background in mobile security and blockchain related development working on various projects in the blockchain space as well as with Fortune 500 companies, we felt that there was a need for a mobile wallet focusing on security as well as usability. Hardware wallets like Ledgers are not always easy to come by due to shortage or being too expensive in certain countries.

Also, there is no simple approach to effectively sign transactions entirely offline, which motivated us to tackle the not so trivial problem and develop a secure and usable solution. With AirGap we want to enable the users to securely manage one secret and interact with as many protocols as possible and on the other hand also provide a toolset for dApp developers to offer a secure key handling solution to their users.

### The AirGap Approach

AirGap tackles the problem of secure and usable interaction with a protocol. With the AirGap two device approach where transactions are signed on an offline device and broadcasted on a second online device or with the same device two app approach where one application is responsible for the signing and secret management and the other for broadcasting and preparing transactions.

With AirGap we want to provide especially for Proof of Stake focused project an easy way for the user to interact with the protocol for spend transactions but also for custom operations like staking, nominating and governance participation.

## Team members

- Alessandro De Carli, MSc. UZH – Software Architect
- Andreas Gassmann, BSc. FHNW – Technical Lead
- Pascal Brun, eidg. dipl. Informatiker – Project Lead, UI/UX & Business Development
- Lukas Schönbächler, BSc. FHNW – Mobile Developer
- Niklaus Knecht, BA. ZHDK – Visual Design

## Team Website

- https://airgap.it

## Legal Structure

Papers GmbH (Switzerland)

## Team's experience

- Alessandro has a master’s Degree in software engineering from the University of Zurich and founded Papers (AirGap is a project of Papers) eight years ago. Back then, Papers developed consumer apps (over 4 Million downloads). We tried to replicate the success with other apps/ideas but the window of opportunity for tech-only companies was closing, it got harder and harder to gain visibility in the App stores. With this in mind, Papers focused on consulting and development for clients, more specifically in the mobile security space for large financial institutions. With clients like Swiss Re we have been implementing their strategic mobile architecture. Alessandro De Carli was the technical lead of the mobile security framework for all mobile apps of Credit Suisse, a framework which still handles all transactions done on the mobile banking app. He got in touch with crypto during his Masters studies and ended up writing his thesis in the area of state channels and micro payments. Already back then Alessandro was developing mobile wallets, given his mobile security background and was heavily involved in other crypto projects (e.g. Equihash Cuda Miner, etc). Today besides his founder role at Papers, Alessandro is also technical strategic advisor for Aeternity and Alethena.
- Andreas has a bachelor’s Degree in software engineering. Andreas studied with Lukas and they have been working together on many projects. He has been working for Papers for two years as a mobile developer, besides working on AirGap he is also responsible for the mobile development of selected customer apps. Andreas likes to experiment and try new development tools and approaches and has also created countless projects like a League of Legends platform for game replays.
- Pascal has a diploma as IT specialist and co-founded Papers together with Alessandro, Lukas and Niklaus. Pascal used to work for a Swiss IT provider in the health sector as a Systems Engineer. While working for Papers, he focused more on UI and UX Design, making user experience his primary focus. Pascal is the lead user experience expert for all our projects. He has strong web development skills and leads the development of accompanying websites for projects. Living in the heart of crypto valley, Zug, Pascal has a wide network in the crypto space and thus play a huge role in business development.
- Lukas a bachelor’s Degree in software engineering. He co-founded Papers and has been working closely with Alessandro for the last eight years. Lukas used to work for a large SAP partner involved in consulting, software development and business processes. Lukas is a skilled mobile developer and works on AirGap in this capacity. He is leading the development of the mobile security product of Papers called Hypergate. Lukas is also helping to grow Papers and closely works with customers like SwissRe.
- Niklaus has a bachelor’s Degree in Graphical Design and co-founded Papers together with Alessandro, Lukas and Pascal. Niklaus is the artist and creative soul in the team, all our illustrations and animations are his work. He used to work for a print designer and won multiple awards with his portfolio. Niklaus is an important asset in refining the user experience of any of our projects, with a high sense of detail and delivering highest quality work on time.

## Team Code Repos

- https://github.com/airgap-it/airgap-vault
- https://github.com/airgap-it/airgap-wallet
- https://github.com/airgap-it/airgap-coin-lib
- https://github.com/airgap-it/cordova-plugin-airgap-secure-storage
- https://github.com/airgap-it/airgap-distro
- https://github.com/airgap-it/airgap-raspberry-apk-signer

## Team LinkedIn Profiles

- Alessandro De Carli, MSc. UZH – Technical Lead https://www.linkedin.com/in/alessandro-de-carli-99011428/
- Andreas Gassmann, BSc. FHNW – Mobile Developer https://www.linkedin.com/in/andreas-gassmann-36040341/
- Pascal Brun, eidg. dipl. Informatiker – UI/UX & Business Development https://www.linkedin.com/in/pascal-brun/
- Lukas Schönbächler, BSc. FHNW – Mobile Developer https://www.linkedin.com/in/lukas-sch%C3%B6nb%C3%A4chler-55489533/
- Niklaus Knecht, BA. ZHDK – Visual Design https://www.linkedin.com/in/niklaus-knecht-23163373/

## Intended language of development

Typescript, Angular, Ionic framework and Cordova

- The airgap-coin-lib (https://github.com/airgap-it/airgap-coin-lib) (Typescript) is a protocol-agnostic library that allows easy handling of the most important tasks relating cryptocurrencies and blockchains. It implements operations such as preparing, signing and broadcasting transactions for a range of protocols.
- AirGap Vault is installed on a is installed on a dedicated or old smartphone that has no connection to any network, thus it is air gapped. (https://github.com/airgap-it/airgap-vault) (Typescript, Angular, Ionic framework and Cordova)
- AirGap Wallet is installed installed on an everyday smartphone. (https://github.com/airgap-it/airgap-wallet) (Typescript, Angular, Ionic framework and Cordova)

## Development Roadmap

The base has already been developed and supports a variety of protocol, our next step is to add support for Polkadot and DOTs.

- Milestone 0: Familiarization with the Polkadot protocol & Requirements Engineering (1 week)
- Milestone 1: Software development of the DOT integration (4 weeks)
- Milestone 2: Testing and iterative bug fixing of DOT integration (1 week)
- Milestone 3: Requirements engineering Staking/Nominating (1 week)
- Milestone 4: Software development of Delegation (3 weeks)
- Milestone 5: Testing and iterative bug fixing of Staking/Nominating (1 week)

After successful implementation of Polkadot, we’ll continue working on improvements and new features related to Polkadot as well as providing support for other protocols.

## Additional Information

- What work has been done so far?  
  AirGap Vault and AirGap Wallet have been fully developed with support for Aeternity, Tezos, Bitcoin and Ethereum. The apps are available in the store and count 10’000 active users.

- Have you applied for other grants so far?  
  Yes, we’ve received a grant by the Tezos Foundation and funding by the Aeternity Anstalt.

- Are there any other projects similar to yours?  
  The Parity Signer has some similarities to AirGap but is not Blockchain agnostic and does not have a complete ecosystem with fully functional apps (a signer and a broadcaster).
