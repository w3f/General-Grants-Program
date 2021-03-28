# Delegate your nominations

* **Status:** Open
* **Proposer:** [mmagician](https://github.com/mmagician)

## Project Description :page_facing_up:

Busy Polkadot users often don't find time to periodically check their nominations and could end up staking with the validator that is no longer in the active validator set for a while, thus missing out on the nomination rewards.

The idea is that we allow users to `delegate` their nomination to another user whom they trust. This could also be a fund manager or even a smart contract that select the "best" validator.

This is a double-edged sword, as it comes with a danger of less decentralisation, as users won't be directly involved in the decision making.

However, with the rise of staking services among centralised exchanges which attract users precisely for the reason that it's "click & forget, receive payout", one could argue that delegation of your nomination power is advantageous over that model:
- the actions of your friend/fund manager are on-chain, and therefore transparent
- users still receive their payout with every block (as opposed to bi-weekly, monthly or yearly with centralised exchanges)

## Deliverables :nut_and_bolt:

* **Total Estimated Duration:** 1 month
* **Full-time equivalent (FTE):**  1 

### Milestone 1 - Delegate call

* **Estimated Duration:** 1 month

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 1. | Delegate call | Add another public method to the `staking`[https://github.com/paritytech/substrate/blob/master/frame/staking/src/lib.rs] pallet. The method should accept parameters listed below and work just as if the user nominated directly (i.e. payouts, slashing) |

## Discusson

It is TBD whether a user can delegate their "nomination power" to a single party or split the tokens across multiple parties.

Clearly this will affect the logic complexity (what happens when one party gets slashed and not the others) & storage (a map vs. tuple per user)

In the case of the former, the logic should be able to handle adding further tokens to the delegation, as well as removing a part of the token. Perhaps behind the scenes it could clear the delegation completely & create a new entry in the next block, but the user should be oblivious to the implementation details and have a smooth UX.

Before proceeding with this development, the details should be discussed in Polkadot/Kusama channels and likely developed in collaboration with core FRAME developers.

### Parameters

- the amount(s) to delegate
- the target address(es) to trust

