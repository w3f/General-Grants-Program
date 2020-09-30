# Subscan Essential

## Project Description
Subscan(https://www.subscan.io/) is a popular blockchain explorer for Substrate based blockchains, it supports various projects including Polkadot CC1, Kusama, Darwinia Crab, Edgeware, Plasm, Acala Mandala etc. We are planning to provide a cloud hosting explorers for Substrate developers to easily deploy explorers for their blockchain, and can flexiblity config and display their domain-specific SRML using Subscan explorer plugin frameworks besides standard runtime modules.

By integrating numerous components into Subscan, we believe Subscan can help developers improve their efficiency substantially by eliminating the need to develop and host explorers.

Scope of this grant will include some essentials components used by Subscan:

* Explorer's common shared indexing and querying service for generalized Substrate types(e.g. Block, Extrinsic, Event, Log, Storage), support any blockchain which is Substrate based.
* Subscan explorer plugin framework and an explorer plugin template.

This project is to build the Substrate explorer infrastructure and reduces the development cost for Substrate developers. It is consistent with the Substrate framework and standards. Blockchain developers can better focus on application layer development, and at the same time, Subscan explorer's fast and agile support can meet the flexible requirement of the development stage and promotion stage.

## Team members
* Yakio Liu, product manager
* Carl Hong, full-stack developer, project outreach
* Bruce Sun, experienced devops and backend developer
* Bei Wan, experienced front-end developer
* Dre, graphic/UX designer
* Denny, architecture consultant

## Team Website
* Explorer: https://www.subscan.io
* Medium: https://medium.com/@subscan_io
* Twitter: https://twitter.com/subscan_io

## Legal Structure 
Shanghai Yitaiyuan Co. LTD

## Team's experience
Our team has many years of blockchain development experience. We are familiar with the Substrate framework and polkadot ecology, and have been actively participating in ecological development. Currently, it is focused on the research and development of explorer.

## Team Code Repos
https://github.com/itering/subscan-essentials

## Team LinkedIn Profiles
* Bruce Sun: https://www.linkedin.com/in/sunbobin/
* Denny: https://www.linkedin.com/in/denny-wang/

## Development Roadmap

### Milestone 1 — Subscan explorer's common components — 1 month — $15,000
* Subcan explorer's common components supporting Substrate general types and datas, can be used by any Substrate based blockchain.
    * A basic indexing and querying framework implemented in Golang
    * Querying service including Block, Extrinsic, Event, Log, Runtime Metadata, indexing the data from Substrate node to relational database (e.g. postgresql)
    * Basic web user interface to query the indexed datas.
* Docker image to setup basic explorer service.
* Documentations for developers to get started and configration.

### Milestone 2 — SRML explorer plugin framework — 1 month — $15,000
* An explorer plugin framework paring with Substrate to provide the flexibility of providing customized explorer plugin for various SRML.
    * Framework Specification
        * Runtime module metadata and types preprocessing and schema auto generating specification
        * Extrinsic dispatch call parsing and indexing solution, using signed extension metadata definition
        * Example of using customize module rpc call to providing data for module explorer plugin
    * Basic Implementation of the framework
        * Indexing and parsing *Extrinsic* calls according to dispatch call definition from decl_module! macro.
        * Indexing and parsing Events, Errors, Logs according decl_event!, decl_error!, Block Digest definition
        * Basic View Control Support: Table Control
    * Custom Data/Storage Parsing API and Data Processing API Specification
* Module plugin template (Balance)
    * Follow the framework specification and implementing a sample plugin which can work with it. (A plugin for Substrate balance module)
    * Deployer can select the plugin through web interface
* Docker image demonstrating its functionality.
* Documentations for deployers.

30,000 USD in total, we are willing to accept up to 50% of payment in vested DOTs.

### Open-source license
Each component in this grant scope will be open sourced, all required code to leverage the components in this grant scope will be open sourced as well. We plan to open source more components of Subscan Essential in the future. The license is GNU GPL v3.

## Future Plans
Subscan is a complex product, we've been building it for 10 months and we can only cover core features during the 3-month period. We would like to combine the components into upcoming Subscan cloud services, and will continue working on Subscan explorer in the future to make it more complete and mature. 

We are optimistic about the prospects of Substrate and will maintain good communication with the Substrate community and developers. We are striving to provide high-quality Explorer Instance cloud services for chains based on Substrate. At the same time, developers can earn income by developing an explorer extension for SRML module via our explorer platform, which may become a new business model in the future. Subscan will always support the update of Substrate and grow together.

We hope this project will benefit Substrate ecological developers.

