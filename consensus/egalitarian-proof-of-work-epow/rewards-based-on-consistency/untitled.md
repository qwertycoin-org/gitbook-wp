# An example of how QWC prevented CryptoNote block reward manipulation

\[Figure 2. Block Reward Adjustment using 'consistency'\] 

![Mining Reward Graph after EPoW \(Area A to C6\)](../../../.gitbook/assets/epow-reward-graph-area-marking.png)

Area A: An area where miners can take more coins per second if find a block within 120 seconds.  
  
Area B: An area that is bound by CN block reward schedule after 120 seconds of mining. No matter how long it takes for miners to find a block, the block reward stays at the level before 120 seconds.

Area C1 - C6: An area where block rewards will increase after 120 seconds of mining. Current block reward algorithm is set to adjust the consistency factor using a power of 1/4.

To demonstrate how this works in our chain 

As mentioned previously, the consistency is a multiplier to the base reward, and it can either make the block reward between 0.8% and 200.0% of the base reward depending on the time difference within adjacent blocks.  

\[Table 2. An example of mining rewards based on EPoW block reward algorithm between block 500,000 and 500,019\]

![Click to enlarge the table.](../../../.gitbook/assets/2%20%281%29.png)

In \[Table 2\], EPoW Reward column shows adjusted base reward for each block from the introduction of ‘consistency’



