# General Grant Proposal

* **Project:** Trusted Health Consul

## Project Overview :page_facing_up: 

### Overview

Current project performs real-time in-depth analysis of medical data and automates decisions using machine learning algorithms. This system empowers patients, service providers, and interested third parties and delivers a highly connected, seamless experience at every step in the care journey. Peer-to-peer database architecture provides secure and anonymous data.

Each interaction with medical data is auditable, transparent and secure, and will be recorded as a transaction on THC’s distributed ledger. During this process, the patient’s privacy is protected at all times. With securely shared health data on blockchain database systems, patients can reclaim control and allow access as desired. 

They can benefit from ML-enabled personal care while knowing their data is protected.

#### Integration
 
Development of our project becomes possible as a result of the Substrate ability to deploy a modular blockchain. We plan to connect this parachain to the main Polkadot relay chain to realise  the purchasing of internal tokens. 

Tokens allow users  to access all features of the platform (once all tokens received through initial airdrop have been used up).

#### Motivation

We are convinced that blockchain technologies change the world, and have been working hard to create more transparent solutions. We have been observing and learning Substrate technologies and find Polkadot as the best ecosystem for us to join depending on technology and strong market position. We believe that our protocol will be useful for other companies in the Polkadot ecosystem.

### Project Details 
####Subject: MVP 

Production-ready  web application implements medical tests decoding with issuing recommendations for the indicators obtained. Service is completely decentralized.  [Substrate-based Polkadot parachain]  focuses on anonymizing  and depersonalizing user data (EHR),  wherein  saving access to database for validator accounts. These accounts validate transactions through the interaction with Ml models via the built-in Machine Learning mechanisms, and subsequently produce predictions for certain conditions. If the user has given consent to a further data processing, machines will be retrained. 


#### Internal token 

Blockchain transactions are based on internal tokens. Tokens are not listed on crypto-exchanges and de facto not a cryptocurrency. Users receive tokens in the following ways:

Initial airdrop.
DOT token exchange for internal token through services directly interacting with relay-chain.
Award: 
for providing medical data to a common database with subsequent model training.
prediction confirmation/refutation.


#### Polkadot ecosystem benefits

Our product will attract the decentralized finance community and provide more liquidity that helps drive increased adoption for the Polkadot Network.

We designed unique pallets  to significantly expand capabilities of Substrate in data storage, machine learning and secure access. 


#### Backend architecture scheme


#### Our goal is to have a complete MVP solution based on: 

#### Healthcare DB
The module allows you to work with the built-in key-value database. 

Technology: It is like a wrapper over the database implementing native interaction with the storage (writing/reading). Databases are optimized for  blockchain and for interaction with ML modules. 

Current pallet helps to create secure controlled access to information while restricting access rights to certain parts of it.

Healthcare ML
ML module is based on received data and allows to train models and make forecasts.

Trained models  then train with natively obtained data from Healthcare Db and stay keeping there. Access keys are operated by the blockchain and they bind with validator accounts.

Current pallet helps to interact with trained models for machine learning and neural networks directly from the blockchain runtime. It makes it possible to deploy the principles of machine learning directly to the blockchain network.


#### Sample Scenario


Creation of the user account 
Created through the Polkadot browser extension, it gives permission to the web application to access data
Generation of hosted wallet during registration (or in  account settings) with the ability to export keys.

Uploading of the medical tests
Frontend side:
Upload a .pdf document through a special form.
Parsing .pdf document to identify the required indicators.
Primary indicators validation according to specified criteria.
If insufficient data has been submitted, user receives a message inviting them to submit missing data manually
A valid transaction is generated and then moves to the blockchain.
Waiting for an event to confirm or fail a transaction (after validation and confirmation in blockchain).
Blockchain side
Validation of transaction and its data.
Commission calculation.
Saving data in Healthcare DB with unconfirmed label and getting hash key.
In case the user has consented to data processing
ML model is retrained with new incoming data
Transaction is formed to reward user with tokens
The transaction is sent to the pool and waits for confirmation
Hash link record - user account in the blockchain with unconfirmed status (link available only to the account owner).
Running an internal event for validators to generate prediction based on received data.
Commission write-off and transaction confirmation.
Starting an external event with transaction status.

