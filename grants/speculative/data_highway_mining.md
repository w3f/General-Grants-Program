# Project name

## Project Description

Data Highway Mining is an inclusive approach that will realize an extended inter-chain outreach by incentivizing different communities  to diversify their means of participation. It will also incentivize usage of LPWAN secure hardware.

Usage of Data Highway token mining involves a holder of certain tokens such as ERC-20 MXC, IOTA or DOT tokens to configure a time period to lock some of their tokens in a smart contract or to just hold that quantity in an account, and this is recorded in the Data Highway token mining configuration runtime module. Users are also incentivized to share usage of their LPWAN hardware on the Data Highway by configuring a time period throughout which they can ensure its uptime will be maintained.

A Data Highway token mining oracle service is used to take samples of how many tokens are in that account or locked in the smart contract at random times over the defined time period, and the results are recorded on the Data Highway token mining sampling runtime module. Likewise there will be a Data Highway hardware mining oracle service that will take samples of whether a users configured hardware is online at randome times over the defined time period, and record the results on the Data Highway hardware mining runtime module.

After the end of the the time period the Data Highway's token mining eligibility runtime module calculates a mining speed boost that the holder of those tokens may claim (i.e. 1.2x), and the Data Highway's hardware mining eligibility runtime module calculates a mining speed boost that the owner of the shared LPWAN hardware may claim (i.e. 1.2x).

After user's claim their eligibility using the Data Highway's token/hardware mining claims runtime module respectively, that mining speed boost will be applied to that users staking rewards that result from them participating in the Data Highway as a validator or nominator to secure the parachain.

Similar projects:
* Edgeware's lock-drop
* ChainX's inter-chain asset mining

If this application in response to an RFP then please indicate this on the first line of this section.

Please provide the following:
  * A brief description of the project.
  * An indication of why this project is good for the ecosystem.
  * An indication of how you will integrate this project into Substrate / Polkadot.
  * An indication of why your team is interested in creating this project.

## Team members
* Xin Hu (Data Highway Mining Lead）
* Aaron Waegener (Data Highway Mining Business Development)
* Siwon Kim (Data Highway Mining Business Development)
* Stéphane Letz (Data Highway Mining Marketing)
* Jeff Stahlnecker (Data Highway Mining Project Manager)
* Luke Schoen (Data Highway Mining Blockchain Developer)
* Shiun Chen (Data Highway Mining Blockchain Developer)
* Suhee Lee (Data Highway Mining UX)
* Namgyeong Cho (Data Highway Mining Frontend Developer)
* Christian Groeschel (Data Highway Mining DevOps)
* Lixuan Jia (Data Highway Mining QA)
* Stefan Bachmann (Data Highway Mining QA)
* Aslan Mehrabi (Data Highway Data Scientist)

* **TODO** - Update the above list of team members if necessary

## Team Website	
* http://datahighway.com/

## Legal Structure 
Name: Data Highway
Address: DAO on the Polkadot Network

## Team's experience
* Luke Schoen uses handle [ltfschoen](https://github.com/ltfschoen) on Github.
  * Recently he has contributed to the following:
    * Data Highway development. He built the node and wrote the whitepaper https://github.com/DataHighway-com
    * Edgeware testnet validator. He built a validator guide https://github.com/ltfschoen/edgeware-node
  * Previously he worked at Parity primarily on the following:
    * Polkadot.js. Example PR https://github.com/polkadot-js/apps/pull/336
    * Parity Fether. Example PR https://github.com/paritytech/fether/pull/332
    * Parity Ethereum. Example PR https://github.com/paritytech/parity-ethereum/pull/10657
  * Prior to that he was a full-stack Ethereum DApp developer.

* TODO - Please describe the team's relevant experience.  If the project involves development work, then we'd appreciated if you can single out a few interesting code commits made by team members on their past projects.  We'll glance at whole repositories too, but not if they contain many vendored dependencies, which often makes commits easier. 

## Team Code Repos
* https://github.com/DataHighway-com/node
* https://github.com/DataHighway-com/documentation
* https://github.com/DataHighway-com/api
* https://github.com/DataHighway-com/mining
* https://github.com/DataHighway-com/website
* https://github.com/DataHighway-com/whitepaper

## Team LinkedIn Profiles
* Luke Schoen [Linkedin](https://www.linkedin.com/in/ltfschoen/)
* https://www.linkedin.com/<person_2>

## Development Roadmap
This section should break out the development roadmap into a number of milestones. Since the milestones will appear in the grant contract, it helps to have as much detail as possible. Whenever milestones are delivered, we refer to the contract to ensure that everything has been delivered as expected.

Here is a reminder of the main criteria of our grants:
* Focus on Substrate / Polkadot related projects.
* Max $100k.
* Timeframe: up to 3 months is ideal.
* Open source license (the preferred license is Apache 2.0)

Below we provide an **example roadmap**. In the descriptions it should be clear how the project is related to Substrate and/or Polkadot. We recommend that the scope of the work can fit within a 3 month period and that teams structure their roadmap as 1 month = 1 milestone. It is always best to describe the functionality we should expect, plus how we can check that such functionality exists in the product.

For each milestone:
* Please be sure to include a specification of the software. The level of detail must be enough so that we are able to test that the software meets the specification.
* Please include total amount of funding requested per milestone. Funding can be in fiat (CHF, EUR or USD) or in DOTs. It can also be in a combination of fiat and DOTs. Please reach out to grants@web3.foundation to discuss what amount in fiat and DOTs would be appropriate for your project.
* Please note that we require documentation (e.g. tutorials) in each milestone. This ensures that the code can be widely used by the community.
* Please commit to providing a docker container for the delivery of your project. 
* Please indicate the number of Full-Time Employees working on each milestone, and include the number of days along with their cost per day.

### Milestone 1 — Implement Substrate Modules — 1 month — $10,000
* We will create a Substrate module that will... (Please list the functions that will be coded for the first milestone).
* We will deliver a working module, along with a simple tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works.
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will build a Docker image with our Substrate chain and the compatibility layer, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the compatibility layer can be used and tested.

### Milestone 2 — Additional features — 1 month — $10,000
* We will create a... (Describe the next round of features and functions that will be added).
* We will deliver... (Explain how you will demonstrate that the functionality you built will work as intended).
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will build a Docker image with our Substrate chain and the compatibility layer, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the compatibility layer can be used and tested.

### Milestone 3 — Additional features — 1 month — $10,000
* We will create a... (Describe the next round of features and functions that will be added).
* We will deliver... (Explain how you will demonstrate that the functionality you built will work as intended).
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will build a Docker image with our Substrate chain and the compatibility layer, demonstrating its functionality.
* We will provide both inline documentation of the code and a basic tutorial describing how the compatibility layer can be used and tested.

## Future Plans
* Please include the team's long-term plans and intentions.

## Additional Information
Any additional information that you think is relevant to this application that hasn't already been included.

Possible additional information to include:
* What work has been done so far?
* Are there are any teams who have already contributed (financially) to the project?
* Have you applied for other grants so far?
* Are there any other projects similar to yours? If so, how is your project different?  
