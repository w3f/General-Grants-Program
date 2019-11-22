# APOIS by Swisscom Blockchain

## Project Description

APOIS by Swisscom Blockchain is a set of tools with the aim to easly deploy and monitor Validators through multiple deployment templates on the most popular cloud platforms using modern devops tools such as Ansible, Terraform, Azure Resource Manager, AWS Resource Manager, etc.
The main focus of the project is the **Kubernetes Operator**. The Operator will make it easy for anyone to set up their own, sophisticated Polkadot validator including a highly secured network of sentry nodes.
This will help making the network as a whole more robust and less prone to attacks on individuals, thus increasing its trustworthyness.

## Team Members:

Jan Bernegger (Lead, DevOps)
Alessio Onori (DevOps)
Jorge Alvarado (Project Manager)
Milos Costantini (Software Developer)

## Company Website

- https://www.blockchain.swisscom.com/

## Linkedin Profiles:

https://ch.linkedin.com/in/jan-bernegger
https://www.linkedin.com/in/alessioonori/
https://ch.linkedin.com/in/alvaradojl
https://www.linkedin.com/in/miloscostantini/

## Legal Structure

Provided in the Google Form.

## Team's experience

- Swisscom Blockchain is a team of software, cryptocurrency & business experts focused on the blockchain ecosystem.
- We built a python wrapper of the Rust Indy SDK.
- For the NEO Fundation we built Seraph ID, a set of tools that can be used by dApps developers and users to leverage Self-Sovereign identity capabilities. It relies on the W3C standards providing DID and verifiable claims functionalities. The set of tools comprehend a C# Smart Contract an SDK and a chrome extention wallet with dapp communication.
- We audited part of the Energy Web Foundation codebase (Work done together with Chainsecurity, who audited the Solidity Smart Contracts)
- Strong DevOps and Node deployment expirience gained building our DAPPI Product (Node Hosting and gateway)
- Expirience in Solidity gained building ERC20 Smart Contracts with extended functionalities and a Smart Contract Factory to easly deploy ERC20 and ERC721 trough UI and using
  the proxy pattern.

## Company Code Repository

https://github.com/swisscom-blockchain

## Specification

### Node Deployment Templates

Templates to reduce the time required to setup and run a Polkadot node and all its tooling.

1. Terraform templates for setting up the required infrastructure to run (validator) nodes
2. Ansible templates for provisioning (validator) nodes, its libraries and tools
3. All templates will be available for Azure, AWS and GCP

The goal is to simplify Polkadot (validator) node deployment so that it only takes one command to have the infrastructure up and running.

### Kubernetes Operator for Validator deployment

A Kubernetes Operator is a pattern that allows complex application deployments through configuration of the desired state using a Kubernetes Custom Resource Definition (CRD).
The resulting Operator will be able to do the following tasks:

1. Deploy the operator with one command on a Kubernetes cluster
2. Use Custom Resource Definitions (CRD) to describe a valid validator sentry deployment on a Kubernetes cluster
3. Secure the communication between the sentry nodes themselves and the validator
4. The possibility to provision a validator node as well within Kubernetes in the deployed secure environment
5. Expose all required ports and enpoints of the nodes for cluster monitoring using Prometheus
6. Possibility to connect the node network to another one setup on a different cluster through the operator (also supporting other cloud providers)

The Operator will make it easy for anyone to set up their own, sophisticated Polkadot validator including a highly secured network of sentry nodes.
This will help making the network as a whole more robust and less prone to attacks on individuals, thus increasing its trustworthyness.

## Operator Development Roadmap

### Milestones

* **Milestone 1 - Operator Setup**:
  * Create Go based operator structure
  * Define CRD spec for validator sentry nodes
  * Define CRD spec for validator node
  * Deployment of CRD through Kubernetes native resources
  * Connection between sentry nodes and validator
  * Basic documentation

* **Milestone 2 - Operator Functions**:
  * Data persistence support
  * Node cluster scaling support
  * Updating of node versions
  * Secure communications

* **Milestone 3 - Validation and Measurement**
  * Testing and optimisations
  * Metrics support using Prometheus
  * Support different methods of exposing node endpoints
  * Interconnecting node networks
  * Finalize documentation

### Deliverables
* **Milestone 1**:
  * Operator that is able to do a simple one-time deploy of sentry nodes and validator

* **Milestone 2**:
  * Operator that supports modification of the deployments of a sentry node cluster and validator on-the-fly

* **Milestone 3**:
  * Resources deployed through the operator can be monitored with Prometheus and can be connected over different deployments
## Longer-Term

We are very interested in POS blockchains and Polkadot appears as one of the more promising and interesting from a technological point of view. We are facinated by the
decentralized bft/nakamoto consensus algorithms that use Proof of Stake; our long-term vision is to build a strong expirience on all of these networks and integrate them in our Swisscom Blockchain DAPPI service.

## Additional Information

- ## What work has been done so far?
- Are there are any teams who have already contributed (financially) to the project?
  - No
- Have you applied for other grants so far?
  - No
- Are there any other projects similar to yours? If so, how is your project different?
  - For the Kubernetes Operator for Validator depoloyment we didn't find anythig similar to our project.
  - Regarding the Node Templates our scripts will be able to deploy to multiple clouds incl Azure, Google and Amazon using terraform. There is already a template available but the goal would be to simplify Validator node demployment so that it only takes one command to have the infrastructure up and running.
