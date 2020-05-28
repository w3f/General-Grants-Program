## **Project Description**

This project focuses on building a set of load balanced endpoints for
the Polkadot and Substrate chains. Specifically, we will be building a
common set of reusable modules that can be deployed on each cloud
provider. Development will initially focus on a VM-based architecture
for building autoscaling archival nodes but will transition to a cloud
native Kubernetes-based deployment with intelligent routing and
caching layers. We will then build templates whereby microservices can
be developed by Insight data engineering fellows in a repeatable
manner. The project will give users easy to use deployments for
hosting their own full nodes and evolve into a managed API service.
Code will use existing DevOps patterns already adopted by the Web3
Foundation and extend them with additional e2e testing, automation,
and benchmarking.

## **Team members**

- Engineers: Richard Mah, Rob Cannon
- Principal Investigator: Mitchell Krawiec-Thayer, Ph.D.

## **Team Website**

- [www.insightdatascience.com](http://www.insightdatascience.com/)
- [www.insightconsensus.com](http://www.insightconsensus.com/)

## **Legal Structure**

Rob and Mitchell are employees of Insight, an existing US-based
company that has been supporting specialized engineers since 2012.
Richard will be brought on as a contractor focusing on this grant for
the duration.

## **Team's experience**

### **Rob Cannon**

DevOps developer in residence at Insight who focuses primarily on
blockchain infrastructure. Focussing primarily on building automated
deployments of validator nodes for the ICON blockchain, he is now
looking to extend these patterns into other blockchains. Prior to
Insight, he worked in the oil and gas industry founding a data science
startup and working for a major operator.

[Github](https://github.com/robc-io),
[Medium](https://medium.com/@robcannonxyz),
[Linkedin](https://www.linkedin.com/in/rob-cannon-21571317/)

### **Richard Mah**

While attaining his PhD in neuroscience, Richard employed a wide
variety of machine learning techniques to automate the analysis of
clinical data with a microservices-based architecture on Kubernetes.
Since then, he became an Insight fellow working on immutable
deployments of validator node infrastructure focusing specifically on
monitoring and alarms. Richard has deep experience in the intersection
between advanced data analysis and high performance computing.

[Github](https://github.com/shinyfoil),
[Website](https://www.richardmah.com/),
[Linkedin](https://www.linkedin.com/in/richardmah/)

### **Mitchell Krawiec-Thayer**

Mitchell started the blockchain engineering program at Insight in 2018
and now leads the R & D Residents (while continuing privacy research
and protocol SecEng for Monero Research Lab). Specializations include
decentralized network security, anti-heuristic engineering, empirical
analysis, on & off-chain anomaly detection, metadata archive design &
analysis. Mitchell works closely with the Fellows and Residents to
ensure that they have access to the resources and mentorship that
empower them to excel at their engineering initiatives.

[GitHub](https://github.com/mitchellpkt/),
[Twitter](https://twitter.com/Mitchellpkt0),
[LinkedIn](https://www.linkedin.com/in/mitchellpkt/),
[Medium](https://medium.com/@mitchellpkt)

## Team Code Repos

**Current list of project related repos - WIP**
- [terragrunt-polkadot](https://github.com/insight-infrastructure/terragrunt-polkadot)
- [terraform-polkadot-aws-network](https://github.com/insight-infrastructure/terraform-polkadot-aws-network)
- [terraform-polkadot-aws-sentry-node](https://github.com/insight-infrastructure/terraform-polkadot-aws-sentry-node)
- [terraform-polkadot-gcp-network](https://github.com/insight-infrastructure/terraform-polkadot-gcp-network)
- [terraform-polkadot-gcp-asg-node](https://github.com/insight-infrastructure/terraform-polkadot-gcp-asg-node)
- [terraform-polkadot-do-network](https://github.com/insight-infrastructure/terraform-polkadot-do-network)
- [terraform-polkadot-azure-network](https://github.com/insight-infrastructure/terraform-polkadot-azure-network)
- [terraform-polkadot-azure-asg-node](https://github.com/insight-infrastructure/terraform-polkadot-azure-asg-node)

## Team LinkedIn Profiles

- [https://www.linkedin.com/in/mitchellpkt/](https://www.linkedin.com/in/mitchellpkt/)
- [https://www.linkedin.com/in/rob-cannon-21571317/](https://www.linkedin.com/in/rob-cannon-21571317/)
- [https://www.linkedin.com/in/richardmah/](https://www.linkedin.com/in/richardmah/)

## Development Roadmap

There are two basic types of repos.

1. Terraform modules to deploy the infrastructure
2. Terragrunt scaffolding to house the deployment of the individual
terraform modules

All deployment steps are wrapped with terraform including calling
packer builds, ansible configuration, and deployment of helm charts.
These terraform modules are then wrapped with terragrunt which have
all the parameters exposed through configuration files that are
rendered with Jinja.  This way, we can go from a high level
configuration file that then informs the critical parameters we want
to adjust across the whole stack.  It also decouples the templating
side of the configuration management from the terraform module itself.
Other terraform projects taken up by W3F perform rendering within the
terraform modules themselves which inhibits their ability to be reused
in other contexts.  By contrast, the modules we build can be reused
directly in a variety of contexts without rendering.  Thus while the
goal of this project is to build load balanced endpoints, the modules
can easily be repurposed for validator node sentry layers.

The first major design decision was to decide on whether to build the
endpoints with VMs or on Kubernetes.  While the ultimate goal of this
project is to build a microservices based architecture with
intelligent routing and a caching layer for pre-indexed queries, we
felt that initially we should focus on building a viable version 1
endpoint for archival queries.  Since archival nodes will be run on
optimized instances with directly attached nvme volumes, the VM based
nodes will likely stay in place for when intelligent routing and
caching layers are added on.

One of the real challenges with this proposal is to minimize the sync
time needed to scale out public facing nodes which requires either
pre-synced images or downloading the DB directly from a peer.
Pre-syncing is done from taking images off a "source of truth" node
and keeping a CDN updated with snapshots that can be pulled down with
the latest blocks.  Downloading the DB from a peer is the existing W3F
approach and is as simple as scaling out the application from scratch.
While API vendors like Infura favor the pre-syncing approach, both
options have their own benefits and will be explored through a series
of benchmarks.

### **Milestone 1: IaC Modules**

**1 Month - 10k USD + 24 b-dots**

---

**Goals:**

- Build autoscaling groups, load balancers, and networking modules on
AWS, Azure, GCP, and Digital Ocean with terraform, ansible, and packer
packaged as reusable modules.
- Build module and scaffolding level CI tooling and testing with terratest
- Integrate logging and monitoring exporters and service discovery agents
- Expose v1 endpoint for full archival queries

**Deliverables:**

- Network modules for each provider - 4 repos
- Autoscaling groups and load balancers for each provider - 4 repos
- Documentation to support deployment processes

### **Milestone 2: Benchmarking**

**1/2 Month - 5k USD + 12 b-dots**

---

- Conduct brief study to determine optimal scaling policies for
autoscaling groups
- Determine metrics and thresholds to inform what chain size will
require syncing optimizations (pre-synced images + CDN)

**Deliverables:**

- Optimization of scaling policies for autoscaling groups
- Report to W3F with findings and discuss next steps to handle syncing
optimizations

### **Milestone 3: Kubernetes Modules**

**1 Month - 9k USD + 24 b-dots**

---

- Build kubernetes clusters and associated provider specific manifests
to bootstrap the clusters in line with the existing
[polkadot-deployer](https://github.com/w3f/polkadot-deployer) tool.
- Build API gateway and service proxy for intelligent routing and caching layers

**Deliverables:**

- Kubernetes cluster modules and manifests for each provider - 4
infrastructure repos
- API gateway (likely Ambassador) and service proxy (likely Envoy)
along with associated helm charts to build service mesh and supporting
observability services - 1 repo or contributions to existing
[polkadot-charts](https://github.com/w3f/polkadot-charts) repo
- Documentation to support deployment process

### **Reach Goals: Microservice Templates**

- Build microservice templates from which Insight data engineering fellows can build specialized endpoints from
- Recruit 10 Insight data engineering fellows to build additional endpoints and data pipelines and 3 dev ops fellows for productionizing and packaging of endpoints 

**Deliverables:**

- Airflow ETL tools for batch processing - Contribute to [github.com/blockchain-etl/polkadot-etl](https://github.com/blockchain-etl/polkadot-etl)
- Microservice cookiecutter templates
    - Flask (Python) - 1 repo
    - FastAPI (Python) - 1 repo

### **Long Term Plans**

---

- Comprehensive library of IaC modules that can be used and repurposed
in a variety of contexts
- CLI tooling for deploying modular sets of self-healing infrastructure
- Microservices library to expose pre-indexed queries
- Additional versions of the API to reference different parachains

## **Additional Information**

While it is important for decentralized network operations to avoid
homogeneity, certain components that have a low impact on the
diversity of the network are prime targets for standardization. We
feel that as the ecosystem grows, having a battle-tested set of
reusable modules will prove to be very valuable for best practice to
be shared around the community.

CLI's are useful for making the deployments easily reconfigurable but
can become quite opinionated when building in how optionality is
expressed.  Right now we leverage
[cookiecutter](https://github.com/cookiecutter/cookiecutter) for both
exposing a simple CLI for rendering scaffolding configs but also in
how we plan on giving our Insight fellows starting points for their
projects.  Because we want to make sure our Insight fellows have the
necessary boilerplate code to begin their projects, we are building
libraries of starter packages to facilitate the productionization of
their projects.

This project will get us to the doorstep of being building out various
microservice endpoints that will make use of different types of
caching and persistence layers.  These types of endpoints make for
fantastic Insight data engineering projects which we hope to recruit a
number of fellows to take on during the session starting in June 2020
and beyond.  Time permitting, we will be building boilerplate
architectures to support both real-time and batch queries against a
number of backends for different types of microservices. A month
before this particular grant comes to an end, we will be soliciting
feedback to inform what endpoints are most interesting to the
foundation.

What we are mainly focused on for now is creating a open framework
from which additional APIs can be built. As new parachains come
online, we hope to create additional endpoints to support their
specialized requests.