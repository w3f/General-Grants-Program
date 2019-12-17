# Polkadot Substrate RUBY API

## Project Description

This is an substrate json-rpc api client and libraries implemented in ruby language for general use. It contains the implementation of low-level data formats,  various substrate types and metadata support.

This work is the prerequisite of our subsequent series of projects. We hope to familiarize and quickly access Polkadot and Substrate through ruby, and use our existing ruby experience to quickly develop applications based on Polkadot / Substrate. We plan to develop some substrate-based web games. The back end of these applications is prepared to be developed in ruby language, and then interact with nodes or synchronize data through rpc.

### Why Ruby Substrate API is Good for the Ecosystem

Ruby is a very elegant language and is very popular among developers. Ruby's development efficiency is very high, so it is widely used in startups and small businesses. Ruby has a very high-quality community, and the Ruby ecosystem is also very mature. If there is a Ruby-based scale codec and API implementation, it will attract many Ruby developers and startups.

### Why our Team is Interested

We have accumulated a lot of experience with Polkadot and Substrate, and think that Substrate is the most valuable blockchain framework. We hope to make more attempts on this framework. And many of our colleagues have ruby development experience. In addition, we believe we can complete this project in a timely and efficient manner with the highest quality standards.

## Team members
* Aki Wu
* Alex Chien
* Denny Wang
* Bruce Sun

## Team Website	
https://www.itering.com 

https://darwinia.network/

## Team's experience

- Aki Wu

Technical expert in blockchain and web development, has been using ruby development since 2011, and have been involved in blockchain development since 2017, and has used ruby to develop tools that connect to blockchain nodes such as Ethereum and Bitcoin.

- Alex Chien

Excellent technical expert in blockchain, full stack ruby engineer, has been involved in the technical work of bitcoin and blockchain since 2011, and has participated in the technology development of several open source projects, especially in graphene technology and EVM smart contract technology. Very rich development experience.

- Denny Wang

Excellent technical expert in blockchain, core developer of BitShares 1.0, intelligent contract security expert. Now he is mainly engaged in Ethereum's Layer2 network and Polkadot cross-chain related research. He has served as technical leader in several blockchain technology companies.

- Bruce Sun

Full-stack developer graduated from NUIST, and has more than 5 years experiences of web development. He worked as a back-end development project for companies such as momo company, ATA, etc. Now he is doing development of blockchain browser and  smart contracts.

Core team  is from Itering Tech Co., Ltd.

Itering has a complete and professional team from technology to operation. The technical department has many senior experts engaged in the development and technical research of blockchain field, and has rich experience in consulting and development on blockchain technology such as public chain technology, Ethereum and smart contract.

## Team Code Repos
* https://github.com/itering
* https://github.com/wuminzhe
* https://github.com/darwinia-network
* https://github.com/evolutionlandorg

## Team LinkedIn Profiles
* https://www.linkedin.com/in/alex-chien-46448216/
* https://www.linkedin.com/in/denny-wang/
* https://www.linkedin.com/in/sunbobin/

## Development Roadmap
### Milestones

* M1 (2 weeks): Implement scale codec low level data format

* M2 (2 weeks): Implement types of substrate, support dynamic type generation from json

* M3 (2 weeks): Metadata(versioned) support

* M4 (2 weeks): Full compatibility with native Substrate API

All milestones will include documents for explaining how to use the features.

After these are completed, this project will be used in subsequent projects and adjusted according to actual usage, which may include: better exception handling, and add support for other substrate-based chains.

## Additional Information

### What work has been done so far?

Substrate encodes data in the "Simple Concatenated Aggregate Little-Endian" (SCALE) data format, as implemented by:
* [parity-scale-codec](https://github.com/paritytech/parity-scale-codec) in Rust
* [@polkadot/types](https://github.com/polkadot-js/api/tree/master/packages/types) in Javascript
* [ChainSafe/gossamer](https://github.com/ChainSafe/gossamer/tree/development/codec) in Go
* [opennetsys/golkadot](https://github.com/opennetsys/golkadot/tree/develop/common/codec) in Go
* [soramitsu/kagome](https://github.com/soramitsu/kagome/tree/master/core/scale) in C++
* [polkascan/py-scale-codec](https://github.com/polkascan/py-scale-codec) in Python
