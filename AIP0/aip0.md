# AIP0: The Astroport Improvement Proposal Framework

## Preamble

```
AIP#: 0
Title: The Astroport Improvement Proposal Framework
Author(s): Stefan Ionescu (@stefanionescu)
Contributors:
Type: Other
Status: Draft
Date Proposed: 2022-02-08
Date Ratified: 
Last Amended: 2022-02-08
Dependencies: n/a
Replaces: n/a
Ratification Poll URL:
Forum URL: https://forum.astroport.fi/t/general-arc-0-the-astroport-improvement-proposal-framework
```

## Proposal Authors

Stefan Ionescu (@stefanionescu).

## References

**[General-AIP-Template.md](General-AIP-Template.md)**  
**[Technical-AIP-Template.md](Technical-AIP-Template.md)**

## Summary

AIP0 defines the *Astroport Improvement Proposals (AIPs) Framework* for all subsequent AIPs to utilize.

## Abstract

AIP0 defines the *Astroport Improvement Proposals (AIPs) Framework* for all subsequent AIPs to utilize. This AIP is the foundational AIP that provides the necessary templates, processes, and guidelines for working within the framework and defines the key roles required for the operation of the AIPs Process.

## Motivation

For Astroport to evolve into a fully decentralized and self-sustainable DAO, a formalized process of decision-making is required. In a permissionless protocol, everyone should be able to propose changes and improvements.

The AIP Framework serves to empower each Assembly participant by giving them a standardized way of interacting with the wider DAO and defining its future shape.

## Specification

### AIP0: Definitions of the Astroport Improvement Proposal Framework

- **Astroport Improvement Proposals (AIPs):** AIPs are standardized proposals subject to voting that define the behavior of the Astral Assembly and the Astroport Protocol. AIPs can be added, amended, replaced, and removed.
-   **AIP Types:** AIPs can be either general or technical. General AIPs are sub-categorized as treasury, UI, tokenomic and generator.
-   **Minimum Feedback Period:** The minimum amount of time within which the community can give feedback in response to a proposed ARC before it can advance to an on-chain vote (AIP).
-   **Minimum Frozen Period:** The minimum amount of time during which an AIP must remain unchanged before it can advance to an on-chain vote.
-  **AIP Editor(s):** AIP Editors enforce the administrative and editorial aspects of the overall AIPs process.

---

### AIP0: Core Principles

1. **Specificity:** An AIP must define and address a specific behavior or single responsibility.

2. **Completeness:** An AIP must be thorough. Relevant, specific particulars must not be left undefined or unreferenced.

3. **Avoid overlap:** Multiple AIPs must not implement the same type of behavior independently. For instance, there should not be two separate, interchangeable ways to create new Astroport pool types.

4. **Clarity:** An AIP must not have equally valid conflicting interpretations. An AIP must be as clear and easy to understand as possible.

5. **Brevity:** An AIP must be as short as possible, including only what is essential given the other core principles.

---

### AIP0: The AIP Lifecycle

#### AIP Lifecycle Breakdown

