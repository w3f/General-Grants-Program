# General Grant Proposal
 
* **Nsure.Network:**  Open Insurance Platform for Open Finance
 
## Project Overview
 
### Overview
Nsure is an open insurance platform for Open Finance. The project borrows the idea of Lloyd’s London, a market place to trade insurance risks, where premiums are determined by a Dynamic Pricing Model. Capital mining will be implemented to secure capital required to back the risks at any point of time. A 3-phase crowd voting mechanism is used to ensure every claim is handled professionally.
 
Nsure will include the following parts::
 * Nsure protocol: with full support for capital mining, buying, staking etc.
 * Nsure products: enable more and more financial applications(including smart contracts) to insure.
 * Nsure financial service app: integrate with selected Polkadot wallet, to provide full functions and good experience.
 
### Project Details
For the project, we have finished a MVP on ethereum rinkeby network which can be found here: https://buy.nsure.network/#/insure, and the code could be found here: http://github.com/nsure-tech. In general, it has 3 parts:
 
#### Capital mining
By providing capital to the Nsure Network, Nsure tokens are minted and issued to the capital providers. Token holders can 1) stake on the projects and earn premiums; 2) hold to enjoy the benefit from the growth of the system; 3) sell in the market to realize profit.

#### Open market to trade risk
Nsure tokens can be used to stake on the risks that Nsure token holders feel comfortable with. Insurance premiums are paid daily, and Nsure token holders benefit from the system and leverage provided.
 
#### Dynamic Pricing
Rather than a single centralized entity setting up a premium rate, or individual capital suppliers and policy holders having to negotiate over premium terms, Nsure uses the Dynamic Pricing Model to set the price, based on supply and demand, the tokens backed and the policies bought.

#### Capital Management
The capital model is used to ensure claims will be paid and that systematic risk is under control. Insurance is a highly leveraged industry; therefore, the primary concern of the insurance capital model is to calculate the capital required to guarantee solvency of the risk pool to some arbitrary and high confidence level like 99.5%. 

### Ecosystem Fit
Nexus mutual is the first player in the decentralized space. Nsure borrows the idea from liquidity mining to capital mining and use the capital to provide leverage of all policies sold. Dynamic pricing model will generate price quote based on demand and supply which fixed NXM's pricing model that is only based on capital supply. Staking model is much friendlier than NXM in terms of locking period, risk taking and leverage setting. Risk model takes lower leverage than NXM which protects both risk assessors and capital suppliers. Claim process is optimized to only one round of public vote which reduced unnecessary public vote steps. Policyholder will file claims together as a group instead of filing each case one by one.
 
## Team
 
### Team members
* Jeff Ren - Project Lead/Management & Research
* Alex Peng - Insurance Model Design & Actuarial Analysis
*Alvaro Fernandez - Strategy & Growth
* Leafan Chan - Lead Developer
* Vincent Bauwens - Marketing
* Gherardo Lattanzi - Operation
 
### Team Website
* https://nsure.network
 
### Legal Structure
Nsure Limited which is registered at Unit8, 3/F., Qwomar Trading Complex, Blackburne Road, Port Purcell, Road Town, Tortola, British Virgin Islands.
 
### Team's experience
* Jeff Ren: M.Sc in Management. M.Sc in Coastal Engineering. Previously with Chainfunder Capital as Investment Director & Researcher. Research about blockchain protocols and ecosystems since 2017. Has been developing for Hurricane surge model for NOAA(US National Oceanic and Atmospheric Administration).
 
* Alex Peng: Master’s Degree in Financial Engineering. 10 years insurance professional in AON with extensive experience in Actuarial Analysis, Insurance Linked Securities structuring and Reinsurance broker. Expert in Financial Modeling and Quantit-ative Analytics.
* Leafan Chan: Project Management Professional (PMP) certificate. Expert in Project Management, smart contracts and public blockchain development. He formly worked for supporting dpos of ethereum, and leading a dex program which can be accessed here: www.btswap.com
* Alvaro Fernandez: Majored in Economics & Finance.
Developed his career in Venture Capital space. Previously Vice President and Managing Director for Europe at JRR Group. prior to that Investment & Incubation Manager at ChainFunder. Provided strategic consulting, including DBS Singapore & Italian Undersecretary of State for the Ministry of Economic Development.

* Vincent Bauwens: Msc. in Finance and Business Engineering. Co-Founder of several companies and ecommerce brands.Currently managing a marketing agency. 5+ years of experience in marketing & business development and early stage investments in the blockchain industry.
* Gherardo Lattanzi: Crypto Data Analytics | Ecosystem Developer @ OceanProtocol. Data Analtycs and ML certificate from Ubiqun Code Acadamy. Degree in International Business Trading and Development.
 
 
### Team Code Repos
* nsure:  https://github.com/nsure-tech
* btswap: https://github.com/btswap/contracts
* dpeth:  https://github.com/goomtu/dpeth
* Leafan: https://github.com/leafan
 
### Team LinkedIn Profiles
* https://www.linkedin.com/in/lattagher/
* https://www.linkedin.com/in/keyang-ren/
* https://www.linkedin.com/in/aschwinbauwens/
* https://www.linkedin.com/in/leafan/
 
## Development Roadmap
 
For now, we have finished our whitepaper and MVP, and will split our project plan into several parts:
 
### Overview
* **Total Estimated Duration:** 6 months
* **Full-time equivalent (FTE):**  3
* **Total Costs:** 30k
 
### Milestone 1 — MVP
* **Estimated Duration:** 1 month
* **FTE:**  2
* **Costs:** $5,000
 
