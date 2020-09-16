# substrate x (prometheus + grafana) by B-Harvest

## Project Description

- general initiative
  - substrate should provide more general information exporter inside the module so that users can expand their monitoring tool in various ways.
  - telemetry has already customized feature and it is difficult to expand such potential use-cases using existing tools.

- substrate module expansion(prometheus exporter built in substrate)
  - objective : we hack substrate so that it can stream node/blockchain information by prometheus as a default feature of substrate.
  - why : telemetry does not provide user customization for monitoring and alarming. therefore we want to provide any node operator of substrate base blockchain one of the most general and customizable node monitoring/alarming platform, prometheus.

- prometheus-grafana easy default implementation for nodes monitoring center
  - objective : we provide validator/collator community basic prometheus-grafana implementation with various parameters and easy installation.
  - why : we want to provide high standard of node monitoring and alarming capability to substrate base blockchain node operators by easy implementation of prometheus-grafana.

- potential expansion of the project
  - support monitoring and alarming of various economic activities on the relay chain and parachains, including transaction and state change monitoring.
  - connecting prometheus to Grafana for better visualization and query functionality, which will significantly upgrade node operator's post-event analytic abilities on stability of node operation.
  - expansion of this project will greatly benefit blockchain statistics explorer on substrate base blockchains.

## Team members

- Hyungyeon Lee: B-Harvest Team CEO, spec design
- Jeseon Lee: B-Harvest Team Engineer, major development
- Dongsam Byun: B-Harvest Team Engineer, development support
- Hyungsuk Kang: Korean Polkadot Ambassador, technical/relationship advisor


## Team Website

- <https://bharvest.io/>

## Legal Structure

13F Horim Art Centr, Dosan-daero 317, Gangnam-gu, Seoul, Korea

## Team's experience related to this project

- development and use experience of prometheus and grafana on Cosmos Network
- experience on hacking tendermint and cosmos-sdk for better data exporter including prometheus, rpc, lcd
- experience on hacking hybrid data query program for efficiently searching data in no-sql database like leveldb, rocksdb
- development and use experience of ELK(elastic search - logstash - kibana) on Cosmos Network
- building and serving website for blockchain(Cosmos Network) statistics analytics using various hacked exporter, data management tools and api

## Development Roadmap

### Deliverables

- PRs on substrate and polkadot repository allowing prometheus exporter built in as a default feature, including its configuration.
- a public repository which allows users to easily adapt prometheus-grafana server with built-in pages and alarming features.
- All deliverable repositories provided will have Apache 2 license.

### Feature Testing Environment

- We will provide a procedure to adopt the new feature into Kusama so that anyone can test the new Prometheus-Grafana feature.
- We will also provide a guide to adopt this feature on mainnet Polkadot when it is launched

### Milestones

-   *(4 weeks)*
    Consult with substrate devs to agree on PR implementation details and develope prometheus exporter built in substrate with basic data spec

-   *(2 weeks)*
    Expand the data spec provided by prometheus with broader range with optionality by configuration and provide a public repository for prometheus-grafana easy installation using implemented prometheus exporter in substrate



### Commitment

We understand that our role as a granted contributor is a significant responsibility and will make it a priority. We will do our best to deliver the product as quality as possible with due diligence.

## Additional Information

-   What work has been done so far?

    specs on prometheus exporter in substrate is underway(figured out general approach)

-   Are there are any teams who have already contributed (financially) to the project?

    No.

-   Have you applied for other grants so far?

    No.

-   Are there any other projects similar to yours?

    telemetry serves similar role of our project, but with limited expansion potential.

-   How is your project different?

    prometheus exporter in substrate will expand great potential to the community for better information management 
    using different kinds of well-established open-source tools such as grafana, elastic search, kibana, apis, databases, etc.
