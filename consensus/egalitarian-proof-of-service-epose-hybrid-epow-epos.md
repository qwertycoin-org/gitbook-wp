---
description: Last Updated 2020-07-10
---

# Egalitarian Proof of Service \(EPoSe\) - Hybrid EPoW/EPoS

**`For those developers of other cryptos.. stop copying without giving a proper credit. I see already two CN coins or maybe 3 cheating all the time. Shame on those copies. Implementations are poor and they did not think through. The end realization is incomplete and they jump on to something else to create just hypes. No real work there. Just using names and terms does not make them right. Funny, right?`**

QWC’s EPoSe is the first that introduces a consensus that recognizes all network contributors and has attributes to proportionate rewards based on their services as well as optimizing all levels of services to the latest regulatory and technical standards.

The conventional structure of Proof of Work \(PoW\) or Proof of Stake \(PoS\) allows individuals either in single or in a group to have massive power over the blockchain’s consensus. This is called ‘centralization’. These types of consensus may seem appropriate in our free-market world because Return-on-Investment \(ROI\) must be satisfied or foreseeable in order to bring more attention on board and invest time and money for management and equipment respectively.

The major service groups in QWC network are divided into developers, community managers, mining pool operators, and public node operators.

For codebase and community development, a certain percentage of block rewards shall be reserved, currently set at 10% of block rewards. The activation height of this will be determined and stated in the configuration file of the blockchain. Upon activation, this information will be updated.

For miners in PoW scheme, mining pool wallets receive the block rewards initially and send out miners’ payments based on their contributions in finding the hash value. For solo miners, they receive coins in their wallet immediately. Nothing is changed in payment distribution.

What changes is the formula for determining block rewards for solo miners and mining pools? The concept of time is applied to block reward formula for their consistencies, or continued services. A sudden increase or decrease in hash rate will change the block rewards. More details can be found in the following section: **Egalitarian Proof of Work \(EPoW\).**

For node operators, we considered implementing PoS but this is also problematic because coins are emitted for circulation instead of banking them to run a particular service. In a sense, PoS is very meaningful if the staking party operates an individual service based on a staked number of coins. Since the role of nodes will become more important as more coins are emitted, a new reward algorithm for node operators will be introduced based on the concept of time.

The nodes that operate the required version of the software and served a certain period with sufficient H/W specification and speed will be nominated to become uptime nodes. These nodes will form a quorum for validating blocks and making important decisions in protecting QWC blockchain. This decision process will be coded for their autonomous actions and a certain percentage of block rewards will be provided to these nodes. To avoid any types of centralization, a group of uptime nodes will be randomly selected for the decision-making process.

More details can be found in the following section: **Egalitarian Proof of Service \(EPoSe - QWC Original\)**

The word egalitarian stands for providing equal rights and equal opportunities. It is currently free to run a QWC masternode since node reward program does not offer a staking option for providing a node.

In order for nodes to receive rewards, a node must be configured and used as a remote daemon in wallet software. Based on the number of transactions processed in remote daemon connections, Maximum 10 QWC is rewarded per transaction. \[June 29th, 2018\]

QWC nodes perform the following tasks in the network.

1. Holding transactions in the memory pool so that a miner can find a block with a group of these transactions
2. Verifying one-time ring signature of the entire blockchain
3. Validating correct blockchain during a chain split from PoW
4. Propagating validated blockchain to all daemons running in our network

As QWC develops and brings more traffic to our network, the performance of these nodes will be very critical to our success for the following reasons.

1. When blockchain size increases, it will take more time to synchronize with the network since desktop wallets are mostly not online.
2. Mobile wallets will always use a remote daemon feature and network sync will be instant.

QWC team believes that the existing PoS reward system is not fair since the cost of running a node can be more than its rewards for the amount of work they provide to the network, and node information is currently not available when wallet users want to choose a remote daemon. In order to change this, QWC will implement EPoSe system.

EPoSe is based on the concept of dedication in terms of service duration of nodes for their conformance, performance, and reliability within QWC network. It features a block reward program for node operators based on dedicated service time \(Uptime\).

There are 4 components to make EPoSe work.

1. Nodes, run by network participants
2. Sentinel, which checks the status of nodes periodically filters nodes based on conformance and performance criteria
3. Node Map, which shows geographical information of operating nodes
4. Network Explorer, which displays the network status of the node and detailed information.

Sentinel provides API of online-node information after checking node’s conformation to network requirements and the performance of its hardware and internet speed as well as 24-hour and Uptime measurements to Network Explorer\(NE\). NE displays information from Sentinel to allow users to select desired nodes while having the ability to check the overall status of each node. The API provided by Sentinel will be available for the selection of remote nodes.

There will be a number of conformance and performance criteria evaluations for masternodes of which the data will be identified / measured / stored / analyzed to determine nodes eligible for the rewards of accumulated transaction fees over a set period.

EPoSe reward system has following features:

1. Rewards: accumulated transaction fees, which has been traditionally awarded to miners, are switched to node operators. Depending on the current operation costs of nodes, this reward scheme will be adjusted when deemed necessary.
2. Reward Period: 24 hours UTC time
3. EPoSe algorithm functions just like mining but provides infinite rewards throughout the lifetime of QWC blockchain without causing any inflation.

\[Table 5. Transaction Fee & EPoSe Rewards Estimation\]

![Click to enlarge the table](../.gitbook/assets/5%20%281%29.png)



