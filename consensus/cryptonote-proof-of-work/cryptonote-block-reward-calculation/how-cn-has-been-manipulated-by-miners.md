---
description: Last Updated 2020-07-23
---

# An example of CryptoNote Block Reward Manipulation

Let us give you an example of how miners and mining pools have taken advantage of CryptoNote original block reward schedule.

In \[Table 1\], the column 'Base Rewards' column is the design block rewards for miners for each block.

\[Table 1. An example of mining reward based on original Cryptonight algorithm between block 500,000 and 500,019\]

![](../../../.gitbook/assets/3%20%281%29.png)

The total time miners put into mining these 19 blocks are 2,161 seconds whereas the total time for the mining 20 blocks \(20 \* difficulty target\) is set to be 2,400 seconds. This shows that the blocks are issued at the inconsistent interval and miners are basically taking advantage of their hashing power to get the rewards in a shorter time span.

In fact, \[Table 1\] shows that the miners were receiving approximately 10% additional profits compared to intended blockchain design. This additional profits theoretically can range from 0.8% to 11,900.0%.

To prevent this abuse, the concept of time will be introduced through a variable called ‘consistency’. The new EPoW block reward consensus will be adjusted based on ‘consistency’ \(actual mining time divided by difficulty target time\). 

