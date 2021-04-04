---
description: Last Updated 2021-04-04
---

# Time Locked Transactions \(TLT\)

Time Locked Transaction \(TLT\) is a preliminary work for smart contract implementation.

These TLTs will take place **on a different mempool** from the one we are using for normal transactions.

This is how it works.

1\) User A creates a TLT\(X\) and TLT\(X\) will not be included in a block until a certain time is passed.

2\) Unlike normal transactions User A can cancel TLT\(X\) by creating a negative transaction  
ex\) -TLT\(X\) before the designated time condition is met.

3\) If there is no cancellation of TLT\(X\) until the designated time condition, TLT\(X\) will be moved to the mempool used for normal transactions. At this point, TLT\(X\) becomes irreversible.

