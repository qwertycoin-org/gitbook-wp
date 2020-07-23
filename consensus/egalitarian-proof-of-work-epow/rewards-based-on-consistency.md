---
description: Last Updated 2020-07-23
---

# Rewards based on Consistency

A factor called 'consistency' is multiplied to a standard CryptoNote\(CN\) block reward equation for reward adjustment.

The block time between two adjacent blocks by default is 120 seconds.

If miners find a block less than 120 seconds, then the consistency will be less than 1.  
If miners find a block after 120 seconds, the consistency will be greater than 1.

The value of consistency ranges from 0.08 to a maximum of 2.00.

The standard CN block reward is calculated using the following formula:

*  Block Reward = \(Total Supply of Coins - Already Generated Coins\) / \(2^emission speed factor\)

In the mathematical expression,

* BR = \(T - A\*\(10^\(number of decimals\)\)\) / \(2^19\) / \(10^\(number of decimals\)\)

For example, let's try to calculate the block reward of the genesis block.  
  
- T = \(2 ^ 64\) - 1 = 18,446,744,073,709,551,615, a constant  
- A = 0, This is a genesis block, a varible   
- emission speed factor = 19, a constant  
- number of decimals = 8, a constant  
  
Block \#1 \(18,446,744,073,709,551,615 - 0\) \* \(2^-19\) \* \(10^-8\) = 351,843.72088832 QWC  
  
For the next block, The calculation is as shown below  
  
Block \#2 \(18,446,744,073,709,551,615 - 35,184,372,088,832\) \* \(2^-19\) \* \(10^-8\) = 351,843.72088831 QWC  
Block \#3 \(18,446,744,073,709,551,615 - 70,368,744,177,663\) \* \(2^-19\) \* \(10^-8\) = 351,842.37871104 QWC  
Block \#4 ... and so on.

Now, let's take a look at how rewards change under EPoW.  
If the block time between block \#1 and \#2 \(timestamp of \#3 - timestamp of \#2\) = 80 seconds.  
This makes the consistency factor  80 sec / 120 sec = 3/4  = 0.75.

The block reward for finding block \#2 will be reduced to 0.75.   
This changes the block reward from:   
351,843.72088831 QWC to 351,843.72088831 QWC x 0.75 = 263,882.79066623 QWC.

The application of the consistency factor allows EPoW to fairly reward network participants\(under EPoW, miners\) based on their contributions to the security of the QWC blockchain while protecting the rewards from well-known majority attacks \(51% or 99% attack\) since miners do not gain anything by finding many blocks in a short period of time. 
