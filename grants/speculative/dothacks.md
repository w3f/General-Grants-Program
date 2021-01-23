# DotHacks: a privacy-preserving and fair Security Response Platform on a public blockchain

## Project Description
### Overview (Introduction)
Blockchain world has been suffering from vulnerabilities, e.g.,

1. in centralized exchange: MtGox hack (https://en.wikipedia.org/wiki/Mt._Gox),
2. in cryptography: double-spending in Bytecoin due to small subgroup attack (https://jonasnick.github.io/blog/2017/05/23/exploiting-low-order-generators-in-one-time-ring-signatures/),
3. in smart contracts: The DAO hack (https://en.wikipedia.org/wiki/The_DAO_(organization)).

Moreover, since 1) the market value involved is massive, 2) there is still lacking clearly defined or practical legal protections for cryptocurrency users, and 3) the techniques used in blockchains are still emerging and keeping evolving, which makes Blockchain security specialists become more desired, the security concerns of blockchain systems become significantly crucial.

However, there is no current Security Response Center (SRC) existing in the Polkadot ecosystem to mitigate the loss caused by blockchain vulnerabilities.
 
In this RFP, we propose DotHacks, a SRC platform built on a public blockchain, Polkadot in specific, to enable trustless SRC service. What make it different from conventional ones are: 1) we make use of Polkadot blockchain as the public ledger for persisting records; 2) we use consensus to govern the arbitrations; 3) and we use cryptography to preserve privacy and fairness; 4) we use tokenomics to incentivize the participants.
 
As Polkadot is a project aiming at providing a feasible solution to bridge all other public blockchain projects, we believe that, with its design goal and promising progress, Polkadot is becoming the center of the blockchain world. Thus DotHacks can serve as a comprehensive SRC platform for blockchain projects and achieve its best potential.

### Project Details
Conventional SRC and crowdsourced bug-bounty platforms (e.g., hackerone, bugcrowd) suffer from limitations including:

+ insufficient privacy protection for white-hats
+ insufficient privacy protection for vulnerability reports
+ centralized arbitration mechanism

These are also cases for some decentralized crowdsourced bug-bounty platforms (e.g., https://dvpnet.io/).
 
DotHacks addresses these issues in the following ways:

+ White-hats can choose to submit reports anonymously.
+ DotHacks splits each report into shards and encrypt each shard to mitigate sensitive data leakage. Though a report is sharded, its logic correctness and consistency can still be verified, see section #Sharded report verification for details.
+ DotHacks uses State Channel Network (a layer 2 solution). State channel network enhances report submission privacy by privacy-protected peer-to-peer communication, and the submission can be verified by smart contract once exiting the state channel network and submitted on chain. The submission may comes with a dispute, and DotHacks uses arbitration committee to address disputes.
+ DotHacks uses randomness for an arbitration committee election to improve fairness.
+ On-chain reports are encrypted and each of them comes with a time-lock puzzle. Full vulnerability details will only be disclosed and be public after a set period. Vendors can also choose to keep the full report private.

In specific, DotHacks works as follows:

**Fig.1 Bug-bounty program workflow** (from a Whitehat's perspective):
![](https://github.com/dothacks/dothacks.github.io/raw/main/assets/whitehat.png)

**Fig.2 Bug-bounty program workflow** (from a Vendor's perspective)
![](https://github.com/dothacks/dothacks.github.io/raw/main/assets/vendor.png)

**Fig.3 Bug-bounty program workflow** (from an Arbitrator's perspective)
![](https://github.com/dothacks/dothacks.github.io/raw/main/assets/arbitrator.png)

#### Sharded report verification
To verify a report while mitigating sensitive data leakage, DotHacks shards each report and encrypt them during submission. Common used stage conclusions among shards are extracted, to examine logic consistency and enable cross-shard verification.

![](https://github.com/dothacks/dothacks.github.io/raw/main/assets/sharding.png)

![](https://github.com/dothacks/dothacks.github.io/raw/main/assets/shard2.png)

Arbitration committee are elected by randomness, to ensure fairness. Neither the whitehats nor vendors can predict who are arbitrators and thus cannot bribe them. Arbitrators can neither collude with each other to learn the full report.

## Team & Team experience
We would like to keep our team information private.

## Development Roadmap
+ Total Estimated Duration: 12 weeks
+ Full-time equivalent (FTE): 24

### Milestone 1
We implement a bug bounty platform without considering disputes.

+ Estimated Duration: 4 weeks
+ FTE: 8
+ Costs: $30, 000

| Deliverable | Specification   |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Repository         | A git repository containing source code and a README that describes the work done during this milestone and how to use API to announce a bug bounty program or participate into one. |
| Tests              | The code will have proper unit-test coverage to ensure functionality and robustness. |
| Docker             | Docker cluster of DotHacks nodes, demonstrating its functionality. |
| Documentation      | Full documentation for the DotHacks parachain. |
| Experiments report | A report of evaluating the DotHacks protocol without considering disputes. |

### Milestone 2
We add layer 2 for dispute resolving to the system, with a fixed arbitrators set.

+ Estimated Duration: 4 weeks
+ FTE: 8
+ Costs: $40, 000

| Deliverable | Specification   |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Repository         | A git repository containing source code and a README that describes the work done during this milestone. |
| Tests              | The code will have proper unit-test coverage to ensure functionality and robustness. |
| Docker             | Docker cluster of DotHacks nodes, demonstrating its layer 2 protocol. |
| Documentation      | Full documentation for the DotHacks' layer 2 protocol. |
| Experiments report | A report of evaluating the DotHacks' layer 2 protocol. |

### Milestone 3
We integrate randomness into dispute resolvings.

+ Estimated Duration: 4 weeks
+ FTE: 8
+ Costs: $40, 000

| Deliverable | Specification   |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Repository         | A git repository containing source code and a README that describes the work done during this milestone. |
| Tests              | The code will have proper unit-test coverage to ensure functionality and robustness. |
| Docker             | Docker cluster of DotHacks nodes, demonstrating its functionality. |
| Documentation      | Full documentation for the DotHacks parachain. |
| Experiments report | A report of evaluating the DotHacks protocol. |

## Future Plan
1. Integrate a full-featured front-end (and in addition a blockchain explorer) into the system, to offer a more friendly user experience.
2. Add decentralized governance for improving vulnerability assessment standards and administration regulations.
3. Establish an industry-impactful whitehat community on top of DotHacks platform.

