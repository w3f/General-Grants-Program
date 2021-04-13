# General Grants Program <!-- omit in toc -->

<p align="center">
  <img src="../src/General_Grants_Program.png" style="width:1300px";>
</p>

**:loudspeaker: Important:** The Web3 Foundation _General Grants_ Program focuses on technology grants which teams wish to keep **private**, need to be **paid out in fiat** or are **larger than $30,000**.

We ask teams to first consider applying via the [:arrow_right: _Open Grants_ Program](https://github.com/w3f/Open-Grants-Program), which has **faster processing times** and provides grants of up to $30,000 for initial applications and $100,000 for follow-up ones. Please consider applying via Open Grants no matter the scope of your project.

---

- [:wave: Introduction](#wave-introduction)
  - [Guidelines](#guidelines)
  - [Project ideas](#project-ideas)
  - [Support](#support)
- [:pencil: Process](#pencil-process)
- [:mailbox_with_mail: Request for Proposals (RFP) Suggestions](#mailbox_with_mail-request-for-proposals-rfp-suggestions)
- [:bulb: Help](#bulb-help)
  - [Additional information](#additional-information)
  - [Real-time conversation](#real-time-conversation)
- [:rocket: Alternative Funding Sources](#rocket-alternative-funding-sources)
  - [Treasury](#treasury)
  - [Open Grants Program](#open-grants-program)
  - [Other Grant Programs](#other-grant-programs)

## :wave: Introduction

As part of our commitment to promoting the Web3 ecosystem, we offer comprehensive grants programs focused on funding software development and research efforts related to **Polkadot, Kusama and Substrate**. For more information about the Web3 Foundation, please visit the [About page](https://web3.foundation/about/) on our website.

**Only apply via the General Grants Program if:**

- you seek funding of $30,000+ and your work cannot be split into smaller milestones,
- you want your team/project information to remain private, or
- you can only accept fiat payments.

The maximum amount of funding per application is limited to US $100,000. Projects requesting **$30,000 or less** are likely to receive faster approval, whereas larger projects necessitate closer evaluation and may face longer waiting times as a consequence.

Teams can apply for grants more than once, but they need to successfully complete the previous project before receiving additional funds. Furthermore, teams shouldn’t seek to cover 100% of their early-stage funding via W3F Grants alone.

### Guidelines

Anyone is welcome to apply for a grant. Projects funded through our programs are broad in scope, but our focus lies on strong technical projects that add value to the ecosystem.

Generally, your project will have better chances to get accepted if:

- It presents a **well-researched** or tested concept, for which ideally you are able to show some prior work.
- You can demonstrate that the project will be **maintained** after completion of the grant, be it through an obvious commitment to the technology from your side, additional funding sources or an existing business model.
- Your team has **proven experience** with the relevant languages and technologies and/or a strong technical background. We ask you to provide the GitHub profiles of all team members as part of your application and will examine these for past activity and code quality. Naturally, you can also link to projects on other platforms.
- Your application is **rich in technical details** and well-defined.
- You can clearly present how your project stands out among competitors or implements technology that doesn't exist in the ecosystem yet.

Additionally, it must fulfill the following requirements:

- All code produced as part of a grant must be **open-sourced**, and it must also not rely on closed-source software for full funcionality. We prefer Apache 2.0, but GPLv3 or Unlicense are also acceptable.
- We do not award grants for projects that have been the object of a successful token sale.
- Lastly, we do not fund projects that actively encourage gambling, illicit trade, money laundering or criminal activities in general.

In addition to the information provided on your application, note that your project will need to comply with our [Guidelines for Milestone Deliverables](grants/milestone-deliverables-guidelines.md). In particular, we require all projects to create documentation that explains how their project works. At a minimum, _written_ documentation is required for funding. Tutorials or videos are also helpful for new users to understand how to use your product. If your team's background is purely technical, consider hiring a freelance or part-time technical writer as part of the grant.

### Project ideas

[Requests For Proposals](rfps) (RFPs) represent ideas for projects that we would like to see implemented. Several teams may apply for the same RFP, out of which one or more strong applications will be selected. So even if another team has already applied to implement a certain RFP, we encourage you to still apply if you are interested.

An overview of existing projects in the Web 3.0 Technology Stack along with broad project ideas we would potentially be interested in funding can be found [here](grants/polkadot_stack.md), as well as a list of previously accepted applications [here](grants/accepted_grant_applications.md). Additionally, the Substrate Builders [feedback board](https://feedback.parity.io/) may contain some useful ideas for grant projects.

If you have a **good concept of the technical challenges** that your idea entails and would like feedback before applying, you can send us an [email](mailto:grants@web3.foundation) and tell us about it.

### Support

The scope of our Grants Programs consists of funding and feedback on delivered milestones. This means that we do not provide hands-on support as part of a grant, but if you face specific issues during development, we will do our best and try to direct you to the correct resources. If this sounds like something you would like however, you may also want to apply to Parity's [Substrate Builders Program](https://www.substrate.io/builders-program/), which provides hands-on technical, ecosystem and strategical long-term support and access to extensive resources.

## :pencil: Process  

1. **Application**

    We strongly recommend working off of the [grant application template](grants/grant_application_template.md), which gives an indication of what a good roadmap should look like and outlines the criteria and information we look for in an application.

    Partially public applications that limit financial information (i.e. the requested funding amount) to the application form in step `ii.` are preferred. However, teams are free to make fully public applications as well as fully private applications.

    1. **Fully or partially public** applications should be initiated with a pull request to this repository by following the steps below. Teams who intend to make a fully private application can skip this step.
        1. [Fork](https://github.com/w3f/General-Grants-Program/fork) this repository.
        2. In the newly created fork, create a copy of the application template ([`grants/grant_application_template.md`](grants/grant_application_template.md)). If you're using the GitHub web interface, you will need to create a new file and copy the [contents](https://raw.githubusercontent.com/w3f/General-Grants-Program/master/grants/grant_application_template.md) of the template inside the new one. Make sure you **do not modify the template file directly**. Name the new file after your project: `project_name.md`.
            - In the few cases where your application is in response to a specific RFP, you should create the file inside the [`rfp-responses`](grants/rfp-responses) folder.
            - All other applications go into the [`speculative`](grants/speculative) folder.
        3. Fill out the template with the details of your project. The more information you provide, the faster the review.
        4. Once you're done, create a pull request. The pull request should only contain _one new file_—the Markdown file you created from the template.
        5. You will see a comment [template](.github/PULL_REQUEST_TEMPLATE.md) that requests an abstract of the project and provides a checklist. Please complete these as appropriate.
    2. Fill out the General Grants application form [:arrow_right: here](https://docs.google.com/forms/d/e/1FAIpQLSfMfjiRmDQDRk-4OhNASM6BAKii7rz_B1jWtbCPkUh6N7M2ww/viewform).

2. **Application Review**
   - The Web3 Foundation will review the application, determine if more information is required and potentially schedule a call with the team.
   - Parity Technologies may assist in the review of some applications.

3. **Decision**
   - Applicants will be notified via email of whether their proposal has been accepted or not.
   - If a proposal is successful, further communication will be required to determine specific details around timelines and payment schedules.

4. **Follow-up**
   - Once work on the project has started, the Web3 Foundation will want to have follow-up conversations to see how the project is progressing.
   - To help speed up the milestone evaluation process, take a look at the [Guidelines for Milestone Deliverables](grants/milestone-deliverables-guidelines.md). Milestones will be evaluated based on this document and the details provided in your application.

## :mailbox_with_mail: Request for Proposals (RFP) Suggestions

If you think that we should support the development of certain tools or projects (related to **Polkadot, Kusama or Substrate**) that aren't in the Polkadot/Kusama [tech stack](grants/polkadot_stack.md), feel free to submit an RFP suggestion using the process described below. We are particularly interested in supporting projects that could be leveraged by other builders in our ecosystem. We will review your proposal and, if we believe it’s useful, will create an RFP based on your idea and try to find teams to work on it.

**Instructions for submitting an RFP suggestion:**

1. [Fork](https://github.com/w3f/General-Grants-Program/fork) this repository.
2. In the newly created fork, create a copy of the suggestion template ([`rfps/suggestion-template.md`](rfps/suggestion-template.md)) inside the [`rfps`](rfps) folder. Make sure you create a new file and copy the [contents](https://raw.githubusercontent.com/w3f/General-Grants-Program/master/rfps/suggestion-template.md) of the template inside the new one, and _do not modify the template file directly._
3. Name the file after your idea: `project_name.md`.
4. Fill out the template with the project details. Please include as many details as possible.
5. Once you're done, click on "Create new pull request". The pull request should only contain _one new file_—the Markdown file you created from the template.
6. You will see the same template as for creating an application. Plase replace it with [this one](.github/PULL_REQUEST_TEMPLATE/rfp_pr_template.md).

If you have an idea for a project but lack the technical background to create a detailed outline, you can open an [issue](https://github.com/w3f/General-Grants-Program/issues/new) instead or add it to the [tech stack](grants/polkadot_stack.md) as a potentially interesting project. However, your idea will have better chances of being implemented if you can provide a project outline such that it can be picked up straight away by a capable team.

## :bulb: Help

### Additional information

| <img src="../src/web.png?s=50" width="50"> | <img src="../src/twitter.png?s=50" width="50"> | <img src="../src/medium.png?s=50" width="50"> | <img src="../src/like.png?s=50" width="50"> | <img src="../src/reddit.png?s=50" width="50"> | <img src="../src/youtube-play.png?s=50" width="50"> |
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

Our [Open Grants Program](https://github.com/w3f/Open-Grants-Program) is suited for technology grants of up to $30,000, which are tracked transparently on GitHub and disbursed in Bitcoin or DAI.

### Other Grant Programs

Below is a list of other grant programs in the Polkadot/Substrate ecosystem:

- [Darwinia Grants Program](https://docs.darwinia.network/docs/en/dev-bounty#grant-program)
- [Moonbeam Grants Program](https://moonbeam.network/community/grants/)
- [Edgeware Grants and Bounties](https://github.com/edgeware-builders/construction-projects)

## :information_source: License <!-- omit in toc -->

[Apache License 2.0](LICENSE) © Web3 Foundation.
