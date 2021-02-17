# General Grants Program <!-- omit in toc -->

<p align="center">
  <img src="./src/General_Grants_Program.png" style="width:1300px";>
</p>

**:loudspeaker: Important:** The Web3 Foundation _General Grants_ Program focuses on technology grants which are meant to remain **private**, **paid out in fiat** or **larger than USD 30,000**. We usually ask teams to first consider applying via the [**Open Grants Program**](https://github.com/w3f/Open-Grants-Program), which supports grants of up to USD 30,000 and has **faster processing times**.

---

- [Introduction](#introduction)
  - [:clipboard: About](#clipboard-about)
  - [Licensing](#licensing)
  - [Documentation](#documentation)
- [:pencil: Process](#pencil-process)
- [:mailbox_with_mail: RFP Suggestion](#mailbox_with_mail-rfp-suggestion)
- [:bulb: Help](#bulb-help)
  - [Additional information](#additional-information)
  - [Real-time conversation](#real-time-conversation)
- [:rocket: Alternative Funding Sources](#rocket-alternative-funding-sources)
  - [Treasury](#treasury)
  - [Open Grants Program](#open-grants-program)
  - [Other Grant Programs](#other-grant-programs)
- [:information_source: License](#information_source-license)

## Introduction

As part of our commitment to promoting the Web3 ecosystem, we offer a comprehensive grants program focused on funding software development and research efforts related to Polkadot, Kusama and Substrate. For more information about the Web3 Foundation please visit the [About page](https://web3.foundation/about/) of our website.

### :clipboard: About

Technical grants are intended to fund **Polkadot**, **Kusama** and **Substrate** specific **_research_** and **_software development_** projects.

The maximum funding for technical grants is $100,000 per project. We ask teams to first consider applying via the [Open Grants Program](https://github.com/w3f/Open-Grants-Program), which supports grants of up to $30,000 and has faster processing times. If your project has a scope larger than that, we encourage you to split your work into multiple stages of $30,000 or less.

For more specific information on our funding priorities, please view the [Polkadot Stack](./grants/polkadot_stack.md) and take a look at the [accepted grant applications](https://github.com/w3f/Web3-collaboration/blob/master/grants/accepted_grant_applications.md). Additionally the builders program [feedback board](https://feedback.parity.io/) may contain some useful ideas for grant projects.

**Only apply via the General Grants Program if:**

- You seek funding of $30,000+ and your work cannot be split into smaller milestones
- You want your team/project information to remain private
- You can only accept fiat payments

Furthermore, teams shouldn’t seek to cover 100% of their early-stage funding via W3F Grants alone.

Any project requesting **$30k or less** might receive fast approval. Projects between **$30k and 100k** will likely face longer wait times.

Teams can apply for grants more than once, but they need to complete the previous project (as described in their application) before receiving additional funds.

### Licensing

In order to successfully receive grant funding for your application it is necessary for the project to contain **open source** code. We prefer Apache 2.0 but the GNU GPL v3 license is also acceptable. Furthermore, only work directly relating to open source code will be funded.

### Documentation

To ensure ease-of-use, we require all projects to create documentation that explains how their project works. At a minimum, _written_ documentation is required for funding. _Tutorials_ or _videos_ are also helpful for new users to understand how to use your product.

## :pencil: Process

If you are considering applying for a grant, please follow the process below.
  
1. **Determine the scope of your project**

   - Review the [Polkadot Stack](./grants/polkadot_stack.md) and take a look at the [accepted grant applications](https://github.com/w3f/Web3-collaboration/blob/master/grants/accepted_grant_applications.md). If your idea isn&rsquo;t listed, but you think it&rsquo;s worth supporting, you can send us an [email](mailto:grants@web3.foundation) and tell us about it.
   - Ensure the scope of your project falls within our [guidelines](#clipboard-about).

   Once you determine that your project falls within the [Polkadot Stack](./grants/polkadot_stack.md) and corresponds to the guidelines above, proceed to the next step.

2. **Application**

    We strongly recommend working off of the [technical grant template](https://github.com/w3f/Web3-collaboration/blob/master/grants/grant_application_template.md). It gives an indication of what a good roadmap should look like and outlines the criteria and information we look for in an application.

    1. Fill out the Google form for your grant application by clicking the following link: [:arrow_right: Apply here](https://docs.google.com/forms/d/e/1FAIpQLSfMfjiRmDQDRk-4OhNASM6BAKii7rz_B1jWtbCPkUh6N7M2ww/viewform)

        Partially public applications that limit financial information (e.g. funding amount requested) to the Google form are preferred. However, teams are free to make fully public applications as well as fully private applications.

        Teams that chose to make a fully private application are done once this form is complete. Teams that have chosen to make a fully or partially public application should proceed to the next step.

    2. Fully or partially public applications should be made via a pull request to this repo by following the steps below.
       1. [Fork](https://github.com/w3f/General-Grants-Program/fork) this repository.
       2. In the newly created fork, **create a copy** of the [technical grant template](https://github.com/w3f/Web3-collaboration/blob/master/grants/grant_application_template.md).
           - In the few cases where the application is a response to a specific RFP (Request For Proposal), the application goes into the [`rfps`](https://github.com/w3f/Web3-collaboration/tree/master/grants/rfps) folder.
           - All other applications go into the [`speculative`](https://github.com/w3f/Web3-collaboration/tree/master/grants/speculative) folder.
       3. Rename the file after your project (`project_name.md`).
       4. Fill out the template with the details of your project. The more information you provide, the faster the review process will be.
       5. Once you have completed the application, submit the file (and _only_ the file) as a pull request (click on "Create new pull request" under the appropriate branch of your fork).
       6. The body of the pull request form will show a template that requests an abstract of the project and the completion of a checklist. Please complete these as appropriate. Take care to include all necessary information. The **pull request template** can be viewed [here](https://github.com/w3f/Web3-collaboration/blob/master/.github/PULL_REQUEST_TEMPLATE.md).

3. **Application Review**
   - The W3F will review the application, determine if more information is required and potentially schedule a call with the team.
   - Parity Technologies may assist in the review of some applications.

4. **Decision**
   - The W3F will notify the applicants of whether their proposal has been accepted or not.
   - When a proposal is successful, further communication will be required to determine specific details around timelines and payment schedules.

5. **Follow up**
   - Once work on the project has started, the W3F will want to have follow-up conversations to see how the project is progressing.
   - To help speed up the milestone evaluation process, take a look at the [Milestone Deliverables Guidelines](./grants/milestone-deliverables-guidelines.md)

## :mailbox_with_mail: RFP Suggestion

If you think that we should support the development of certain tools or projects (related to **Polkadot**, **Kusama** and/or **Substrate**) that aren't in the [Polkadot Stack](./grants/polkadot_stack.md), feel free to submit an RFP suggestion using the process described below. We are particularly interested in supporting projects that could be leveraged by other builders in our ecosystem. We will review your proposal and, if we believe it’s useful, we will create an RFP based on your idea and try to find teams to work on it.

**Instructions for submitting an RFP suggestion:**

1. [Fork](https://github.com/w3f/General-Grants-Program/fork) this repository.
2. In the newly created fork, **create a copy** of the [suggestion template](./rfp-proposal/suggestion-template.md).
3. Rename the file after your idea (`project_name.md`).
4. Fill out the template with the details of your project.
5. Once you have completed the application, submit the file (and _only_ the file) as a pull request (click on "Create new pull request" under the appropriate branch of your fork).

## :bulb: Help

### Additional information

| <img src="src/web.png?s=50" width="50"> | <img src="src/twitter.png?s=50" width="50"> | <img src="src/medium.png?s=50" width="50"> | <img src="src/like.png?s=50" width="50"> | <img src="src/reddit.png?s=50" width="50"> | <img src="src/youtube-play.png?s=50" width="50"> |
| :-: | :-: | :-: | :-: | :-: | :-: |
| [W3F Website](https://web3.foundation) | [W3F Twitter](https://twitter.com/web3foundation) | [W3F Medium](https://medium.com/web3foundation) | [Polkadot Wiki](https://wiki.polkadot.network/en/) | [Web 3.0 Reddit](https://www.reddit.com/r/web3) | [W3F YouTube](https://www.youtube.com/channel/UClnw_bcNg4CAzF772qEtq4g) |

### Real-time conversation

We have Riot channels for real-time discussions on Web3 and Polkadot. Join the conversations.

- [Web3 Foundation](https://riot.im/app/#/room/#web3foundation:matrix.org)
- [Polkadot Watercooler](https://riot.im/app/#/room/#polkadot-watercooler:matrix.org)

## :rocket: Alternative Funding Sources

### Treasury

The treasury is a pot of on-chain funds collected through transaction fees, slashing, staking inefficiencies, etc. The funds held in the treasury can be spent by making a spending proposal. [Polkadot](https://polkadot.network/) as well as [Kusama](https://kusama.network/) offer everyone the opportunity to apply for funding via the treasury. See:

- [Treasury Wiki](https://wiki.polkadot.network/docs/en/learn-treasury#docsNav)
- [Kusama Treasury Guide](https://docs.google.com/document/d/1p3UQUjph5t8TVaWnTkfrI5mE-BABnM9Xvtuhdlhl6JE/edit)
- [Polkadot Treasury Guide](https://docs.google.com/document/d/1IZykdp2cyQavcRyZd_dgNj5DcgxgZR6kAqGdcNARu1w/edit)

### Open Grants Program

For technology grants up to **$30k**, which are tracked **transparently** on GitHub and disbursed in **Bitcoin or DAI**, see our [Open Grants Program](https://github.com/w3f/Open-Grants-Program).

### Other Grant Programs

Below is list of other grant programs in the Polkadot/Substrate ecosystem:

- [Darwinia Grants Program](https://docs.darwinia.network/docs/en/dev-bounty#grant-program)
- [Moonbeam Grants Program](https://moonbeam.network/community/grants/)
- [Edgeware Grants and Bounties](https://github.com/edgeware-builders/construction-projects)


## :information_source: License

[Apache License 2.0](https://github.com/w3f/Web3-collaboration/blob/Noc2-patch-3/LICENSE) © Web3 Foundation
