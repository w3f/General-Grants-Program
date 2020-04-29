# Predictive Performance Management Runtime Modules

## Project Description

Cathegories:
* Research / Benchmarking
* Monitoring / Statistical analytics
* Polkadot Runtime Modules and corresponding UIs / Governance

This grant application supports the development of a Decentralized Service Governance platform and network of Service-Level Agreements (SLA) called Stacktical. 

Within the framework of this grant application, we will provide a series of tools and Substrate/Polkadot runtime modules that aim at streamlining the performance testing of the Polkadot network, and the easy identification of trustworthy Validators in the nomination and telemetry scenarios.

First, we will develop a benchmarking and scalability prediction module for Polkadot researchers and developers, to increase the velocity and the quality of developments using mathematical models and DevOps performance management techniques.

Second, we will develop a performance monitoring module that will ultimately display performance and availability information on the Polkadot UIs, to reassure Nominators they can trust a given Validator with their stake, and provide a governance alternative to the existing Polkadot reputation system.

**Benefits**

1. The project will help Polkadot Researchers engineer the Polkadot network with very little performance testing and node provisioning overhead.

2. The project will help Polkadot Nominators nominate Validators using decentralized SLA/SLI information overlays.

Ultimately, the developed modules will serve as the foundation of a SLA-driven, Decentralized Service Governance mechanism, between all actors of the Polkadot network. 

Along with significantly strengthening the existing Polkadot reputation system, it will pave the way to more DOT-based incentives to secure the network.

**Integration**

Performance testing container, Off-chain computations, Substrate runtime modules.

**Motivation**

Actively working on runtime modules for the Substrate/Polkadot ecosystem is the first step towards becoming a fully-fledged parachain, and tapping into the full potential of the Stacktical Platform.
We also believe in Polkadot’s vision for interoperability, as we’ve stated in the past that ”DApps, platforms and protocols will ultimately rely on multiple other DApps, platforms and protocols to mature into fully-fledged solutions and pave the way to more intuitive user experiences.”
https://medium.com/stacktical/blockchain-is-platforms-with-a-s-48049bb49efe



## Team members
* Wilhem PUJAR: Team Lead, Full Stack developer
* JeanDaniel Bussy: Ops and BlockOps
* Yosra Helal: Blockchain Developer and Security Auditor

The three of them are joined by the Stacktical DevOps Residents, a distributed team of DevOps practitioners that contribute to the engineering of the Stacktical Platform.

## Team Website	
* https://stacktical.com

## Legal Structure

Stacktical S.A.S, 3 BOULEVARD DE SEBASTOPOL 75001 PARIS FRANCE

## Team's experience


* Wilhem holds a MSc in Computer Science. He has a 10 year experience in distributed software architecture, software development and product management.
He previously founded a Tag&See, a Big Data startup specialized in social media monitoring and sentiment analysis.
He started getting involved with the Blockchain in 2015, by experimenting with chaincode development in IBM Bluemix, one of the legacy components of the now Hyperledger consortium.

* Jean-Daniel holds a MSc in Computer Science. He is a Google Certified Architect with 10 years experience in System Administration, IaaS, High performance tuning and Cloud Architecture
He has been one of the first OpenStack and Kubernetes administrators in Asia.
He started getting involved with cryptocurrencies in 2014, when he applied DevOps automation principles to the deployment of Litecoin nodes.

* Yosra’s strong skills and experience in blockchain architecture and Smart Contracts(POA network, Quorum, Hyperledger, NXT), are essential in ensuring the flawless execution blockchain projects. Coming from web3js background, she was drawn to blockchain developing smart contracts for ICOs, leading the full cycle through coding, writing, testing and auditing. She worked on a number of successfully interactive projects and has joined the Stacktical team from Paris to boost the execution of Ethereum-based service-level agreements.

## Team Code Repos

* https://github.com/Stacktical
* https://hub.docker.com/r/stacktical/willitscale


## Team LinkedIn Profiles
* https://www.linkedin.com/in/wilhempujar/
* https://www.linkedin.com/in/bussy/
* https://www.linkedin.com/in/yosra-helal-aaa439101/

## Development Roadmap

**Milestone 1 — Benchmarking & Scalability Prediction module — 1.5 months — €25,000**

* We will add throughput and latency measurements to the current performance testing capabilities of polkadot-deployer. 
Alternatively, we will develop a Kubernetes validator performance testing sidecar. (ndlr: since polkadot-deployer is already designed to run on Kubernetes).

* We will develop a scalability prediction runtime module leveraging off-chain workers, that will fit the performance testing results into predictive mathematical models. 
This will enable researchers to surface complete, actionable scalability insights by spinning and test just a couple of dozens nodes (8+ should suffice), specifically:
	* Draw the scalability chart of the network;
	* Predict the peak tps capacity of the network;
	* Predict the network latency, at peak tps capacity;
	* Predict the ideal validator count of the tested network (before the network starts generating diminishing returns);
	* Quantify the contention and coherence penalties of the network (scalability bottlenecks).
	* Adding performance regression testing to their software delivery pipeline and track the evolution of scalability insights, release after release.

	E.g. Each new Release Candidate Pull Request could deploy a test network using polkadot-deployer, run 8 performance tests and predict the scalability of the build. A RC failing to meeting certain scalability requirements could then be QA Refused to avoid further regression.
* We will deliver a working performance testing tool and module, with a tutorial describing how to run performance tests, run scalability predictions and add scalability regression testing to an example CI server.

**Milestone 2 — Performance Monitoring module — 1.5 months — €25,000**

* We will develop a performance monitoring module that will:
Return the current uptime and latency of a (group of) Validator(s)
Check these metrics periodically, if deemed possible at the time
Store the metrics (on-demand or periodically) in a decentralized way
Compute Service-Level Indicators (SLI) from the stored metrics
Return the daily | weekly | monthly | yearly | era SLI of a (group of) Validator(s)

* We will then develop a Polkadot UI that will display uptime and latency SLI on Validator UI elements (list items, typically) so that Nominators can curate and make a more informed selection of the nodes that are less likely to experience slashing, based on their ability to meet uptime and latency SLAs.

* We will then enrich the Substrate Telemetry tool to display uptime and latency SLI columns.

The total funding is €50K for 3 months of work.

## Additional Information

For the past 2 years, we’ve helped a wide variety of organizations generate in 250% increase in system performance thanks to predictive scalability testing.
Stacktical is the first and only platform for rolling-out decentralized SLAs and automating the compensation of SLA violations using cryptocurrencies.

Dubbed “DSLA Network”, the Stacktical Platform MVP is up and running at https://dsla.network. It is currently built on the Ethereum blockchain.

We appreciate very much how Polkadot’s work on interoperability is pushing our vision of a more reliable Web, backed by cryptography-verified service-level agreements.

No other team has financially contributed to the Stacktical project, and we haven’t applied to any other grant.
