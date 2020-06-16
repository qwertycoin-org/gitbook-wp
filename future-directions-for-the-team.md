---
description: Last Updated 2020-06-16
---

# Future Directions for the Team

**Future Directions for the Team and the Community Members**

![](.gitbook/assets/top-2.png)

**A. Multi Language Support \(Wallet Software and Web\)**

Qwertycoin wallet platforms\(Desktop/Web/Mobile\) and QWC official websites will support multiple languages. English is the default language for the software services. Additional language updates shall be requested through official communication channels.

**B. Transforming QWC into Blockchain 3.0**

QWC developers and communities shall find work towards to get below all five properties.

* High Scalability
* Interoperability
* Sustainability
* Privacy
* Governance

B-1. High Scalability

As written in the main part of this whitepaper, Blockchain size grows in linear trend under a fixed set of parameters. These configurations such as block time and block size embedded in codes will have be changed from QWC blockchain in the future depending on the outcome of QWC’s high scalability solution.

QWC proposes to solve this scalability issue by generating a new \(genesis\) reference block after a fixed interval. Our approach is different from a hard fork, which most cryptocurrency developers opt to choose for solving this issue.

The validation of ring signature back to genesis block will add significant loads to QWC network in the later stage of any blockchain as the number of transactions increases. To minimize this bottle neck, a mega block will be issued. Since the ring signature verifications on this mega block will be confirmed by checking all previous signatures from the previous blocks, this block can act as a new reference point for future ring signature verifications thereafter.

A complete blockchain data file up to this mega block will be backed up and stored in the conventional blockchain data base as a backup source. Users can download this complete blockchain file as well if their systems have enough processing power and storage to run wallets or nodes. If not, they can always connect to remote nodes to use QWC blockchain.

It is a type of compression that will keep our working blockchain to a manageable size in the long run. Assuming that average internet speed of 100Mbps, which can provide 12.5MB/s download speed in optimal condition, this \(genesis\) reference block shall be created before every 100GB of blockchain size, equivalent to 100,000 blocks \(pprox.. 139 day interval\) to allow seamless network-wide synchronization within an hour.

In order to create this genesis reference block, all wallets initiate self-transactions to assure the number of coins per address is correctly reflected in this mega block to avoid ring signature verifications back to the genesis hash of individual address for future transactions.

The prerequisites required for this plan

1. 2FA enabled wallets \(preferably mobile or web wallet\)
2. A permission feature in wallet to **only allow self-transactions** required for generating reference blocks.
3. Optimizing difficulty algorithm \(or network propagation time setting\) depending on the total size of transaction hashes to be included in the reference block to avoid any fork from possible malicious attack.
4. Synchronization \(Automatic download of the reference block\) feature after reference block creation for daemon.

A higher transaction fee will be charged to wallets that failed to be included\(or make a self-transaction\) in the reference block for additional loads on QWC network as a penalty, but it also motivates users to adapt to mobile/web wallet environment, that boosts the effectiveness of QWC’s scalability solution.

B-2. Interoperability and Privacy \(Through Reserve Requirement System \[The Purpose of Qwertycoin Foundation\] and Billionaire Club\)

The fundamental of blockchain interoperability largely depends on the basic algorithm on which cryptocurrencies are built. It will come down to choices of cryptocurrency systems or platforms that are popular and how many businesses/entities/organizations/communities are willing to build blockchains above such platform. QWC is a cryptocurrency and it means that it should be able to convert to other cryptocurrencies at users’ discretions and used as a mean of payment.

Privacy is compromised when they make a C2C or C2F transactions through an exchange platform with AML and KYC processes in place.

To solve these two issues, QWC team proposes the following solution with three prerequisites.

1. QWC Foundation – Reserve Requirement System up to 7% of maximum QWC supply \(Max. 18.447 Billion QWC\)
2. QWC Billionaire Club – Total holding stake of 20% of maximum QWC supply \(Max. 36.894 Billion QWC\)
3. QWC exchange accounts on all exchange platforms that list/trade QWC.

First, a trading solution will be developed or implemented, not in a form of a conventional exchange, but more like a bot system for all members.

C2C Transaction \(Coin to Coin Exchange\)

Seller/Buyer -&gt; Wallet \(Transaction Fee\) -&gt; Individual Exchange \(CEX/ DEX\) & API-&gt; C2C Exchange \(Exchange Taker/Maker Fee\)

to

Seller\(Lender\)/Buyer\(Loaner\) -&gt; Qwerty Wallet -&gt; C2C Exchange based on Best Market Price from Multi-Exchange API \(CEX / DEX\)

1. Buyer\(Loaner\) checks exchange rate from wallet software.

2. The bot will allocate the best trading deal on the market among exchanges.

3. Buyer\(Loaner\) initiates C2C exchange upon confirming exchange rate + service fee + receiving address of exchanged coin, which sends QWC to a designated wallet address + transaction fee in QWC \(% of total transaction\)

4. The QWC coins funded by Seller\(Lender – Reserve Requirement System and/or QWC Billionaire Club\) on exchange platform will initiate C2C exchange from the market and send the exchanged coin to Buyer\(Loaner\)’s designated address excluding a service fee form exchanged coin unit. \(% of total transaction\)

5. Exchange status will be confirmed in QWC wallet software.

Pro:  
1. Personal identity is masked through this system.  
2. Buyers can receive the best market deal by taking the lowest sell order rate from Multi-Exchange API \(CEX / DEX\) at their fingertips.  
3. Lenders can receive the best market deal by making the highest buy order rate from Multi-Exchange API \(CEX / DEX\) at their fingertips + service fees.  
4. By normalizing sell price in the market, buy price is also normalized and stabilized. This will be the main difference from other cryptocurrencies in terms of trading ecosystem.

Con: Investor holds risks against the overall stability of the QWC blockchain.

C2F / F2C Transaction \(Coin to Fiat / Fiat to Coin Exchange\)

For this type of trade It is important to inform our members that your registrations on exchange platforms with personal information such as ID and bank/credit card accounts will/can expose your identity and your actions and outcomes from trading activities can be subjected to applicable laws and regulations. We are dealing with centralized currencies and their systems in the end. This service is not an option for QWC network.

For cryptocurrency to fiat exchanges, it would be the best to have local stores and businesses to engage and host an individual/independent exchange to allow more decentralized network of QWC blockchain. There will be no requirement of personal information for this type of transactions.

B-3. Sustainability

Through EPoSe in place, there will be an infinite circulation of incentives among network service providers and it will energy-wise more efficient for our environments. QWC blockchain and its infrastructure is supported by the core team and the source code is provided as an open source on github for 3rd party integration. The more 3rd parties’ services are provided, the less involvement of core team will take place in the service.

B-4. Governance

The most important part of the governance is the incentive system for participants. Please refer to EpoW and EPoSe sections of this white paper.

Unless Process Automation or AI takes over the entire development and implementation of new features or updates, QWC blockchain will have a centralized authority run by human that develops features, manages implementations/updates and provides support for the service.

QWC team \(a centralized authority that consists of a group of people who volunteer to provide services\) reflects the decisions of QWC community through a community voting system. All QWC members can participate in making community-wide decisions.

\*\*\*\*

