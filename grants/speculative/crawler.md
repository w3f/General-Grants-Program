# Polkadot Network Crawler

## Project Description

Build a standalone Polkadot network crawler to scan currently available nodes and saving details in external storage for further analysis or visualization.

The crawler is going to implement a subset of Polkadot p2p protocol to connect to nodes it can find and gather any additional information that can be fetched by requesting a connected node. I.e., current height, blocks, genesis, node software, IP address, and so forth. Gathered details a supposed to be stored in a database (for example, MySQL), and can be accessed by a 3rd party software for analysis. 

## Team Experience

Igor Artamonov, lead developer. He has a master's degree in Computer Science, is a professional software developer since 2001, has been writing code since 1995. The main focus of his work has been on scalable, decentralized, distributed, and fault-tolerant applications; on projects storing and processing big data; on user authentication and security.

For the past few years, he got involved in blockchain space. From 2016 through the end of 2018, he was leading the development of Ethereum Classic blockchain. He was also working on a Block Explorer, integration libraries for Ethereum, and Emerald project. He is knowledgeable of tech aspects of blockchain implementations, APIs, and usage scenarios of blockchain. 

He is currently working on a decentralized infrastructure for cryptocurrency transactions, and part of this work is a node crawler for Ethereum compatible networks. Some of the data is currently published one Emerald Insights website, in relation to Ethereum Istanbul upgrade progress.

Links:

- https://www.linkedin.com/in/igorartamonov/
- https://medium.com/splix/measuring-ethereum-nodes-530bfff08e9c
- https://insights.emeraldpay.io/status/ethereum-istanbul

## Legal Structure

Swiss GmbH

## Development Roadmap

### Strategy and Technology

The current crawler, which is designed specifically for the Ethereum and Bitcoin networks, is a closed source. However, the current proposal offers the creation of an entirely new Open Source crawler based on the experience learned from that closed source crawler.

It's going to be based on JVM and the following technologies:

- Kotlin
- Spring Framework
- Project Reactor
- Other related libraries, such as io.web3j:libp2p

The strategy is to create a daemon that implements a subset of the P2P protocol to discover and connect to each node one by one to learn their details. 

In general, there're two major components:

- Nodes discovery - passive and active discovery of the network participants, by registering on a rendezvous point and query for other peers
- Connect to a node and execute series commands to learn details about the node. The commands are specifically requesting info about the software, current status, genesis, etc.

The result of such processing streamed to a log file in a JSON format and/or to a SQL database for further processing by an external application.

### Crawler Daemon MVP - 4 weeks

Implement a basic crawler and p2p protocol. The crawler should be launchable from a command line and/or as a Docker image. As a result of the work, it is going to produce a log of found nodes to stdout.

### Gather nodes details - 4 weeks

The main goal of this phase would be the stabilization of the architecture and the process of discovery and nodes processing. 

As a result, the crawler will be able to execute additional commands, such as block details, to gather additional information about the current state of the blockchain on a remote node. Results are going to be streamed to a file in JSON format.

### Storage - 4 weeks

The crawler can store found nodes into:

- MySQL database
- AWS S3 Storage
- GCP Storage
