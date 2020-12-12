## **Project Description**

This project serves as an extension to the previously proposed and accepted load balanced endpoints proposal in which we provided the ecosystem with a multi-cloud reference architecture to deploy globally distributed sets of load balanced API endpoints configurable with a custom CLI. 

This proposal is now focused on operating those publicly accessible endpoints to be used by the Polkadot community. It is being paired with a soon to be submitted development proposal aimed at optimizing query response times for these endpoints with a microservices approach.  To inform which methods are highest priority for optimization, we will take a data driven approach by analyzing log data from this proposal and focus efforts on the most popular / most computationally demanding queries.  With these two grants executed in parallel, we aim to not only provide the community with an Infura-like interface at feature parity, but also make it easy for new users with different levels of experience to easily deploy their own clusters and contribute new endpoints.  

## **Team members**

- Engineers: Richard Mah, Rob Cannon
- Project manager: Mitchell Krawiec-Thayer

## **Team Website**

[www.insightdatascience.com](http://www.insightdatascience.com/)

[www.insightconsensus.com](http://www.insightconsensus.com/)

[Insight-W3F Workspace](https://www.notion.so/insightx/Insight-W3F-Home-2709be23f5014084b4527443378041e5)

[Insight-W3F Task Management](https://www.notion.so/insightx/All-W3F-4718ab99f2bf47409cda71812e62e9fd)

## **Legal Structure**

All contributors work with Insight, an US-based company that has been supporting specialized engineers since 2012.

## **Team's experience**

**Richard Mah** 

Richard is a DevOps engineer at Insight whose recent projects in the blockchain domain include the development of advanced monitoring solutions for PoS validators, load-balanced endpoints, and a ledger ETL + analytics stack. He has deep experience in the intersection between advanced data analysis and high performance computing. During his PhD, he employed a wide variety of machine learning techniques to automate the analysis of clinical data with a microservices-based architecture on Kubernetes. Since then, he joined Insight and has been focusing on building automated deployments of various blockchain related infrastructure components.

[Github](https://github.com/shinyfoil)

**Rob Cannon**

Rob is Insight’s infrastructure architect who focuses primarily on blockchain infrastructure, DevOps tooling, and Infrastructure as Code. Like Richard, Rob has contributed to Polkadot tooling, and is technically knowledgeable about the W3F ecosystem and the infrastructure development roadmap. Prior to Insight, he worked in the oil and gas industry founding a data science startup and working for a major operator.

[Github](https://github.com/robc-io), [Medium](https://medium.com/@robcannonxyz)

**Mitchell Krawiec-Thayer**

Mitchell is Insight’s Head of Research for Developers in Residence, and is currently coordinating teams contributing open-source tooling and analyses for Polkadot, Zcash, Monero, Harmony, and ICON. Mitchell founded the Monero Archival Project in 2017 and has been working with blockchain data sources and analyses ever since. Specializations include blockchain data engineering, data products, empirical analysis, on & off-chain anomaly detection, and blockchain data visualization.

[GitHub](https://github.com/mitchellpkt/), [Twitter](https://twitter.com/Mitchellpkt0), [LinkedIn](https://www.linkedin.com/in/mitchellpkt/), [Medium](https://medium.com/@mitchellpkt)

## **Team Code Repos**

- [github.com/insight-w3f](https://github.com/insight-w3f)
    - Main GH Org
- [github.com/insight-w3f/terragrunt-polkadot](https://github.com/insight-w3f/terragrunt-polkadot)
    - Main reference architecture
- [github.com/insight-infrastructure](https://github.com/insight-infrastructure)
    - Parent GH Org
- [github.com/insight-infrastructure/tackle-box](https://github.com/insight-infrastructure/tackle-box)
    - Code generator / DSL used in architectures for deploying infrastructure

## **Team LinkedIn Profiles**

- Mitchell: [linkedin.com/in/mitchellpkt/](https://www.linkedin.com/in/mitchellpkt/)
- Rob: [linkedin.com/in/rob-cannon-21571317/](https://www.linkedin.com/in/rob-cannon-21571317/)
- Richard: [https://www.linkedin.com/in/richardmah/](https://www.linkedin.com/in/richardmah/)

## **Development Roadmap**

This project aims at operating the previously developed load balanced endpoints.  All the infrastructure is in place and is currently operating at api.kusama.polkfura.com (json-rpc + wss).  While the prior grant gave us most of the production level components, certain items will still need further tuning to allow for easy operations of large clusters at scale. We would then like to aggregate health metrics from across the system and make them publicly available via a status page to display uptime.

One of the primary goals of this period in the grant is to gather user behavior to understand which queries need optimization. While the prior grant gave us a log collection stack (ELK), further improvements need to be made to support usage statistics. We intend on building those workflows to make analysis simple for benchmarking improvements.

We will also develop and operate a variety of quick sync chain data download locations on S3, CloudFront, and IPFS.  These locations will leverage the already developed "source of truth" node chain sync architecture as implemented by Infura for quick syncing of nodes.  Prior experience showed that sync times can be reduced by several orders of magnitude using this architecture that we believe would be beneficial to offer to the community. The intention would be to build an easily deployable quick sync tooling that can be shared around the community.

### Milestones and Deliverables

For a bottoms up breakdown of each milestone and deliverable, please consult our [public project management que](https://www.notion.so/insightx/All-W3F-4718ab99f2bf47409cda71812e62e9fd) for a time estimate of each task.

**Milestone 1: Public Load Balanced API Endpoints Deployment** 

**23 Days**

---

**Goals:**

- Cost effective operation of globally distributed deployment of API endpoints
- Integrate metrics and logs collected from operation for optimizing API endpoints

**Deliverables:**

***D1 - 5 Days***
- Extend API to include both Kusama and Polkadot
    - Routing based on subdomain (ie kusama.polkfura.com)

- Operation of V1 endpoint on AWS in 2 regions with geo-routing through cloudflare
    - Up to 6 API nodes per cluster
    - Cluster operation shall begin within days of starting the grant

***D2 - 13 Days***
- Centralized monitoring and logging integration
    - Aggregate logs and metrics from multi-region deployment

- Tuned metrics and logs populating Grafana and Kibana dashboards
    - Tune alarms on low blockheight and other important metrics
    - Elasticsearch query for latency on a per json-rpc request method basis + kibana dashboard for analysis

***D3 - 5 Days***
- Aggregated metrics from prometheus to feed high level status page endpoints
- Status page for high level healthchecks on each zone
    - Single VM deployment using [Cachet](https://github.com/CachetHQ/Cachet) - 1 Repo

**Milestone 2: Quick sync endpoint development** 

**8 Days**

---

**Goals:**

- Provide an endpoint for node operator to quickly sync nodes off of
- Make CDN production

**Deliverables:**

- Operation of "source of truth" node to send copies of the chain data for kusama and polkadot to persistent layers on a schedule
- "Requestor Pays" s3 bucket for downloading uncompressed blocks
- Content delivery network (cloudfront) for distributing compressed copies of the chain data
    - Alarms when for when download quotas are reached (eg each TB of download)
- IPFS content addresses with both compressed and uncompressed chain data

**Milestone 3: Long Term Operations** 

**3 Months Ops **

---

**Goals:**

- 99% up time for publicly accessible load balanced and quick sync endpoints
- Cost optimizations based on resource utilization

**Deliverables:**

- Operation of clusters for 3 months
- Report describing uptime, incidents, and operational changes
- Steady improvements with main reference architecture to maintain an exact mapping of what is running on the cloud and what is deployable in automation.

| Milestone | Deliverable |  Days |
|----|----|---:|
| M1 | D1 |  5 |
| M1 | D2 | 13 |
| M1 | D3 |  5 |
| M2 | D1 |  8 |
| M3 | D1 |  0 |


### **Long Term Plans**

---

- Decentralized API providers
- Microservices library to expose pre-indexed queries
- CLI tooling for deploying modular sets of self-healing infrastructure

## **Additional Information**

A centralized API endpoint provider like Infura presents a variety of risks to the ecosystem that can only be averted by taking a decentralized approach.  While this grant will provide a centralized API endpoint, our approach is fully open source such that anyone can run their own endpoints with the same capabilities.

While our main goal with building the v2 architecture is to optimize query response time, many opportunities arise from building a robust pattern that can easily be extended to be inclusive of additional endpoints. While it would be impossible to build all the optimizations and additional endpoints ourselves, we hope to lay the ground work such that other groups / Insight fellows can expand on it to deliver additional features to the ecosystem.

CLI's are useful for making the node deployments simple to new users but can become quite opinionated when building in how optionality is expressed.  To make things customizable and configurable, we have built [tackle-box](https://github.com/insight-infrastructure/tackle-box), a declarative CLI with loops and conditionals, that we will be supporting in the long term.  It is an upstream fork of [cookiecutter](https://github.com/cookiecutter/cookiecutter), the worlds most popular code templating tool. We hope to make building customizable parachains one-click and allow for quick rendering of common code templates and best practices starter packages. For node operation, we based the CLI for our [reference architecture](https://github.com/insight-w3f/terragrunt-polkadot) on this tool and will be streamlining its patterns over time.

Operational costs were calculated on a run rate basis. If use of the endpoints becomes high and need to scale to reach demand beyond the expected run rate, a report will be generated to the foundation accounting for the increased traffic and an assessment can be made at that time.
