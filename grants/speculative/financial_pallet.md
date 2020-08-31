# Financial pallet
## Project Description

Equilibrium’s Financial pallet will be a 6-week long project with the final aim to deliver the following:
- An open-source substrate module that subscribes to external price feeds/oracles, gathers asset prices and calculates financial metrics based on the information collected.
- Financial module will store price arrays for different assets supporting different time frequencies.
- Financial module will calculate simple and log returns based on price information.
- Financial module will implement  methods to calculate volatilities of assets based on price data arrays using several different statistical approaches from traditional finance.
- Financial module will implement methods to calculate pairwise correlations of assets based on price data arrays using several different statistical approaches from traditional finance.
- Financial module will implement method to calculate portfolio volatility given user/account portfolio of assets.
- Financial module will implement methods to calculate portfolio Value at Risk given user/account portfolio of assets using several different statistical approaches from traditional finance. 
- Financial module will be extendable allowing to add custom and/or non-standard approaches to financial data analysis and modeling. 

The Financial module will be a must-have pallet for anyone building complex DeFi and Fin-tech solutions using Substrate technology. It will allow to gauge instrument and portfolio risk irrespective of the asset and portfolio considered. The pallet will be of great benefit to anyone building DeFi DAPPs on substrate, and in particular for those teams who are willing to go beyond hard-coded arbitrarily-set risk metrics. 

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
N/A as we haven't been involved in any public or open-source projects so far. 

## Development Roadmap
### Milestone 1 - Initial implementation, subscription to oracle.
- We will use https://github.com/encointer/substrate-fixed library for fixed point math implementation
- We will implement subscription to oracle price changes and will store prices in price arrays with default time intervals: 1 minute, 10 minute, 1 hour, 4 hour, 1 day.
- Subscription to oracle require oracle contract sending on_price_update events to all of the subscribers, all price history needed for calculations is stored within the financial pallet.  
- We will implement functions which perform returns and log returns calculations for given frequency.
- We will define pallet interface with a complete set of functions (calc. returns, calc. volatility, calc. correlations, calc. portfolio vol, calc. Value at Risk). 
- We will implement traits for each statistical parameter calculation.  
- The code will have complete unit-test coverage to ensure functionality and robustness.
- We will publish the code in the Equilibrium’s public GitHub repository.
### Milestone 2 - returns, volatilities, and correlation calculations - 2 weeks
- We will implement a unified data structure for each asset with calculated information.
- We will add an ability to supply historical prices via config when starting the chain. 
- We will implement functions for volatility and correlation calculations which will return corresponding numbers for given asset and frequency.
- We will calculate volatility and correlations using standard statistical approach and using exponential weighted average approach.  
- The code will have complete unit-test coverage to ensure functionality and robustness.
- We will publish the code in the Equilibrium’s public GitHub repository.
### Milestone 3 - portfolio volatility calculations, Value at Risk calculations - 3 weeks
- We will implement method to calculate portfolio volatility given user account / portfolio.
- We will implement method to calculate Value at Risk using standard and log normal approaches.
- The code will have complete unit-test coverage to ensure functionality and robustness.
- We will demonstrate volatility and VaR calculations in action within our substrate for several different portfolios.  
- We will perform integration tests: run a full node, deploy substrate with oracle and financial pallet, calculate sample portfolios using different assets and different frequencies with time shifts. 
- We will publish the code in the Equilibrium’s public GitHub repository.
- We will provide detailed technical documentation describing pallet logic, storage, interfaces, subscriptions.

## Future Plans

The Financial pallet will be further used in Equilibrium’s DeFi parachain for the risk and pricing models to calculate interest rate fees, assess borrower portfolio risks and overall system risks.

We have a plan of the further financial pallet evolution that will add complex and non-parametric ways of volatility, correlation and portfolio risk estimations. We will offload heavy calculations in some of these methods to designated off-chain worker. Following additional methodologies/calculations will be introduced: EWMA, GARCH, Garman-Klass volatility estimates, as well as GARCH, CVaR, Monte-Carlo simulation, Historical simulation, and Copula methods for assessing value at risk.

## Additional Information
### What work has been done so far?
We've drafted the pallet design, its storage, and interfaces. We've created an oracle to feed prices to our substrate, we will use this oracle within the financial pallet to feed asset prices. 
### Are there are any teams who have already contributed (financially) to the project?
So far we're fully self-funded.
### Have you applied for other grants so far?
No
### Are there any other projects similar to yours? If so, how is your project different?
The financial pallet we're developing will be used inside Equilibrium's DeFi parachain. Equilibrium proposes novel approach to on-chain pricing (interest rate calculation) and risk (determination of entire system health) calculations, which distinguishes its framework from known competitors (Acala/MakerDAO) in several ways:
- There are no arbitrary governance-set interest rates, they are determined by borrower portfolio, borrower debt amount, and market dynamics and risks. 
- As a consequence from the above: there are no arbitrary set LTV requirements. The system makes sure every position remains solvent at a 100% collateralization ratio. 
- There are no selling of liquidated collateral into falling markets, e.g. there is no risk of accumulation of non-handled “debt” in the system. 
- There are no arbitrary set liquidation penalties which are currently very high with competitors: ~10-20% of borrower debt.
- By design there are always two sides to the system: lenders / bailsmen one side and borrowers on the other side. Borrowers pay fees and interest rates which are distributed to lenders / bailsmen.    
- Equilibrium's unique balances module architecture allows for capturing of various promising mechanics such as: asset lending, fractional reserves, and synthetic asset creation (all of these features are not part of the 1st stage and will be introduced to the product in its further development stages).  