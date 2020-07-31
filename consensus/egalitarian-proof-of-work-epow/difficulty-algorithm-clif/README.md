---
description: Last Updated 2020-07-23
---

# Difficulty Algorithm - CLIF \(Critical Level Impediment Failsafe\)

**CLIF stands for Critical Level Impediment Failsafe.** Yes, it sounds similar to the word "cliff", and this DA is supposed to do just that. Drop difficulty. It is an algorithm that is triggered when a long interval is detected between the last block time and the current block.

**So why do we need CLIF and what does it do?**

As mentioned, CIMA + Consistency already protects the blockchain from individuals with malicious intent to get block rewards by using massive hash rates. Yet, it still does not solve another vector of attack, stalling the network itself.

Although miners with large hash rates cannot gain profits from attacking QWC blockchain at all [\(an example\)](https://wp.qwertycoin.org/consensus/egalitarian-proof-of-work-epow/difficulty-algorithm-cima-confidence-interval-moving-average/testnet-result), attackers with the sole purpose of sabotaging the blockchain can increase the difficulty and drop out at any moment. 

This creates a huge gap between blocks and halts the operation of blockchain for a long time. As a result, honest and long-term miners and wallet users are negatively affected.

Depending on the duration and the magnitude of attack\(s\), the previous solutions were;  
1. A certain amount of mining power is rented from NiceHash like services to lower the difficulty.  
2. Just wait long enough until a future block is found.

**What improvements does CLIF bring to crypto-space?**

This type of difficulty adjustment was not possible because  
1. such action exposed the network's block rewards to centralized groups and influential miners.  
2. the conventional DA\(difficulty algorithm\) is simply incapable of reacting to such an event due to inherent nature to forecast the future from historical data.

Now that we have protection on reward from attackers, implementation of CLIF is possible.

When triggered, a new block template is issued with an adjusted difficulty to allow miners to find blocks within a short period of delay.The timing of the trigger is designed so that the amount of work versus reward yields the best consistency.

**CIMA + CLIF + Consistency = A stainable self-adjusting EPoW blockchain = QWC**

