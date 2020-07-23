---
description: Last Updated 2020-07-23
---

# Rewards based on Consistency

A factor called 'consistency' is multiplied to a standard cryptonote reward equation for reward adjustment.

The block time between two blocks by default is 120 seconds.

If miners find a block less than 120 seconds, then the consistency will be less than 1.  
If miners find a block after 120 seconds, the consistency will be greater than 1.

The value of consistency ranges from 0.08 to a maximum of 2.00.

The standard block reward is calculated using the following formula:

Block Reward = \(Total Supply of Coins - Already Generated Coins\) x 2^-19

This allows EPoW to fairly reward network participants\(under EPoW, miners\) based on their contributions to the security of the QWC blockchain.

This blockchain is fully 51% or 99% attack proof since miners do not gain anything by finding many blocks.

