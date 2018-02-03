# Swift Protocol White Paper (Draft)

The Swift Protocol is a DAO-based protocol that implements a Universal Basic Income (UBI)

**https://www.swiftdemand.com/**

## Abstract
The Swift Protocol is an implementation of a Decentralized Autonomous Organization (DAO) that provides Universal Basic Income. The Swift currency is designed to be used as a transactional currency. It has been designed for [low transaction latency](#transaction-latency), the ability to [scale to thousands of transactions per second](#transactions-per-second), [low transaction fees](#low-transaction-fees), and [dispute resolution for transactions](#buyer--seller-protections). Income is distributed on a daily basis to all participants and represents a UBI. This paper is written to give a clear understanding of how the Swift Protocol works.

- [Introduction](#introduction)
- [Account Types](#account-types)
  * [Swift Citizens](#swift-citizens)
  * [Swift Entities](#swift-entites)
  * [Delegated Nodes](#delegated-nodes)
  * [Identity Providers](#identity-providers)
- [Income Distribution](#income-distribution)
  * [Stage One](#stage-one)
  * [Stage Two](#stage-two)
  * [Region Multiplier](#region-multiplier)
  * [Referral System](#referral-system)
- [DAO based governance](#dao-based-governance)
  * [Elections](#elections)
  * [Election Duration](#election-duration)
  * [Delegated Node Voting](#delegated-node-voting)
- [Transaction Capabilities](#transaction-capabilities)
  * [Transactions Per Second](#transactions-per-second)
  * [Low Transaction Fees](#low-transaction-fees)
  * [Buyer / Seller Protections](#buyer--seller-protections)
  * [Transaction Latency](#transaction-latency)
- [Compensation](#compensation)
  * [Delegated Node Salary](#delegated-node-salary)
  * [Identity Provider Salary](#identity-provider-salary)
- [Reserved Funds](#reserved-funds)
  * [Funding Proposals](#funding-proposals)
- [Consensus Protocol](#consensus-protocol)
  * [Selecting Forgers](#selecting-forgers)
  * [Consensus](#consensus)
- [Protections](#protections)
  * [Skip Attack ](#skip-attack)
  * [Incubation Period](#incubation-period)
  * [Sybil Attacks](#sybil-attacks)
  * [Round Robin Order Attack](#round-robin-order-attack)
  * [Deactivation of an Identity Provider](#deactivation-of-an-identity-provider)
- [Constitution](#constitution)
- [Connection to SwiftDemand](#connection-to-swiftdemand)
  * [SwiftDemand Features](#swiftdemand-features)
- [References](#references)

## Introduction
Universal Basic Income is a critical societal movement that must exist for the world to continue to function as jobs continue to be replaced by automation<sup>[[1]](#1)</sup>. We live in a world with more abundant resources than ever before, yet there are still people who struggle to make ends meet. It is our duty as humans to ensure that every person has access to the core necessities of life. The Swift Protocol is a proposal that lays the framework for a DAO with the purpose of distributing Universal Basic Income. Worldwide adoption of the Swift Protocol will allow the dream of Universal Basic Income to become realized. The protocol has been designed with practical and proven solutions, with additional functionality to aid mass adoption.

## Account Types
To create a transactional currency that provides basic income, some form of structure is required to ensure the following remain true:

1. A unique individual should only be allowed to have one account that receives basic income.
2. Accounts not tied to individual identities must be permitted to exist for business and privacy reasons.
3. The system must remain decentralized to avoid single points of failure.
4. Rules must be able to be modified over time to allow for the changing needs of an active economy.

To solve these issues the Swift Protocol proposes 4 different account types that together, fill these different responsibilities.

### Swift Citizens
Swift Citizens are unique inidividuals that have been validated by an [Identity Provider](#identity-providers). Citizens have the ability to add claims to the blockchain once every day (days begin and end at midnight UTC). Swifts will be awarded based on the number of days passed--with a maximum of seven. For example, if the three days have passed and a user makes a claim with the current production rate at 100 Swifts, 300 Swifts will be awarded.

### Swift Entities
Swift Entities are not connected to a personal real-world identity and therefore do not receive Basic Income. These accounts still must be approved by Identity Providers before being created. An Identity Provider must be linked to all Swift Entities, however Identity Providers are not allowed to make transactions on behalf of a Swift Account. Delegated Nodes and Identity Providers both inherit from the Swift Account type.

### Delegated Nodes
Delegated Nodes are responsibile for maintaining full nodes and creating new blocks. Each election cycle Swift Citizens will sign votes to help choose which Delegated Nodes they would like to represent them. This means that Delegated Nodes act as elected officials with the capability to vote on proposals to add/remove other Delegated Nodes and Identity Providers.

### Identity Providers
Identity Providers are responsible for validating the identity of Swift Citizens and creating new citizens by generating a keypair for each new Swift Citizen and including the idenentity on the blockchain. Identity Providers have the added responsibility of protecting Swift Citizens whose keys they control with buyer and seller protections.

**Identity Providers** have the following capabilities:
* Add new Swift Citizens
* Freeze/Unfreeze Swift Citizens they have verified
* Make transactions on behalf of Swift Citizens they have verified
* Delete Swift Citizens they have verified
* Rescue orphaned Swift Citizens

## Income Distribution
The goal of the Swift Protocol income distribution model is to provide a fair method of providing Swifts to all Swift Citizens. The distribution method also must ensure that the amount of Swifts entering the system should never cause a decrease in value. To more quickly reach the state where a mature economy has formed, early users will receive extra daily Swifts during Stage One.

Swifts are distributed to users on a daily basis with a maximum of seven unclaimed days of Swifts. A Swift Citizen must explicity claim their Swifts at least once per week to convert their *Unclaimed Swifts* to normal *Swifts*. Days are marked by blocks that occur between 00:00 UTC to 23:59 UTC.

The total number of Swifts targeted to be added to the economy in Stage One is 70 Billion. After this stage has been reached, Stage Two will limit the amount of new Swifts that enter the economy to a healthy inflation rate.

### Stage One
In Stage One, income will be generated at an accelerated rate so the economy can grow to maturity within a shorter time period. During this stage, Swift Citizens will receive Swifts dependent on the number of Swift Citizens that are in the ecosystem. The formula to calculate the _Income Distribution Multiplier_ is as follows: `(781250 / (5^(log10(users))))` with a maximum value of 100, and minimum value of 1.

### Stage Two
After the 70 Billion cap has been reached by following the formula of Stage One, Stage Two will come into effect. During this stage, new Swifts will be given out to users at an inflation rate decided by the [Delegated Nodes](#delegated-node-voting) to all users in the ecosystem. It's their responsibility to choose an inflation rate that will avoid devaluing existing currency while ensuring the distribution is sufficiently large.

### Region Multiplier
Several different income tiers will exist based on the cost of living associated with each region. The tiers and the multipliers associated with them will be decided by the [Delegated Nodes](#delegated-node-voting). The region that each citizen belongs to will be validated by [Identity Providers](#identity-providers) when added to the blockchain. These multipliers will range between 0.01x to 1.0x.

### Referral System
When a new Swift Citizen joins, there's an option to include the public key of the Swift Citizen that referred them. Referral bonuses are calculated using `5 * Income Distribution Multiplier`. For example, if there are 100,000 Swift Citizens at the time of a referral, the bonus would be 500 Swifts. 

## DAO Based Governance
Governance is an integral part of the Swift Protocol as it allows for outside data to be safely used for identity verification and economic control. However, the decentralized and autonomous elements of the Swift Protocol allow certain rules to be set in stone. These rules ensure a fair system exists where nobody has the ability to cheat in a way that is possible with centralized systems.

The Swift Protocol features an internal system that simulates a decentralized government. Swift Citizens have the responsibility to elect representitives known as [Delegated Nodes](#delegated-nodes) that will have various powers within the government. These Delegated Nodes are required to both maintain the blockchain, forge new blocks, and vote on proposals.

### Election of Delegated Nodes
Each Swift Citizen has the ability to cast one vote on the network during each election of Delegated Nodes. The Delegated Nodes that receive the most votes will be elected to serve during that election cycle. The number of Delegated Nodes is decided by the following formula: `(10 + (swift_citizens/100000))`

### Election Duration
Elections will occur every six months for the first five years. Citizens will have a two-week time period in which they may cast their vote for their preferred Delegated Node. After the voting period has ended, a one-month grace period will begin--giving time for newly-elected nodes to prepare for their responsibility, and to prevent any potential splits in the chain.

### Delegated Node Voting
Delegated Nodes have the following abilities
* Elect new Identity Providers.
* Ban existing Identity Providers.
* Revert the chain state to some time within the past 72 hours.
* Ban Delegated Nodes.
* Elect replacement Delegated Nodes.
* Choose the [regional tiered-income levels](#region-multiplier).
* Choose the inflation rate in [Stage Two](#stage-two).
* Vote on the [salary for Delegated Nodes](#delegated-node-salary).
* Vote on the [Salary Multiplier for Identity Providers](#identity-provider-salary).
* Vote to approve or disapprove [funding proposals](#funding-proposals).

To perform these abilities, a proposal must be submitted to the blockchain by one Delegated Node. All other Delegated Nodes on the network will then vote on the proposal. Any proposal that receives 50% + 1 votes within 24 hours of submission will be executed.

## Transaction Capabilities
The Swift Protocol is built to be a transactional currency. This means that exchanging money in the form of Swifts needs to be *at least* as convenient and safe as traditional banking systems. Four main factors have been focused on that will allow transferring Swifts to be as simple as clicking a button or swiping a credit card.

### Transactions Per Second
Due to the controlled nature of the Delegated Node network, nodes can work to forge blocks extremely fast with a targeted time of three seconds per block. Other algorithms that have implemented proof-of-stake algorithms (such as EOS--which has the same functionality of having selected speaker nodes that forge blocks<sup>[[2]](#2)</sup>) have proven that it's possible to scale such a system to 50,000 transactions per second<sup>[[3]](#3)</sup>. For comparison, Visa is able to scale to 24,000 TPS <sup>[[4]](#4)</sup>.

### Low Transaction Fees
Transactions have no inherent cost on SwiftDemand, however [Identity Providers](#identity-providers) have the ability to set transaction fees--allowing them to have funds to resolve transaction disputes. The Swift Protocol reserves 80% of each block to be used exclusively by Identity Providers. The space is further partitioned by Identity Provider--proportional to the number of Swift Citizens each has verified with a minimum of 10 transactions per block. It's therefore the responsibility of Identity Providers to ensure that spam transactions are not added to the chain. The remaining 20% of each block will be open for transactions with a bidding system--in a similar manner to how bitcoin functions <sup>[[5]](#5)</sup>.

### Buyer / Seller Protections
Transactions are able to be signed either by a Swift Citizen's private key or the private key of an Identity Provider. This gives Identity Providers the ability to reverse transactions. Non-authorized transactions should only be used to settle disputes between buyer and sellers on the platform. When reversing funds is not possible, Identity Providers have the responsibility to use the money earned from transaction fees to settle any issues.

### Transaction Latency
A single confirmation of a transaction will usually occur within three seconds after publishing a transaction. Normal transactions should be signed by Identity Providers on behalf of a Swift Citizen when the citizen initiates an action. Therefore, any transaction signed by an Identity Provider has a high level of trust--as an Identity Provider is very unlikely to attempt a double-spend attack and can be trusted after a single confirmation. Transactions signed by individual citizens should wait for multiple transactions before being treated as final; this follows the same logic laid out in Bitcoin's Whitepaper <sup>[[6]](#6)</sup>.

## Compensation
Compensation for Delegated Nodes and Identity Providers are a core part of the Swift Protocol. This compensation is used to heavily disincentivize bad behavior as these bad actions would result in heavy financial losses. Compensation also has the added benefit of making sure that the entire economy can continue to run smoothly for an indefinite period of time as funds will never be depleted.

Both Delegated Nodes and Identity Providers receive a salary in Swifts for their service. Salary will be paid out on a daily basis at the same time Swift Citizens receive their daily income. The Swifts generated will initially be drawn from the 70% pool dedicated to regular Swift distribution. Once that pool has been fully distributed, Swifts for salaries will be created in addition to the Stage Two inflation distribution.

### Delegated Node Salary
Delegated Nodes will each receive an equal salary. The Delegated Nodes themselves will vote on their own salary--with the constraint that the salary must stay within a certain percentage of the previous salary. In the event that Delegated Nodes attempt to abuse this power, it's the responsibility of Swift Citizens to [vote out the nodes](#elections).

### Identity Provider Salary
The _Salary Multiplier_ for Identity Providers is decided by the Delegated Nodes. An Identity Provider's salary is determined by multiplying the number of Swifts that have been claimed by Citizens under that specific Identity Provider by the Salary Multiplier. For example, if the Salary Multiplier is 0.01 and the Identity Provider has 100,000 active validated citizens that claimed 5,000,000 Swifts during that day, the Identity Provider will receive 50,000 Swifts at the first block after midnight UTC. 

## Reserved Funds
30 Billion Swifts will be reserved; these Swifts are not controlled by any central source. Delegated Nodes have the ability to award these funds to proposals with a majority vote. It's the responsibility of the Delegated Nodes to assign these funds on an as-needed basis to Identity Providers, Delegated Nodes, Swift Citizens, or Swift Entities in an effort to further the success of the Swift Protocol.

### Funding Proposals
When a Swift Citizen or Identity Provider requires funds to perform some task, they must submit a public funding proposal. This proposal will be written in plain text, signed with the requester's private key and then added to the blockchain. Nodes will then have one week to vote on the proposal. Non-votes are counted as "No"s. A majority consensus is required for the funds to be transferred.

## Consensus Protocol
A new consensus mechanism is used in the Swift Protocol that allows for extremely fast block times while still being trustable. The Swift Protocol uses a new consensus mechanism called DPOI (delegated Proof of Identity). The mechanism works almost identitally to DPOS (delegated Proof of Stake) <sup>[[7]](#7)</sup>. The primary difference is that in DPOS people have a say proportional to the amount of stake they own in the currency. In DPOI, each Swift Citizen has the ability to cast a single vote regardless of the stake they own.

### Selecting Forgers
When Delegated Nodes are elected, they are placed into an ordered list of Delegated Nodes that are permitted to forge blocks. The ordering is determined by the amount of votes that each Delegated Node has received during an election. Nodes will then take turns forging blocks round-robin. When it's a node's turn to create a block, they will have a ten-second window to forge a block. If no block is forged during this duration, the next Delegated Node on the list will also have permission to forge a new block. This will be achieved by using a timestamp server <sup>[[6]](#6)</sup>.

### Consensus
Consensus is decided by following the longest chain. Delegated Nodes that attempt to perform a double-spend attack by signing multiple blocks will promptly be [banned by other Delegated Nodes](#delegated-node-voting).

## Protections
Due to the decentralized government system implemented by the Swift Protocol, there are potential attack vectors that should be carefully analyzed. These attacks have been outlined along with their potential impact and preventative measures.

### Skip Attack 
If nodes are in the order `<Bad Node> <Good Node> <Bad Node>`, then the two bad nodes can collude to skip over the good node. When it's the first bad node’s turn to create a block, it can create a block immediately, and only broadcast to the next bad node in the list. The second bad node can then wait ten seconds, sign the node, and then broadcast it normally. The chain with the two bad nodes will be accepted since it's longer. While this attack is normally harmless, it does allow colluding bad nodes to take control of the network with only 25% +1 of the nodes if the nodes happen to be optimally placed.

### Incubation Period
All new Swift Citizens that join the Swift Protocol will be placed into an incubation period of one week. This prevents an Identity Provider from creating fake Swift Citizens to quickly create Swifts for themselves--and gives Delegated Nodes sufficient time to ban the offending Identity Provider.

### Sybil Attacks
Identity Providers are disincentivized from performing sybil attacks as it comes with the risk of getting banned from the platform by Delegated Nodes. Additional safeguards such as the [incubation period ](#incubation-period) and the [blockchain rollback capability of Delegated Nodes](#delegated-node-voting) also exist to help mitigate any abuse. Swift Citizens can attempt to submit fake documents to gain additional basic income, however they are disincentized from doing so since being caught would result in losing both sources of income. It's expected that a few fake accounts may be created, but Identity Providers will be required to have very strict levels of regulation on how they approve new Swift Citizens, which should eliminate most abuse.

### Round Robin Order Attack
A group of colluding bad actors could collude to all try to receive a similar number of votes, allowing them to be placed in similar locations within the round-robin ordering. (See [Selecting Forgers](#selecting-forgers).) A double-spend attack could then be completed with only a handful of bad nodes. This attack, however, can only occur once before being detected. Large transactions should wait for a sufficient amount of confirmations to combat this. Small transactions should be insured by Identity Providers.

### Deactivation of an Identity Provider
In the event that an Identity Provider attempts to perform fraud, they can be banned by [Delegated Nodes](#delegated-node-voting). In the event that damage has already been caused by the action of the Identity Provider, Delegated Nodes can vote to revert the chain to a previous state with an Identity Provider banned. This will cause a large amount of economic damage, but is meant as a last resort to enable the Swift Protocol to not be devastated by an attack and to disincentivize Identity Providers from acting poorly. Swift Citizen accounts that belong to that Identity Provider would consequently be orphaned until they were claimed and validated by another Identity Provider.

## Constitution
Due to the fact that the Swift Protcol directly interacts with the real world through decentralized governance, there are certain rules which cannot be programmatically enforced yet are crucial for the Swift Protocol to function as intended. Delegated Nodes or Identity Providers that perform actions in contradiction to the items listed in the constitution should be [banned](#delegated-node-voting).

* Regional tiers should be based on the cost-of-living associated with the geographical region of which the Swift Citizen is a legal resident.
* Identity Providers should share a decentralized internal system of identites to guarantee Sybil accounts cannot be created. The internal system should also make any potential transitions of Swift Citizens easier to accomplish.
* Delegated Nodes should be [banned](#delegated-node-voting) for the following reasons:
  * Regularly not performing their duty to vote on proposals.
  * Not forging new blocks during their turn within dBFT.
  * Refusal to include block data that does not support them.
  * Unreasonable policy voting that demonstrates harmful favoritism.
* Official announcements should always be signed to protect against forgery.
* The inflation rate should be balanced with the following factors in mind:
  * Avoiding an inflation rate that would overly devalue existing Swifts.
  * Real-world effects that would result from a change in the rate.
  * The amount of income required to provide the basic neccesities in life.
* Identity Providers should be [banned](#delegated-node-voting) for the following reasons:
  * Weak approval process allowing sybil accounts--whether due to malice or negligence.
  * Failing to provide adequate dispute resolution for transactions.
  * Not performing their duty to approve new Swift Citizens.
  * Unwillingness to cooperate with other Identity Providers on the platform.
* Proposals that are approved for funding should remain relatively liberal when the protocol is in its early stages and should slowly become more strict over time.
* Identity Providers should shield the user from the knowledge that there is a one-week incubation period and that transactions can take a few seconds to process. From the user's perspective, it's important that SwiftDemand appears to function as efficiently as a centralized system. In the event something does go wrong, it's the responsibility of the Identity Provider to take the loss to remedy the situation.

## Connection To SwiftDemand
The Swift Protocol is simply the protocol that has been outlined above. SwiftDemand will be the initial Identity Provider on the Swift Protocol and all Swifts that exist on SwiftDemand at the time of launching the Swift Mainnet will be transferred at a 1:1 ratio. Swift Citizens will be required to undergo stricter Identity Verification requirements at this time to comply with KYC<sup>[[8]](#8)</sup> and AML<sup>[[9]](#9)</sup>. 

### SwiftDemand Features
SwiftDemand is designed to be an extremely user-friendly platform that requires no prior knowledge of cryptocurrency--setting the standard for future Identity Providers. SwiftDemand provides an API as well as a marketplace to make it as easy as possible to transfer Swifts for goods and services.

## References

<a name="1">[1]</a> https://www.mckinsey.com/global-themes/future-of-organizations-and-work/what-the-future-of-work-will-mean-for-jobs-skills-and-wages

<a name="2">[2]</a> https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md#transaction-confirmation

<a name="3">[3]</a> https://www.youtube.com/watch?v=UC6RYwYPnpU

<a name="4">[4]</a> https://usa.visa.com/run-your-business/small-business-tools/retail.html

<a name="5">[5]</a> https://en.bitcoin.it/wiki/Transaction_fees

<a name="6">[6]</a> https://bitcoin.org/bitcoin.pdf

<a name="7">[7]</a> https://www.researchgate.net/publication/318131748_An_Overview_of_Blockchain_Technology_Architecture_Consensus_and_Future_Trends

<a name="8">[8]</a> https://en.wikipedia.org/wiki/Know_your_customer

<a name="9">[9]</a> https://www.investopedia.com/terms/a/aml.asp

<a name="10">[10]</a> https://github.com/CirclesUBI/docs/blob/master/Circles.md

**Note**
This Swift Protocol is designed to evolve over time. Improvements will be made as new technology is developed or it becomes clear that a change would improve the system. The core principle of distributing a Universal Basic Income will NEVER change.

Here are examples of changes / improvements that may come in the future:
* Identity verification performed in a decentralized manner similar to circles <sup>[[10]](#10)</sup>--if proven effective against sybil attacks.
* Separating the responsibility of running a platform from verifying identities.
* A bounty program to find sybils.
* A smart contract-enforced insurance system provided by identity providers.
* Having subsystems for individual countries with unique currencies while remaining automatically exchangable.
* Hashed biometric data stored on the chain as added protection against sybil attacks.
