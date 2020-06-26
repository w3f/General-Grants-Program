# Crust Network

## Project Description

Crust implements the incentive layer protocol for decentralized storage. It is adaptable to multiple storage layer protocols such as IPFS, and provides support for the application layer. Crust's architecture also has the capability of supporting a decentralized computing layer and building a decentralized cloud ecosystem.

Crust contains 3 major layers:

1. GPoS (Guaranteed Proof of Stake) consensus layer. GPoS consensus uses storage resources as a guarantee. It encourages nodes to provide more storage resources, and improves the security and robustness of the network.
2. MPoW (Meaningful Proof of Work) layer. Based on the Trusted Execution Environment (TEE) technology, MPoW mechanism quantifies storage resource usage and generates corresponding work report in a reliable way.
3. Storage service layer. With the ability to quantify and consensus on storage resource usage, Crust's storage service layer provides decentralized cloud storage capabilities.

### Why Substrate

Crust uses Substrate in three major ways:

1. On block generation

    Crust builds layer-1 protocol layer based on Substrate. Its GPoS consensus algorithm is based on GRANDPA/BABE algorithm.

2. On governance

    Crust leverages Substrate autonomous upgrading mechanism for on-chain governance, to manage the TEE tech list from various companies.

3. On technical acceleration

    Based on Substrate, Crust is implemented as parachain. It accelerates Crust to tap into the shared security and interoperability within the ecosystem.

## Team Members

- **Chen Bao** - Founder, Project Manager, Business Development.
- **Lie Wang** - Co-Founder, Product Manager, Technical Advisor.
- **Zikun Fan** - Co-Founder, Technical Leader.
- **Yang Zhao** - Full-Stack Lead Developer.
- **Yao Zhao** - Full-Stack Developer.
- **Dean Yan** - Product Designer.
- **Shengnan Yang** - Frontend Developer.
- **Hui Yu** - Server-Side Developer.

## Team Website

