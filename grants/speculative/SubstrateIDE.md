# Substrate IDE

## Project Description

We would provide a graphical integrated development environment (IDE) for developing substrate-based blockchains on all major operating systems. By integrating numerous tools into a graphical interface, we believe Substrate IDE can help developers improve their efficiency substantially throughout the entire development process. Key features of Substrate IDE will include code editor, compiler, substrate node manager, debug tools to interact with substrate nodes, etc.

## Team members

Our team, Obsidian Labs, is a Silicon Valley based startup focused on blockchain technology. Our founders were YC alumni and have been working together on blockchain for more than two years.

* Phil Li, founder of Obsidian Labs, YC alumni, PhD from Massachusetts Institute of Technology, 3rd place of EOS Global Hackathon in San Francisco. Full stack developer with experience on mobile & web applications, blockchain and smart contract. Core developer of EOS Studio.
* Rose Ren, co-founder of Obsidian Labs, Bachelor from University of Michigan, Ann Arbor. 3rd place of EOS Hackathon in San Francisco. Former PR & Marketing director at Nebulas. Former investment manager at Continue Capital and Danhua Captial.
* Leon Liang, full-stack developer.
* Aaron Li, full-stack developer.
* Sabrina Zhang, product manager.

## Team Website	
* https://www.eosstudio.io
* https://www.obsidianlabs.io

## Legal Structure 
Obsidian Labs Technology Inc.
A company registered in the state of Delaware, USA.

## Team's experience

Our team has released EOS Studio for EOSIO mainnet in February 2019 and since then we've attracted thousands of developers and received very positive feedback. Most EOS development teams have already used EOS Studio as their standard tool for developing dApps. Meanwhile, EOS Studio was recommended in Block.one's developer portal as the only official IDE made by the community.

## Team Code Repos
* https://github.com/ObsidianLabs

## Team LinkedIn Profiles
* https://www.linkedin.com/in/zehao-li
* https://www.linkedin.com/in/roseren

## Development Roadmap

### Milestone 1

**Time estimate:** 6 weeks

**Budget:** $50,000 (80% in USD or stable coins, 20% in DOTs)

**Deliverable:** installation packages for Substrate IDE (Mac OS).

**Specifications:**

Build Substrate IDE for Mac OS with features listed below

- Create a new substrate project (electron component `@obsidians/substrate-up`)
  - Through graphical interface
  - Show creation logs in an embedded terminal
  - Write codes for the project
- Build/compile the substrate project (electron component `@obsidians/substrate-compiler`)
  - Through graphical interface
  - Generate both WASM and native binary
  - Show build logs in an embedded terminal
- Start a built substrate node (electron component `@obsidians/substrate-node`)
  - Through graphical interface
  - Support start with the purge option
  - Show node running logs in an embedded terminal
- Read data written in the substrate node (React component `@obsidians/substrate-states`)
  - Select module & field
  - Keep a list of data and track for value changes
  - Refresh button
- Push transactions (React component `@obsidians/substrate-extrinsics`)
  - Select module & function
  - Fill parameters in a generated form
  - Sign transaction and push to the blockchain
  - View execution result
- Documentations for each components and the IDE
 
Each of the above components can be started separately as individual apps.
Substrate IDE will combine the components together as a single application.
Each components will be open sourced at the ennd of milestone 1, but the IDE itself 
will remain close sourced for now. We plan to open source more components of the IDE 
in the future when they are ready, with the ultimate goal to fully open source the IDE.

The features in milestone 1 should be able to finish all processes of substrate tutorials 
[Creating your first substrate chain](https://substrate.dev/docs/en/next/tutorials/creating-your-first-substrate-chain/) 
and 
[Substrate collectables workshop](https://substrate.dev/substrate-collectables-workshop/#/)
in the IDE, except for frontend development.


**Notice** Milestone 1 is only an alpha-stage release and not intended for production use.

### Milestone 2

**Time estimate:** 6 weeks

**Budget:** $50,000 (80% in USD or stable coins, 20% in DOTs)

**Deliverable:** installation packages for Substrate IDE (Mac, Linux & Windows).

**Specifications:**

Build Substrate IDE for Windows and Linux operating systems with the same features in milestone 1. Milestone 2 will also cover extra features listed below

- Substrate node (update the electron component `@obsidians/substrate-node`)
  - Start substrate node with extra configurations
  - Upgrade node using the WASM file
  - Visualize node metrics
- Account visualization and operations (React component `@obsidians/substrate-account`)
  - View account information (address, pubkey, etc)
  - View account balance
  - View account transaction history
  - Transfer funnds
- Keypair manager (electron component `@obsidians/substrate-keypair`)
  - Create new keypair
  - Save available keypairs
  - Sign transactions with Polkadot-js extension
- Documentations for each components and the IDE

As mentioned above, each component will be open sourced but the IDE itself will remain close sourced for now.

### Long term plan

IDE is a complex product and we can only cover very basic features during the 3-month period.
We would like to continue working on Substrate IDE in the future and make it more helpful for substrate developers.

## Additional Information

* **What work has been done so far?**

  We've built a [demo](https://www.dropbox.com/s/tcnd6v7bylb13a7/Substrate%20IDE.mp4?dl=0) for Substrate IDE

* **Have you applied for other grants so far?**

  No.

* **Are there any teams who have already contributed (financially) to the project? Are there any other projects similar to yours?**

  Not to our knowledge.