Getting of the predictions
Blockchain side
Validators receive an event for a prediction request.
Validators make a request to return the ML model from the database.
Prediction is generated with received data through an internal ML algorithm.
Saving prediction results in Healthcare DB and getting a hash key.
Transaction with hash key is formed.
The transaction is validated and written to the blockchain.
Hash link record - user account in the blockchain (link is available only to the account owner).
Launching an external event that predictions have been generated and are available for reading by the account owner.
Front end side
Receiving an event with transaction status to save prediction results.
Getting recommendations from the blockchain.
Parsing results into a humanoid view.
Providing visual results to the user.

Confirmation of the recommendations
Uploading a medical report from a doctor with diagnosis that confirms or refutes the recommendations received.

Blockchain side
Validation of transaction and its data.
Commission calculation.
Running an internal event for validator accounts.
Commission write-off and transaction confirmation.
Starting an external event with transaction status.
Project advisers manually check the medical report.
Upon successful validation, a transaction with a reward is generated and sent to the blockchain.
Launching an external event after transaction confirming.
Frontend side
Uploading .pdf document with medical report through a special form (we recommend to remove personal data that may identify the person)
The .pdf document is loaded into IPFS and we get the hash key
We form and send transaction  to the blockchain, with written hash key
Waiting for event to confirm or fail a transaction (after validation and confirmation in the blockchain)


Repository Hierarchy





There will be three (3) primary directories

Node: A blockchain node is an application that allows users to participate in a blockchain network. Substrate-based blockchain nodes expose a number of capabilities like, Networking, Consensus, RPC Server.

Runtime: The terms "runtime" and "state transition function" are analogous - they refer to the core logic of the blockchain that is responsible for validating blocks and executing the state changes they define. The Substrate project in this repository uses the FRAME framework to construct a blockchain runtime. FRAME allows runtime developers to declare domain-specific logic in modules called "pallets".

Pallets: The runtime in this project is constructed using many FRAME pallets that ship with the core Substrate repository and a template pallet that is defined in the pallets directory. A FRAME pallet consists of a number of blockchain primitives namely, Storage, Dispatchables, Events, Errors and Trait.


### Ecosystem Fit 
Are there any other projects similar to yours? If so, how is your project different?

## Team :busts_in_silhouette:

### Team members

Andrew Skurlatov (Tech lead, backend)
https://www.linkedin.com/in/andrew-skurlatov/

Mike Manko (Head of product)       
https://www.linkedin.com/in/mikhail-manko-97a491a2/
   
Anuar Zhumaev  (Product design)          
https://www.linkedin.com/in/yxorama/

Ivan Podcebnev (DevOps)        
https://www.linkedin.com/in/naykip/

Constantine Czerniak (Data Science) 
https://www.linkedin.com/in/%D1%81czerniak/

Nikita Velko (Frontend)               
https://www.linkedin.com/in/nikichv/


### Team Website	
* https://uddug.com/
(experience, projects, technologies)

### Team's experience
Core of our team is of united, like-minded professionals with solid experience. We are constantly evolving our capabilities to help software technology companies to do more with less: develop software solutions faster and ensure high quality within time constraints, with fewer resources, and lower costs. We combine proven methodologies, business domain knowledge and technology expertise of skilled software professionals to deliver highly optimized solutions and services across a wide range of industry domains.

Team range of experience begins from developing small scaled websites up to complex blockchain architectures. Our projects are diverse, but all of them share the need to have a software solution for human.

### Team Code Repos
* http://github.com/andskur/
* http://github.com/uddugteam/

Commits 
https://github.com/uddugteam/thc-node/commits/master


## Development Roadmap :nut_and_bolt: 

This section should break out the development roadmap into a number of milestones. Since the milestones will appear in the grant contract, it helps to describe the functionality we should expect, plus how we can check that such functionality exists in the product. Whenever milestones are delivered, we refer to the contract to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions it should be clear how the project is related to Substrate and/or Polkadot. We recommend that the scope of the work can fit within a 3 month period and that teams structure their roadmap as 1 month = 1 milestone. 

