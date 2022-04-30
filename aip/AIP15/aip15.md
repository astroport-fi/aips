# ARC-15: Increase ASTRO-UST Incentives

## Preamble

```
AIP#: 15
Title: Increase ASTRO-UST Incentives
Author(s): @delphilabs
Contributors: n/a
Tags: general, generator
Type: Generator
Category: Binding (Executable Purely On-Chain)
Status: Active
Date Proposed: 2022-04-28
Date Ratified:
Dependencies: n/a
Replaces: n/a
```

## Summary

Increase ASTRO emissions from 15% to 23.5% on the ASTRO-UST pool with the aim of deepening liquidity for two reasons:

1) Slippage reduction for meta-governance projects looking to accumulate ASTRO ahead of the vxASTRO launch.
2) Deeper liquidity will increase the safety of the TWAP oracle for protocols like Mars.

## Motivation

The goal of this proposal is to improve ASTRO liquidity for the upcoming launch of Retrograde, Reactor, Apollo DAO, and other meta-governance projects looking to accumulate ASTRO. This will help increase the quality and decentralization of Astroport governance.

With the upcoming conversion events of [Retrograde](https://twitter.com/retrogrademoney/status/1516110451733667842?s=20&t=FH7Aw_EwhMWSPxXAJQ8QHg)& [Reactor](https://twitter.com/reactor_money/status/1517089245730541568?s=20&t=SWfyCmXdiG9mX1QZjjhkpw), one would expect an increase in ASTRO volumes. With the high xASTRO APY of 45% we have seen ASTRO-UST liquidity deteriorate. These additional ASTRO emissions should help increase liquidity and prevent excessive price slippage for projects that are trying to build synergistically with Astroport.

Additionally, by potentially increasing liquidity, this proposal could make using a TWAP oracle based on the ASTRO-UST pool safer. All else being equal, the more liquidity in a given pool, the more expensive it is to manipulate the TWAP. As such, this could allow lending protocols (and other oracle-based protocols) such as Mars or Edge to more confidently list ASTRO using an ASTRO-UST based TWAP.

## Specification

Since emissions will be changing upon the release of vxASTRO it seems best to keep this proposal straightforward. We propose reducing the emissions weights of all pools except ASTRO-UST by 10% and redirecting those emissions to ASTRO-UST. This will bring emissions up from 15% to 23.5%.

This would result in an `alloc_point` value of 235,000 in the generator contract.

|Pool|Current Weights|Proposed Weights|
| --- | --- | --- |
|bLUNA-LUNA|25.00%|22.50%|
|ASTRO-UST|15.00%|23.50%|
|LUNA-UST|13.00%|11.70%|
|ANC-UST|10.44%|9.40%|
|stLUNA-LUNA|9.40%|8.46%|
|MINE - UST|3.66%|3.29%|
|STT-UST|3.39%|3.05%|
|MIR-UST|3.39%|3.05%|
|ORION - UST|2.61%|2.35%|
|PSI-UST|2.35%|2.12%|
|PSI-NLUNA|1.83%|1.65%|
|VKR-UST|1.83%|1.65%|
|APOLLO-UST|1.83%|1.65%|
|PSI-NETH|1.57%|1.41%|
|XDEFI - UST|1.57%|1.41%|
|wewstETH-UST|1.57%|1.41%|
|wsstSOL-UST|1.57%|1.41%|

With this proposed change, we can see the estimated reward APR shown below for various levels of liquidity.

|Liquidity In ASTRO-UST Pool|Current Generator APR|Proposed Generator APR|
| --- | --- | --- |
|50,000,000|90%|141%|
|75,000,000|60%|94%|
|100,000,000|45%|71%|
|125,000,000|36%|56%|

(estimated APRs assume ASTRO = $3)

## Disclosures / Disclaimers

This proposal is being made by or on behalf of Delphi Labs Ltd., a British Virgin Islands limited company. Delphi Labs engages in incubation, investment, research and development relevant to multiple ecosystems and protocols and was part of the joint venture which researched and developed the Astroport Protocol. Delphi Labs is one of several entities which associate with one another under the “Delphi Digital” brand. Delphi Digital’s associated entities and/or equity holders or service providers of such entities hold ASTRO and MARS tokens (through Delphi Labs) and have invested in certain Astroport meta-governance protocols (primarily through Delphi Ventures); thus, these entities and their personnel have potential financial interests in this proposal. Such entities and persons may also have financial interests in competing projects or ecosystems.

All analysis and recommendations set forth herein are based on Delphi Labs' evaluation of publicly available facts in its possession. Interpretation and analysis of these facts could reasonably vary. Additionally, Delphi Labs may lack access to all relevant facts or may have failed to give appropriate weighting to available facts. Delphi Labs is not providing any advice, representation, warranty or guarantee regarding the accuracy or completeness of its analysis or any of the statements set forth in this proposal, and Delphi Labs shall have no liability in the event of losses or damages ensuing from approval of the proposal. Each user and voter should undertake their own research and analysis into the subject matter discussed herein in order to arrive at their own personal evaluation of the proposal.
