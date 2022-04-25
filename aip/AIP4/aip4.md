# AIP-4: ORNE<>UST Pool Addition to Astroport with Dual Incentives

## Preamble

```
AIP#: 4
Title: ORNE<>UST Pool Addition to Astroport with Dual Incentives
Author(s): @Luc-Michault
Contributors: n/a
Tags: general, generator
Type: Generator
Category: Binding (Executable Purely On-Chain)
Status: Accepted
Date Proposed: 2022-02-19
Date Ratified: 
Dependencies: n/a
Replaces: n/a
```

## Summary

Add a ORNE<>UST pool to Astroport and reward LPs with dual incentives ($ORNE & $ASTRO token emissions). The purpose of this proposal is to receive feedback from the community about this idea and gather thoughts regarding the rewards before putting up a poll.

## Abstract

Launched on December 3rd 2021, $ORNE lets you purchase tokenized real trees represented by unique NFTs. Orne redistributes the full profit from the trees’ harvest back to you.

Basically, $ORNE is used as a store of value. For each tree NFT, 50% of the tree’s value is represented with $ORNE and is locked in a smart contract. When a tree reaches maturity and the proceeds from its sale are ready to be claimed, the token owner can burn their tree NFT in exchange for the value of the tree (in USD) converted into $ORNE.

For more details around the NFT mechanics and ORNE’s tokenomics, you can check out [our website](https://orne.io/) and [this post](https://medium.com/@orne/introduction-to-the-tokenomics-of-orne-5bba87dfa625).

## Motivation

To reduce price impact and volatility for $ORNE and ensure that our store of value is not subject to price manipulation, the Orne community can provide 20 million $ORNE as LP rewards, distributed over 3 years as follows: 10 million $ORNE the first year, then 5 million $ORNE on both the second and the third year.

## Specification

In order to grow the ORNE-UST pool and protect the Orne protocol’s funds, we propose a dual incentive campaign involving both $ORNE and $ASTRO tokens.

We propose that the Astral Assembly provides rewards in line with $ORNE pool incentives which would be equivalent (given the current $ORNE price) to approximately 1000 ASTRO tokens per day (365,000 ASTRO per year).

The estimated dual rewards APR is shown below for various levels of liquidity.

| Liquidity in ORNE-UST pool | ORNE Rewards APR | Astro APR | Total Reward APR |
|----------------------------|------------------|-----------|------------------|
| $1,000,000 | 30% | 30% | 60% |
| $2,000,000 | 15% | 15% | 30% |
| $5,000,000 | 6% | 6% | 12% |
| $10,000,000 | 3% | 3% | 6% |
| $20,000,000 | 1.5% | 1.5% | 3% |

(estimated APR values assume that $ORNE = $0.03)

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