For each milestone:
* Please be sure to include a specification of the software. The level of detail must be enough so that we are able to verify that the software meets the specification.
* Please include total amount of funding requested per milestone.
* Please note that we require documentation (e.g. tutorials, API specifications, architecture details) in each milestone. This ensures that the code can be widely used by the community.
* Please provide a test suite, comprising unit and integration tests, along with a guide on how to run these.
* Please commit to providing a dockerfiles for the delivery of your project. 
* Please indicate the milestone duration, as well as number of Full-Time Employees working on each milestone, and include the number of days along with their cost per day.

### Overview
Total Estimate Duration 4 months
FTE from 3.5 up to 4.5 
Total Costs $67 800 
License GNU GPL v3

### Milestone 1 - Distributed Database

Duration 2 months
Costs $29 500
FTE 3.5

We will create a Substrate pallet that will provide a distributed ipfs-based key-value database. The goal is for it to store a big amount of  data off-chain and store on-chain only ipfs hashes as database keys. Module will be integrated  with an encryption pallet from previous milestones with out of the box data encryption support.
We will deliver a working module, along with a simple tutorial that explains how a user can spin up one of our Substrate nodes. It will be possible to test functionality on our node.
We will update our web application with new components for interacting with the database.
The code will have proper unit-test coverage to ensure functionality and robustness.
We will provide complex quality Assurance for all platform features.
We will update our Docker image with a new version of our Substrate chain, demonstrating its functionality.
We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.

***Milestone  2 - Embedded Machine Learning

Duration 2 month
Costs $38 300
FTE 4.5

We will create a Substrate pallet that will provide a configurable machine learning module with allowance to make on-chain predictions based on ML algorithms  (prefered random forest). Module will be closely integrated with Distributed Database and Encryption pallets. All dataset will be stored securely in IPFS with allowance to encryption and users can control access to their predictions results and provided data.
We will deliver a working module, along with a simple tutorial that explains how a user can spin up one of our Substrate nodes. It will be possible to test functionality on our node.
We will update our web application with new components for interacting with the database.
The code will have proper unit-test coverage to ensure functionality and robustness.
We will provide complex quality Assurance for all platform features.
We will update our Docker image with a new version of our Substrate chain, demonstrating its functionality.
We will provide both inline documentation of the code and a basic tutorial describing how the software can be used and tested.


## Future Plans

UI/UX optimization
ML model optimization
Uprising the number of datasets
Mobile application
Fully health monitoring and management solution
Medical research (on population / groups / individuals)

## Additional Information :heavy_plus_sign: 

Many of the components in this project have already been created.

Proof of concept

Prototype overview: Substrate-based blockchain with all accompanying infrastructure enables account users to upload securely their medical data and then receive predictions on the probability of developing certain conditions. At this stage, we test business hypotheses, build product architecture and develop prototype.

How It Works 

User creates an account via a browser extension and gives permission to the web application for access.
Each account has tokens for transactions within the system.
Users can upload their data through the form in the web application interface.
When data is being loaded the transaction occurs into the blockchain.
Before the transaction is included in the block, the data is validated.
Upon successful transaction and  validation the user data is written to the    blockchain.
ML pallet creates predictions with the help of trained model based on the received data.
The model retrains with a new data
Predictions are recorded to blockchain.
Predictions are recorded into the blockchain and fixed to an account.
Web application catches the prediction record event and presents it to the user.

Components

  Healthcare Substrate Node
	Stack: Rust, Substrate, WASM

The main node with extended POE and ML pallets organizes connection between accounts, medical data, predictions and transaction validation extensions.
2.          Web Application
Stack: Javascript, React, Redux, Websocket

SPA web application is a modified polkadot-js-app / substrate frontend template add in of blockchain-specific healthcare Ui / Ux elements and methods of communicating with the node. 
Websocket JSON-RPC API - interaction with node. 
             Account management is possible via the Polkadot browser extension.


Advisors and medical institutions support

We have reached agreements with medical institutes in the field of further development of the project such as belgium University of Antwerp and russian Pirogov Medical University on the further development of the project, in particular, providing access to their databases, as well as the creation of specialized departments on the basis of institutes for the innovative development of universities, promotion, participation in healthcare exhibitions and advisors.

 
Personal contribution 
 
The development of the prototype and initial research started with the personal funds. 
 
Other foundation 
 
We have not applied for any other grants with this project. But we have applied for the Substrate Builders Programm and  have proceeded with general interview to iterate around steps going forward. Also we are planning to start discussion with Blockchers.



