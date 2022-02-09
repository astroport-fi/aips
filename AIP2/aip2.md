# AIP-2: Delist Functionality for Specific Tokens in Generator

## Preamble
```
AIP#: 2
Title: Delist Functionality for Specific Tokens in Generator
Author(s): @stefanionescu
Contributors: n/a
Tags: technical, generator
Category: Signaling (Non-Binding Social Consensus Signal)
Status: Deferred
Date Proposed: 2022-02-05
Date Ratified:
Dependencies: n/a
Replaces: n/a
License: GNU General Public License v3.0
```

## References

- [Mochi & Curve Incident](https://thedefiant.io/curve-wars-mochi-turned-off-rewards/)

## Summary

Add functionality in the Generator contract to prevent specific tokens from getting ASTRO emissions.

## Abstract

Add the possibility to prevent specific tokens from receiving ASTRO emissions from an Astro Generator. The only tokens that cannot be prevented from receiving emissions would be ASTRO itself and Terra native assets.

## Motivation

Some protocols may abuse the ASTRO emissions mechanism.

As a concrete example, in November 2021, the Curve community had an incident where a stablecoin protocol called Mochi tried to maximize their CRV token emissions in an unusual way. Mochi minted its own governance token and swapped large amounts to CVX (the governance token of the Convex protocol) which allowed them to boost their CRV emissions.

As a result, the Curve community decided to remove all CRV emissions directed to Mochi’s stablecoin. The main reason was that a large part of the Curve community believed that Mochi’s tactics (minting a brand new governance token and use it to get emission boosties) is questionable at best.

## Specification

### Proposed Code

There is no implementation made available just yet.

### Test Cases

Test cases are not yet available as the smart contract implementation is not done.

### Security Considerations

The main risk associated with this Generator contract update is making sure the currently staked LP tokens in the Generator will not get stuck.

### Auditor Information and Report

Given there's no implementation yet for this proposed Generator change, there are no audit reports.

### Licensing

GNU General Public License v3.0
