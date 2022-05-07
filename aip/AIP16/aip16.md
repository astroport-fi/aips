# ARC-16: bLUNA-stLUNA Virtual Pool

## Preamble

```
ARC#: 16
Title: stLuna <> bLuna virtual pool
Author: Lidofinance
Contributors: @kai, @spaydh and the Lido on Terra Team.
Tags: <technical, smart-contracts>
Category: Binding (Executable Purely On-Chain)
Status: <>
Date Proposed: <2022-04-29>
Date Ratified: <>
Dependencies: stluna/bluna staking contract
Replaces: <null>
License: <Apache-2.0>

```

## References

- About bLuna and stLuna: [https://docs.terra.lido.fi/introduction/tokens](https://docs.terra.lido.fi/introduction/tokens)
- Lido’s bLuna and stLuna converter: [https://terra.lido.fi/convert](https://terra.lido.fi/convert)
- Lido Hub: [https://finder.terra.money/columbus-5/address/terra1mtwph2juhj0rvjz7dy92gvl6xvukaxu8rfv8ts](https://finder.terra.money/columbus-5/address/terra1mtwph2juhj0rvjz7dy92gvl6xvukaxu8rfv8ts)
- bLuna upgrade proposal: [https://forum.anchorprotocol.com/t/proposal-bluna-upgrade/1598](https://forum.anchorprotocol.com/t/proposal-bluna-upgrade/1598)
- Proposed upgrade for the bLuna-Luna pool: [https://forum.astroport.fi/t/arc-5-upgrade-bluna-luna-pool-to-handle-bluna-rewards/277](https://forum.astroport.fi/t/arc-5-upgrade-bluna-luna-pool-to-handle-bluna-rewards/277)

## Summary

Enable the bLuna <> stLuna swaps with no slippage on Astroport via a pool-like API.

## Abstract

Make Astroport the main hub for bLuna <> stLuna swaps by creating a virtual pool that leverages the Lido Hub to enable zero-slippage conversion.

## Motivation

The demand for bLuna, Anchor’s first collateral type, has skyrocketed with the rise of Terra’s saving protocol. Today, more than 46M bLuna (worth ~4.6B$) are deposited into Anchor. As a result, deeper and deeper bLuna liquidity is needed to keep the money market solvent and maintain a tight peg.

Unfortunately, bLuna’s design makes it unwieldy to DeFi: bLuna is hard to bridge and LPs are forced to forgo their staking rewards, [unless additional code is implemented](https://forum.astroport.fi/t/arc-5-upgrade-bluna-luna-pool-to-handle-bluna-rewards/277). These issues evaporate with stLuna, which can be bridged or provided to a pool without any additional code nor loss of yield.

As a result of a more composable design, stLuna liquidity on Astroport quickly picked-up to reach one-third of bLuna’s. Current liquidity is thus fragmented between bLuna liquidity, crucial to Anchor’s collateral market, and stLuna liquidity, used in the rest of TeFi. 

What if we could unite these assets and combine their liquidity on Astroport somehow? Surely, this would give the protocol an edge.

**Enters the bLuna <> stLuna virtual pool.** 

Because bLuna and stLuna are two representations of the same thing (Luna staked with Lido), it is possible to leverage Lido’s smart-contracts to burn one and mint an equivalent value of the other. In effect, such a conversion is akin to a swap through an AMM pool with infinite liquidity. 

To integrate this conversion mechanism into Astroport, a special pool can be created. It is ‘virtual’ because liquidity is sourced from the Hub, not from LPs, and deposits are disabled. To the user, it functions as any other pool, but in the background, tokens and messages are forwarded to the Hub and the proceeds returned to the user, in a single transaction.

The benefits of such a pool are numerous:

- **Improved UX:** Astroport’s Router and users will benefit from the best bLuna/stLuna trade execution possible without having to leave Astroport for [terra.lido.fi/convert](http://terra.lido.fi/convert).
- **Improved liquidity:** because stLuna and bLuna are made freely interchangeable, one token’s liquidity becomes the other’s. Both assets become more liquid, more robust to manipulation and their pegs tighten. Concentrating liquidity and incentives around the more composable and LP-friendly stLuna now directly bolsters collateral markets rather than undermining them.
- **Improved competitiveness:** As liquidity and UX improves relative to competing venues, Astroport should capture a larger share of trades, increasing churn and fee collection for LPs and ASTRO stakers.

## Specification

- stLuna <> bLuna pool provides a regular pools method except the ProvideLiquidity and
WithdrawLiqudity, as there is no liquidity

## Proposed Code

- [The final code that can be used directly in the Assembly vote to accept or reject the AIP.](https://github.com/lidofinance/lido-terra-stluna-bluna-converter-contract)

## Test Cases

Tests covering swap transactions, simulations and the logic for accumulated price queries can be found [here](https://github.com/lidofinance/lido-terra-stluna-bluna-converter-contract/blob/main/contracts/converter/src/testing/tests.rs) (bLuna-stLuna converter) and [here](https://github.com/lidofinance/lido-terra-integration-tests/blob/main/src/testcases/converter_pool.ts) (integration contract). 

Because the price of stLuna increases every hour, even when no swaps occur, calculating an accurate TWAP for the converter contract could be problematic. We made a script to simulate the TWAP’s calculation using three different methods, and used the results to inform the development of the converter contract. More info [here](https://github.com/lidofinance/lido-terra-stluna-bluna-converter-contract/tree/main/contracts/converter#twap).

## Security Considerations

- **No drainage risk:** virtual pools don’t hold assets, so liquidity can’t be drained.
- **Ownership overtake:** configuration can be modified by the owner. If ownership is overtaken, swapped assets could be routed through a malicious contract instead of the Hub.
- **Erroneous price diffusion:** external services could be fed wrong prices if the contract’s calculations are faulty.
- Overall, **the contract’s risk profile is low.** Nonetheless, we believe **an audit is still required.**

## Auditor Information and Report

- Lido on Terra created the code, which Astroport will deploy, own and manage the risk of. Astroport will thus bear most of the risk associated with this code, which is why we believe it should be responsible for the code’s external audit, so as to be aware of every security considerations. Lido on Terra cannot provide Astroport with security guarantees and the code “as is”, however, we are open to collaborating on the audit’s issue, and at Astroport’s disposal should any assistance be required.

## Licensing

- Apache-2.0: [Apache License, version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
