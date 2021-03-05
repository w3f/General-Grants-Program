# General Grants Program <!-- omit in toc -->

<p align="center">
  <img src="./src/General_Grants_Program.png" style="width:1300px";>
</p>

**:loudspeaker: Important:** The Web3 Foundation General Grants Program focuses on technology grants which are meant to remain **private**, **paid out in fiat** or **larger than USD 30,000**. We ask teams to first consider applying via the [**Open Grants Program**](https://github.com/w3f/Open-Grants-Program), which supports grants of up to USD 30,000 and has **faster processing times**. If your project has a scope larger than that, we encourage you to split your work into multiple stages of USD 30,000 or less.

---

- [:wave: Introduction](#wave-introduction)
  - [About](#about)
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

## :wave: Introduction

As part of our commitment to promoting the Web3 ecosystem, we offer a comprehensive grants program focused on funding software development and research efforts related to **Polkadot, Kusama and Substrate**. For more information about the Web3 Foundation please visit the [About page](https://web3.foundation/about/) of our website.

**Only apply via the General Grants Program if:**

- You seek funding of $30,000+ and your work cannot be split into smaller milestones
- You want your team/project information to remain private
- You can only accept fiat payments

Otherwise, you should apply to the [Open Grants Program](https://github.com/w3f/Open-Grants-Program).

Furthermore, teams shouldn’t seek to cover 100% of their early-stage funding via W3F Grants alone.

Any project requesting **$30k or less** might receive fast approval. Projects between **$30k and 100k** will likely face longer wait times.

Teams can apply for grants more than once, but they need to complete the previous project (as described in their application) before receiving additional funds.

### Guidelines

Anyone is welcome to apply for a grant. Projects funded through our programs are broad in scope, but our focus lies on strong technical projects that add value to the ecosystem.

Generally, your project will have better chances to get accepted if:
- It presents a **well-researched** or tested concept, for which ideally you are able to show some prior work.
- You can demonstrate that the project will be **maintained** after completion of the grant, be it through an obvious commitment to the technology from your side, additional funding sources or an existing business model.
- Your team has **proven experience** with the relevant languages and technologies and/or a strong technical background. We ask you to provide the GitHub profiles of all team members as part of your application and will examine these for past activity and code quality. Naturally, you can also link to projects on other platforms.
- Your application is **rich in technical details** and well-defined.
- You can clearly present how your project stands out among competitors or implements technology that doesn't exist in the ecosystem yet.

Additionally, it must fulfill the following requirements:
- All code produced as part of a grant must be **open-sourced**, and it must also not rely on closed-source software for full funcionality. We prefer Apache 2.0 but the GNU GPL v3 license or Unlicense are also acceptable. 
- We do not award grants to teams that have successfully conducted a token sale or otherwise launched their own token unless there is a clear reason for it. If this applies to you, make sure to clearly present your case and explain why you cannot self-fund this project in your application.
- Lastly, we do not provide funding for gambling-related projects.

[Request For Proposals](./rfps) (RFPs) represent ideas for projects that we would like to see implemented. You are welcome to submit a proposal for one of them.

A more general list of areas in the Web 3.0 Technology Stack that demand particular development can be found [here](https://github.com/w3f/General-Grants-Program/blob/master/grants/polkadot_stack.md), as well as a list of previously accepted projects [here](https://github.com/w3f/Web3-collaboration/blob/master/grants/accepted_grant_applications.md). Additionally, the builders program [feedback board](https://feedback.parity.io/) may contain some useful ideas for grant projects.

If you can't find your idea or don't know how it fits into the existing Technology Stack but you think it's worth supporting, you can send us an [email](mailto:grants@web3.foundation) and tell us about it.

Additionally to the information provided on your application, note that your project will need to comply with our [Guidelines for Milestone Deliverables](./grants/milestone-deliverables-guidelines.md). In particular, we require all projects to create documentation that explains how their project works. At a minimum, _written_ documentation is required for funding. _Tutorials_ or _videos_ are also helpful for new users to understand how to use your product.

## :pencil: Process  

1. **Application**

     We strongly recommend working off of the [grant application template](./master/grants/grant_application_template.md), which gives an indication of what a good roadmap should look like and outlines the criteria and information we look for in an application. 

    1. Fill out the General Grants application form [:arrow_right: here](https://docs.google.com/forms/d/e/1FAIpQLSfMfjiRmDQDRk-4OhNASM6BAKii7rz_B1jWtbCPkUh6N7M2ww/viewform).

        Partially public applications that limit financial information (i.e. funding amount requested) to the Google form are preferred. However, teams are free to make fully public applications as well as fully private applications.

        Teams that chose to make a fully private application are done once this form is complete.

    2. Fully or partially public applications should be completed via a pull request to this repo by following the steps below.
       1. [Fork](https://github.com/w3f/General-Grants-Program/fork) this repository.
       2. In the newly created fork, create a **copy** of the application template ([`grants/grant_application_template.md`](./grants/grant_application_template.md)). If you're using the GitHub web interface, make sure you create a new file and copy the content of the template inside the new file. _Don't change the template file directly!_
           - In the few cases where the application is a response to a specific RFP (Request For Proposal), the application goes into the [`rfps`](./rfps) folder.
           - All other applications go into the [`speculative`](./speculative) folder.
       3. Rename the file after your project (`project_name.md`).
       4. Fill out the template with the details of your project. The more information you provide, the faster the review process will be.
       5. Once you have completed the application, click on "Create new pull request". The pull request should only contain _one new file_ — the markdown file you created from the template.
       6. You will see a template that requests an abstract of the project and the completion of a checklist. Please complete these as appropriate. The **pull request template** can be viewed [here](./.github/PULL_REQUEST_TEMPLATE.md).

2. **Application Review**
   - The W3F will review the application, determine if more information is required and potentially schedule a call with the team.
   - Parity Technologies may assist in the review of some applications.

3. **Decision**
   - The W3F will notify the applicants of whether their proposal has been accepted or not.
   - When a proposal is successful, further communication will be required to determine specific details around timelines and payment schedules.

4. **Follow-up**
   - Once work on the project has started, the Web3 Foundation will want to have follow-up conversations to see how the project is progressing.
   - To help speed up the milestone evaluation process, take a look at the [Guidelines for Milestone Deliverables](./grants/milestone-deliverables-guidelines.md)

## :mailbox_with_mail: RFP Suggestion

If you think that we should support the development of certain tools or projects (related to **Polkadot**, **Kusama** and/or **Substrate**) that aren't in the [Polkadot Stack](./grants/polkadot_stack.md), feel free to submit an RFP suggestion using the process described below. We are particularly interested in supporting projects that could be leveraged by other builders in our ecosystem. We will review your proposal and, if we believe it’s useful, we will create an RFP based on your idea and try to find teams to work on it.

**Instructions for submitting an RFP suggestion:**

1. [Fork](https://github.com/w3f/General-Grants-Program/fork) this repository.
2. In the newly created fork, **create a copy** of the suggestion template ([`rfp-proposal/suggestion-template.md`](./rfp-proposal/suggestion-template.md)).
3. Rename the file after your idea (`project_name.md`).
4. Fill out the template with the details of your project idea.
5. Once you have completed the application, click on "Create new pull request". The pull request should only contain _one new file_ — the markdown file you created from the template.

## :bulb: Help

### Additional information

| <img src="src/web.png?s=50" width="50"> | <img src="src/twitter.png?s=50" width="50"> | <img src="src/medium.png?s=50" width="50"> | <img src="src/like.png?s=50" width="50"> | <img src="src/reddit.png?s=50" width="50"> | <img src="src/youtube-play.png?s=50" width="50"> |
| :-: | :-: | :-: | :-: | :-: | :-: |
| [W3F Website](https://web3.foundation) | [W3F Twitter](https://twitter.com/web3foundation) | [W3F Medium](https://medium.com/web3foundation) | [Polkadot Wiki](https://wiki.polkadot.network/en/) | [Web 3.0 Reddit](https://www.reddit.com/r/web3) | [W3F YouTube](https://www.youtube.com/channel/UClnw_bcNg4CAzF772qEtq4g) |

### Real-time conversation

We have Element channels for real-time discussions on Web3 and Polkadot. Join the conversation.

- [Web3 Foundation](https://app.element.io/#/room/#w3f:matrix.org)
- [Polkadot Watercooler](https://app.element.io/#/room/#polkadot-watercooler:web3.foundation)

## :rocket: Alternative Funding Sources

### Treasury

The treasury is a pot of on-chain funds collected through transaction fees, slashing, staking inefficiencies, etc. The funds held in the treasury can be spent on spending proposals. Both [Polkadot](https://polkadot.network/) and [Kusama](https://kusama.network/) offer everyone the opportunity to apply for funding via the treasury. See:

- [Treasury Wiki](https://wiki.polkadot.network/docs/en/learn-treasury)
- [Polkadot Treasury Guide](https://docs.google.com/document/d/1IZykdp2cyQavcRyZd_dgNj5DcgxgZR6kAqGdcNARu1w)
- [Kusama Treasury Guide](https://docs.google.com/document/d/1p3UQUjph5t8TVaWnTkfrI5mE-BABnM9Xvtuhdlhl6JE)

### Open Grants Program

Our [Open Grants Program](https://github.com/w3f/Open-Grants-Program) is suited for technology grants of up to USD 30,000, which are tracked transparently on GitHub and disbursed in Bitcoin or DAI.

### Other Grant Programs

Below is a list of other grant programs in the Polkadot/Substrate ecosystem:

- [Darwinia Grants Program](https://docs.darwinia.network/docs/en/dev-bounty#grant-program)
- [Moonbeam Grants Program](https://moonbeam.network/community/grants/)
- [Edgeware Grants and Bounties](https://github.com/edgeware-builders/construction-projects)

## :information_source: License <!-- omit in toc -->

[Apache License 2.0](./LICENSE) © Web3 Foundation