Milestone 1 will implement our mvp as a substrate module. We will implement capital mining to let users deposit the test tokens, and get the returned rewards(test Nsure token).
* We will implement staking functions which perform staking and price handling for insurance. 
* We will define the interfaces with a complete set of functions (deposit, withdraw, doWithdraw, getReward, stake, withdrawStaking, doWithdrawStaking etc).
* We will publish the code in our public GitHub repository.
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works.
* Documentation will be delivered according to the Web3 Milestone Deliverables Guidelines.
 
 
### Milestone 2 — beta release: Capital Mining; Cover purchasing; Leveraged Staking; Claim payment
* **Estimated Duration:** 4 month
* **FTE:**  3
* **Costs:** $15,000
 
We will publish our beta release in 4 months for the full functions of nsure project as a substrate module. It includes the contract/frontend/backend and related coding. Finally open to public for beta test. In this version :
* We will define a unified data structure for each product(such as compound contract, balancer contract etc) with price, description and any other information in need.
* We will implement the buying logic for insurace with a detailed order structure. The order will record the buyer, price, period, premium etc.
* We will define and implement the claim procedure so that buyers can do a claim if they found that they need a compensation.
* We will integrate the captial mining and staking functions with buying logic, and do a full joint debugging/testing for them.
* We will use javascript with vue framework as our frontend language.
* We will publish the code in our public GitHub repository.
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works.
* We will provide a dockerfile to demonstrate the full functionality of our chain
* Documentation will be delivered according to the Web3 Milestone Deliverables Guidelines.
 
 
### Milestone 3 — official version
* **Estimated Duration:** 1 month
* **FTE:**  3
* **Costs:** $10,000
 
The official version will support all the functions in milestone2, and support voting via decentralised governance features with its own token for claiming(DAO goverance).
* We will support users to claim by voting as a fully decentralized function which means no admin needed in claim procedure.
* We will fix the bugs which was founded in beta version.
* We will perform integration tests: run a full node, deploy substrate with nsure module, do staking and capital mining, and get quote or buy insurances from the system.
* We will publish the code in our public GitHub repository.
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works.
* We will provide a dockerfile to demonstrate the full functionality of our chain
* Documentation will be delivered according to the Web3 Milestone Deliverables Guidelines
 
### Community engagement
 
We have published some articles on medium: https://medium.com/@nsure_network. Meanwhile, we will give talks and do AMA sessions to advertise the project to the Polkadot community.
 
## Future Plans
* Nsure will implement our project both in ethereum and polkdadot.
* After its main functionalities are finished and tested, Nsure.Network will enable capital mining and staking.
* We plans to be the biggest insurace project for Polkadot ecosystem.
 
## Additional Information
 
Possible additional information to include:
* What work has been done so far?
We have finished our MVP on ethereum, and our development jobs are on the way, and will publish our first official version in 2020Q1. Our mvp can be found here: https://buy.nsure.network/#/insure(should switch to rinkeby network)
 
* Are there any teams who have already contributed (financially) to the project?
No.
 
* Have you applied for other grants so far?
No.
 

## Questions

* Q1:Can you go into detail of what exactly you mean by capital mining?
Does this mean users are staking tokens (DOTs?) in exchange for nsure tokens?
A1: In regards to capital mining, it is intended to have capital deployed to the pool for MCR requirements. Rewards in order to incentivise capital providers are paid out in Nsure (mined @ 2/block rate). On Ethereum we allow capital to be defined as ETH and stablecoins such as DAI, USDC. In order to be able to adapt to other potential chains, it would be possible to adapt such, i.e. having DOT & other stable coins accepted as capital provision for the capital pool.
 
* Q2: How do you plan to integrate stable coins? At the moment there are no functional stablecoin bridges with Polkadot.
A2: Stablecoins are intended to give users an alternative currency according to their desire for exposure towards market fluctuations. We would rely on each chain’s available ressources/alternatives for such integrations. Nsure can be seen as being focused on functioning as part of the application layer, hence reliability on the given choices of each ecosystem. If at this stage Polkadot has no stablecoin solutions deployed, DOT can be the main resource utilised as means of payment of premiums, settlement, capital provision and claim payouts.
 
* Q3: MCR will be locked accordingly when a policy is sold
Who creates and sells the policy? How do you envision policy creation?
A3: Policy could be bought as long as 1) buyers are comfortable about the price offered by the dynamic pricing model 2)  the MCR is lower than the total funds in Surplus Pool and Capital Pool. Policy is offered by the system, and the pricing is determined by tokens staking on that project.

* Q4: Staking: Staking rules will be supported to accelerate capital mining.
What rules do you mean? How does that differ from my first question?
 A4: Nsure tokens can be used to stake on the risks that Nsure token holders feel comfortable with. Insurance premiums are paid daily, and Nsure token holders benefit from the system and leverage provided. Staking needs study on the risk of projects, which have higher return and higher risk accordingly. Capital Mining provides the additional funds to support business development, it is the second cushion of the potential claims, which have lower risk, and the return determined by how much funds are in capital mining.

* Q5: Can you explain the rounds of "3-phase vote claim assessment" & how a user can participate in assessment?
A5: Phase 1, all policyholders vote whether to file the claims or not, which is designed to prevent the waste of auditing and public voting resource from malicious claim requests. Phase 2, professional auditing companies vote whether the claim should be paid, we believe claim assessments are highly complex and require domain specific knowledge. Phase 3, Public vote, if phase 2 is challenged, where users can participate and share the reward.For more details, please reach thewhite paper.



