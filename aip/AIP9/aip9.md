# ARC-9: Incentivise weUSDC/UST pool with Astro

## Preamble

```
AIP#: 9
Title: Incentivise weUSDC/UST pool with Astro
Author(s): @MaxCallisto
Contributors: n/a
Tags: general, generator
Type: Generator
Category: Binding (Executable Purely On-Chain)
Status: Deferred
Date Proposed: 2022-03-28
Date Ratified:
Dependencies: n/a
Replaces: n/a
```

## Summary

Incentivise Astroport stablecoin pools to build up liquidity. The purpose of this proposal is to create a deep liquidity pool of weUSDC/UST, wavUSDC/UST, wsoUSDC/UST, wpoUSDC/UST, bUSD/UST to bring swaps from USDC/bUSD to UST and vice versa from Curve Finance to Astroport.

## Abstract

The weUSDC/bUSD pools are currently available in Astroport with a shallow liquidity of ~$2mil. Compare this against the other UST-USDC pool in various chains:

1. Pangolin Exchange (Avalanche): $43mil
2. Excalibur Exchange (Fantom): $8.43mil
3. Saber (Solana): $67.6mil

Since Astroport is the only DEX with a stableswap invariant pool on Terra for now, this places Astroport in the prime position to solidify itself as the cheapest and deepest liquidity of USDC, bUSD & UST swaps. This sentiment is resonated by Luke, the CTO of Delphi, in his [tweet](https://twitter.com/lukedelphi/status/1500546385367773190?s=20&t=muomBeW1T3qyA_WXkGpqOQ).

Although UST is the default stablecoin within Terra, attracting liquidity of other stables such as USDC, bUSD, USDT, FRAX and DAI/MIM could make Astroport a primary DEX for many who believes that Terra is the ecosystem with the deepest liquidity for DeFi. 

## Motivation

Although this could be speculative, but creating a deep stablecoin pool in Astroport may one day be useful should Astroport decides to build cross-chain via xAstro and allowing users swapping USDC to UST directly from the Ethereum chain as I've explained in [this Twitter thread](https://twitter.com/Theramatics/status/1506607155926896648?s=20&t=muomBeW1T3qyA_WXkGpqOQ). 

As the trading APR for weUSDC/UST pool is approx. 2.5%, the pool should be aggressively incentivised for the first 3 months, with the renewal pass 3 months being subjected to the price of Astro 1 month before the expiry of the Astro emissions. As the trading APR improves alongside the price of Astro, the actual emissions beyond 3 months could be significantly lower. The reason for aggressively incentivising this pool is due to the fact that this pool is in direct competition with Anchor (before it's dynamic earn rate kicks in). As Anchor Earn drops, the need for aggressive emissions can be tapered down. 

## Specification

In order for us to provide a deep enough liquidity, the pool should aim to build up to total liquidity of at least $50mil. I propose that the Astral Assembly provides Astro emissions as per the following table: 

With an Astro price of $3.50 at writing, I would propose the following:

|USDC-UST Pools|Mth 1 Astro Emissions|Mth 2 Astro Emissions|Mth 3 Astro Emissions|
| --- | --- | --- | --- |
|weUSDC-UST LP|214,000|214,000|214,000|
|wavUSDC-UST LP|214,000|214,000|214,000|
|wpoUSDC-UST LP|214,000|214,000|214,000|
|wsoUSDC-UST LP|214,000|214,000|214,000|
|bUSD-UST LP|214,000|214,000|214,000|
|**Total Emissions**|1,070,000|1,070,000|1,070,000|

With the above emissions, the estimated rewards APR will be revised to:

|Liquidity in LP Pool|Astro APR|
| --- | --- |
|$10,000,000|89.9%|
|$20,000,000|44.9%|
|$50,000,000|18.0%|
|$100,000,000|9.0%|
|$200,000,000|4.5%|

(estimated APR values assume that $ASTRO = $3.50)

Given that the annual emissions for Year 1 is 100mil ASTRO, I propose to allocate 1,070,000 Astro to all 5 stablecoin pools for the first 3 months or until gauge vote is launched. This will direct 12.84% of the Astro tokens to the stablecoin pools.

## Copyright

Copyright and related rights waived via [CC0 ](https://creativecommons.org/publicdomain/zero/1.0/).
