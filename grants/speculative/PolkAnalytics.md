# PolkAnalytics (Tentative name)

## Project Description :page_facing_up:

### Problem Statement

The Polkadot Community faces a problem of information asymmetry, which creates friction around decision-making for current participants on the network and presents a high barrier of entry for newcomers.

This problem is created due to the lack of abstraction and accessibility of information. To explain this in detail, this problem can be broken down as follows:

1. **Information about validators can be dispersed, opaque and time consuming to navigate**. This can be identified from the following:
    1. Nominators currently resort to tools like Telemetry, Polkascan, PolkaStats and PolkadotJS UI to manually analyze several parameters including self stake, commission, number of backers, etc.
        - This makes it difficult, time consuming and tedious to select a handful of optimal validators to stake on, from a list of 160, based on personal risk preferences.
        - For new users, this proves to be an unnecessary barrier of entry to the Polkadot ecosystem.
        - Once the Polkadot mainnet is released and incentives become real, attracting a plethora of new users, this will cause friction in the onboarding process.

        Reducing the vast number of parameters to just the incentives and risks will:

        - reduce cognitive load and save time for existing community members
        - significantly lower the barrier of entry for new users.

        This problem is compounding exponentially with the increase in number of validators, which is already at 160 and expected to go up to at least 1000.

        > The chain’s governance process sets (and can change) the number, but the goal is to have at least 1,000 validators running BABE and GRANDPA in Polkadot. - Source

        ### Validation from community

        ![https://i.imgur.com/MeQLYwU.png](https://i.imgur.com/MeQLYwU.png)

        ![https://i.imgur.com/S1SKzU6.png](https://i.imgur.com/S1SKzU6.png)

        ![https://i.imgur.com/gaskhnE.png](https://i.imgur.com/gaskhnE.png)

    2. Validators promote themselves on forums, social media, blogs, et al. because there's no standard format for validators to share essential on-chain and off-chain information to market themselves.

        Currently, the community is relatively small and hence the members try to identify trustworthy validators from their activity on riot channels.

        However, this becomes increasingly difficult as more and more validators join the Polkadot Network.

        A standard format to display consolidated information about each validator will:

        - reduce the effort spent in research by nominators
        - make it easier for validators to market themselves.

        ### Validation from community

        ![https://i.imgur.com/o7wupCr.png](https://i.imgur.com/o7wupCr.png)

2. **Lack of clarity about the consequences of proposals being passed or dismissed.**

    While PolkadotJS UI makes the proposals and referenda readily available to the community by solving the visibility problem, the consequences of a referendum or proposal being passed continue to remain unclear to the vast majority of voters due to lack of structured discourse about each proposal.

    Currently, community members resort to having governance related discussions on riot channels which is sub-optimal to say the least, because it leads to:

    - unstructured discussions, making the information inaccessible to the vast majority
    - difficulty in maintaining a history of discussions around previous proposals - practically impossible to revisit discussions around a particular proposal passed a while ago

    Structured, open and transparent discussions about the proposals will:

    - make the discussions more accessible to the community
    - allow users to look up historical data for proposals along with the discussions that led to the decision for it's dismissal or approval
    - allow the community to understand the consequences and act accordingly

    ### Validation from community

    In our conversation with Bill Laboon from W3F, he gave us an idea about a
    feature to make information surrounding council members and referenda
    more readily available:

    ![https://i.imgur.com/g5miBVL.png](https://i.imgur.com/g5miBVL.png)

3. **Council members and validators lack a persona.**

    The introduction of identity module has made the identities of network operators more transparent, verifiable and accessible. But there's only so much that it can do.

    The council members and the validators still lack a persona (or a brand image) and thus they are still not "memorable".

    Knowledge of the company or individual(s) name can only go so far in creating trust.

    Information such as their vision, motives and beliefs connected with their identities make the network operators more accountable, allowing users to elect and stake with confidence and provides the operators with more leverage within the community.

    ### Validation from community

    The lack of and identifiable persona behind network operators is evident in the following community call: [https://youtu.be/ASUW_YCmuEs](https://youtu.be/ASUW_YCmuEs)

    The topics discussed in the community call are listed [here](https://forum.stakingdefense.org/t/validator-business-model-discussion/244).

## Solutions

1. To make information about validators more accessible, a validator intelligence platform with consolidated information about every validator will reduce the effort required by nominators to make staking decisions. It will also reduce the cost (in terms of time, effort and money) for marketing validator services. The platform shall include:
    1. Consolidated on-chain information about the validator, specifically:
        - Reward prediction mechanism (already implemented on Polka Analytics) which clearly defines the incentives for staking, encouraging mass participation.
        - Risk level calculated based on time of operation, slash history, number of backers, self stake, etc., thereby reducing the effort required by the end user for analyzing the same.
        - Using the above information, a mechanism to allow users to simply enter the amount they would like to stake and risk level they’re comfortable with to determine the optimal validators for them to stake on will completely automate this process of staking and significantly lower the barrier of entry for newcomers. [**Idea Credits:** Anson Lau]
        - To further reduce the friction to stake, a mechanism to allow users to directly stake tokens from within the platform itself, using PolkadotJS browser extension for identity verification.
    2. Current marketing efforts by validators become less and less effective over time due to creation of dispersed information. A “wall” feature (similar to 3box) on the specific views for validators, will allow:
        - Validators to post regular updates related to their service, which may include recent upgrades to their hardware, add-on services that they offer, et al. in a predictable and impactful format
        - Nominators to easily compare off-chain information about validators, by reducing the time and effort cost of searching through various different sources of information, thereby making it easier for them to select feature-rich and trustworthy validators to stake on
2. Sunlight is absolutely the best disinfectant. Radical transparency in decision making for each proposal will be the very best form of regulation. Let people make informed decisions for themselves based on high-quality, free, public information. This transparency can be achieved by creating threads for each proposal containing:
    - On-chain information about the proposal, which will allow users to understand the facts about what is being proposed
    - A comment section allowing open and transparent discourse about the consequences, which will allow users to understand what would happen if the proposal is passed and subsequently make informed decisions based on the general consensus of the community
        - Threads would be closed once a decision about a proposal is made to avoid unnecessary arguments after the fact from crowding the threads, thereby making it easier to find the primary reasons behind approval or rejection of a proposal
3. Increasing accountability for council members and validators, by creation of "profiles" for these network operators, will allow voters and nominators to make voting and staking decisions based on which network operators they find to be more accountable and trustworthy depending on how transparently they operate. These profiles will contain both on-chain and off-chain information, specifically:
    1. On-chain information
        1. For council members, creation of specific views similar to what exists for validators, will allow visualization of relationships between council members and their voters. Along with the visualization, the specific views will contain the following information:
            - Record of vetoes
            - Votes on proposals
            - Locked stake
            - Backing Amount
            - Voters
        2. For validators, there already exists specific views, which already include number of backers, self stake, total stake, commission and daily earning.
        3. For both council members and validators, the following information will be added to their specific views:
            - All available information from the identity module
            - Based on the amount of information provided in the identity module and other off chain information, calculation of a transparency score
    2. Off-chain information
        - Mission statement for users to easily identify the motives and beliefs of the network operators
        - Team, previous experience and brief team member profiles to further strengthen the identity of the network operator, increasing accountability
        - Core beliefs/values to generate trust
        - As already stated under point 1.2., the "wall" feature will contribute in further increasing the trust

The combination of all of these solutions into one cohesive platform will make information about the Polkadot ecosystem more accessible, transparent and easy to navigate thereby reducing effort, time and cost for current participants on the network and also lowering the barrier of entry for newcomers and easing the on-boarding process.

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

It took us weeks to get to a point where we felt comfortable with the concept of staking on a validator. This problem is going to compound exponentially in light of the following information:

> "The chain’s governance process sets (and can change) the number, but the goal is to have at least 1,000 validators running BABE and GRANDPA in Polkadot." - Source.

We believe that we are not the only ones looking for these answers.

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
- **Website:**	[https://www.thevantageproject.com/](https://www.thevantageproject.com/)
- **Legal Structure:** Information in Google form.
- **Team's Experience:**

    Our team has been spending mindspace on this particular problem for the past 6+ months:

    1. We started with building PolkaViz, which visualizes relationships developing between validators and nominators.
    2. Then we built reward calculators for both Kusama and Alexander Network.
    3. We recently shipped out the [Polka Analytics Platform](https://polkanalytics.com/). that connects PolkaViz and Rewards Calculator under one umbrella along with UX upgrades.
    4. Along with the above efforts, we also shipped out [Polkabot](https://twitter.com/Polkabot5) - a twitter bot to post updates about the Kusama Network - which already has 74 followers at the time of writing this proposal.

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

### Milestone 1 -- Implement mechanism for Automated Selection of Validators

In this milestone, we will automate the selection of validators thereby reducing:
1. cognitive load for nominators
2. the friction involved with staking.
 
We've divided this into 2 phases:

1. Phase 1 will automate selection of validators based *only* on the daily earnings potential.
2. Phase 2 will add a `cumulative risk level` for each validator set to determine the most optimal set of validators based on `risk/reward` ratio.


| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1.  | Automation of selection of validators | This will be the Phase 1: <ul><li>Taking all possible combinations of 16 validators with commission != 100%, we'll run offline phragmen to guess stake allocation in the next era (actual allocation may vary depending on other nominators' decisions)</li><li>Using the stake allocation, we'll determine `net expected rewards` for each set and compare each validator set</li><li>Using the `net expected rewards` as the metric, we'll return the most rewarding set of 16 validators</li></ul>|
| 2. | Logic and implementation for risk level calculation to improve automated selection | This will be Phase 2: <ul><li>First, we'll develop a risk calculation mechanism to determine how risky each validator is. To do this, we'll take on-chain information like `self stake`, `total stake`, `number of nominators`, `history of slashes`, et al. as input and return a `risk level` as output</li><li>Using the `risk level`, we'll calculate cumulative risk for each set of 16 validators (similar to phase 1 for rewards).</li><li>Using `cumulative risk` and `net reward` for each set, we'll compare `risk/reward` ratio for each validator set, to return the most optimal set of validators (one with the lowest `risk/reward` ratio)</li></ul> |
| 3.  | Integration with PolkadotJS wallet| Finally, to make it easier for the users act on their staking decisions, we'll use PolkadotJS wallet to allow users to add and manage their stakes from within the platform itself. |

### Milestone 2 -- Implement Profiles for Validators and Council Members -- 1 month

In this milestone, we will create specific views for council members, similar to those we created for validators (screenshot attached below) to visualize relations between council members and voters.
![](https://i.imgur.com/SH8nhOh.png)

To allow validators and council members to market themselves to nominators and voters, we'll also extend these specific views to serve as "profiles". This will include on-chain data from the `identity module` along with some basic information like `number of nominators`, `amount of stake`, etc. and also off-chain information like `information about team members`, `vision of the organisation/company`, `bio`, et al.


| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Extension of specific views to serve as profiles for validators | <ul><li>Addition of support for identity module</li><li>Allowing page claims using PolkadotJS wallet</li><li>Allowing authenticated users to updated their profile information which shall include things like `bio`, `logo`, `theme color`, `team members section`, `vision of the company`, et al.</li></ul> |
| 2. | Creation of extended specific views for council members | Using the extended specific views for validators as a template, we'll develop extended specific views for council members, to display consolidated on-chain information and allow them to update off-chain information about themselves. |

### Milestone 3 -- Implement Proposal Threads and Wall feature -- 1 month

In this milestone, we will create threads for public, open and transparent discussions on proposals in a structured format. We'll also add a "wall" feature for validators to post updates related to their services and for council members to post their opinions about proposals.


| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Threads for proposals | We'll develop threads for proposals to encourage structured, open and transparent discourse. The threads will include <ul><li>On-chain information about the proposal like `time left`, `number of ayes with amount at stake`, `number of nays with amount at stake`, etc. </li><li>Comments section for users to have public discussion on why they are for, against or neutral about the proposal.</li></ul>This will make it easier for token holders to understand what might be the consequences of a proposal being passed and encourage mass participation in voting. | 
| 2. | "Wall" feature to post updates | We will further extend the "profiles" for validators and council members to allow authenticated users to post updates related to their services or their opinions on recent network events. This "wall" feature is inspired by 3box.io. |

## Additional Information :heavy_plus_sign:

**What work has been done so far?**

As reflected in the [Team Experience Section](https://www.notion.so/33dc8a620ded490d86c23d9c248bf0f1?v=38b2dfff302c4f279c8b830d79e25cbf&p=ea85de9367544c57b359b3e7bb055aee#Team%E2%80%99s-experience), we've developed a rewards prediction system to predict the payout for a nominator if they decide to stake on a given validator based on the stake amount they enter. We've also built the specific views for nominators and validators which shall be extended to serve as a "profile" page for validators and council members (possibly even nominators). We're currently working on an authentication system to allow users to login using PolkadotJS wallet. The progress so far is reflected on [https://polkanalytics.com](https://polkanalytics.com/)

**Are there are any teams who have already contributed (financially) to the project?**

As mentioned in the [Team Experience Section](https://www.notion.so/33dc8a620ded490d86c23d9c248bf0f1?v=38b2dfff302c4f279c8b830d79e25cbf&p=ea85de9367544c57b359b3e7bb055aee#Team%E2%80%99s-experience), the only financial contributions we've received for building the product so far are from PolkaDAO.

**Have you applied for other grants so far?**
No.

**Are there any other projects similar to yours? If so, how is your project different?**
Polkascan, PolkaStats and Polkadot JS UI are the three existing projects being actively used by the community, which are similar to ours.

Apart from these significant platforms, there exists [commonwealth.im](http://commonwealth.im/) which is under development and not widely used at the time of writing this proposal, there's also [lunie.io](http://lunie.io/) which doesn't have support for Polkadot yet, but intends to add support for the same in the near future. Lastly, there's [Nomidot](https://github.com/paritytech/Nomidot), which is also still under development and so far, the plan is to add historical on chain data as opposed to our solution of automation of the process of selection of validators.

All of these platforms solve problems related to visibility of data, thereby:

1. enabling users to analyze that data
2. to gain insight on the current state of the network and it's participants
3. which then allows them to make decision

We intend to reduce the friction for making any decision (related to staking or governance) for the end users by abstracting details like analyzing the data and instead giving users the information that they want in the form of a result. In other words, instead of giving users the tools to solve a problem, we intend to solve the problem for them and simply give them the solution.

**The team's long-term plans and intentions with this project.**

In the long run, we intend to make the Polkadot ecosystem more accessible, to encourage mass adoption, by solving UX problems, to reduce friction for both existing and new users.
