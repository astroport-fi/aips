# AIP-5: Upgrade bLUNA-LUNA Pool to Handle bLUNA Rewards

## Preamble
```
AIP#: 5
Title: Upgrade bLUNA-LUNA Stableswap Pool to Handle bLUNA Rewards
Author(s): @stefanionescu
Contributors: n/a
Tags: technical
Category: Signaling (Non-Binding Social Consensus Signal)
Status: Draft
Date Proposed: 2022-03-05
Date Ratified:
Dependencies: n/a
Replaces: n/a
License: GNU General Public License v3.0
```

## References

- [bLUNA-LUNA Special Stableswap Implementation](https://github.com/astroport-fi/astroport-core/blob/main/contracts/pair_stable_bluna/src/contract.rs)
- [Lockdrop Contract Upgrade to Allow for bLUNA Reward Claims](https://github.com/astroport-fi/astroport-periphery/commit/9005051db57c2f72d18b0e59720212342ca24077)
- [Proposal: Pay bLuna's UST yield to liquidity providers rather than having it sit unclaimed](https://forum.astroport.fi/t/proposal-pay-blunas-ust-yield-to-liquidity-providers-rather-than-having-it-sit-unclaimed/271)

## Summary

Upgrade the bLUNA-LUNA stableswap pool so that bLUNA rewards can be claimed by LPs.

## Abstract

Add new functionality in the bLUNA-LUNA stableswap pool that allows LPs to claim bLUNA rewards pro-rata to the size of their LP position.

## Motivation

As mentioned in [this forum discussion](https://forum.astroport.fi/t/proposal-pay-blunas-ust-yield-to-liquidity-providers-rather-than-having-it-sit-unclaimed/271), "if you hold bLUNA in your wallet, you earn about 8%-10% APR in UST every year, which has to be manually claimed on the Anchor website. If you supply your bLUNA to the bLUNA-LUNA LP in Astroport, that UST is sitting around unclaimed.".

This proposal aims to solve the problem of having bLUNA rewards stuck in the Astroport pool. The new pool implementation linked in the sections below allows bLUNA-LUNA Astroport LPs to claim bLUNA rewards pro-rata to the size of their LP position. It is also worth noting that bLUNA-LUNA lockdrop participants as well as LPs that stake their bLUNA-LUNA LP tokens in the Generator contract will also be able to claim bLUNA rewards.

Lastly, bLUNA rewards that already accrued in the Astroport pool will become claimable once the bLUNA-LUNA pool is upgraded. A caveat is that **only LPs that are in the pool at the moment of the upgrade will become eligible to claim the already accrued bLUNA rewards**. While this is not ideal, it is still a better option than letting currently accrued rewards stay stuck in the Astroport pool.

## Specification

### Proposed Code

The proposed code for the bLUNA-LUNA stableswap where LPs can claim bLUNA rewards can be found [here](https://github.com/astroport-fi/astroport-core/blob/main/contracts/pair_stable_bluna/src/contract.rs). Moreover, a new version of the lockdrop contract that will allow bLUNA-LUNA lockdrop participants to claim bLUNA rewards can be found [here](https://github.com/astroport-fi/astroport-periphery/commit/9005051db57c2f72d18b0e59720212342ca24077).

### Test Cases

Test cases for the new bLUNA-LUNA pool implementation can be found [here](https://github.com/astroport-fi/astroport-core/blob/main/contracts/pair_stable_bluna/src/testing.rs). Test cases for the new lockdrop contract version can be found [here](https://github.com/astroport-fi/astroport-periphery/blob/main/contracts/lockdrop/tests/integration.rs).

### Security Considerations

The main risk associated with upgrading bLUNA-LUNA is the significant amount of funds that are currently in the pool and that may be stuck or drained in the case where the new pool implementation has a major bug. For this reason, the new bLUNA-LUNA implementation has to be thoroughly audited.

Another major risk is associated with upgrading the lockdrop contract so that bLUNA-LUNA lockdrop participants can also claim bLUNA rewards. A large portion of the Astroport TVL is currently held by lockdrop participants and a bug in the lockdrop contract can leave all these funds stuck in the protocol.

### Auditor Information and Report

Audits for this new bLUNA-LUNA stableswap pool as well as for the latest lockdrop contract version are scheduled for the second half of March 2022.

### Licensing

GNU General Public License v3.0
