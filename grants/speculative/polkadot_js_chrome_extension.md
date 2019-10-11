# Enhancements for the Polkadot Browser Extension

## Project Description

### A brief description of the project.

Polkadot{.js} Extension is an ongoing project, that aims to provide reliable browser
plugin allowing to interact with Polkadot network. So far it is the most used extension in the ecosystem.

Our work will be focused on two goals:
1. Significant UI/UX improvement
1. Account management with secret URIs

[Project repository](https://github.com/polkadot-js/extension).

### Why this project is good for the ecosystem?

Providing usable and aesthetic browser interface is essential for the whole ecosystem usability. Experience gained
during development of solutions for the Ethereum ecosystem taught us that quality
of such user-facing tools is crucial to mass adoption of the system.

Account management with Hierarchical Deterministic wallet is the industry standard, employed for example by the Metamask extension.
It makes it easier for users to safely preserve the mnemonic giving access to all the accounts.

### How you will integrate this project into Substrate / Polkadot?

Polkadot{.js} Extension is already a part of the ecosystem. With this grant we plan to improve it.

### Why your team is interested in creating this project?

Ethworks is a software house that offers blockchain solutions. We had
an opportunity to work on numerous dApps integrated with blockchain
via web extension. For example, we created POA bridge with extensive Metamask interaction.
We deeply understand the needs that such
a tool should meet - both from the developer and user perspective.
This project fits our skillset and the tech stack we use. Contributing to it
gives us a chance to get to know the fast-growing Polkadot ecosystem.

## Team members

- Krzysztof Jelski (Team leader)
- Natalia Kirejczyk (Designer)
- Bartłomiej Rutkowski (Developer)
- (optionally) other developers at Ethworks

## Team Website	

https://ethworks.io

## Legal Structure 

Ethworks sp z o.o.<br>
VAT ID: PL7010771665.<br>
Ignacego Krasickiego 35<br>
02-611 Warsaw, Poland<br>
Office:<br>
Czeczota 29<br>
02-606 Warsaw, Poland

## Team's experience

We have been actively involved in the Ethereum ecosystem for many years, many of
us even before Ethworks was founded. During this time we had the opportunity to
build many widely used tools such as Ethereum.rb (the ethereum library for the
Ruby language) or Waffle (a library for writing and testing smart contracts).

For our clients we have developed numerous customer-facing dApps.
We not only know how to create robust and reliable software, but also clean, modern and user-friendly UI.
Our design team had pleasure to work with such great brands as Ethereum Foundation, Bitcoin or IOTA.

Additionally members of Ethworks are building Universal Login, a tool for
storing funds and connecting to Ethereum applications, aiming to simplify
on-boarding of new users.

## Team Code Repos

* https://github.com/polkadot-js/extension (the project we want to contribute to)
* https://github.com/Ethworks/Waffle
* https://github.com/EthWorks/ethereum.rb
* https://github.com/UniversalLogin/UniversalLoginSDK/

## Team LinkedIn Profiles

* https://www.linkedin.com/in/krzysztofjelski/
* https://www.linkedin.com/in/nkirejczyk/
* https://www.linkedin.com/in/bartłomiej-rutkowski-958751118/

## Development Roadmap

### Milestone 1

#### UX overhaul

We’ll create a look and feel and UX that is pleasant and smooth to work with. This will both raise extension attractiveness and usability. None of the features will be removed, none will be added. Some changes in the flow are possible to deliver better UX. At this stage, we will focus only on improving the user's interaction with the software.

Here are some examples of screens we've redesigned so far for the Polkadot extension: 

![Example screen 1](https://i.imgur.com/4S5Bhfc.png)
![Example screen 2](https://i.imgur.com/rC1yjGA.png)
![Example screen 3](https://i.imgur.com/SgS9EvO.png)

#### Deliverables:

- Re-design of current screens and flows
- Necessary changes in the extension code, mainly in the layouts
- Screenshots for the Chrome Store
- Design both dark and light themes + choosing a theme in settings
- Update of screenshots in existing documentation

#### Time estimate
 - 2 weeks of team's work
 
#### Cost estimate:
 - 8400 €

### Milestone 2

#### Account derivation

In the current version of the extension, users can add a derivation path when creating an account from a seed. But this feature is hidden and not documented. We will create an interface allowing users to easily manage the derivation path while creating new accounts. The user will be able to decide if he wants to use soft or hard derivation. The user will be able to provide the whole derivation path on his own or compose it out of predefined elements (eg. *//kusama//funding/1*).

#### Deliverables:

- Extension feature: compose derivation path of predefined elements
- Extension feature: enter freeform derivation path
- Update to Readme (and other docs if necessary) on how to use new features

#### Time estimate
 - 3-4 weeks of team's work
 
#### Cost estimate:
 - 9600 €

### Milestone 3

#### Master seed

We will reorganize the way extension creates new accounts. The extension will have one master account created from master seed and any new account created will be derived from it. We will introduce standard defining how derivation paths should look like and how should they be used.
These features may introduce some major changes to application flow, which will be designed to provide the best UX possible.
Old accounts won't be removed. They will be preserved and managed in a manner similar to Metamask’s "imported" accounts.

#### Deliverables:

- Extension feature: new flow upon first interaction with the extension - master seed creation
- Extension feature: distinguishing the derived and imported accounts
- Extension feature: allow users to choose between automatic and manual derivation path creation
- Update to Readme (and other docs if necessary) on how to use new features

#### Time estimate
 - 4 weeks of team's work
 
#### Cost estimate:
 - 12000 €

### Long term plans

We intend to create a solution that will take place in Polkadot ecosystem similar to place
taken by Metamask in Ethereum ecosystem. We hope that Polkadot{.js} will become first-choice
browser account manager and irreplaceable developer tool.

## Additional Information

### What work has been done so far?

We have opened a Pull Request on Export feature. It has been approved and merged.
- [Project repository](https://github.com/polkadot-js/extension)
- [Our PR](https://github.com/polkadot-js/extension/pull/166)

Also we have created a design draft, showing how the extension popup might look like in the future
- [Clickable prototype](https://www.figma.com/proto/5NAICV06SHNbbIoYhrUS3u/PolkaDot?node-id=99%3A0&viewport=-28%2C572%2C0.2018236368894577&scaling=min-zoom)
- [Demo video](https://i.imgur.com/5M4Ratb.mp4)

### Are there are any teams who have already contributed (financially) to the project?

No.

### Have you applied for other grants so far?

Yes.
Bridging RFP (https://github.com/w3f/Web3-collaboration/issues/155#issuecomment-531254920).
Tranquility - Smart contract programming language (https://github.com/w3f/Web3-collaboration/pull/176)
