---
description: Last Updated 2020-07-05
---

# Egalitarian Proof of Work \(EPoW\)

QWC introduces Egalitarian Proof of Work \(EPoW\) for the first time in blockchain space for protecting the blockchain from the well-known majority attacks and double-spending. This is also the first step towards EPoSe consensus.

The core team found fundamental flaws in the original CryptoNote Proof of Work because it allowed miners, especially influential groups of miners, to take advantage of mining more coins than what the system was intended for. Also, difficulty algorithm \(DA\) was not carefully designed to cover many different possible cases.



This ‘consistency’ is a multiplier to the base reward, and it can either make the block reward between 0.8% and 200% of the base reward depending on the time difference within adjacent blocks.  

\[Table 2. An example for mining reward based on EPoW algorithm between block 500,000 and 500,019\]

![Click to enlarge the table.](../../.gitbook/assets/2%20%281%29.png)

In \[Table 2\], EPoW Reward column shows adjusted base reward for each block from introduction of ‘consistency’

Among CryptoNote developers, some expressed concerns that the fact that the longer miners mine to find a block, the bigger the reward gets. Therefore, miners or pools is attracted to exploiting this point and get maximum rewards by setting the block timestamp in the future. This can drag mining difficulty down to the bottom as a side effect. **EPoW reward algorithm is designed so that any forged extra time posted by a malicious actor is rather penalized for every second compared to issuing a new block with the shortest timestamp for the next block. There are simply no incentives for them to do this. QWC does not consider this argument valid. A game theory analysis of miners' behavior leads to the expected result.**

![Click to enlarge the table](../../.gitbook/assets/game-theory.png)

