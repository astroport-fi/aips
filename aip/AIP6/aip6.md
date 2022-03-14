# ARC-6: Add ASTRO Emissions for the MARS-UST pool

## Preamble

```
AIP#: 6
Title: Add ASTRO emissions for the MARS-UST pool
Author(s): @TopHatOnURHead
Contributors: n/a
Tags: general, generator
Type: Generator
Category: Binding (Executable Purely On-Chain)
Status: Deferred
Date Proposed: 2022-03-10
Date Ratified:
Dependencies: n/a
Replaces: n/a
```

## References

- [Announcing Astroport's Post-launch ASTRO Emissions Schedule](https://astroport.medium.com/announcing-astroports-post-launch-astro-emissions-schedule-8a4ccd28ead2)
- [Airdrop Smart Contract](https://finder.extraterrestrial.money/mainnet/address/terra1dpe2aqykm2vnakcz4vgpha0agxnlkjvgfahhk7)
- [Airdrop 2 Smart Contract](https://finder.extraterrestrial.money/mainnet/address/terra1hk7fturdl9fnvrn566dxer6ds7v4jklp2wqmp7)

## Summary

Add ASTRO emissions to the MARS-UST pool.

## Abstract

Mars is emerging as a significant member of the Terra ecosystem. There are no ASTRO emissions for the MARS-UST pool, however. As of 3/9/2022, with 13 days remaining to claim, there are approximately 8 million unclaimed ASTRO tokens (from Airdrop, and Airdrop 2). When the period to claim ASTRO tokens ends these tokens will return to the Astral Assembly. The unclaimed ASTRO tokens would kickstart the MARS-UST pool. It may be few or many. Whichever the case, the bi-weekly vote can address disparities, if any, in the quantity of ASTRO the MARS-UST pool is receiving

## Motivation

Liquidity for the MARS-UST pool is approximately $30M, identifying it as a significant player in Astroport. MARS liquidity providers are important to the Terra ecosystem and should be provided the opportunity to earn ASTRO and to participate in governance.
This proposal would serve to establish initial emissions for the MARS-UST pool.

## Specification

When Kujira transferred liquidity from Astroport their initial ASTRO emissions were distributed to all active pools. In a similar way, any unclaimed ASTRO from Astroport's airdrops 1 and 2 would be distributed but only to MARS-UST providers as they aren't receiving ASTRO at the moment.

## Implementation

Calculate total unclaimed ASTRO tokens when the period to claim the ASTRO airdrop ends. Apply its fractional value of ASTRO tokens to liquidity providers on a per block basis- in the same way the other pools distribute ASTRO to their providers.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
