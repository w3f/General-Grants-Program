# Oracle pallet
## Project Description

Equilibrium’s oracle module will be a 9-week long project with the final aim to deliver the following:

- An open-source oracle module which provides prices of different assets on-chain.
- Off-chain module configurable via UI/CURL.
- Staking functionality for designated feeders.
- Support of multiple data-sources both public and private. 
- Ability to change/switch the data-source on the fly. 
- Adjustable price_peridocity changed on the fly, but no faster than once per block.
- Built-in medianizer to calculate final reference price with configurable price relevance period. 
- Reward/slashing mechanism for feeders. 

Equilibrium oracle provides high speed price feeds for DeFi applications within the polkadot Ecosystem. 


## Team members

- Alex Melikhov: Founder & CEO 
- Josh Goodbody: Founding Legal advisor
- Lesley Czuma: Director of Customer Success
- Peter Sergeev: Sr. Project Manager Tech Team
- Kyle Ellicott: Lead Strategist
- Yves Renno: Lead Analyst
- Veniamin Khrapov: Tech Lead
- Pavel Gavrilushkin: Tech Lead

## Team website
- https://equilibrium.io/en

## Legal Structure 
Provided separately.

## Team's experience

- Alex Melikhov: Co-Founder of Changelly, Oxygen, EOSDT. Leading for 14 years in digital and fin-tech. MSc Applied Mathematics
- Josh Goodbody: Former VP at J.P. Morgan Asset Management, ex-Legal Counsel at State Street, former Head of Europe & the Americas of Huobi Global, currently Director of Growth and Institutional Business of Binance
- Lesley Czuma: Extensive international experience in consulting tech startups and blue chip companies e.g. METRO on BizDev. PhD, Free Uni of Berlin
- Peter Sergeev: Mobile trading, integration of internal bank departments, new margin trading engine, automation of OTC order placement. Alfa-Bank
- Kyle Ellicot: Strategic management and product development at Ticketmaster, Eventup, TechZulu etc.
- Yves Renno: Quantitative Research and Structured derivatives trading at Societe Generale / Dresdner Kleinwort / Commerzbank AG; MSs Statistics and Financial Modeling, MSs Financial Mathematics
- Veniamin Khrapov: Focuses on blockchain DeFi projects. Has developed high-load projects and automated marketing at Mindbox. Experienced in trading automation on MOEX, CME, and several blockchain exchanges. 
- Pavel Gavrilushkin: Former head of service development at Alfa-Bank. Specializes in blockchain, network security audits, developing brokerage service infrastructure, and charting market exchanges. 

## Team Code Repos
- https://github.com/equilibrium-eosdt

## Team LinkedIn profiles
- Alex Melikhov: https://www.linkedin.com/in/alex-melikhov-bb272532/
- Lesley Czuma: https://www.linkedin.com/in/lesleyczuma/?locale=en_US
- Peter Sergeev: https://www.linkedin.com/in/peter-sergeev-32520b54/
- Pavel Gavrilushkin: https://www.linkedin.com/in/pavel-gavrilushkin-3116a979
- Veniamin Khrapov: https://www.linkedin.com/in/%D1%85%D1%80%D0%B0%D0%BF%D0%BE%D0%B2-%D0%B2%D0%B5%D0%BD%D0%B8%D0%B0%D0%BC%D0%B8%D0%BD-4272ba5b/ 
- Josh Goodbody: https://www.linkedin.com/in/josh-goodbody-815a7a36/
- Kyle Ellicott: https://www.linkedin.com/in/kyleellicott/
- Yves Renno: https://www.linkedin.com/in/yves-renno/

## Team GitHub profiles
Previous web3 grant work that has been completed: https://github.com/equilibrium-eosdt/equilibrium-financial-pallet

## Development Roadmap
### Milestone 1 - Initial implementation, oracle registration, off-chain worker, oracle subscriptions - 3 weeks
- We will implement registration of the feeder. Registration will require an initial transfer/stake of generic currency into the oracle module.  
- Only top N feeders by stake feed prices at any given point in time.  
- We will make sure the module works with the standard substrate assets module. 
- Initially only one private (requires to specify a key) external data source will be supported: cryptocompare 
- The code will have complete unit-test coverage to ensure functionality and robustness.
- We will publish the code in the Equilibrium’s public GitHub repository.
### Milestone 2 - multiple data-sources,custom data sources, feeding frequency - 3 weeks
- We will add an ability for feeders to choose what asset prices they want to feed.
- We will add an ability for feeders to select custom off-chain sources of price information.
- We will add an ability to correctly parse the price information given JSON path expressions. 
- We will add an ability for feeders to specify feeding frequency 
- We will add an ability to configure off-chain via UI / Curl. 
- The code will have complete unit-test coverage to ensure functionality and robustness.
- We will publish the code in the Equilibrium’s public GitHub repository.
### Milestone 3 - portfolio volatility calculations, Value at Risk calculations - 3 weeks
- We will build a median reference price: every time a new set of prices is received, the median is computed and used to update the reference price value.
- We will add a reward mechanism where feeders will earn rewards for providing price information. 
- We will implement a slashing mechanism of the feeder's stake if the feeder doesn’t update prices for some period of time or feeds prices that are outliers. 
- We will perform integration tests: run a full node, deploy substrate with oracle, add several feeders with different price sources, add consumers/subscribers and test the setup in its entirety
- We will publish the code in the Equilibrium’s public GitHub repository.
- We will provide detailed technical documentation describing pallet logic, storage, interfaces, subscriptions.


## Future Plans

The oracle pallet will be integrated into Equilibrium substrate to provide timely price data for user portfolio evaluation and timely risk measurements/defaults. 
When parity/web3 will come up with XCMP/Spree we would like to make the oracle pallet XCMP/Spree compatible and also introduce reference prices across the entire Polkadot ecosystem.

## Additional Information
### What work has been done so far?
We've drafted the pallet design, its storage, and interfaces. We've created a basic oracle to feed prices to our substrate, we will use this oracle as a basis to expand on.  
### Are there are any teams who have already contributed (financially) to the project?
Equilibrium is fully self-funded.
### Have you applied for other grants so far?
Previous web3 grant work that has been completed: https://github.com/equilibrium-eosdt/equilibrium-financial-pallet
### Are there any other projects similar to yours? If so, how is your project different?
We've looked through other oracles here: https://github.com/w3f/General-Grants-Program/blob/master/grants/polkadot_stack.md#link-chains-and-modules 
Equilibrium's solution  seems to be better than others in following aspects: 
- We have off-chain with configuration via ui / curl - no additional services required to feed prices.
- It is possible to use any custom data sources (including sources with authorization keys).
- Oracle has the setting to adjust the frequency of the feed.
- We are tailored specifically for prices, while Acala, for example, makes a more general case, i.e. for use by third-party projects, you need to write integration code.
- We offer medianizer as part of the oracle, it comes out of the box. 
- Staking/Slashing functionality will be part of the oracle. 