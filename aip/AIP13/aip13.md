# ARC-13: gOHM-UST Pool Addition to Astroport with Dual Incentives

## Preamble

```
AIP#: 13
Title: gOHM-UST Pool Addition to Astroport with Dual Incentives
Author(s): @json
Contributors: n/a
Tags: general, generator
Type: Generator
Category: Binding (Executable Purely On-Chain)
Status: Active
Date Proposed: 2022-04-21
Date Ratified:
Dependencies: n/a
Replaces: n/a
```

## Summary

Incentivise gOHM-UST pool on Astroport to build up liquidity. The purpose of this proposal is to create a deep liquidity pool of gOHM-UST to bring swaps from gOHM to UST and vice versa from to Astroport and the Terra ecosystem.

## Abstract

Olympus would like to incentivize a gOHM-UST pool on Astroport to officially bring gOHM to the Terra ecosystem. The gOHM rewards are not contingent on this proposal, however, it would be preferable to begin rewards at the same time with ASTRO.

Olympus DAO is a decentralized reserve currency protocol based on the OHM token. Each OHM token is backed by a basket of assets (e.g. UST, DAI, FRAX, wETH) in the Olympus treasury, giving it an intrinsic value. Olympus also introduces novel economic dynamics into the market through staking and bonding.

## Motivation

Olympus continued its expansion toward being the reserve currency of DeFi through a cross-chain expansion initiative called Proteus. Recently Olympus has begun discussions with TFL on how to integrate the OHM token further into the Terra ecosystem. This was first realized in the accumulation of UST into the treasury from a [governance proposal](https://forum.olympusdao.finance/d/500-oip-52-add-ust-to-the-treasury) on the Olympus forum. Astroport is the primary DEX within Terra ecosystem so it was a natural choice for a gOHM-UST pool.

## Specification

Olympus will provide gOHM emissions to approximately 0.4 gOHM tokens per day for a period of 3 months (36 gOHM or $111K for 3 months), at time of writing 1 gOHM is worth $3095. In exchange the Astral Assembly provides ASTRO emissions to approximately 333 ASTRO tokens per day for a period of 3 months (30,000 ASTRO for 3 months).

The estimated rewards APR is shown below for various levels of liquidity.

|Liquidity in gOHM-UST pool|gOHM APR|ASTRO APR|Total APR|
| --- | --- | --- | --- |
|$1,000,000|45%|45%|90%|
|$3,000,000|15%|15%|30%|
|$5,000,000|9%|9%|18%|
|$15,000,000|3%|3%|6%|
|$20,000,000|2%|2%|4%|

(estimated APR values assume that $ASTRO = $3.72)

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
