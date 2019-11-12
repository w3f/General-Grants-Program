# Polkadot Network Crawler

## Project Description

Build a standalone Polkadot network crawler to scan currently available nodes and saving details in external storage for further analysis or visualization.

The crawler is going to implement a subset of Polkadot p2p protocol to connect to nodes it can find and gather any additional information that can be fetched by requesting a connected node. I.e., current height, blocks, genesis, node software, IP address, and so forth. Gathered details a supposed to be stored in a database (for example, MySQL), and can be accessed by a 3rd party software for analysis. 

## Team Experience
Igor Artamonov, lead developer. He has a master's degree in Computer Science, is a professional software developer since 2001, has been writing code since 1995. The main focus of his work has been on scalable, decentralized, distributed, and fault-tolerant applications; on projects storing and processing big data; on user authentication and security.

For the past few years, he got involved in blockchain space. From 2016 through the end of 2018, he was leading the development of Ethereum Classic blockchain. He was also working on a Block Explorer, integration libraries for Ethereum, and Emerald Wallet. He is knowledgeable of tech aspects of blockchain implementations, APIs, and usage scenarios of blockchain. He is currently working on a decentralized infrastructure for cryptocurrency transactions. Dshackle Load Balancer is a part of this work.

Links:
https://www.linkedin.com/in/igorartamonov/

## Legal Structure

Swiss GmbH

## Development Roadmap

### Crawler Daemon MVP - 4 weeks

Implement a basic crawler, which can be started from the command line or docker. It supposed to produce a log of found nodes to stdout.

### Storage - 4 weeks

The crawler can store found nodes into:

- MySQL database
- AWS S3 Storage
- GCP Storage

### Gather all details

The crawler can execute additional commands, such as block details, to gather additional information about the current state of the blockchain on a remote node. In addition, the crawler may be configured to check IP addresses against a Geo IP database.
