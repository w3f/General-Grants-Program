# Bifrost IPO Liquidity (Grant Application)
## Project Description
Bifrost is a parachain that provides liquidity for staking and collateral assets. It is positioned as the defi protocol in the Polkadot ecology. Based on the development of substrate, the parachain slot will be auctioned. Staking is the first kind of asset for Bifrost to unlock liquidity. Users can use Bifrost to PoS Such assets can be minted into Bifrost vToken to obtain staking rewards and liquidity.

Bifrost plans to provide DOT liquidity for the Polkadot parachain slot auction, because of the limited number of Parachain Slots, the initial price of parachain slots is expensive, the parachain will conduct the first parachain crowdfunding (IPO) to gain an advantage in the slot auction. At this time, a large number of DOTs will be locked into the parachain slot auction due to parachain incentives, and users will lock the DOT through the original method. Users who participate in parachain slot auction will need to wait for the parachain to expire (6-24 months) before it can be redeemed, during this period, users will not be able to trade DOT and will bear the risk of parachain support errors. However, currently users can use DOT/KSM to participate in the parachain card slot auction through this proposal, and obtain the corresponding vsDOT (Voucher Slot DOT) or vsKSM to unlock liquidity. When the user holds vsDOT or vsKSM, they can obtain the incentives given by the parachain crowdfunding. When users want to cash out, they can sell vsDOT or vsKSM to others, the cash out has been completed in advance, and vsDOT or vsKSM will be a derivative of the second type of collateral assets supported by Bifrost Finance

