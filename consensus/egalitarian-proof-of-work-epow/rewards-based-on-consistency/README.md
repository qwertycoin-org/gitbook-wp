---
description: Last Updated 2020-07-23
---

# Introduction of EPoW block reward algorithm based on Consistency

QWC introduces a new block reward algorithm that utilizes a time-based factor called 'consistency', multiplied to a standard CryptoNote\(CN\) block reward equation in order to adjust block rewards.

The block time between two adjacent blocks by default is 120 seconds.

If miners find a block less than 120 seconds, the value consistency is less than 1.  
If miners find a block after 120 seconds, the value of consistency is greater than 1.  
If miners find a block at 120 seconds, the value of consistency is 1. 

The value of consistency can change between 0.08 to a maximum of 2.00.

Now, let's take a look at how rewards change with Consistency under EPoW.  
  
Case 1\)  
If the block time between block \#1 and \#2 \(timestamp of \#2 - timestamp of \#1\) = 80 seconds.  
In this case, the value of Consistency is 80 sec / 120 sec = 3/4  = 0.75.

The block reward for finding block \#2 will reduce by 0.75X. Please find the method used to calculate block reward for block \#2 [here](https://app.gitbook.com/@qwertycoin/s/qwertycoin-white-paper/~/drafts/-MCv9PsnU_pw7XL59E4E/consensus/cryptonote-proof-of-work/cryptonote-block-reward-calculation).

This changes the block reward for block \#2 from the original reward of 351,843.72088831 QWC to 351,843.72088831 QWC x 0.75 = 263,882.79066623 QWC.  
  
Case 2\)  
If the block time between block \#2 and \#3 \(timestamp of \#3 - timestamp of \#2\) = 240 seconds.  
In this case, the value of Consistency is \(240 sec / 120 sec\)^\(0.25\) = 2.00^\(1/4\) or 2.00^\(0.25\) = 1.189.

The block reward for finding block \#3 will increase by 1.189X. Please find the method used to calculate block reward for block \#3 [here](https://app.gitbook.com/@qwertycoin/s/qwertycoin-white-paper/~/drafts/-MCv9PsnU_pw7XL59E4E/consensus/cryptonote-proof-of-work/cryptonote-block-reward-calculation).

This changes the block reward for block \#2 from the original reward of 351,842.37871104 QWC to 351,842.37871104 QWC x 1.189 = 418,340.58828743 QWC.  
  
**\* So, what improvements/benefits does this consistency bring to QWC?**

The application of the consistency factor allows EPoW to fairly reward network participants \(under EPoW, miners\) based on their contributions to the QWC blockchain project while protecting the rewards from well-known majority attackers \(51% or 99% attack\) since miners do not gain anything by finding many blocks in a short period of time. 

Along with CIMA and CLIFF, the effectiveness of consistency will only increase and the security of the network will be reinforced greatly. A significant milestone for achieving something others have failed to implement.

