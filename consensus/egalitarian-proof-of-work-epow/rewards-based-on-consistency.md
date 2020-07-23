---
description: Last Updated 2020-07-23
---

# EPoW Block Rewards based on Consistency

A factor called 'consistency' is multiplied to a standard CryptoNote\(CN\) block reward equation for reward adjustment.

The block time between two adjacent blocks by default is 120 seconds.

If miners find a block less than 120 seconds, then the consistency will be less than 1.  
If miners find a block after 120 seconds, the consistency will be greater than 1.

The value of consistency ranges from 0.08 to a maximum of 2.00.

Now, let's take a look at how rewards change under EPoW.  
If the block time between block \#1 and \#2 \(timestamp of \#3 - timestamp of \#2\) = 80 seconds.  
This makes the consistency factor  80 sec / 120 sec = 3/4  = 0.75.

The block reward for finding block \#2 will be reduced to 0.75. Please find the method used to calculate block reward for block \#2 [here](https://app.gitbook.com/@qwertycoin/s/qwertycoin-white-paper/~/drafts/-MCv9PsnU_pw7XL59E4E/consensus/cryptonote-proof-of-work/cryptonote-block-reward-calculation).

This changes the block reward for block \#2 from the original reward of 351,843.72088831 QWC to 351,843.72088831 QWC x 0.75 = 263,882.79066623 QWC.

The application of the consistency factor allows EPoW to fairly reward network participants\(under EPoW, miners\) based on their contributions to the security of the QWC blockchain while protecting the rewards from well-known majority attacks \(51% or 99% attack\) since miners do not gain anything by finding many blocks in a short period of time.



