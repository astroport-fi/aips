# AIP-3: LunaX<>Luna Pool Addition to Astroport DEX with Dual Incentives

## Preamble
```
AIP#: 3
Title: LunaX<>Luna Pool Addition to Astroport DEX with Dual Incentives
Author(s): @vbrpm
Contributors: n/a
Tags: general, generator
Type: Generator
Category: Binding (Executable Purely On-Chain)
Status: Deferred
Date Proposed: 2022-02-05
Date Ratified:
Dependencies: n/a
Replaces: n/a
```

## Summary

Add LunaX-Luna pool to Astroport and reward LPs with dual incentives ($SD & $ASTRO token emissions). Purpose of this proposal is to receive feedback from the community about this idea and gather thoughts regarding the rewards before putting up a poll.

## Abstract

LunaX is an auto-compounding accrual token (similar to aUST) that can be minted when users stake with Stader using the liquid staking pool.
Launched on December 9th 2021, LunaX received tremendous traction from the Terra community. Stader proposes to bring the LunaX-Luna pool to Astroport users.

## Motivation

Around ~16k unique wallets have minted LunaX on Stader’s liquid staking contract.

1. Total Staked Luna: 1.5 M Luna (82 M UST as on Feb 9th 2022)
2. Size of LP Pool on Terraswap: 1.74 M Luna (95 M UST as on Feb 9th 2022)

Luna <> LunaX pool is the largest pool on Terraswap. Stader would like to work with Astroport & bring the LunaX-Luna liquidity to Astroport (if governance approved) benefiting both Astro and Stader community. We will ensure users who move their LP from terra swap to Astro will continue to vest their farmed SD tokens.

## Specification

In order to grow the LunaX-Luna pool further, we propose a dual incentive mechanism. Stader would be providing 13500 USD worth of SD tokens per day.

We propose Astroport to provide rewards in line with stLuna-Luna pool incentives which would be 27000 USD worth of ASTRO tokens per day.

The estimated APY is as shown below for various levels of liquidity.

Colons can be used to align columns.

| Liquidity in LunaX-Luna pool  | Stader Rewards APR | Astro APR  | Reward APR to User |
| -----------------------------:|:------------------:| ----------:|-------------------:| 
| $50,000,000                   | 9.86%              | 19.71%     | 29.57%             |
| $100,000,000                  | 4.93%              | 9.86%      | 14.78%             |
| $150,000,000                  | 3.29%              | 6.57%      | 9.86%              |


_* Total SD token supply is 150 Mn. SD token TGE and listing is expected to be around 7 March._

_* Transaction volumes on Luna <> LunaX are lower vis-a-vis other pools as SD tokens farmed are vested over 6 months from Feb - Jul’22. Expected to increase over time as farmed SD rewards vest._

_*The SD token incentives mentioned here are indicative and may change upon SD token TGE in early March._

## Copyright

Copyright and related rights waived via CC0.
