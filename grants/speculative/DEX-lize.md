# DEX-lize

## Project Description
DEX-lize is an aggregative decentralized exchange protocol. It adopts aggregation, market-maker, incentive etc.. to offer the best liquidity and implement best price discovery mechanism. It's the center of liquidity.
There are some popular dex aggregators on ethereum. eg: totle, 1inch, dex.ag. These projects provide a single point entry for different dex like bancor, kyber, uniswap to discover the best exchange price on dex. Some of them even provide more advanced functions.

Currently, these projects are integrated with other dex passively. It requires the team to match the dex handly. For example, the Totle project wrote a lot of handlers to access different dex & liquidity providers(https://github.com/TotlePlatform/contracts/tree/master/contracts/exchange_handlers).

`Passively Access` brings a lot of problems. One of the most important is,  when a 3rd party contract wants to use the aggregator to have a swap, it has to specify the dex it wants to use. Because it costs a lot to query every dex and get the best swap price on-chain.

We are trying to build a liquidity aggregator that allows liquidity providers (eg, dex) to actively integrate with. `Actively Access` liquidity aggregator has the potential to become a standard of the liquidity aggregator and the project could be the entry of on-chain liquidity.

Since there are not enough dex in substrate/polkadot ecosystem and cross-chain communication is not fully ready, `Passively Access` is not a good direction right now. But building an `Active Liquidity Aggregator` will bring a meaningful possibility for the substrate/polkadot ecosystem.

## Team members
* Jamie Cheng: Blockchain & Tech Leader
* Terence Ge: Front-end developer
* Thomas Yu: Business Development & Product Manager

## Team Website
* https://www.dexlize.org/

## Legal Structure
A company in Singapore: Dexlize Foundation PTE LTD.

## Team's experience
Dexlize Team was founded in early 2018. Most of the team members are experienced blockchain engineers. Some of us has been worked in BTCChina or WanXiang since 2015.

In 2018, we developed a mobile wallet BitPortal (https://www.bitportal.io/) which supports BTC, ETH, EOS, and ChainX. (It will support Polkadot ecosystem in the future and also will integrate with the polkadot extension to support dapps).

In 2018, we won the 2nd prize of the WanXiang Blockchain Hackathon (Shanghai).

We are especially interested in dex related direction since we start to develop exchange in 2015. We realize the on-chain liquidity is very important to the Defi ecosystem.

## Team Code Repos
* https://github.com/DexlizeProject/dexlize-node
* https://github.com/BitPortal

## Team LinkedIn Profiles
* Jamie Cheng: https://www.linkedin.com/in/starit/
* Terence Ge: https://www.linkedin.com/in/terence-ge-4a146185/
* Harry Hong: https://www.linkedin.com/in/hao-hong-028b9b64/
* Thomas Yu: https://www.linkedin.com/in/wenqing-yu-812b4ab2/

## Development Roadmap

Open Source License will be Apache 2.0.

### Milestone 1 — Implement Dexlize Core Substrate Modules — 1 month — $10,000
* We will create the DEX-lize in-chain aggregator module. It will support at least 2 types of dex to integrate with.
* We will create two example dex module that will integrate with the dexlize in-chain  aggregator module.
* The code will have proper unit-test coverage to ensure functionality and robustness.
* We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.


### Milestone 2 — Frontend — 1 month — $10,000
* We will create a page to show the status and graph of total dex liquidity. (which is very important to the project)
* We will implement the swap api in aggregator to implement best price discover.

### Milestone 3 — More dex types — 1 month — $10,000
* We will integrate with more dex types
* Research on XCMP
* Blockchain Explorer Integration

## Future Plans
The target of the DEX-lize project is to optimize on-chain liquidity as much as we can. So we will use multiple methods to explore and optimize on-chain liquidity.

* In the future, the project should combine with `XCMP` to provide cross-chain liquidity aggregator.
* In the future, the DEX-lize blockchain may become one of the parachain and try to become the center of onchain liquidity.
* More dex types will be supported.
* Performance optimization.

## Additional Information
* There are some similar projects which have proven the idea on Ethereum network (1inch, dex.ag, totle). Ultimately,we will have integrated/updaterd models and implementation
