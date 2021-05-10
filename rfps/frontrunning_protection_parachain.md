# Frontrunning protection

## Motivation

At the moment, there are no built-in (native) protection mechanisms against front-running in Polkadot

## Options

There exist a number of options at different protocol layers.

### Smart-contract layer

Solutions such as Submarine Sends offer an annonymizing set that is implemented as a smart contract. It does not offer perfect anonimity but rather is constrained by the size of the set of all other Tx's which fulfill special criteria: previously unused address & **value** amount in a certain range.
This solution also suffers from the typical delays known to commit-reveal schemes, where the Tx is only finalised after the reveal part, thus introducing a couple blocks of setback.

### 

## Anti-frontrunning parachain

While still suffering the commit-reveal delay, we propose a solution that offers full anonymity and is shielded from any front-running attacks. The only forseeable downside is susceptibility to censorship, especially on a PoS blockchain.

In the new mechanism, transactions are split into two types: Commits and Reveals. This is achieved either by attaching an extra field `type` or by wrapping all Tx as another data type which has a `type` field.


### Finality

Currently, blocks are considered final after their branch has been voted by 2/3 of the active validator set as final. This is the point when the transactions that were included in such blocks become "rightful", i.e. are accepted by (majority of) the network.

Not much changes regarding finality mechanism in the anti-frontrunning parachain. The majority of the changes happens during block production, which must be tightly coupled to finalised blocks.

### Storage and priority

(permanent) On-chain storage is only affected when a transaction has been Committed (and finalised) and Revealed (and finalised). Since, by definition, there are two types of Txs (and we might be getting both types, for unrelated Txs, in any block), we might need to pick out only a subset of Txs that we even look at. 

We need to de-reference all Commits relevant to a finalised block and apply their extrinsic in order that they were Committed (else we are yet again subject to a frontrunning attack):
1. Get all Reveal Txs from a finalised block
2. For each Reveal, find its corresponsing Commit (we might need to look in multiple different blocks, but not too far ahead since Txs are limited by TTL)
3. Order the Commit Txs by block number (and if multiple within block, by placement in the extrinsic list)
4. Following the Commit Txs order, apply the extrinsics from Reveal Txs, hence modifying the storage.


### Block production mechanism

Under the proposed mechanism, a Commit transaction can be included in any block by the active parachain collators.

All Commit transactions have a short Time-To-Live (TTL) as a mechanism to prevent spamming. The concrete scenario to circumvent is that of collators bloating the blocks by including a range of potentially beneficial Commit Txs, and only selectively publishing Reveals which benefit them.

A Reveal Tx, however, should only be put into a block if there is a corresponding alive Commit Tx that attests the validity of the Reveal Tx. It is required for the Commit Tx to already be in a finalised block to be valid (at time of submission)

A collator is free to include invalid Tx in a block, but these should be rejected by the peers (and relay chain validators) given the invalidity of transactions it contains.

### Refundable Commit fee
In order to submit a Commit Tx, a user must attach a "deposit" - a high, refundable fee that will be returned upon successful reveal.

Commit Tx contents are secret, so attackers don't have a way of knowing what they're attacking. Cost of executing a sandwich attack will be very costly, as they would need to publish a range of transactions in the hope that their Txs manage to sandwich an honest trade.

Fee is returned to sender upon a successful Reveal. This opens up another attack vector for collators, namely censoring transactions and causing loses for users (without any cost nor benefit to the block producer).

In the case of a "forgotten" Commit, the attached fee is either burnt or returned to the treasury.
 

### Option 1: Reveal Txs Receipts / Broadcast proof
We would like to force collators to issue a receipt of each Reveal Tx received. It's kind of like a collator committing to including a particular Tx.

The problem is that as soon as the collator sees a Reveal Tx, they know the contents of the original Commit and can decide to censor the Reveal, leading to sender's punishment.

Maybe instead of collators submitting receipt proofs, the sender could create a "broadcast proof" and rely on at least one collator-listener being honest.

If a malicious collator then omits a Reveal (and by design, they are supposed to prioritise Reveals), then another peer can "report" on them, thus causing a slash for dishonest behaviour.

The challenge that still stands is how to get a proof of submission. It seems that we need to "convince" a collator to collaborate on this?

### Option 2: Longer TTL to leverage rotation in PoS

Maybe, because it's PoS, we don't need to have this incentive mechanism, at the expense of allowing higher TTL.

Then we hope that even if one collator ghosts us, there is a very high chance that next block will be produced by another, hopefully honest, collator. Then we need to think of how many potentially malicious collators we have and so how many blocks on average it will take for our Tx to get included. 

In the end, it doesn't matter for security whether the Reveal is done after 2 or 10 blocks, since by design the order is determined by Commit Txs. The only thing suffering, of course, is UX if someone has to wait 10 blocks...

Hopefully one could show that the number won't ever be higher than say 5 -> then 30s should be an acceptable price to pay for frontrunning protection.

### Option 3: Incentivise Tx inclusion by high fees

One could argue that there are three rational strategies for any collator when deciding on whether or not to include a Reveal Tx:
a) follow the rules and include it
b) ignore it (as a griefing attack to the sender), or
c) not include it, and after learning the content of the tx, produce a Commit tx that front runs it, and include that in a block, in the hope that it will get finalized and the collator will be able to include the corresponding reveal tx, before the original reveal tx is included in any block.

If we assume each collator acts only in their best interest (not necessarily honest, but not colluding with other either), then they could all decide to go with strategy C. In the extreme case, the original Reveal Tx will never make it from the mempool to the block, but rather each collator would be trying his luck in getting the Commit that front-runs it included, and then hoping to get lucky and get a chance to further include the Reveal, without it expiring.

In a generic block authorship system, some block producers might have more chances than others to include two consecutive blocks (especially for PoW).
In the case of our NPoS mechanism, however, the chances that you get to "choose" twice in a row are 1/|active validator set| (although with a larger TTL of n blocks, this generalises to n/|active validator set|).

Therefore, it seems logical to make the fee for Reveal Txs high enough in order to offset the potential MeV of a frontrunning attack. The actual value could be variable per Tx and could depend on the size of the active validator set as well as the value of the Tx itself (or rather, the potential MeV, which is expected to be lower than the Tx value itself for most cases).

Hopefully, at the end we can prove that the only stable equilibrium is one where everybody picks strategy A.

### Option 4: Quorum of collators signing a Reveal Tx

Either as an alternative to the above options or more likely, an enhancement:
We introduce the need for a quorum of collators to sign a set of reveals from a block before they go into a new block. They wouldn't sign the set of reveals if they'd seen an extra reveal for a while that was not included in the set. That way it would be harder for the one collator producing the block to censor individual reveals.

## Changes needed

1. Extrinsics should be wrapped as being either Commit or Reveal
2. TTL for Commit Tx
3. Reveal Tx only allowed (i.e. accepted by peers) when a corresponding Commit Tx is finalised (and alive)
4. Refundable fee paid upon submitting a Commit
5. Storage should be modified based on order of Commit Txs, not inclusion of Reveals
6. Collators must prioritise Reveals
7. ? Sender creates a proof of broadcast ?
8. ? Collatorss can "report" if its peer censors a Tx ?
9. ? New slashing condition for collators (are there slashing rules for collators already?): if it's reported to censor Tx's ?
10. ? Quorum of collators needed to produce a valid block ?

