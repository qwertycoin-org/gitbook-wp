---
description: Last Updated 2020-06-16
---

# Egalitarian Proof of Service \(EPoSe\) - Hybrid EPoW /EPoS

**Circulation: How to Get Coins \[Masternode\]: Egalitarian Proof of Service \(EPoSe\)**

The word egalitarian stands for providing equal rights and equal opportunities. It is free to run a QWC masternode since node reward program does not offer a staking option for providing a node. In order for nodes to receive rewards, a node must be configured and used as a remote daemon in wallet software. Based on the number of transactions processed in remote daemon connections, Maximum 10 QWC is rewarded per transaction. \[June 29th, 2018\]

QWC nodes perform following tasks in the network.

1. Holding transactions in the memory pool so that a miner can find a block with a group of these transactions
2. Verifying one-time ring signature of entire blockchain
3. Validating correct blockchain during a chain split from PoW
4. Propagating validated blockchain to all daemons running in our network

As QWC develops and brings more traffic to our network, the performance of these nodes will be very critical to our success for following reasons.

1. When blockchain size increases, it will take more time to synchronize with the network since desktop wallets are mostly not online.
2. Mobile wallets will always use a remote daemon feature and network sync will be instant.

QWC team believes that the existing PoS reward system is not fair since the cost of running a node can be more than its rewards for the amount of work they provide to the network, and node information is currently not available when wallet users want to choose a remote daemon. In order to change this, QWC will implement EPoSe system.

EPoSe is based on the concept of dedication in terms of service duration of nodes for their conformance, performance and reliability within QWC network. It features is a block reward program for node operators based on dedicated service time \(Uptime\).

There are 4 components to make EPoSe work.

1. Nodes, run by network participants
2. Sentinel, which checks the status of nodes periodically filters nodes based on conformance and performance criteria
3. Node Map, which shows geographical information of operating nodes
4. Network Explorer, which displays the network status of node and detailed information.

Sentinel provides API of online-node information after checking node’s conformation to network requirements and the performance of its hardware and internet speed as well as 24-hour and Uptime measurements to Network Explorer\(NE\). NE displays information from Sentinel to allow users to select desired nodes while having the ability to check the overall status of each node. The API provided by Sentinel will be available for the selection of remote nodes.

There will be several conformance and performance criteria evaluation for nodes of which the data will be identified / measured / stored / analyzed to determine nodes eligible for the rewards of accumulated transaction fees over a set period. Through QWC’s solution towards scalability,

EPoSe reward system has following features:

1. Rewards: accumulated transaction fees, which has been traditionally awarded to miners, are switched to node operators. Depending on the current operation costs of nodes, this reward scheme will be adjusted when deemed necessary.
2. Reward Period: 24 hours UTC time
3. EPoSe algorithm functions just like mining but provides infinite rewards throughout the lifetime of QWC blockchain without causing any inflation.

\[Table 5. Transaction Fee & EPoSe Rewards Estimation\]

![Click to enlarge the table](../../.gitbook/assets/5%20%281%29.png)

