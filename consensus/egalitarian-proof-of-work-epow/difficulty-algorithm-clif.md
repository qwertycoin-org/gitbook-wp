---
description: Last Updated 2020-07-23
---

# Difficulty Algorithm - CLIF \(Critical Level Impediment Failsafe\)

While CIMA+Consistency with Poisson measure protects the blockchain from malicious intents to get rewards by using massive hash rates, it still does not solve another vector of attack that can stall the network.

Although miners with large hash rates cannot gain profit from attacking QWC blockchain, attackers with the sole purpose to sabotage the blockchain can increase the difficulty and drop out at any moment. 

This creates a huge gap between blocks and halts the operation of blockchain for a long time depending on the duration and the magnitude of attack\(s\). As a result, honest and long-term miners and wallet users are negatively affected.

The solutions to this issue in the past were  
1. a certain amount of mining power is rented from Nicehash like services to lower the difficulty.  
2. just wait long enough until a future block is found.

The conventional DA\(Difficulty Algorithm\) is simply incapable of reacting to such an event due to inherent nature to forecast the future from historical data. 

CLIF stands for Critical Level Impediment Failsafe. It is an algorithm that is triggered when a long interval is detected between the last block time and the current block.

When triggered, a new block template is issued with an adjusted difficulty to allow miners to find blocks within a short period of delay.

The timing of the trigger is designed so that the amount of work versus reward yields the best consistency. 
