# Auto-funded public P2P infrastructure - Vedar

## Project Overview
*In response to the [APPI: Auto-funded public P2P infrastructure RFP](https://github.com/w3f/General-Grants-Program/blob/dc11900e46c2bd28ccee0353afc53f77e0911bba/rfp-proposal/appi.md).*

In Ethereum, most user-facing applications default to Infura as an endpoint to access full node information.
While it is tempting to conclude that this is because running home nodes 
is prohibitively expensive, the main reason is in fact inertia.
Put simply, people weren't given the option or incentive to run
their own nodes fast enough, and defaulted to an easier route.

This document describes auto-funded public p2p infrastructure 
(APPI) for the Polkadot and, specifically, Kusama ecosystem.
The idea is to incentivize people to run full and archive nodes at home,
without relying on cloud servers and centralized points of failure.

We think that we are suitable for developing such infrastructure since 
we already built similar infrastructure for Filecoin, [monitoring daemon and dashboard written in Go](https://www.hactar.app/).


## Project Details

### Load Balancer (LB)

The Load Balancer is a tool that assigns an incoming connection request
to a node in its pool. 
The Load Balancer should only accept nodes with the same settings as every other node. 

E.g. if a node is running with some RPC endpoints off,
it should not share a pool with a node that has them all on,
otherwise the users connecting to the pool might experience lower QoS.

Load balancer is going to be written in Go and delivered as standalone executable.

#### Request forwarding
Rpc request received on LB public endpoint should be forwarded to
node based on configured selection algorithm.

A penalized node should enter an initial cooldown of 1 minute,
and issue another check after the cooldown expires.
After every check, if the offense is still on-going,
the duration of the last cooldown doubles. 
When a node's cooldown exceeds 17 hours,
the node is permanently removed from the pool (automatically removed from the whitelist).

#### Nodes telemetry
The Load Balance should expose http for receiving node updates from [LB Daemon](#lb-daemon).

The Load Balancer should store node updates and
 log penalties into the database if a node is offline 
(not reporting a ping for more than 30 seconds) 
or not fresh (a node's latest and best block lag 
behind the best in the pool by more than 10 blocks).


#### Metrics
The load balance should provide [prometheus metrics](https://prometheus.io/)
endpoint for setting up [Dashboard](#dashboard).

#### LB Settings
An LB operator can define the following settings:

- LB name
- LB capacity (max number of nodes)
- Whitelist (list of node IDs)
- Blacklist (list of node IDs)
- Fee (cut to take)
- Selection method (random or round robin)
- Aliases: if the operator is running alternative clones of the same LB on other infra,
aliases can be defined here.
All LB clones should also define the same list of aliases, including the original.
This should reduce reliance on a single LB endpoint.
- Payout period in days
- Payout script executable path

The LB should be able to automatically and periodically - based on *payout period* - call out to a [Payout script](#payout-script) which takes as input a list of addresses and points.

#### Payout Calculation

The LB adds points to a node in the ratio of 90:10 for requests:liveness. In other words, a node that has been online but got no requests due to bad luck should still be paid something.

### LB Daemon

The LB Daemon is a background process meant to be run alongside a Substrate node. This Daemon:

- pings its home LB every few seconds with the node's ID
- alphabetically orders and standardizes, then hashes a node's startup settings (exclude basepath and name) and sends them along with every ping
- retrieves the node's best and latest blocks and sends them along with every ping
- reports telemetry data to the LB, like connected peers, memory use, etc.

LB Daemon is going to be written in go and delivered as standalone executable.

### Payout script

The Payout script is in charge of disbursing payments. This is a multi-pay script which takes as input a mapping of addresses and points. The payout script should be an account of the chain it is paying out for (e.g. a Kusama account if we're dealing with a Kusama pool), so that it can receive the [auto-payout from the Treasury](https://github.com/paritytech/substrate/issues/6551).

The payout script should be a standalone executable. Future efforts can develop payout scripts for other chains, which would make them immediately compatible with the other components in this document.

### Dashboard

Json file containing [Grafana](https://grafana.com/) dashboard definition
using prometheus metrics endpoint on [Load Balancer](#load-balancer-lb)
as data source. Should display load balancer stats as well as each node stats.

## Ecosystem Fit 
There have been attempts at financing home-run infrastructure 
- projects like VIPNode have lead the charge - but the aforementioned inertia prevented any significant adoption.
Another recent contender is Pokt.network.

We feel like this project provides alternative with simple financing 
and operating model available to everyone.

## Team members
* Marin Petrunić
* Mak Muftić
* Belma Gutlić
* Matija Petrunić

## Team Website	
* https://nodefactory.io

## Legal Structure 
Company in the Republic of Croatia

## Team's experience
We are a blockchain research and development company but also a group of friends and developers working from an office in Zagreb. Being mostly fullstack developers and blockchain developers for the last 3 years, we are successfully providing services such as dapp development, infrastructure and tooling.

We are already working on some grant sponsored projects like:
- [Metamask snap for Polkadot](https://github.com/nodefactoryio/metamask-snap-polkadot)
- [ChainGuardian](https://github.com/NodeFactoryIo/ChainGuardian) - Eth2 validator desktop application 
- [js-libp2p-noise](https://github.com/NodeFactoryIo/js-libp2p-noise) - libp2p stream security transport to be used in eth2 mainnet
- [Hactar](https://www.hactar.app/) - a Filecoin miner analyzer
    - https://github.com/NodeFactoryIo?q=hactar

Some of the other projects that we've been working on can be found on our [website portfolio](https://nodefactory.io/portfolio/).

## Team Code Repos
* https://github.com/nodefactoryio

## Team LinkedIn Profiles
- https://www.linkedin.com/in/mpetrunic/
- https://www.linkedin.com/in/mak-muftic/
- https://www.linkedin.com/in/belmagutlic/
- https://www.linkedin.com/in/matija-petruni%C4%87-4b78a615b/

## Development Roadmap
* **Total Estimated Duration:** ~2 months
* **Total Costs:** ~27600 USD

### Milestone 1: LB Daemon and Server
See [LB Daemon](#lb-daemon) for definitions.

* **Estimated Duration:** 2 weeks
* **Full Time Employees:** 1
* **Costs:** 4800 USD
* Implement:
   * the LB Daemon, a standalone daemon to run alongside a Kusama or Polkadot node and feed data into http server
   * http server to store daemon data
* Deliver docker-compose file to run node, daemon and server to store telemetry data
* The code will have proper unit-test coverage to ensure functionality and robustness.
* Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

### Milestone 2: Load Balancer

See [Load Balancer](#load-balancer-lb) for definition.

* **Estimated Duration:** 2 weeks
* **Full Time Employees:** 2
* **Costs:** 9600 USD
* Implement:
   * Load balancer that is able to read data from database and route requests to qualified node
 * Deliver docker-compose file to run node, daemon and load balancer
 * The code will have proper unit-test coverage to ensure functionality and robustness.
 * Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

### Milestone 3: Payout Script

See [Payout Script](#payout-script) and [Payment Calculation](#payout-calculation) for details.

* **Estimated Duration:** 1 week
* **Full Time Employees:**  2
* **Costs:** 4800 USD
* Implement:
   * standalone payout script
* Deliver executables and example payout sheet
* Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.
* The code will have proper unit-test coverage to ensure functionality and robustness.

### Milestone 4: Dashboard

See [Dashboard](#dashboard) for details.

* **Estimated Duration:** 1 week
* **Full Time Employees:**  2
* **Costs:** 4800 USD
* Implement:
   * prometheus metrics on loadbalancer
   * grafana dashboard for previewing data as json
* Deliver docker-compose for setting up services and grafana dashboard in json format
* Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.
* The code will have proper unit-test coverage to ensure functionality and robustness.

### Milestone 5: Landing page and instructions
* **Estimated Duration:** 1.5 week
* **Full Time Employees:**  1
* **Costs:** 3600 USD
* Implement:
   * landing page for user onboarding
   * public list of load balancer endpoints (adding new endpoint is done via Github Pull Request)
* Deliver Link to landing page and instructions
* Provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.