[https://crust.network/](https://crust.network/)

## Team Code Repos

1. [crust](https://github.com/crustio/crust)
2. [crust-tee](https://github.com/crustio/crust-tee)
3. [crust-client](https://github.com/crustio/crust-client)
4. [crust-api](https://github.com/crustio/crust-api)

## Team Linkedin Profiles

- [https://www.linkedin.com/in/chen-bao-6b0a4125/](https://www.linkedin.com/in/chen-bao-6b0a4125/)
- [https://www.linkedin.com/in/lie-wang-b2292955/](https://www.linkedin.com/in/lie-wang-b2292955/)
- [https://www.linkedin.com/in/zikunfan/](https://www.linkedin.com/in/zikunfan/)
- [https://www.linkedin.com/in/yang-zhao-2b42921a2/](https://www.linkedin.com/in/yang-zhao-2b42921a2/)
- [https://www.linkedin.com/in/dean-yan-717784100/](https://www.linkedin.com/in/dean-yan-717784100/)

## Legal Structure

Clouderium Technologies Co.,Ltd in Shanghai, China.

## Team's Experience

**Chen Bao**  
Chen Bao has more than 10 years’ working experience of financial investment. He manages the company’s funds (total amount about 1 billion CNY) as the investment director. He invested some crypto projects in the past 3 years and founded Winsun Capital.
Chen Bao was the co-founder of Lava project, which is a decentralized digital infrastructure based on Proof-of-Capacity with over 500PB network capacity.

**Lie Wang**  
Lie has been working in IT industry for over 14 years. He worked in Microsoft and Cisco as development lead. Lie co-founded Namek Technologies in 2015, which raised series-A funding from China’s leading education technology company TAL (NYSE: XRS) for tens of millions CNY. Its major product leveraged blockchain and distributed storage technologies to track the ownership and usage of education resources.

**Zikun Fan**  
Zikun is experienced in both cloud computing and blockchain technologies. Zikun got his master degree in Computer Science from ZheJiang University and majored in distributed cloud computing. He received the PhD offer from CERCS Lab of Georgia Tech.
Zikun worked in Microsoft on Azure Kubernetes, distributed computing and blockchain based projects.

**Yang Zhao**  
Yang has extensive work experience in the fields of security and distributed storage. Yang graduated from the Department of Electronics of Tsinghua University and obtained his master's degree in the complex network laboratory. He has participated in many open source projects and made significant contributions. Yang worked in Microsoft on cyber security, distributed storage and big data based projects.

**Dean Yan**  
Dean is experienced in information security and blockchain technologies. Dean got his master degree in Computer Science from Nanjing University of Posts and Telecommunications and majored in opportunistic network. Before Crust project, Dean has been working in Cisco on supply chain blockchain based projects, one of his innovation projects was announced in global Development@Cisco conference.

## Development Roadmap

### M1: AlphaNet – 6 weeks

1. MPoW
   - Implement work report runtime module to quantify storage volume and monitor storage status. Users will be able to check Crust nodes’ empty and meaningful storage volume and status through Crust explorer.
   - Implement TEE (SGX solution) node onboarding and on-chain verification. Nodes with SGX CPU can join Crust network. Users will be able to see nodes’ TEE identity through Crust explorer.
   - Implement dynamic storage scaling feature (including both empty and meaningful storage) to improve network availability. Once nodes’ physical storage space changes, node owners will be able to see nodes’ storage volume automatically changes next era through Crust explorer, without additional steps like node restart or enrollment.
2. GPoS
   - Implement the feature to set stake limitation based on storage volume reported by MPoW work report. Users will be able to check nodes’ (both validators and candidates) stake limit and valid stake through Crust explorer.
   - Implement active stake check based on validators and guarantors’ actions. Users will not be able to stake/vote exceed any node’s staking limit at any time, and a node will not be able to become a validator with no stake limit claimed.
   - Implement passive stake check. At the end of each era, while nodes’ stake limit could be changed according to factors like whole network storage volume and local volume, the stake limit and guarantors’ valid voting stake will be changed accordingly. Users should be able to see the change through Crust explorer.
   - Implement validator set election algorithm. It selects validators from high to low according to the nodes’ total stakes. Users will be able to see validator set changes at each era through Crust explorer.
3. Storage Service
   - Provide basic meaningful storage capabilities. Storage API will be finalized in M2. In M1 Crust AlphaNet will provide basic IPFS interfaces. Users will be able to get/put files through Crust AlphaNet’s IPFS interfaces. In addition, users will be able to see the meaningful storage volume changes accordingly through Crust explorer.
4. Documentation
   - Finish technical white paper and publish on Crust website.
   - Provide wiki on how to explore Alphanet on GitHub.
5. Open Source
   - Provide a basic Github action including building and testing on Ubuntu in crustio/crust repo.
   - Provide a basic Jenkins webhook including building and testing on Ubuntu in crustio/crust-tee repo.
   - Provide a basic Github action including building on Ubuntu in crustio/crust-api repo.

### Future Work

### M2: BetaNet - 8 weeks

1. GPoS
    - Provide fully functional GPoS consensus, including storage based staking limitation and staking allocation;
    - Provide fully functional reward and slash mechanism;
2. MPoW
    - Implement node storage capacity scaling mechanism;
    - Implement TEE based sealing function, which is able to resist Sybil Attach and Generative Attach;
3. Storage Service
    - Provide fully functional storage management and download mechanism;
    - Provide basic storage market and retrieval market;
    - Provide SDKs to upper layer applications and platforms;
4. Documentation
    - Finish economic design document;
    - Provide wiki that contains Crust brief, the guidance on how to join Betanet, and how to test storage service;

### M3: MainNet – 8 weeks

1. GPoS
    - Provide on-chain governance function, users can vote on Crust running parameters;
    - Optimize the storage order space taking, in order to support MainNet in long run;
2. MPoW
    - Support abstract layer of TEE interfaces, in order to adapt to multiple TEE solutions;
    - Provide dynamic account-TEE binding mechanism;
3. Storage Service
    - Support multiple token types in Crust markets;
    - Support multiple underlying storage protocols;
    - Provide fully functional storage market and retrieval market;
    - Implement layer2 flexible storage services including object storage;
4. Documentation
    - Publish the finalized version of economic document and technical whitepaper;
    - Provide the wiki and guidance on how to join Crust network and how to use storage service;

## Additional Information

### What work has been done so far?

1. AlphaNet is now available at https://github.com/crustio/crust/wiki/Join-Crust-Alphanet.
2. Code is open source at https://github.com/crustio/ 
3. Over 30000 lines of code change is done.

### Have you applied for other grants so far?

No.

### How is your project different?

1. **Less complexity and lower running cost:**
    Crust's MPoW mechnism uses trustable local resource inspector to quantify resource usage. It does not require rich computing or network resource to do zero-knowledge proof. 
    Crust's GPoS consensus is simpler. It does not rely on VDF or other unimplemented algorithms.
2. **More decentralized and robust:**
    Instead of relying on "super nodes", Crust's block generation is done by broader scope of nodes. With GPoS requires both storage resource and stake, Crust network is robust and hard to attack.
3. **Accountable economic model:**
    Crust’s incentive is mainly based on un-cheatable storage resource and stake, not on market orders. In Crust storage service income is additional from market. This boosts cold start of the ecosystem and smooth the transition to market-driven.
4. **Cloud computing extensibility:**
    MPoW's trustable resource inspector is also able to inspect and measure computing resource. So besides storage, layer2 computing and close integration with other computing projects will be easily done.
