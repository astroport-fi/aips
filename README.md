# Astroport Improvement Proposals (AIPs)

Astroport Improvement Proposals are the main mechanism for improving the Astroport Protocol as well as funding and coordinating the Astral Assembly. AIPs provide a mechanism for any community member to define key issues and suggest changes and additions to the system.

# Overview

## Definitions

### AIPs

AIPs are standardized documents subject to community feedback and voting that, once enacted, define the behavior of the Astral Assembly and the Astroport Protocol.

AIPs have two types: **technical** if they propose changes or additions to smart contracts code related to the Astroport Protocol; or **general** otherwise. The **general** category can be broadly categorized in four sub-categories: **treasury** for Astral Assembly treasury allocation, **UI** for proposing changes to and implementing interfaces that interact with the Astroport Protocol, **tokenomic** for proposing changes to ASTRO tokenomics and **generator** for proposing changes to ASTRO generator contract emissions.

Note that the **generator** sub-category is mostly relevant prior to vxASTRO being released and vxASTRO stakers taking over decisions regarding ASTRO emissions. Regardless, the **generator** sub-category may be used in case the Assembly wants to white or blacklist a specific token from the generator contract or enact any other change that cannot be handled by vxASTRO stakers.

If you feel that your API does not fit in any pre-existing sub-categories, you can simply leave it as **general**.

## Authoring and Proposing

AIPs can be brought forth and proposed by anyone.

If you're interested in proposing an AIP, please read below for more details around the lifecycle of an AIP as well as templates you should use to submit your ideas to the Astroport community.

### Getting Started with AIPs (for Authors)

AIPs are written using Markdown and hosted on GitHub. Please note that all AIPs (and their associated ARCs) must conform to specific templates!

#### Markdown

Markdown is a very simple markup language for formatting text, i.e., adding headers, bullet lists, italicized text, et cetera. When working with AIPs, you should use GitHub-flavored Markdown.

> [GitHub’s Mastering Markdown](https://guides.github.com/features/mastering-markdown/) will get you up to speed in no time. The online Markdown editor [HackMD](https://hackmd.io/) is a solid platform for practice and production.

#### GitHub

[GitHub](https://github.com/) is a code hosting platform for version control and collaboration built on [git](https://git-scm.com/), a version control software. GitHub is complex and may seem daunting at first, but only a basic familiarity is necessary for our purposes.

> We recommend that you read these two short guides: [Hello World](https://guides.github.com/activities/hello-world/) and [Forking Projects](https://guides.github.com/activities/forking/).

#### Templates

- Technical AIPs must conform to the [Technical AIP Template]().
- General AIPs must conform to the [General AIP Template]().

### Proposing

**NOTE**: please note that prior to the Astral Assembly being online, AIPs will only be discussed on the Astroport Forum without having an official community vote.

Once you've picked the appropriate template for your proposal and have a workable draft, the next steps are the following two tasks:
- Post an ARC [on the Astroport Forum](https://forum.astroport.fi/)
- Submit the ARC to the [GitHub AIP repository](https://github.com/astroport-fi/aips)

After the two above tasks have been completed, AIP Editors will help assign a number for the proposal. The proposed ARC will then enter a period of community feedback. This is a great opportunity to iterate on your proposal. Once the feedback period is over and you've incorporated your final changes, there will be a one-week period before you can formally submit the proposal for voting as an AIP. Lastly, your proposal will go through a voting period.

For a more detailed breakdown of the full AIP lifecycle, check out [AIP0]().

# License

The AIP framework was inspired by the [Maker Improvement Proposal Framework](https://github.com/makerdao/mips).