1. **Conception**: An AIP Author posts a ARC proposal on the [Astroport forum](https://forum.astroport.fi/) under the *Astroport Requests for Comments* category. From this point on, AIP Editors will be available to assist the AIP Author.

2. **Approved by AIP Editor(s)**: An AIP Editor verifies that the posted ARC proposal:

   - Follows the appropriate format of the AIP Template for its type.
   - Is either an original AIP or a replacement for an older AIP.
   - Has been submitted to the [AIPs GitHub](https://github.com/astroport-fi/aips) repository with a Pull Request by either the AIP Author or an AIP Editor.

   If the verification is successful, the AIP Editor:

   - Approves the AIP and assigns it a formal AIP number.
   - Merges in the PR.

3. **Astroport Request for Commments (ARC)**: A period of reviewing by the community and attendant redrafting begins. The minimum duration of this period is determined by two variables:

   - `Feedback Period`: 7 days.
   - `Frozen Period`: 2 days.

Please note that in the case of UI ARCs, there is no need for a `Frozen Period`.

4. **Fulfilled Feedback Period Requirements:** After the AIP has fulfilled the ARC phase, it is ready for on-chain submission.

5. **On-Chain Submission:** At this point, the AIP Author has two options: submit an on-chain AIP vote referencing the associated ARC and then notify the Astroport community on the forum or request help from an AIP Editor to submit the on-chain vote.

6. **Accepted/Rejected:** The AIP is voted on. If it passes, it is officially accepted and is given the `Accepted` status. If not, the AIP is rejected.

#### On-Chain Submission

In order to submit an AIP on-chain, the AIP submitter must call the `submit_proposal` function from the Astral Assembly contract and specify the following parameters:

    - `sender` which is the address of the proposal submitter
    - `deposit_amount` which is the amount of xASTRO that must be locked in the Astral Assembly contract until the proposal expires, is rejected or is approved by Assembly voters. In case the proposal is rejected, the deposited xASTRO will be confiscated
    - `title` which is the title of the AIP. It must start with "AIP-" and the number of the AIP which was assigned by an AIP Editor. The AIP title must be maximum 64 characters long
    -  `description` which is a condensed description of the AIP, taken from the submitted (and associated) ARC on the community forum. The `description` must be maximum 1024 characters long
    - `link` which is a link to the associated ARC posted on the community forum. The `link` must be maximum `128` characters long
    - `messages` which is the AIP payload that defines which contracts and parameters the AIP is meant to change

#### Resubmission

An AIP can be resubmitted for an on-chain vote up to 3 times without having to go through phases 1-4 again if it failed to pass due to legitimate external reasons (e.g., potential low governance participation that did not meet the minimum on-chain quorum).

#### Other AIP Statuses

- **Withdrawn:** Assigned when an AIP Author withdraws their AIP proposal.

  > A AIP may be withdrawn at any point before it enters an on-chain vote. Note that a withdrawn proposal can be taken over from the original Author with a simple transition facilitated by an AIP Editor and the respective parties. If the original AIP Author ceases to be available, an AIP Editor may proceed with the transfer of authorship.

- **Deferred:** Assigned when a proposal has been deemed as not ready or not a priority but can be re-proposed at a later date. This status can be assigned during ARC or by a rejecting forum poll or Signal Request.

- **Obsolete:** Assigned when:

  - An AIP has been superseded or deprecated.
  - An AIP has been deferred for over six months.
  - An AIP Author has abandoned the proposal and no person has communicated willingness to take over the responsibility of an AIP Author.

#### AIP Status Change Process

If an AIP Author requests a status change for an AIP, an AIP Editor will review it. If the status change is warranted, the AIP Editor will change the status. Otherwise, the AIP Editor will revert and highlight issues for the AIP Author to fix before requesting another status change.

---

### AIP0: AIP Replacement Process

An AIP can define one or more replacement targets in its preamble. If the AIP is given the `Accepted` status, the replacement target(s) AIPs receive the `Obsolete` status and effectively become inactive. The replaced AIP will record the number of the AIP that replaced it. AIPs that depend on the replaced AIP will instead interact with the new AIP.

Since dependencies carry over, an AIP with defined replacement targets must strictly adhere to dependency requirements and interface correctly with AIPs that depend on the replaced AIP.

---

### AIP0: Supporting Materials

AIPs can optionally refer to external materials. External materials must be added to the [AIPs GitHub](https://github.com/astroport-fi/aips) in the same folder as the AIP which references them.

Externally referenced materials are not AIP content and are not ratified when an AIP becomes `Accepted` unless it is explicitly stated otherwise in an AIP Component specification.

---

### AIP0: AIP Templates

#### General AIP Template
- The General AIP Template should be used for AIPs whenever a more specific template is not more appropriate.
- The General AIP Template is located at **[General-AIP-Template.md](General-AIP-Template.md)**.

#### Technical AIP Template
- The Technical AIP Template should be used for AIPs whenever an AIP proposes changes to the smart contract code within the Astroport Protocol.
- The Technical AIP Template is located at **[Technical-AIP-Template.md](Technical-AIP-Template.md)**.
---

### AIP0: AIP Editors

The AIP Framework depends on AIP Editors.

#### AIP Editor

AIP Editors enforce the administrative and editorial aspects of the overall AIPs process and program.

##### Specific authority of the AIP Editor(s) in AIP0 processes

* AIP Editors control phase 2 of the AIP lifecycle and can assign AIP numbers.
* AIP Editors are admins on the [AIPs GitHub repository](https://github.com/astroport-fi/aips).
* AIP Editors moderate the ARCs category in the forum.
* AIP Editors are responsible for updating the status of AIPs.

#### Editor Responsibilities

An AIP Editor's responsabilities include:
-   Providing feedback in the [AIP section of the forum](https://github.com/astroport-fi/aips).
-   Assign formal number labels to AIPs.
-   Make sure that titles, AIP statuses, category placements all track the actual AIPs.
-   Confirm there is a (real) dedicated AIP author, coordinator, funder and/or sponsor, etc.
-   Correspond with AIP authors/coordinators.
-   Review AIPs for obvious defects in the language.
-   Make sure that AIPs follow the style guide (template).
-   Work and communicate with AIP authors to help them submit an ARC for on-chain voting as an AIP.

AIP Editors can correct issues themselves, but they are not required to.

---

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