![structure](https://cdn.liebi.com/images/bifrost-ipo-liquidity/1.jpg)

## Team members
### Core Team (Team a total of 12 people)
- Lurpis (Co-Founder & CEO) - Also CEO of Liebi technology; 5 Years of blockchain product and development experience; Sina Weibo early full-stack engineer;Leader of blockchain cross-border settlement in Ping++; Good at creating quality experiences product.
- Edwin (Co-Founder & CTO) - 10 Years of development experience in blockchain and finance; Rich experience in large-scale system architecture design; Former core engineer of Ankr; Substrate course instruct.
- Buffalo (System Architect), with more than ten years of experience in information technology, cryptography applications, and blockchain system research and development, and rich research and development experience in Hyperledger-Fabric, Quorum, Ethereum, Bitcoin and other systems.
- Jamie (Lead Developer) - Leader of bridge / contract / core runtime development; Former National Instruments Test and Development Engineer; Rich RUST development experience.
- Bonnie (Research & Marketing) - 3 Years of blockchain operation experience;Good at using innovative operating system to promote project; Served Fidelity, providing fund dealing support for the APAC.

## Team experience
Through the construction of the Bifrost project, the team has accumulated nearly 14 months of development experience based on Substrate. It is a member of the Substrate Builders Program and Web3 Bootcamp. At the same time, it has obtained the Web3 Foundation Grant through EOS Bridge and has completed the first milestone acceptance. Ready to deliver the second milestone. Have rich practical experience on how to design pledge derivatives and how to provide liquidity for them.

## Team Website 
* https://bifrost.finance

## Team repository
* https://github.com/bifrost-finance

## Technical solutions
In this solution, Bifrost provides an intermediate abstraction layer between investors, parachain projects, and the Polkadot relay chain, providing investors with better financial tools and flexibility, and also providing parachain projects Standardized and configurable IPO tools help parachain projects to better bid for parachain slots and enrich the ecosystem of the entire Polkadot community.

- Investers: DOT, KSM token holders, parachain users and investment institutions are all potential investors in the parachain slot auction.
- Parachain: Need to auction parachain card slots, access polkadot or kusama relay projects.
- Bifrost: Through decentralized provision of vsDOT or vsKSM derivatives, the middle layer protocol that unlocks the liquidity of the parachain slot auction。
- Polkadot/Kusama: Relay chain that has parachain slots and needs to be locked for auction.

### Runtime modules
To implement the above mechanism, we will add the following modules to Substrate runtime of Bifrost:
1. PrepareIPO module
It contains the following features:
    - Parachain Registration: Registration of the parachain’s information and IPO-related arguments on Polkadot-Relaychain.
    - Parachain Rewards Deposit: Parachain deposits IPO Rewards into Bifrost platform .
    - Investors DOTs Deposit: Investors Give Bifrost the capabitlity of bounding their DOTs to support Parachain IPO, and get vsDOT-X or vsKSM-X.
2. ExecuteIPO module
It contains the following features:
    - Bounding DOTs: Bounding DOTs for parachain on Polkadot relay chain to support it’s IPO.
    - Redeeming DOTs: When the IPO fails or slot lease expires, it needs to receive the returned DOTs.
2. Asset module
It contains the following features:
    - Rewards Distribution: Rewards of ParachainX are distributed to vsDOT-X or vsKSM-X holders linearly in time.
    - DOT-vsDOT or KSM-vsKSM Conversion: When slot lease expire, vsDOT-X or vsKSM-X should be converted to DOT.

### Workflow
- Investors participate in the parachain slot auction process
![workflow-parachain-slot-auction](https://cdn.liebi.com/images/bifrost-ipo-liquidity/2.jpg)

- Investors use Bifrost to participate in the parachain card slot auction process with liquidity
![workflow-parachain-slot-auction-with-bifrost](https://cdn.liebi.com/images/bifrost-ipo-liquidity/3_1.jpg)

### Security
Investors use XCMP to transfer DOTs to the Bifrost platform, so the security of user funds is guaranteed by XCMP. Parachain projects that require IPO also use XCMP to deposit rewards asset on the Bifrost platform. These rewards will be released linearly in time. The unreleased part is always locked and no one can embezzle it. It is as safe as being locked in the parachain itself. Parachain projects can also choose to deposit rewards gradually on the Bifrost platform in multi-batches.

## Development Roadmap
##### Milestone 1 - PrepareIPO Development - 1 month - $10k
- Parachain info structs
    - Infomation
    - Arguments
- Parachain rewards deposit
    - Prachain deposit
    - Investor deposit
    - vsDOT release
    - vsKSM release
##### Milestone 2 - ExecuteIPO Development - 1 month - $10k
- Bounding DOTs
    - Bonding
- Redeeming DOTs
    - Redeeming
- Bounding KSMs
    - Bonding
- Redeeming KSMs
    - Redeeming
##### Milestone 3 - Asset Development - 1 month - $10k
- Rewards Distribution
    - Rewards Claim
- DOT-vsDOT Conversion
    - vsDOT Destroy
- KSM-vsKSM Conversion
    - vsKSM Destroy

## Overview
##### Milestone 1
Implement PrepareIPO module in Substrate Frame. Complete Registration workflow.

##### Milestone 2
Implement ExecuteIPO module in Substrate Frame. Complete Bounding DOTs or KSMs and Redeeming DOTs or KSMs workflow.

##### Milestone 3
Implement Asset module in Substrate Frame. Complete rewards distribution and DOT-vsDOT or KSM-vsKSM conversion.

## Additional Information
The code related to the roadmap will be open source in the form of runtime and packaged into docker containers for acceptance. At the same time, this runtime will provide DOT and KSM liquidity for Polkadot and Kusama parachain slot auctions. Bifrost Finance will serve as the first parachain for this feature application. Regarding grant, we are happy to accept DOT.

##### What work has been done so far?
Bifrost has released the third version of the testnet. The mint, redeem and swap of staking derivatives have been completed in the testnet. Currently, the Bifrost testnet supports three types of derivatives: vKSM, vDOT, and vEOS. Holding staking derivatives (vToken) can indirectly participate in staking to obtain benefits, and staking derivatives can also trade at any time and transfer staking rights to avoid the loss of opportunity cost due to staking lockup. After research, Polkadot or Kusama auction parachain card slots have decentralized execution, predictable returns, and absolute principal security, which are similar to staking assets. So it can also solve the problems of equity transfer and lock-up opportunity cost for its casting derivatives.

##### Have you applied for other grants so far?
We have obtained EOS Bridge Grant and completed the acceptance of the first phase milestone. The second phase milestone has been developed and we are preparing for the delivery of the second phase milestone.