# YieldScan (Tentative Name)

**Tagline:** Stake smarter with us. 

## Project Description :page_facing_up:
Scanning yield on nominated proof-of-stake networks. Starting with Kusama.

This proposal builds upon our insights gained after building [PolkaViz](https://polkavizproject.surge.sh/), [PolkaAnalytics](https://polkanalytics.com/#/dashboard) & [Polkabot](https://twitter.com/Polkabot5). 

### Problem Statement:

Problems of information asymmetry and lack of transparency are faced by the Polkadot community in  identifying returns on staking, which incurs time and capital costs to nominators in taking staking decisions. 

#### Questions (by category):
that users (including us) find difficult to get answers to: 
#### 1. Information asymmetry in maximizing returns:
- How do I find and nominate the best validators to maximize returns with minimum effort?
- Who are the nominators earning more than me and why? 
  
#### 2. Lack of transparency causing risk mitigation problems: 
- How can I minimize risk in my staking choices? 
    -  How do I find out how reliable a validator/validator company is?

These above questions are intertwined in their nature as information asymmetry causes lack of transparency and vice versa. This cyclic nature of these questions leads to compounding problems. 

### Problems identified from the above questions: 

#### 1. Information asymmetry in maximizing returns:

Information about validators, validators's earnings, nominator's earnings are  dispersed leading to information asymmetry. This makes staking decision a very time intensive process.  

Patterns identified from the community: 

1. Dispersed Information: nominators currently resort to tools like Polkascan, PolkaStats and PolkadotJS UI to manually analyze several parameters including self stake, commission, number of backers, etc.
2. Time consuming to arrive at decision: inability to select a handful of optimal validators to stake on (from a list of 160 and expected to grow to 1000)
    
> The chain’s governance process sets (and can change) the number, but the goal is to have at least 1,000 validators running BABE and GRANDPA in Polkadot. - [Source](https://polkadot.network/polkadot-consensus-part-4-security/)

Polkadot mainnet release will make incentives real, attracting a plethora of new users. The above will cause high barriers of entry leading to friction in onboarding new users.

#### Validation from community

![https://i.imgur.com/MeQLYwU.png](https://i.imgur.com/MeQLYwU.png)

![https://i.imgur.com/S1SKzU6.png](https://i.imgur.com/S1SKzU6.png)

![https://i.imgur.com/gaskhnE.png](https://i.imgur.com/gaskhnE.png)

#### 2. Lack of transparency causing risk mitigation problems
The introduction of identity module has provided a great tool to make the identities of network operators more transparent, verifiable and accessible. But there's only so much that it can do.

- Validators lack incentive to update their identities and hence they still lack a persona (or a brand image) and are still not "memorable".
- The identity module still lacks crucial off-chain information like vision/team behind the nodes which leads to pseudonymous identities behind validators, making it difficult for users to put their trust on such entities.

#### Validation from community
The lack of an identifiable persona behind network operators is evident in the following community call: [https://youtu.be/ASUW_YCmuEs](https://youtu.be/ASUW_YCmuEs)

The topics discussed in the community call are listed [here](https://forum.stakingdefense.org/t/validator-business-model-discussion/244).


Our assumption is that most nominators are value conscious and rational and they would want to spend the least amount of time or/and stake to obtain maximum returns. We feel that currently there is no easy way do to this in the Polkadot ecosystem. 


## Solutions

### 1. Solving the problem of information asymmetry: 

- For users who wish to passively participate in staking, the platform will provide a one (or few) click solution, by taking in `stake amount` and `risk preference` as input and returning a list of recommended suggestions optimized for returns. [Idea credits: Anson Lau]
- For users who want to actively analyze metrics and filter choices based on the same:
    - a filtering mechanism to allow users to find a list of desired validators based (similar to [Baking Bad](https://baking-bad.org/))
        ![](https://i.imgur.com/TGY2a2a.png)
- > Who are the nominators earning more than me and why?
    
    A leaderboard of nominators, sorted by **expected daily earning** will make such information readily available for users, allowing them to analyze the state of the rest of the network. It also encourages active participation in staking by creating a competitive spirit.
    

### 2. Solving the problem of transparency: 

1. Extension of existing specific views for validators to include consolidated information about team members running a node, hardware powering the node, subjective information about the company like their vision, etc. will:
    - strengthen the identities of validators 
    - increasing accountability and leverage for validators
    - allow nominators to make staking decisions based on which network operators they find to be more accountable and trustworthy depending on how transparently they operate
2. Creation of specific views for council members, similar to the ones existing for validators to visualize relations between voters and councillors:
    ![](https://i.imgur.com/SH8nhOh.png)
3. A quantified metric like a `transparency score` assigned to each validator based on the amount of information they publish, will incentivize them to update on-chain and off-chain information.
4. A nominator profile to monitor nominations and manage stakes along the following lines (tentative design):
    ![](https://user-images.githubusercontent.com/40575379/73833446-03f15880-4830-11ea-8345-a498af3f5d3d.png)

The combination of these solutions into one cohesive platform will make information about the Polkadot ecosystem more accessible, transparent and easy to navigate thereby reducing effort, time and cost for current participants on the network and also lowering the barrier of entry for newcomers and easing the on-boarding process.

### Why are we interested in solving this problem?

After getting context around how difficult it can be to deep dive into the sea of information to fish for what is relevant, we decided that we want to lower the barrier of entry to the Polkadot ecosystem for people like us who want to participate, but have no clue how to.

Our story:

1. When trying to nominate validators, we were personally faced by the challenge of having to pick the "16 optimal validators" to nominate. Specifics about the problem:
    - We didn't know about the incentives on staking.
    - We had no idea about how to choose a trustworthy and high ROI validator.
    - We were oblivious to the risks involved with staking (although we did know there has to be some risk involved).
2. To make an informed decision on whom to stake, we realized that we need to fill in a gap of knowledge. That gap can be summarized by the following questions:
    - how payouts work in Polkadot?
    - what makes a validator better than the other from an end user's perspective?
    - how to compare different validators and what are the factors to take into account for the same?
3. After gaining awareness around the above gaps, we had to wade through dispersed information in the form of blogs, articles, documentation, et al. to find answers to these questions.

It took us weeks to get to a point where we felt comfortable with the concept of staking on a validator. We believe that we are not the only ones looking for these answers.

## Team :busts_in_silhouette:

- **Members:**
    - Saumya Karan
    - Bhaskar Singh
    - Sahil Nanda
    - Prastut Kumar
- **LinkedIn Profiles:**
    - Saumya Karan - [https://www.linkedin.com/in/skrn/](https://www.linkedin.com/in/skrn/)
    - Bhaskar Singh - [https://www.linkedin.com/in/bhaskar-singh-55a535b9/](https://www.linkedin.com/in/bhaskar-singh-55a535b9/)
    - Sahil Nanda - [https://www.linkedin.com/in/sahil-nanda-8b1b88143/](https://www.linkedin.com/in/sahil-nanda-8b1b88143/)
    - Prastut Kumar - [https://www.linkedin.com/in/prastut/](https://www.linkedin.com/in/prastut/)
- **Code Repos:** All our code repos can be found on: [https://github.com/thevantageproject/](https://github.com/thevantageproject/)
- **Website:**	[https://buidllabs.io/](https://buidllabs.io/)
- **Legal Structure:** Information in Google form.
- **Team's Experience:**

    Our team has been spending mindspace on this particular problem for the past 6+ months:

    1. We started with building PolkaViz, which visualizes relationships developing between validators and nominators.
    2. Then we built reward calculators for both Kusama and Alexander Network.
    3. We recently shipped out the [Polka Analytics Platform](https://polkanalytics.com/) that connects PolkaViz and Rewards Calculator under one umbrella along with UX upgrades.
    4. Along with the above efforts, we also shipped out [Polkabot](https://twitter.com/Polkabot5) - a twitter bot to post updates about the Kusama Network - which already has 74 followers at the time of writing this proposal. See analytics so far below: 

![](https://i.imgur.com/CD6n6MG.png)


These efforts have been funded by PolkaDAO so far and have received great feedback from the community.

For maintaining accountability in a remote setting, we documented our progress every week [here](https://docs.google.com/document/d/1IMF_Ik3mLoZrB3eDAhSb88J3aVtllyiy6c5ciNEJjAc/edit).

Brief info about the team members:

- Project Lead: Saumya Karan
    - Currently spending mindspace in solving UX problems in onboarding people to decentralized economic networks.
    - Previously built and shelved a social network for developers. Led design and product management for it.
    - Will be leading product management + lead designer for the project
    - [GitHub.](https://github.com/saumyakaran)
- Lead Product Engineer: Bhaskar Singh
    - Previously built and shelved 2 startups. Led frontend for them.
    - Will be leading full stack engineering efforts to build out the platform.
    - [GitHub.](https://github.com/bhaskarSingh)
- Lead Researcher: Sahil Nanda
    - Currently spending mindspace in understanding validator & nominator relationships across various PoS stakes.
    - Previously built PolkaViz. Built algorithmic trading strategies for a crypto hedge fund.
    - Will help the team with vantage around emerging patterns in validation & nominator relationships + advising on full stack development.
    - [GitHub.](https://github.com/sahilnanda1995)
- Advisor: Prastut Kumar
    - Currently spending mindspace in understanding economic incentives in participating in decentralized economic network.
    - Has 5+ years of product-dev experience across multiple startups, research labs and companies.
    - Will help the team with vantage of making something which people want.
    - [GitHub.](https://github.com/prastut)

## Development Roadmap

### Milestone 1 -- Validator recommendation system to ease staking decisions -- 1 month

The goal of this milestone is to significantly reduce the cognitive load for nominators to make staking decisions by providing actionable advice, easy-to-use filtering mechanism and transparent rewards.

- We've divided the recommendation system into 2 phases:

    1. Phase 1 will upgrade the [current dashboard](https://polkanalytics.com/#/dashboard) to include recommendations for staking to increase returns. 
    2. Phase 2 will add a `cumulative risk level` for each validator set to determine the most optimal set of validators based on `risk/reward` ratio.

- For users who prefer a "DYOR" approach, we'll add a filtering mechanism to narrow the list down to a preferred validators set.

- To promote active participation in staking via healthy competition, we'll build a nominator leaderboard sorted by earnings

| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1.  | Suggested prompts | This will be the Phase 1: <ul><li>We'll take in `stake amount` as input</li><li>We'll divide the `stake amount` by 16 equal </li><li>Using our [rewards predicition mechanism](https://hackmd.io/-k2e9Xy0RCarSK8PIJjYuA), we'll determine the top 16 validators for maximum returns</li><li>The top 16 validators will be suggested to the user, where they can simply sign a transaction to stake on the 16 validators</li></ul>|
| 2. | Risk score for each validator | This will be Phase 2: <ul><li>First, we'll develop a risk calculation mechanism to determine how risky each validator is. To do this, we'll take on-chain information like `self stake`, `total stake`, `number of nominators`, `history of slashes`, et al. as input and return a `risk level` as output</li><li>Using the risk calculation mechanism, we'll determine and display risk scores for each validator on the UI</li><li>Lastly, we'll improve our suggested prompts using these scores by suggesting top 16 validators based on rewards/risk ratio</li></ul> |
| 3. | Filtering mechanism (similar to [Baking Bad](https://baking-bad.org/)) |  For users who prefer "DYOR" approach, we'll develop a filtering mechanism to filter validators based on attributes like commission, self-stake, total stake, number of backers and more. The idea for UI is similar to the following: ![](https://i.imgur.com/TGY2a2a.png) |
| 4. | Nominator Earnings Leaderboard | We'll create a leaderboard to rank nominators by their earnings from staking |
| 5. | Integration with PolkadotJS wallet| Finally, to make it easier for the users to act on their staking decisions, we'll use PolkadotJS wallet to allow users to add and manage their stakes from within the platform itself. |

### Milestone 2 -- Implement extended profiles for transparent display of information  -- 1 month

The goal of this milestone is to implement profiles for validators, council members and nominators to enable users to make informed decisions by creating transparency.

**NOTE:** These profiles will NOT be "social profiles", these will be similar to a portfolio which nominators can look over to make staking decisions - meaning that the focus shall be on the data with an identity behind it, in contrast to a social network, where the primary focus is on identity and conversations.

This milestone is divided in 2 phases:

1. In the first phase, we will create an actionable UI for nominator profile to monitor their balances, earnings and nominations in the form of a staking dashboard.

2. In the second phase, we will extend the existing specific views for validators and council members to leverage the identity module and make these network operators more accountable.

    - In this phase, we will create specific views for council members, similar to those we created for validators (screenshot attached below) to visualize relations between council members and voters creating transparency in the operations of council members.
    ![](https://i.imgur.com/SH8nhOh.png)

    - To create stronger, trustable identities for validators and council members, we will extend the specific views to serve as "profiles". These "profiles" will include on-chain data from the `identity module` along with some basic information like `number of nominators`, `amount of stake`, etc. and also off-chain information like `information about team members`, `vision of the organisation/company`, `bio`, et al.


| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Staking dashboard to monitor stakes | To make it easier for nominators to monitor and manage their stakes, we'll create a dashboard with information about their nominations, rewards and balances. The tentative design is along the following lines: ![](https://user-images.githubusercontent.com/40575379/73833446-03f15880-4830-11ea-8345-a498af3f5d3d.png) |
| 2. | Extension of specific views to serve as profiles for validators | <ul><li>Addition of support for identity module</li><li>Allowing authenticated users (via PolkadotJS wallet) to update their profile information which shall include things like `bio`, `logo`, `theme color`, `team members section`, `vision of the company`, et al.</li></ul> |
| 3. | Creation of extended specific views for council members | Using the extended specific views for validators as a template, we'll develop extended specific views for council members, to display consolidated on-chain information and allow them to update off-chain information about themselves. |

### Milestone 3 -- Incentivizing transparency via twitter and gamification -- 1 month

The goal of this milestone is to encourage users to operate transparently, and share their experiences socially to create network effect. In this milestone, we will:
- build a `transparency score` to incentivize validators and council members to publish more on-chain and off-chain information
- use our [twitter bot](twitter.com/Polkabot5) to market features
- group validators by company to allow users to identify nodes being run by a particular company they might trust


| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Transparency score |  We’ll develop a “transparency score” based on the amount of information (both on-chain and off-chain) that’s shared by validators and council members to promote transparency in identities. Updating each attribute like display name, legal name, twitter handle, etc. will carry some points, which will be added to the transparency score. Inspiration: ![](https://pbs.twimg.com/media/ERv6MLVXYAUYylQ?format=jpg&name=small)|
| 2. | Twitter bot additions (Marketing) | <ul><li>Nominator leaderboard</li><li>Twitter optimized screenshots of data</li><li>Using twitter usernames from identity module (if available) to tag top validators and nominators</li></ul> |
| 3. | Group validators using identity | Using the identity module, we'll group validators who share the same uniquely identifiable attribute like twitter account or email |




## Additional Information :heavy_plus_sign:

**What work has been done so far?**

As reflected in the [Team Experience Section](https://www.notion.so/33dc8a620ded490d86c23d9c248bf0f1?v=38b2dfff302c4f279c8b830d79e25cbf&p=ea85de9367544c57b359b3e7bb055aee#Team%E2%80%99s-experience), we've developed a rewards prediction system to predict the payout for a nominator if they decide to stake on a given validator based on the stake amount they enter. We've also built the specific views for nominators and validators which shall be extended to serve as a "profile" page for validators and council members (possibly even nominators). We're currently working on an authentication system to allow users to login using PolkadotJS wallet. The progress so far is reflected on [https://polkanalytics.com](https://polkanalytics.com/)

**Are there are any teams who have already contributed (financially) to the project?**

As mentioned in the [Team Experience Section](https://www.notion.so/33dc8a620ded490d86c23d9c248bf0f1?v=38b2dfff302c4f279c8b830d79e25cbf&p=ea85de9367544c57b359b3e7bb055aee#Team%E2%80%99s-experience), the only financial contributions we've received for building the product so far are from PolkaDAO.

**Have you applied for other grants so far?**
No.

**Are there any other projects similar to yours? If so, how is your project different?**

- PolkaStats
- Lunie
- Nomidot
- DotHub
- ~~Commonwealth~~ (was similar)
- ~~SubSocial~~ (was similar)
- ~~PolkaAssembly~~ (was similar) - We were unaware of this platform before our discussion with David - thanks to him we were able to plan a better project which will be of more value to the community

For detailed analysis of how we're different from the above project https://hackmd.io/@skaran/ryDFoUDN8

**TL;DR:**
- PolkaStats
- Lunie
- Nomidot
- DotHub

The above projects present information in a DIY format for the users, in contrast, we provide actionable suggestions to ease staking decisions.

- Commonwealth
- SubSocial
- PolkaAssembly

We believe it is worth mentioning that the previous version of our proposal had problematic overlaps with the above projects in that we were trying to solve discussion problems like commonwealth and Polkassembly and had a wall feature similar to subsocial.

Thankfully, David pointed us in the right direction and we made changes to our proposal to focus on vertical depth in building a platform which helps users make smarter staking decisions by giving actionable suggestions.

**The team's long-term plans and intentions with this project.**

In the long run, we intend to make the Polkadot ecosystem more accessible, to encourage mass adoption, by solving UX problems, to reduce friction for both existing and new users.
