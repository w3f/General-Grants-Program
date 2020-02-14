## **Project Description**

This project focuses on building a common set of infrastructure as code modules used to deploy autoscaling sentry layers and public nodes for DoS protection and load balanced endpoints. The project aims to integrate into the existing polkadot-secure-validator architecture and serve as drop in replacements for the single node / multi-provider public node deployments with secure tunnels to the validator node on a private network. Code will use the existing DevOps patterns already adopted by the Web3 Foundation and extend them with additional e2e testing, automation, and benchmarking. The proposal will lay the ground work for more advanced load balanced API endpoints and caching solutions by proving out simpler patterns for serving archival requests.

## **Team members**

- Lead Engineer: Rob Cannon
- Principal Investigator: Mitchell Krawiec-Thayer, Ph.D.

## **Team Website**

- [www.insightdatascience.com](http://www.insightdatascience.com/)
- [www.insightconsensus.com](http://www.insightconsensus.com/)

## **Legal Structure**

Rob and Mitchell are employees of Insight, an existing US-based company that has been supporting specialized engineers since 2012.

## **Team's experience**

**Rob Cannon**

DevOps developer in residence at Insight who focuses primarily on blockchain infrastructure. Focussing primarily on building automated deployments of validator nodes for the ICON blockchain, he is now looking to extend these patterns into other blockchains. Prior to Insight, he worked in the oil and gas industry founding a data science startup and working for a major operator.

[Github](https://github.com/robc-io), [Medium](https://medium.com/@robcannonxyz)

**Mitchell Krawiec-Thayer**

Decentralized Consensus Lead at Insight, mentor for Insight Residents. Have been doing privacy research and protocol SecEng for Monero Research Lab since 2017, and founded Noncesense Research Lab. Specializes in private protocol design, anti-heuristic engineering, empirical analysis, on & off-chain anomaly detection, metadata archive design & analysis.

[GitHub](https://github.com/mitchellpkt/), [Twitter](https://twitter.com/Mitchellpkt0), [LinkedIn](https://www.linkedin.com/in/mitchellpkt/), [Medium](https://medium.com/@mitchellpkt)

## Team Code Repos

- [https://github.com/insight-infrastructure/terragrunt-polkadot](https://github.com/insight-infrastructure/terragrunt-polkadot)
- [https://github.com/insight-infrastructure/terraform-polkadot-aws-sentry-node](https://github.com/insight-infrastructure/polkadot-terragrunt)

## Team LinkedIn Profiles

- [https://www.linkedin.com/in/mitchellpkt/](https://www.linkedin.com/in/mitchellpkt/)
- [https://www.linkedin.com/in/rob-cannon-21571317/](https://www.linkedin.com/in/rob-cannon-21571317/)

## Development Roadmap

The basics for building the necessary infrastructure with a packer, ansible, and terraform based workflow are in place. Minimal templating is performed over configuration files with actions triggered off a single Makefile to deploy the stack. 

The real challenge with this proposal is to minimize the sync time needed to scale out public facing nodes which requires either pre-synced images or downloading the DB directly from a peer.  Pre-syncing is done from taking images off a "source of truth" node and keeping a CDN updated with snapshots that can be pulled down with the latest blocks.  Downloading the DB from a peer is the existing W3F approach and is as simple as scaling out the application from scratch.  While API vendors like Infura favor the pre-syncing approach, both options have their own benefits and will be explored through a series of benchmarks.  

**Milestone 1: IaC Modules**

[1-2 months]

---

- Build source of truth nodes and autoscaling groups on AWS, Azure, and GCP with terraform
- Build integration testing with terratest over all providers 
- Build agent to trigger periodic snapshots being taken to object store
- Build logging and monitoring exporters and service discovery agents

**Milestone 2: Benchmarking**

[1 Month] 

---

- Build load balancer and reverse proxy layer 
- Integrate with existing secure validator CLI and/or build own CLI tool to support multiple node configurations
- Build testbench for various types of benchmarking to optimize scaling policies and source of truth node snapshot increments
- Build helm chart distribution 

### Long Term Plans

---

- Comprehensive library of IaC modules that can be used and repurposed in a variety of contexts
- CLI tooling and API endpoints for deploying modular sets of self-healing infrastructure
- Caching layers and ETL pipelines to build indexed data endpoints to mimic Infura functionality

## Additional Information

While it is important for decentralized network operations to avoid homogeneity, certain components that have a low impact on the diversity of the network are prime targets for standardization. We feel that as the ecosystem grows, having a battle-tested set of modules will prove to be very valuable for best practice to be shared around the community.

The methodology of pre-syncing images off a "source of truth" node was inspired by Infura's architectural pattern as within the context of ethereum, it is unreasonable to scale nodes with autoscaling groups when the nodes themselves take many hours to sync from scratch. As the polkadot ecosystem grows and hence the size of the chain data, it will be critical for operators to easily adopt best practices so that they are ready to scale out their infrastructure as the increase in API requests grows.