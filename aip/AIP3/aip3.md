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
Date Proposed: 2022-04-13
Date Ratified:
Dependencies: n/a
Replaces: n/a
```

## Summary

Add LunaX-Luna pool to Astroport and reward LPs with dual incentives ($SD & $ASTRO token emissions). Based on the community’s feedback and updated market conditions since the earlier proposal, we have updated the proposal.

## Abstract

LunaX is an auto-compounding accrual token (similar to aUST) that can be minted when users stake with Stader using the liquid staking pool. Launched on December 9th 2021, LunaX received tremendous traction from the Terra community. Stader proposes to bring the LunaX-Luna pool to Astroport users.

## Motivation

With over 20,000 wallets minting LunaX, LunaX is a widely used aUST style liquid staking derivative. LunaX is already used as a collateral on Mirror (Poll link here) and Edge protocol while several DeFi integrations are in the pipeline. Here are a few key details about LunaX:

1. Total Staked Luna: 1.9 M Luna (155 M UST as on April 12th 2022)

2. Total size of LunaX <> Luna LP Pool: 1.6 M Luna (130 M UST as on April 12th 2022)

Luna <> LunaX pool is the largest pool on Terraswap. Stader would like to work with Astroport & bring the LunaX-Luna liquidity to Astroport (if governance approved) benefiting both the Astroport and Stader communities.

With this dual incentives proposal we expect the LunaX-Luna LP pool to grow 2-3x compared to its current size. With increasing utilities for LunaX across Terra, we also anticipate significant transaction volumes on the pool.

We will ensure that LPs who move their liquidity from Terraswap or Loop to Astroport will continue to vest their farmed SD tokens.

## Specification

Based on feedback from our community, we would like to add additional SD rewards to the Lunax-LUNA Astroport pool. We propose an increase in Stader rewards to 7500 SD per day (2.5x of initial proposal). SD rewards would be determined and changed by Stader governance after it is live.

In order to further grow the LunaX-Luna pool, we propose a dual incentive mechanism.

We propose that the Astral Assembly rewards the Luna <> LunaX LPs with 26,027 ASTRO tokens per day (9.5 M ASTRO per year). This results in an alloc_point value of 105,000 in the Generator contract.

The estimated APY is shown below for various levels of liquidity.


| Liquidity in LunaX-Luna pool  | Stader Rewards APR | Astro APR  | Reward APR to User |
| -----------------------------:|:------------------:| ----------:|-------------------:| 
| $150,000,000	                | 9.2%               | 19.5%      | 28.7%              |
| $200,000,000                  | 6.9%               | 14.6%	  | 21.5%              |
| $250,000,000                  | 5.5%               | 11.7%      | 17.2%              |
| $300,000,000                  | 4.6%               | 9.8%       | 14.4%              |

The Stader (whSD) rewards contract address on Columbus is terra1g683f7ddlc4zfpwvk93sdky9q53jc6g3uwj09l.

_* Total SD token supply is 150 Mn._

_** Transaction volumes on Luna <> LunaX are lower vis-a-vis other pools as farmed SD tokens are vested over 6 months from Feb - Jul ’22. Volume is expected to increase over time as farmed SD rewards vest._

_*** whSD is wormhole SD_

## Copyright

Copyright and related rights waived via CC0.
