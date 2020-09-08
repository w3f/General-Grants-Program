**Bool Network And Filecoin Bridge**

**Project Overview**

The ultimate goal of the transit bridge is to be able to transfer any message from the outside to the target chain in a trustless manner, and vice versa. This is a very challenging problem. In this project, we will implement basic trustless asset conversion between Polkadot and Filecoin. We will design a set of transit bridge specifications and implement a minimal executable environment.

The reason why it is good for the Polkadot ecosystem is because it connects the emerging Filecoin ecosystem to the Polkadot ecosystem and bring the large user base and online traffic of Filecoin to the Polkadot. 

Technically, the Bool Network provides a transit bridge service based on TSS which will extend the ways to implement the bridge in Polkadot. 

ABMatrix Team is dedicated to blockchain technology with the mission “Establish the trust with blochchain technology”. ABMatrix was founded on May 2018. It has been working on providing the professional blackchain technology services since then. ABMatrix has been developing projects with Rust on Polkadot for long time. We share Polkadot mission of “envision a web where our identity and our data is our own – safely secured from any central authority”. Therefore, we believe it is our job to connect two of the most influential blockchain ecosystem Polkadot and Filecoin with bridge.

In addition, in August 2019, ABMatrix team won the third prize of the world's first substrate developer competition. In April 2020, we were selected into the first Web3.0 Bootcamp initiated by Wanxiang blockchain Lab, Parity and Web3.0 Foundation. 

**Project Details**

To connect FileCoin to bool chain, we need effective proof to verify the correctness of transactions and events. In short, a message courier will deliver a valid Filecoin block set to the bool chain, and each verification node will verify the validity of the block set. Then any user submits the transfer transaction and proof, the verification node will release the corresponding assets after the verification is passed.

