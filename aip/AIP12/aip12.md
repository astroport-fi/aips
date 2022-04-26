# ARC-12: Astroport Separate UI for Limit Orders and Stop Losses

## Preamble

```
AIP#: 12
Title: Astroport Separate UI for Limit Orders and Stop Losses
Author(s): @caraluna
Contributors: n/a
Tags: ui
Type: UI
Category: Signaling (Non-Binding Social Consensus Signal)
Status: Accepted
Date Proposed: 2022-04-18
Date Ratified:
Dependencies: n/a
Replaces: n/a
```

## References

Autonomy Network Website: [https://www.autonomynetwork.io](https://www.autonomynetwork.io/)

## Summary

Offer limit orders and stop losses for AstroPort on a separate UI with Autonomy Network. For context, Autonomy Network is a generalized automation protocol that can be used by dApps to add features such as limit orders/stop losses, automatic self liquidations, automation of recurring functions(payments, voting, etc) for DAOs, Autonomous NFTs and much more. Advanced order types for DEXes are a major focus at Autonomy. The project is live on most EVM chains, Avalanche, Ethereum, BSC, Polygon. Most recently it went live on Solana with plans to expand into a few more major chains including Terra.

## Abstract

In order to onboard the next wave of people into DeFi, AMMs need to provide similar tools as centralized exchanges. We think that limit orders and stop losses are here to stay and it’s just a matter of time until all DEXes adopt limits and stops either for differentiation or because of end user demand. DEXes on the EVM ecosystem have been adding these features, Pancakeswap, Apeswap, Quickswap and Sushiswap to name a few.

## Motivation

To meet the growing demand of DeFi on Terra, AstroPort should develop its own UI to offer advanced trading features such as limit orders and stop losses to offer flexibility to its users, while at the same time remaining relevant in the competitive DEX landscape.

Although it is very early in the Terra ecosystem, there is already community discussion on Astroport about limit orders [here](https://forum.astroport.fi/t/limit-ordering-via-astroport-swap-function/197), a quick google search “Terra limit orders” quickly reveals many forums talking about the same features. Furthermore, projects like Miaw Trader offer limits and stops on top of TerraSwap, a clear example that showcases the general trend of DEXes offering more advanced features.

## Specification

We propose to develop a separate UI built using AstroPort contracts and leveraging Autonomy Network generalized automation protocol to offer limit orders and stop losses. With a possibility of doing a native integration on AstroPort main if there is enough demand.
Implementation:

1. Migrating Autonomy’s general automation contracts and infrastructure to Terra
2. Creating use-case specific wrapper contracts for limit orders and stop losses
3. Building a UI on top of AstroPort to offer limits and stops to test out the infrastructure and demand
4. Native limit orders and stop losses integration on AstroPort
