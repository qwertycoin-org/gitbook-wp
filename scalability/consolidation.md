---
description: Last Updated 2020-07-28
---

# Consolidation

Consolidation is a solution for the wallet-side scalability.

Consolidation is a wallet feature that will literally consolidate all the UTXOs\(Unspent Transaction Outputs\) from previous incoming transactions to a smaller set \(preferably one set if continuously consolidated\) of outputs without changing the balance in the wallet.

**The benefits of consolidation are:**  
  
1. Transaction size: a single transaction with the amount of 500 million QWC is about 4kb. Now users can send a large number of coins without tx size limitation when and if necessary.

2. Synchronizing speed: wallet is no longer required to scan all the way back to the first transaction of the wallet address. The height of the first confirmation is where sync should start.

3. Reducing server load: by reducing the dependency, the server operates more efficiently. 

The consolidation feature shall be considered a network-wise movement from users for solving the scalability issue, just as Genesis Reference Block\(GRB\) is for the node-side within public blockchain projects.

