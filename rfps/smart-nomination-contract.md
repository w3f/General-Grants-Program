# Validator selection smart contract

* **Status:** Open
* **Proposer:** [mmagician](https://github.com/mmagician)


## Project Description :page_facing_up: 

Nomination is not such a trivial task as it may seem. It requires an active effort on the part of the nominators in order to maximise both the network security as well as their own rewards.

There are a couple of reasons for this:
- new validators joining the ecosystem might have something better to offer
- validators from the previous active set might no longer make it to the set in the next session
- validators leaving the ecosystem
- previous validators degrading their performance
- validators increasing their commission
- validators actively blacklisting nominators

In an attempt to tackle these challenges, we propose a smart contract which automatically distributes the nominator's stakes to the best validators, based on the qualitative preferences of the user.

### Preferences
Different users might care about different criteria when selecing for their validators, for example:
- comission
- performance in the last X sessions
- inclusion in the active set in the last X sessions
- total number of sessions active
- slashing history
- etc.

We would like to propsoe a solution that fits all types of user preferences. There are two possible approaches:
1. Create a single contract that takes various input arguments and has internal logic to adjust for the given preferences
2. Create various smart contracts, each with a different nomination strategy (e.g. one to maximise payout, another to select for lowest slashing history etc.)

### Drawbacks

The most obvious drawback of such an approach is the potential for aggregating all the nominations across only a small subset of validators. If this turns out to indeed be the case, perhaps some randomness can be introduced into the contract (e.g. when both validators offer a 5% commission, choose randomly as opposed to alphabetically).

However, we argue that such an approach on-chain is still advantageous to centralised nominations that services like Kraken offer to users. This is the main point that we try to circumvent: make it as easy as clicking a button (or adjusting some sliders) for the user, so that they prefer an on-chain, transparent approach.

## Deliverables :nut_and_bolt:


* **Total Estimated Duration:** 3 months
* **Total Costs:** 30,000 DAI

### Milestone 1 - PoC on Relay Chain

* **Estimated Duration:** 2 weeks


| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Basic smart contract for nomination | Create a contract which takes a validator's Address as input. It should also accept a value of how much to stake. |
| 2. | Runtime | Create a runtime mimicking that of Polkadot with regards to nomination & validation (i.e. include [staking pallet](https://docs.rs/pallet-staking/3.0.0/pallet_staking/)), but include a smart contract pallet as well where the contract would be deployed. 
| 3. | Local testnet | Run a local testnet (should be a scripted / Dockerised deployment) with multiple validators and the above runtime.
| 4. | Deploy & test | The smart contract should be deployed to the local chain. A user should be able to call it with the Address & value, and the contract should nominate the specified validator.


### Milestone 2 - PoC on Parachain

* **Estimated Duration:** 2 weeks
* 
| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Runtime | Rather than including the `contracts` pallet in the relay chain, use the provided Rococco chain, and deploy a test parachain with smart contract capabilities (to mimic the envisioned Polkadot setup)
| 2. | Deploy & test | Verify that the smart contract, being on a parachain, is still able to control the nomination of a user for selecting relay chain's validators.

### Milestone 3 - Read relevant information from the chain

* **Estimated Duration:** 1 month

| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Smart contract logic | The logic for selecting the validator should still be dummy (i.e. just use input). In this milestone, it's all about reading the relevant information from the chain, as outlined in the list in the [Preferences](#Preferences) section.
| 2. | Reading the values | Anyone should be able to query the smart contract and ask for the relevant information, e.g. inclusion in the active set in the last 10 sessions.

### Milestone 4 - Custom logic

* **Estimated Duration:** 1 month

| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Validator selection | Putting all the pieces together, a user should be able to supply as input the various preferences/weights he gives to each criteria. The smart contract will calculate the most appropriate validator(s) and nominate the user's stake to these.


### Milestone 5 (optional or seperate follow up grant) - Frontend for interaction

* **Estimated Duration:** 2 weeks

| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Frontend | To ease the user's interaction with the developed smart contract, they should be able to interact with it visually, e.g. sliders for selecting weights. There should also be a simple option with a buttom "nominate", that would (randomly? average of latest weights?) select the criteria, minimising the users' effort even further.
| 2. | Polkadot-js integration | The frontend should integrate with Polkadot-js extension.
| 2. | Deploy to IPFS | The frontend should be deployed on IPFS


Note that each milestone should come with an extensive suite of unit (especially for 3 & 4) and integration (1 & 2) tests.

