---
description: Disclaimer
---

# Risks

## Pre-Audit

It is critical that users know that Mobius as of right now has not completed an official audit. Though we have every intention of doing one as soon as possible! 

Mobius core contracts however are a fork of [Nerve.](https://nerve.fi/) The Nerve contracts have previously been [audited by Certik ](https://github.com/nerve-finance/contracts/blob/main/audits/Certik%20-%20REP-Nerve_Finance_Core_Contracts-06_04_2021.pdf), and as of 09/03/2021.  
  
In general we did not change much from the Nerve contracts, besides adding a few methods to retrieve pool information, and removing the withdrawal fee for LP providers.  
  
You can view the exact differences between our contracts [here.](https://github.com/nerve-finance/contracts/compare/main...mobiusAMM:main)

## Admin Keys

Mobius admin keys are controlled by a 3/4 multisig. The signers are Dylan Mooers, Kyle Scott, Robert Leifke, and Eric Cuellar. This multisig has capabilities to pause new deposits and trades in case of technical emergencies. Users will always be able to withdraw their funds regardless of new deposits being paused. The multisig can also change the swap fees.

## Permanent Loss of a Peg

If one of the assets in a pool significantly depegs, it will effectively mean that pool liquidity providers will be left holding only that asset.

