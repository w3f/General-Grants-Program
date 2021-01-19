# Curve automated market maker
## Project Description

Curve AMM module will be a 9-week long project with the final aim to deliver the following:

- Low slippage, high efficiency stablecoin exchange
- High efficiency exchange tool for other homogeneous assets on Polkadot (e.g. wrapped assets) 
- Low risk fee income for liquidity providers. 
- Liquidity superfluidity with additional rewards from supplying liquidity to lending protocols such as Equilibrium and Acala.

Curve’s unique stableswap invariant utilizes liquidity much more efficiently compared to all existing DEXes for stablecoins at already several hundred USD TVL (total value locked). Since initial liquidity on Polkadot is hardly going to be very large, proposed efficiency is VERY important for the ecosystem to flourish.

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
### Milestone 1 - nitial implementation, pool manipulations, invariant calculation - 3 weeks
- Assets will be handled using a new assets trait. 
- We will implement a pool storage structure for handling different asset pools with different parameters. 
- We will implement methods to set up custom asset pools. 
- We will implement a method to iteratively calculate Curve’s invariant D and points on the bonding curve in non-overflowing integer operations. 
- The code will have complete unit-test coverage to ensure functionality and robustness.
- We will publish the code in the Equilibrium’s public GitHub repository.
### Milestone 2 - actual assets exchange - 3 weeks
- We will implement methods to work with asset pools: add liquidity / remove liquidity. 
- We will implement methods to exchange assets within pools.
- We will implement a mechanism to reward liquidity providers with LP tokens.
- The code will have complete unit-test coverage to ensure functionality and robustness.
- We will publish the code in the Equilibrium’s public GitHub repository.
### Milestone 3 - portfolio volatility calculations, Value at Risk calculations - 3 weeks
- We will implement liquidity superfluidity: assets locked inside Curve liquidity pools may be further used in various lending protocols across the Polkadot ecosystem. 
- We will perform integration tests: run a full node, deploy substrate with Curve module, add several pools with different configurations and initial balances, will perform exchanges, record slippages and fees, and perform liquidity manipulations. 
- We will publish the code in the Equilibrium’s public GitHub repository.
- We will provide detailed technical documentation describing pallet logic, storage, interfaces, subscriptions.

## Future Plans

When parity/web3 will come up with XCMP/Spree we would like to turn the Curve pallet into a SPREE module so the swap logic may be shared across many parachains and parathreads.

## Additional Information
### What work has been done so far?
We've drafted the pallet design, its storage, and interfaces. 
### Are there are any teams who have already contributed (financially) to the project?
Equilibrium is fully self-funded.
### Have you applied for other grants so far?
Previous web3 grant work that has been completed: https://github.com/equilibrium-eosdt/equilibrium-financial-pallet
### Are there any other projects similar to yours? If so, how is your project different?
We've found only one AMM among the projects called SubDEX, but it only allows for constant product swapping without the liquidity and slippage considerations 
