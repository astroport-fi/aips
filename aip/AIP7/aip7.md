# ARC-7: Implement Bribed Voting Mechanism for vxASTRO Holders

## Preamble

```
AIP#: 7
Title: Implement Bribed Voting Mechanism for vxASTRO Holders
Author(s): @Megakupo
Contributors: n/a
Tags: technical
Category: Signaling (Non-Binding Social Consensus Signal)
Status: Draft
Date Proposed: 2022-03-13
Date Ratified:
Dependencies: n/a
Replaces: n/a
License: n/a
```

## References

* [https://forum.astroport.fi/t/proposal-implementing-curve-convex-wars-to-bring-value-to-astroport/275/3](https://forum.astroport.fi/t/proposal-implementing-curve-convex-wars-to-bring-value-to-astroport/275/3)
* [https://forum.astroport.fi/t/vxastro-solidly-dynamics/304/5](https://forum.astroport.fi/t/vxastro-solidly-dynamics/304/5)

## Summary

Allow protocols/users to "bribe" vxASTRO holders to vote for specific LPs as part of the [biweekly ASTRO emissions calibration](https://docs.astroport.fi/astroport/tokenomics/astroport-tokenomics/calibration).  vxASTRO holders receive these "bribes" for the pools that they voted on.

## Abstract

Create a new interface in the Astroport app for "bribers" to deposit tokens as "bribes" for specific LPs, which are paid out to vxASTRO holders who vote for those LPs to receive Astro emissions during the biweekly ASTRO emissions calibration (where Astral Assembly votes to decide which pools get the $ASTRO incentives).  vxASTRO holders who vote for a particular LP receive all of the "bribes" that were placed on that LP, in proportion to the # of votes they put in for that LP.

## Motivation

Astroport incentivzes certain LPs by emitting $ASTRO tokens to the people who provide liquidity to those LPs. Per Astroport’s documentation, Astroport governance will allow xASTRO and vxASTRO holders to vote on which LPs obtain the most $ASTRO emissions ( *see* [Calibration - Astroport](https://docs.astroport.fi/astroport/tokenomics/astroport-tokenomics/calibration)).

These votes carry substantial value.  The LPs with the most votes will receive the most $ASTRO incentives, meaning that they'll have higher APRs.  The tokens associated with those LPs will generally increase in value, and liquidity for those tokens will increase as well.

As a result, other protocols may want to "bribe" voters to vote on the LPs that use the protocol's token.  We've seen this happen with other protocols, such as Curve/Convex and Beets.fi.  These "bribes" result in significant value for ASTRO holders, because locking ASTRO as vxASTRO would now give you a share of all those bribes, in addition to the protocol fees you'd otherwise get.

Other dex’s that have implemented this feature have seen their dex tokens explode in value. And for dex’s that don’t implement this “bribe” feature, inevitably another protocol comes along and does it (e.g. what Convex did to Curve), which results in the other protocol capturing a lot of that value (e.g. people fighting over Convex tokens instead of Curve).  This is described in more detail in [this post.](https://forum.astroport.fi/t/proposal-implementing-curve-convex-wars-to-bring-value-to-astroport/275/3)  

More broadly, Terra is quickly becoming the natural onramp for retail investors, due to apps like Kado and Alice allowing for cheap, direct onboarding of Fiat -> UST.  I anticipate this will lead to a boom in defi on the Terra blockchain.  Implementing a bribe protocol helps enable a defi boom by allowing protocols to incentivize liquidity for their tokens (via bribes).  The whole "bribe wars" dynamic also creates great marketing for the different protocols, for Astroport, and for Terra overall.

## Specification

1. Create a new page in the Astroport app called "Voting Incentives" where users can deposit and view "bribes" for each of the Astroport LPs.

2.  For users who want to deposit bribes, they would just need to press the "Deposit Incentive" button next to the respective LP.  Bribes can take the form of any token in the user's wallet that has been verified by Astroport (e.g., UST, aUST, Luna, Apollo, MINE, ANC, etc.).  The bribe is then locked via smart contract.  

3.  Subject to technical feasibility, the bribe can also be set up so that the size of the bribe would depend on the amount of votes that the LP receives (e.g., "We'll pay $1,000 UST for every 1% of the vote this LP gets, up to $50,000.")  Users submitting this "per % vote" type of bribe would still need to deposit the max amount of tokens (using the above example, $50,000 UST), but could reclaim unpaid bribes after the vote (using the above example, $25,000 if the LP only received 25% of votes).

4.  Anyone can access the "Voting Incentives" page to view the bribes in play for the upcoming calibration vote.  Bribes are locked 24 hours before each vote (meaning no new bribes may be submitted).

5.  The calibration voting process is modified to include one additional step: xASTRO and vxASTRO stakers can also use their votes to vote **against** an LP.  

This modification is necessary to combat an existing flaw in the Astroport governance system:
Without this modification, a bad actor could launch a **"vampire attack"** by creating an LP with coins that only they control (e.g., two brand new tokens minted specifically for this strategy), vote/bribe to have $ASTRO emissions directed to their LP, and then farm the LP to collect 100% of those emissions (because only the bad actor would have the coins necessary to farm the LP).  That LP would provide 0 value to the protocol due to lack of trading fees, but direct substantial $ASTRO emissions to the attacker.  Antagonistic voting allows xASTRO and vxASTRO holers to vote down such behavior in order to protect the protocol.  xASTRO and vxASTRO holders would be incentivized to vote against these vampire LPs because revenue paid to stakers depends on Astroport generating trading fees, which depends in part on incentivizing the LPs that are the most heavily transacted (in order to attract more liquidity, and therefore lower-slippage trades for traders).  **Again, this "vampire attack" strategy is a vulnerability with Astroport's *current* voting implementation, not a flaw introduced with this proposal.  However, the "antagonistic voting" feature would help safeguard the protocol.**

6.  After calibration voting is completed, vxASTRO stakers (not xASTRO stakers) will receive bribes for the LPs they voted on, paid out in proportion to their share of the votes they placed for each LP.  In other words, if a vxASTRO holder submitted 50% of the votes for a particular LP, then that holder gets 50% of the bribes for that LP.  These bribe rewards can be collected through the same interface used to collect LP rewards.  

**Important Note:**  While both xASTRO and vxASTRO holders are able to vote, bribes are paid out only to vxASTRO holders.  This is to prevent gaming the system, and to reward long-term holders.  Without this limitation, bad actors could simply buy up ASTRO right before a vote, stake it for xASTRO, vote to obtain bribes, then unstake and sell the ASTRO right after calibration votes.  vxASTRO holders must lock their tokens, thus preventing this behavior.  

However, xASTRO holders can still participate in voting and antagonistic voting, and they are financially incentivized to vote for LPs that would enhance protocol revenue (b/c that results in stakers being paid more), and to vote against LPs that would harm the protocol (like the vampire attack I discussed above).  xASTRO holders can also lock their xASTRO for vxASTRO to participate in the bribes.  

### Proposed Code

I unfortunately lack the coding skills necessary to propose code here, so would request an allocation of funds from the treasury to fund development of this interface.  This would be a good investment for the protocol because it will drive significant value to the ASTRO token.

### Test Cases

TBD

### Security Considerations

This is a complicated interface and subject to smart contract risk.  In particular, the smart contracts that hold and pay out the voter incentive "bribes" would potentially be holding and transferring significant amounts of money, and a security exploit could lead to a loss of deposited bribes.

### Auditor Information and Report

TBD

### Licensing

TBD
