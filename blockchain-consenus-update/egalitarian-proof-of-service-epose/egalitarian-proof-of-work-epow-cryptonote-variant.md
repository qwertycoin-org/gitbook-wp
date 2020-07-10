---
description: Last Updated 2020-07-05
---

# Egalitarian Proof of Work \(EPoW\)

The first part of EPoSe consensus update starts from making major changes to conventional Proof of Work. It is called Egalitarian Proof of Work \(EPoW\).

The core team found fundamental flaws in the original CryptoNote Proof of Work because it allowed miners, especially influential groups of miners, to take advantage in mining more coins than what the system was intended for.

Let us give you an example of how they have taken advantage of the original system.

In \[Table 1\], the column 'Base Rewards' column is the design block rewards for miners for each block.

\[Table 1. An example of mining reward based on original Cryptonight algorithm between block 500,000 and 500,019\]

![](../../.gitbook/assets/3%20%281%29.png)

The total time miners put into mining these 19 blocks are 2,161 seconds whereas the total time for the mining 20 blocks \(20 \* difficulty target\) is set to be 2,400 seconds. This shows that the blocks are issued at inconsistent interval and miners are basically taking advantages of their hashing power to get the rewards in a shorter time span.

In fact, \[Table 1\] shows that the miners were receiving approximately 10% additional profits compared to intended blockchain design. This additional profits can range from 0.8% to 11,900.0%. This is represented by Area A.

\[Figure 5. Block Reward Adjustment using 'consistency'\] 

![Mining Reward Graph after EPoW \(Area A to C6\)](../../.gitbook/assets/epow-reward-graph-area-marking.png)

To prevent this abuse, the concept of time will be introduced through a variable called ‘consistency’. The new EPoW block reward consensus will be adjusted based on ‘consistency’ \(actual mining time / difficulty target time\). 

This ‘consistency’ is a multiplier to the base reward, and it can either make the block reward between 0.8% and 200% of the base reward depending on the time difference within adjacent blocks.  

\[Table 2. An example for mining reward based on EPoW algorithm between block 500,000 and 500,019\]

![Click to enlarge the table.](../../.gitbook/assets/2%20%281%29.png)

In \[Table 2\], EPoW Reward column shows adjusted base reward for each block from introduction of ‘consistency’

Among CryptoNote developers, some expressed concerns that the fact that the longer miners mine to find a block, the bigger the reward gets. Therefore, miners or pools is attracted to exploiting this point and get maximum rewards by setting the block timestamp in the future. This can drag mining difficulty down to the bottom as a side effect. **EPoW reward algorithm is designed so that any forged extra time posted by possible malicious actor\(s\) is rather penalized for every second compared to issuing new block with shortest timestamp for the next block. There are simply no incentives for them to do this. QWC does not consider this argument valid. A game theory analysis of this changes shows the same.**

![Click to enlarge the table](../../.gitbook/assets/game-theory.png)

