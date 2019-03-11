## Project Description
MixBytes Tank will be a tool for blockchain stability and performance benchmarking. It will allow to identify bottlenecks and pain points of the project, then report the results and offer recommendations. The tool will be suitable for multiple benchmarking of new Substrate versions.

Key benefits:

* Open-source benchmarking product 
* Multiple benchmarking options (different precision rate, timing and load profiles): smoke tests, massively parallel benchmarking, massively parallel geographically distributed benchmarking.
* Various load profiles written in js: simple cryptocurrency transactions, complex smart contract operations, etc.
* We operate Grafana as a convenient tool for metric collection, display, analysis and download. Key blockchain metrics are: throughput, block latency, finality latency, resource usage. We provide separate statistics with the most insightful indicators such as 99 percentiles.
* Ready-to-use code: an automated stand for recurrent benchmarking allowing to assess quality rate, test releases, etc.
* Minimal cloud resource consumption due to automated network deployment and shutdown

### Why is it relevant?
Building complex software and testing final products make blockchain development a costly process. Blockchain performance assessment can be tricky: the network performs brilliantly when limited to 2-3 nodes running in a lab environment, yet, results change dramatically in production where entire network segments may get cut off and network latency may rise.
Much depends on transaction types and resources for their processing. Usually, developers concentrate more on product creation putting aside benchmarking and infrastructure analysis. 

Also, Substrate developers must be sure blockchain updates and new version release will not cause network splitting, poor operation stability or performance. Blockchain and consensus optimization decisions should be based on factual data and measured values. 


## Team members
* Alexey Makeev (CTO, Analyst, DevOps)
* Sergey Prilutskiy (CRO, DevOps, Fullstack Developer)
* Andrey Levkin (Infrastructure Architect, Senior DevOps)
* Sergey Govyazin (JS Developer)
* Vadim Buyanov (PM)

Our staff also includes blockchain engineers and frontend developers. Three members of our team (including Sergey and Alexey) have a profound knowledge and experience in software development based on Parity Substrate.

## Team Website	
* https://mixbytes.io

## Legal Structure 
Russian LLC

## Team's experience
We have a broad experience in infrastructure system engineering and exploitation for the largest Mail.Ru Group Internet projects with 150 mln user coverage. 

* Alexey: 7+ years of experience with Internet search engine project, 5 of which as a Team Lead. Previous experience also involves developing search engine systems. 
* Sergey:  9 years of experience with web portal development and working with antispam software development teams (7 years as a Team Lead). Previously was engaged into search engine systems development and antivirus analyzers. 
* Andrey: 12 years of *nix administrator experience, 4 years of DevOps Engineer experience, 6 years Team Lead experience.

We developed performance-critical software, various databases, big data clusters and machine learning systems and developed geographically distributed fault-tolerant systems. 
We have a clear-cut understanding of testing and benchmarking, experience in handling load testing issues and developing necessary solutions.

As a dev shop, we are proud to have Parity Substrate as our partner and offer blockchain development services on its basis to a wide range of customers.

We have been into blockchain technologies since 2017 developing cryptographic protocols, various blockchains, smart contracts and complex solutions. POA Network, Trust Wallet, Golos and others are among our satisfied customers and partners. 

## Team Code Repos
* https://github.com/mixbytes
* https://github.com/mixbytes/substrate-module-multisig 
* https://github.com/smartzplatform 

## Team LinkedIn Profiles
* https://www.linkedin.com/in/aleksey-makeyev-98471884/
* https://www.linkedin.com/in/sergey-prilutskiy-2a619951/ 
* https://www.linkedin.com/in/alevkin/ 
* https://www.linkedin.com/in/vadim-buyanov/ 

## Intended language of development
* Ansible, JS, Python, Bash

The main parts of the tool will be infrastructure as code, a load profile executor, auxiliary scripts. Infrastructure will be primarily composed of Terraform and Ansible configuration files. The executor will be implemented in javascript to provide the ability to write complex load profiles and interact via standard APIs and libraries. Depending on a part complexity, auxiliary scripts will be written either in Python or Bash.

## Development Roadmap

* Start: within 1 week after grant receipt
* Research and planning, identifying metrics and load profiles range, preparing project specification (weeks 0 - 1).
* Metric collection and visualization playbooks, system metrics (week 2)
* Virtualized infrastructure deployment, scripts and playbooks (weeks 3 - 4)
* Substrate automated parallel deployment, blockchain initialization and warmup (weeks 3 - 5)
* Substrate telemetry enhancements (weeks 3 - 5)
* Smoke tests, basic documentation (week 4)
* Development of load profiles (weeks 4 - 8)
* Massively parallel tests, scripts and playbooks (weeks 6 - 8)
* Geographically distributed massively parallel test, scripts and playbooks (weeks 9 - 11)
* Infrastructure scripts and tools wrap-up, documentation wrap-up (weeks 9 - 11)
* Benchmarking results analysis and interpretation (weeks 6 - 11)

We are planning to further develop the project under Apache 2 license, adding new features such as system testing for network partitioning tolerance, high network latencies, byzantine actors, etc; testing various blockchain nodes and creating a universal set of metrics for blockchain operation assessment.

Financial information will be disclosed privately.

## Additional Information

### What work has been done so far?
Basic variant of a similar benchmarking tool for EOS blockchain.

### Have you applied for other grants so far?
Yes, for C++ PRE implementation.

### Are there any other projects similar to yours?
Not that we were aware of.