![图片1](file:///C:/Users/yangc/AppData/Local/Temp/msohtmlclip1/01/clip_image002.gif)

From the bool chain to Filecoin, considering that Filecoin is unlikely to implement the parachain of the bridge chain and there is no smart contract, we use the TSS scheme to sign the redemption transaction and submit it to Filecoin.

The core function of the transfer bridge is asset transfer. The following figure describes the relationship between user operations and core modules.

 

![img](file:///C:/Users/yangc/AppData/Local/Temp/msohtmlclip1/01/clip_image004.jpg)

 

**TSS engine**

This module synchronizes the information between TSS nodes through the chain events of substrate.

After the module is started, it monitors all TSS-related events defined on the chain of the substrate, and performs TSS and substrate-related operations through different events. The operation includes creating TSS' pubkey initialization, letting the TSS node sign the transaction for the constructed transfer transaction, and sending the signed fund release transaction to the substrate chain or the Filecoin chain.

 

pub enum TokenType {

  FC, //Asset type FC = FileCoin currency

}

pub struct TxMessage {

  /// The type of Message.

  pub tx_type: TxType,

}

pub enum TxType {

  TssKeyGenSubstrate(Vec<u8>,Vec<Vec<u8>>), // TSS KEY generation transcation for substrate address

  TssKeyGenFilecoin(Vec<u8>,Vec<Vec<u8>>), // TSS KEY generation transcation for filecoin address

  SubstrateDeposit(Vec<u8>,TokenType,u64), //The event of releasing funds FilecoinDeposit(Vec<u8>,TokenType,u128), //The event of releasing funds

}

*Description*

Tss Service will listen to these events on the chain and act accordingly.

 

pub struct TxSender<A,Block,B,C>

  where {...}

{

  pub client: Arc<C>, // substrate client to get information on the chain

  pub tx_pool: Arc<A>,// substrate transcation pool

  //pub key: KeyStorePtr,

  pub ed_key: edPair, // ed key to sign substrate tx

  pub packet_nonce: Arc<Mutex<PacketNonce<Block>>>, // nonce counter of ed key abov

  _phantom: PhantomData<B>,

}

*Description*

Save the private key, maintain the local nonce, as well as the client and txpool to send some on-chain transactions to save information to the substrate, such as the pubkey and sub-pubkey of TSS and the signature result, etc.

 

pub enum TssRole{

  Manager,

  Party,

}

*Description*

Start mode when starting, Party starts as TSS node.Manager starts as a node that helps TSS forward information.

 

pub enum SignatureType{

  FileCoin,

Substrate,

  Others,

}

*Description*

Control tss signature type, filecoin substrate, etc. can be extended.

 

pub struct TssSender<V,B> {

  pub spv: V, //A tool for sending transactions to the chain

  pub sendersubstrate: FcPubkeySender,//channel to receive substrate related messages

  pub senderfc: FcPubkeySender,//channel to receive filecoin related messages

  pub a: std::marker::PhantomData<B>,

}

*Description*

Save all kinds of tools needed for start, and then constantly monitor and react to message events on the chain, and in some events, transactions will be sent to the chain.

 

pub fn start(self,

role: TssRole, // What mode is used in TSS startup

rocket: bool, // Start the server

​    ) -> impl Future<Output=()> +'static

*Description*

start then constantly monitors the message events on the chain and reacts to them, and in some events, transactions are also sent to the chain.

 

fn submit_fc_transfer_tss(&self, relay_message: TxMessage)

*Description*

This interface is used when transferring. After the analysis by TSS Signer is completed, the substrate transfer transaction will be constructed and TSS signed, and then the transfer transaction will be released on the chain to release funds. The outbound interface is monitored by start to obtain the rollback operation of the operation on the chain, and then the filecoin transaction is constructed and signed by TSS and then on the chain.

 

**TSS RUNTIME**

This module acts as an intermediary module between TSS Engine and human operation to achieve interaction.

The initialization process of Filecoin and substrate pubkey triggered by TSSRUNTIME module,

The event generated by this operation will be executed by the TSS Engine and the generated pubkey will be sent back to this module and publicly recorded on the substrate chain as the payment address and refund address of the two chains.

It will also accept TSS Engine to send on-chain signature results to save records after implementing TSS signatures.

 

fn key_gen(origin, url:Vec<u8>,store:Vec<u8>,type:Type) -> DispatchResult

*Description*

Let TSS Engine generate the tsskey used by the address of the substrate or filecoin.

 

fn set_tss_url(origin,url:Vec<u8>) -> DispatchResult

*Description*

Through this interface, a public TSS interactive service URL that is visible to all TSS nodes can be set,

This service helps information forwarding and interaction between TSS nodes.

 

pub fn key_created_result(

pubkey:Vec<u8>, // publickey generated by tss

pubkey_vec:Vec<Vec<u8>>, // child publickey of complete publickey generated by each child node

store:Vec<u8>, // The alias for this public key

keytype: TssKeyType // Public key type:Filecoin=0,Substrate=1,

) -> DispatchResult

*Description*

The TSS Engine module calls the pubkey generated by TSS on the chain through this function.

The keytype can ensure the scalability of accessing other tokens in the future.

 

pub fn check_permissions(id: T::AccountId) -> DispatchResult

*Description*

This module is dedicated to the authority control, and the interface of the module can be operated only by specifying the account address to prevent illegal data from being submitted maliciously.

 

pub fn add_new_member(id:T::AccountId)

*Description*

Special permission control for this module, adding operable people.

 

pub fn delete_member(id:T::AccountId)

*Description*

Special permission control for this module, delete operable persons.

 

**Filecoin relay service**

The main job of this service is to get information on the chain from the outside. Assuming that the relay service is credible and will not do evil, then the asset is credible across the chain. Of course, the above assumptions do not exist in reality, so we are just a general term for relay services, and there are no special restrictions. Anyone can serve as a relay service.

 

At present, the interoperability of the blockchain is demonstrated through the RPC service. We give a simple version of the relay service implementation. Obtaining block chain header data and transaction data from Filecoin full nodes through RPC is the first step of the relay service. Secondly, the service also parses Filecoin's block header and extracts the transaction information of the designated transfer-in address. Then parse out the mapped address A and cross-chain amount V, and construct a substrate transaction and submit it to the chain.

 

Simple implementation of relay service requires access to Filecoin data, here we use LotusApi.

pub struct Relayer<V,B> {

  pub spv: SuperviseClient, 

  pub reciver: MessageStreamR<Value>, 

pub lotus_api: LotusApi,

}

 

**Ecosystem Fit**

There are two projects Bifrost and pLIBRA share some similarities with Bool Network. All of the projects use parachain to transfer external assets to the Polkadot ecosystem. When transferring assets to the sub-chain, Bifrost uses multi-signature technology, while Bool Network uses a multi-party secure computing TSS solution, and pLIBRA uses trusted execution environment (TEE). In the implementation of multi-party security computing, pLIBRA favors hardware, while bool applies software method.

**Team members**

- Team Leader Jingzhong Xu
- Founder and CEO of ABMatrix
- Master of Software Engineering     from Zhejiang University, senior research expert on blockchain, former     Alibaba big data engineer and Chairman of Zhejiang University Blockchain     Association. He has a wealth of big data analysis, data mining and     blockchain development experience. 

 

- Chen He
- ABMatrix Partner
- Master of Laws from Jilin University, Economic Manager, National Fund Practitioner, Certified PPP     Manager in China. She worked in the School of Information Technology of Peking University and Zhongguancun Internet Financial Service Center.  Currently she serves as the President of the Hangzhou Bay Industrial Financial Service Center and was selected as the "3315 Series Talent Plan" in Ningbo and recognized as the top financial talent in Ningbo.

 

- Chao Yang
- Partner of ABMatrix, COO
- Bachelor of Computer Science from Zhejiang University, Master of Computer Science from University of     Utah. With 10 years of work experience in Silicon Valley technology companies, he has a rich research background in distributed storage and computing, big data, artificial intelligence, and blockchain.

 

- Kang Li
- Chief Cryptography Expert of ABMatrix
- Doctor of Hong Kong Polytechnic University, Master of Nanyang Technological University of Singapore,     experts in computer network, computer system security, database system.  His research focuses on security protection and privacy cryptographic schemes, including various digital signatures, zero-knowledge proof technologies, etc. He has long-term dedication in various blockchain system architecture designs.

 

- Kaiyu Lu
- CTO, Chief Architect of ABMatrix
- Graduated from Hangzhou Dianzi     University, with extensive experience in the development and design of the     underlying blockchain platform, and an expert in smart contract     programming models, cryptography, and formal verification.

 

- Quanzhan Lu
- Senior Blockchain R&D Engineer
- Bachelor of Engineering from Jilin University, IPFS/Filecoin distributed storage technology researcher,     with many years’ experience in the system architecture design and development of various blockchain projects.

 

- Ruizheng Pan
- Senior Blockchain R&D Engineer
- Master of Engineering from     Zhejiang University, with in-depth research on consensus algorithms and     cryptography, and long-term participation in the system architecture     design and development of various blockchain projects.

 

- Yilai Tan
- Blockchain R&D Engineer
- Graduated from Harbin Institute  of Technology with a major in information security. He has in-depth     research on consensus algorithms and cryptography, and is mainly engaged in research and development related to zero-knowledge proof.

**Team Website**

https://bool.network/team.html



**Team's experience**

Hangzhou Encryption Matrix Technology Co., Ltd. was established in May 2018 and is the second batch of blockchain companies in the country approved by the Ministry of Industry and Information Technology. It has four invention patents since its establishment two years ago and has become a professional cross-chain gateway technology service provider with strong development capability in China. In Hangzhou, known as the "blockchain capital", with the mission of "Establish trust with technology", we provide intelligent operation solutions for distributed businesses. The team has industry-leading computing and distributed storage research and development capabilities, and has core technologies and patents in blockchain infrastructure such as cross-chain, BaaS platform, consensus algorithm, privacy protection, and smart contracts. The technical team completely independently developed the "Hyperspace Accelerator" platform HA (Hyperspace Accelerator), based on the space-time proof + copy proof + consensus algorithm, deep reconstruction of the underlying code, and is one of the early players in the field of distributed storage.

**Team Code Repos**

- https://github.com/boolnetwork

**Team LinkedIn Profiles**

·    https://www.linkedin.com/in/jingzhong-xu-b066951a8/

·    https://www.linkedin.com/in/chao-yang-a228971b6/

·    https://www.linkedin.com/in/chen-he-2807431b6/

·    https://www.linkedin.com/in/a49578ab/

·    https://www.linkedin.com/in/lukayryu/?locale=en_US

·    https://www.linkedin.com/in/quanzhan-lu-41944161/

·    https://www.linkedin.com/in/ruizheng-pan-a61563152

·    https://www.linkedin.com/in/yilaitang-29ba9b1b2/

 

**Development Roadmap**

**Milestone 1 — Implement TSS Runtime Modules — 1 month — (Two full time developers and one part time project manager)**

·    Initialize TSS Runtime interface, TSS engine, API.

·    For the TSS Runtime interface, the TSS engine creates the initial underlying module and structure, and fills in the simulation function.

·    Implement filecoin token mapping module.

·    Users can access nodes through polkadot.app, call TSS runtime and token functions to return simulation data.

-  

**Milestone 2 — TSS Engine — 1 month —  (Two full time developers, one part time project manager and one part time QA)**

 

·    Save the private key, maintain the local nonce, as well as the client and txpool to send some on-chain transactions to the substrate.

·    Directly control the adaptation of local TSS nodes

·    Verification verification system to verify the correctness of Filecoin transactions

·    Users can deploy TSS Engine, create a private key through the interface, and sign any message.

·    ![img](file:///C:/Users/yangc/AppData/Local/Temp/msohtmlclip1/01/clip_image006.jpg)

·     

![img](file:///C:/Users/yangc/AppData/Local/Temp/msohtmlclip1/01/clip_image008.jpg)

![img](file:///C:/Users/yangc/AppData/Local/Temp/msohtmlclip1/01/clip_image010.jpg)

**Milestone 3 — Implement Filecoin Relay Service and Integrate Them — 1 month —  (Two full time developers , one part time project manager and one full time QA)**

·    Implement the rust version of lotusApi.

·    Realize FileCoin block and transaction analysis, and support structured data on the chain.

·    Provide TSS Engine, full node, TSS information interaction service DockerFile.

·    The integration test script of the project.

·    Deployment documents and usage documents for each milestone.

·    Users can deploy the project according to the document, and can freely convert assets between filecoin and bool chains.

·    ![img](file:///C:/Users/yangc/AppData/Local/Temp/msohtmlclip1/01/clip_image012.jpg)

**Future Plans**

- The first version uses the TSS scheme. The premise is that there is an honest relay service. In order to make it relay agnostic, we will introduce a parachain mechanism in the future. That is to implement Filecoin on top of substrate, which can verify the validity of blocks and transactions.

**Additional Information**

- What work has been done so far?

- - We have implemented TSS third party multi-party-ecdsa library and investigated the Filecoin project.

- Are there are any teams who have already contributed (financially) to the project?

- - No.

- Have you applied for other grants so far?

- - No.

 