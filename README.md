# Swift Protocol White Paper

The Swift Protocol is a DAO based protocol that implements the concept of Universal Basic Income (UBI)

**https://www.swiftdemand.com/**

## Abstract
The Swift Protocol is an implementation of a Decentralized Autonomous Organization (DAO) that provides Universal Basic Income. The Swift currency is desgined to be used a transactional currency and has been designed with low transaction latency, ability to scale to thousands of transactions per second, low transaction fees, and dispute resolution for transaction. Income is distributed on a daily basis to all participants and represents the concept of UBI. This paper is written to give a clear understanding of how the Swift Protocol works while remaining simple to read.

- [Introduction](#introduction)
- [Account Types](#account-types)
  * [Swift Citizens](#swift-citizens)
  * [Swift Accounts](#swift-accounts)
  * [Delegated Nodes](#delegated-nodes)
  * [Identity Providers](#identity-providers)
- [Income Distribution](#income-distribution)
  * [Stage 1](#stage-1)
  * [Stage 2](#stage-2)
  * [Region Multiplier](#region-multiplier)
- [DAO based governance](#dao-based-governance)
  * [Elections](#elections)
  * [Election Durations](#election-durations)
  * [Delegated Node Voting](#delegated-node-voting)
- [Transaction Capabilities](#transaction-capabilties)
  * [Transactions Per Second](#transactions-per-second)
  * [Low Transaction Fees](#low-transaction-fees)
  * [Buyer / Seller Protections](#buyer-/-seller-protections)
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
  * [Incubation Periods](#incubation-periods)
  * [Sybil Attacks](#sybil-attacks)
  * [Round Robin Order Attack](#round-robin-order-attack)
  * [Deactivation of an Identity Provider](#deactivation-of-an-identity-provider)
- [Constitution](#constitution)
- [Connection to SwiftDemand](#connection-to-swiftdemand)
  * [SwiftDemand Features](#swiftdemand-features)
- [References](#references)

## Introduction
Universal Basic Income is a critical societal movement that must exist for the world to continue to function as jobs continue to be replaced by automation\[0]. We live in a world with more abundent resources than ever before, yet there are still people who struggle to make ends meet. It is our duty as humans to ensure that every person has access to the core neccessities needed for life. The Swift Protocol is a proposal that lays the framework for a DAO with the sole purpose of distributing Universal Basic Income. Worldwide adoption of the Swift Protocol will allow the dream of Universal Basic Income to become realized. The protocol has been designed with practical and proven solutions with additional functionality to aid mass adoption. The Swift Protocol will truly revolutionize society by making basic income a sacred human right.

## Account Types
The Swift Protocol functions as a DAO that allows for real world governance to inerconnect with the blockchain. Accounts have the ability to vote on certain events that affect how the Swift Protcol functions. This allows the Swift Protocol to react naturally to real world events by remaining in a fluid state. The Swift Protocol is decentralized to avoid single points of failure while still enabling identity verification and financial controls.

### Swift Citizens
Swift Citizens are unique inidividuals that have been validated by an Idenity Provider. Citizens have the ability to add claim to the blockchain once every day (days begin and end at midnight UTC). Swifts will be awarded based on the amount of days passed with a maximum of 7. For example, if the 3 days have passed and a user makes a claim with the current production rate resting at 100 Swifts. 300 Swifts will be awarded.

### Swift Accounts
Swift Accounts are not connected to any particularly real world identity and therefore do not receive Basic Income. These accounts still must be approved by Identity Providers before being created. An Identity Provider must be linked to all Swift Accounts, however Identity Providers are not allowed to make transactions on behalf of a Swift Account. Delegated Nodes and Identity Providers both inherit from the Swift Account type.

### Delegated Nodes
Delegated Nodes are responsibile for maintaining full nodes and creating new blocks. Each election cycle Swift Citizens will sign votes to help choose which Delegated Nodes they would like to represent them. Delegated nodes have the capability to vote on proposals to add/remove other Delegated Nodes and Identity Providers.

### Identity Providers
Identity Providers are responsible for validating the identity of Swift Citizens and creating new citizens by generating a keypair for each new Swift Citizen and including the idenentity on the blockchain. Identity Providers have the added responsibility of protecting Swift Citizens whose keys they control with buyer and seller protections.

**Identity Providers** have the following capabilities:
* Add new Swift Citizens
* Freeze/Unfreeze Swift Citizens they have verified
* Make transactions on behalf of Swift Citizens they have verified
* Delete Swift Citizens they have verified
* Rescue orphaned Swift Citizens

## Income Distribution
Swifts are distributed to users on a daily basis and will max out at 7 unclaimed days of Swifts. A Swift Citizen must explicity claim their Swifts at least once per week to convert their *Unclaimed Swifts* to normal *Swifts*. Days are marked by blocks that occur between 00:00 UTC to 23:59 UTC.

The total amount of Swifts that are targeted to be added to the economy in the initial stage is 80 Billion. After this stage has been reached stage 2 will kick in limiting the amount of new Swifts that enter the economy to a healthy inflation rate.

### Stage 1
In the first stage income will be generated at an accelerated rate so the economy can grow to maturity within a shorter time period. During this period Swift Citizens will receive Swifts dependent on the amount of Swift Citizens that are in the ecosystem. The formula to calculate the Income Distribution Multiplier is as follows: `(781250 / (5^(log10(users))))` with a maximum value of 100, and minimum value of 1.

### Stage 2
After the 80 Billion cap has been reached by following the formula of Stage 1, Stage 2 will come into effect. During this stage new Swifts will be given out to users at an inflation rate decided by the Delegated Nodes to all users in the ecosystem. It is the responsibility to choose an inflation rate that will avoid devaluing existing currency while ensuring the distribution is sufficiently large.

### Region Multiplier
Several different income tiers will exist based on cost of living associated with each region. The tiers and the multipliers associated with them will be decided by the Delegated Nodes. The region that each citizen belongs to will be validated by Identity Providers when added to the blockchain. These multipliers will range between 0.01x to 1.0x.

## DAO Based Governance
The Swift Protocol features an internal system that simulates a decentralized government. Swift Citizens have the responsibility to elect representitives known as Delegated Nodes that will have various powers within the government system. These Delegated Nodes are required to both maintain the blockchain, forge new blocks, and vote proposals.

### Elections
Each Swift Citizen has the ability to cast one vote on the network during elections. Nodes that receive the most votes will be elected to serve during that election cycle. The amount of nodes is decided by the following formula: `(10 + (swift_citizens/100000))`

### Election Durations
Primary elections will occur every 6 months for the first 5 years of existence. Citizens will have a 2 week time period in which they may cast their vote for their preferred delegated node. After the voting period has ended a 1 month grace period will begin, giving time for newly elected nodes to prepare for their responsibility and to prevent any potential splits in the chain.

### Delegated Node Voting
Nodes have the following abilities
* Elect new Identity Providers
* Ban existing Identity Providers
* Revert the chain state to some time within the past 72 hours
* Ban Delegated Nodes
* Elect Replacement Delegated Nodes
* Choose tiered income levels
* Choose inflation rate
* Vote on salary for Delegated Nodes
* Vote to approve or disapprove Fund Proposals

To perform these abilities a proposal must be submitted to the blockchain by one Delegated Node. All other Delegated Noes on the network will then vote on the proposal. Any proposal that receives 50% + 1 votes within 24 hours of submission will be executed.

## Transaction Capabilities

### Transactions Per Second
Due to the controlled nature of the Delegated Node network, nodes can work to forge blocks extremely fast with a targeted time of 3 seconds per block. Other algorithms that have implemented proof of stake algorithms such as EOS which has the same functionality of having selected speaker nodes that forge blocks\[1] Have proven that it's possible to scale such a system to 50,000 Transactions Per Section\[2] For comparison Visa is able to scale up to 24,000 TPS \[3]

### Low Transaction Fees
Transactions have no inherent cost to send on SwiftDemand, however Identity Providers do have the ability to set transaction fees allowing them to have funds to resolve transaction disputes. The Swift Protocol reserves 80% of each block to be used exclusively for Identity Providers proportional to the amount of Swift Citizens they have verified with a minimum of 10. It is therefore the responsibility of Identity Providers to ensure spam transactions are not added to the chain. The remaining 20% of each block will be open for transactions with a bidding system in a similar manner to how bitcoin functions \[4]

### Buyer / Seller Protections
Transactions are able to be signed either by an Swift Citizen's private key or the private key of an Identity Provider. This gives Identity Providers the ability to reverse transactions and non-authorized transactions should only be used to settle disputes between buyer and sellers on the platform. When reversing funds is not possible Identity Providers have the responsibility to use the money earned from transaction fees to settle any issues.

### Transaction Latency
A single confirmation of a transaction will usually occur within 0 to 3 seconds on publishing a transaction. Normal transactions should be signed by Identity Providers on behalf of a Swift Citizen when the Citizen initiates an action. Therefore any transaction signed by an Identity Provider has a high level of trust as an Identity Provider is very unlikely to attempt a double spend attack and can be trusted after a single confirmation. Transactions signed by individual citizens should wait for multiple transactions before being treated as final and follows the same logic as layed out in Bitcoin's Whitepaper. \[5]

## Compensation
Both Delegated Nodes and Identity Providers receive a salary in Swifts for their service. Salary will be paid out on a daily basis at the same time Swift Citizens receive their daily income. The Swifts that are generated will initially be drawn from the 80% pool dedicated to regular Swift Distribution. Once that pool has been fully distributed additional Swifts generated from salaries will be created in addition to the Stage 2 inflation distribution.

### Delegated Node Salary
Delegated Nodes will each receive an equal salary. The Delegated Nodes themselves will vote on their own salary with the constraint that the salary must stay within a certain percentage of the previous salary. In the event where Delegated Nodes attempt to abuse this power, it is the responsibility of Swift Citizens to vote out the nodes.

### Identity Provider Salary
The Identity Provider salary is decided on by the delegated nodes. The salary is multiplied by the amount of Swifts that have been claimed by Citizens that are under that specific Identity Provider. For example if the salary decided by the Delegated Nodes is 0.01 and the Identity Provider has 100,000 active validated citizens that claimed 5,000,000 Swifts during that day the Identity Provider will receive 50,000 Swifts at the first block after midnight UTC. 

## Reserved Funds
20 Billion Swifts will be reserved, these Swifts are not controlled by any central source, but rather are under the control of the Delegated Nodes. It is the responsibility of the Delegated Nodes to assign these funds on an as needed basis to Identity Providers, Delegated Nodes, Swift Citizens, or Swift Accounts in an effort to further the success of the Swift Protocol.

### Funding Proposals
When a Swift Citizen or Identity Provider requires funds to perform some task they must submit a public Fund Proposal. This proposal will be written in plain text and signed with the requester's private key and then added to the blockchain. Nodes will then have 1 week to vote on the given proposal. Non-votes are counted as Nos. A majority consensus is required for the funds to be transferred.

## Consensus Protocol
A new consensus mechanism is used in the Swift Protocol that allows for extremely fast block times while still being trustable. The Swift Protocol uses a modified version of Delegated Byzantine Fault Tolerance \[6] that is implemented by NEO. Instead of having each block signed by a majority of the nodes, consensus will be decided based on the longest chain.

### Selecting Forgers
When Delegated Nodes are elected, they are placed into an ordered list of blocks that are permitted to forge blocks ordered by the amount of votes received. Nodes will then take turns forging blocks round robin style. When it is a nodes turn to create a block they will have a 10 second window to forge a block. If no block is forged during this duration then the next Delegated Node on the list will also have permission to forge a new block. This will be achieved by using a timestamp server \[5].

### Consensus
Consensus is decided by following the longest chain. Delegated Nodes that attempt to perform a double spend attacks by signing multiple blocks will promptly be voted out by other Delegated Nodes.

## Protections

### Skip Attack 
If nodes are in the following order \[Bad Node]\[Good Node]\[Bad Node] then the two bad nodes can collude to skip over the good node. When it is the first bad node’s time to create a block, they can create a block immediately, and only broadcast to the next bad node in the list. The second bad node can then wait 10 seconds, sign the node, and then broadcast it normally. The chain with the two bad nodes will be accepted since it is longer. While this attack is normally harmless it does allow colluding bad nodes to take control of the network with only 25% +1 of the nodes if the nodes happen to be optimally placed.

### Incubation Periods
All new Swift Citizens that join the Swift Protocol will be placed into an incubation period of one week. This prevents Identity Providers from creating fake accounts to quickly create a bunch of fake Swifts and gives Nodes sufficient time to ban the offending Identity Provider.

### Sybil Attacks
Identity Providers are disincentivized from performing Sybil Attacks as it comes with the risk of getting banned from the platform by Delegated Nodes. Additional safeguards such as the Incubation Period and Rollback Capability also exist to help mitigate any abuse. Swift Citizens can attempt to submit fake documents to gain additional basic income, however they are disincentized from doing so since being caught would result in losing both sources of income. It is expected that a few fake accounts may be created, but Identity Providers will be required to have very strict levels of regulation on how they approve new Swift Citizens which should eliminate most abuse.

### Round Robin Order Attack
A group of colluding bad actors could collude to all try to receive a similar number of votes allowing them to be placed in similar locations within the round robin ordering. A double spend attack could then be completed with only a handful of bad nodes. This attack however can only occur once before being detected. Large transactions should wait for a sufficient amount of confirmations to combat against this. Small transactions should be insured by Identity Providers.

### Deactivation of an Identity Provider
In the event where an Identity Provider attempts to perform fraud their account must be deactivated. In the event where damage has already been caused by the action of the Identity Provider, Delegated Nodes can vote to revert the chain to a previous state with an Identity Provider banned. This will cause a large amount of economic damage, but is meant as a last resort to enable the Swift Protpcol to not be devastated by an attack and to disincentivize Identity Providers from acting poorly. Swift Citizen accounts that belong to that Identity Provider would consequently be orphaned until they were claimed and validated by another Identity Provider.

## Constitution
Due to the fact that the Swift Protcol directly interact with the real world through decentralize governance there are certain rules which cannot be programmatically enforced yet are crucial for the Swift Protocol to function as intended. Delegated Nodes or Identity Providers that perform actions in contradiction to the items listed in the constitution should be stripped of their position.

* Regional tiers should be based on the cost of living associated with the geographical region of which the Swift Citizen is a legal resident of.
* Identity Providers should share a decentralized internal system of identites to guarantee Sybil accounts cannot be created. The internal system should also make any potential transitions of Swift Citizens easier to accomplish.
* Delegates Node should be removed from their position for the following reasons
  * Regularly not performing their duty to vote on proposals
  * Not forging new blocks during their turn within dBFT
  * Refusal to include block data that does not support them
  * Unreasonable policy voting that demonstrates harmful favoritism
* Official announcements should always be signed to protect against forgery
* The inflation rate should be balanced with the following factors in mind
  * Avoiding an inflation rate that would overly devalue existing Swifts
  * The real world effects that would result from a change in the rate
  * The amount of income required to provide the basic neccesities in life
* Identity Providers should be removed from their position for the following reasons
  * Weak approval process allowing the Sybil accounts regardless of the reason being malice or negligence
  * Failing to provide adequate dispute resolution for transactions
  * Not performing their duty to approve new Swift Citizens
  * Unwillingness to cooperate with other Identity Providers on the platform
* Proposals that are approved for funding should remain relatively liberal when the protocol is in its early stages and should slowly become more strict over time.

## Connection To SwiftDemand
SwiftDemand is separate from the Swift Protocol, however they are tightly connected and currently being developed by the same team. SwiftDemand will be the initial Identity Provider on the Swift Protocol and all Swifts that exist on SwiftDemand at the time of launching the Swift Mainnet will be transferred at a 1:1 ratio. Swift Citizens however will be required to undergo stricter Identity Verification requirements at this time to comply with KYC\[7] and AML\[8]. 

### SwiftDemand Features
SwiftDemand is designed to be an extremely user friendly platform that requires no prior knowledge of cryptocurrency setting the standard for future Identity Providers. SwiftDemand also provides an API as well as a marketplace to make it as easy as possible to transfer Swifts for Goods and Services.

## References

\[0] https://www.mckinsey.com/global-themes/future-of-organizations-and-work/what-the-future-of-work-will-mean-for-jobs-skills-and-wages

\[1] https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md#transaction-confirmation

\[2] https://www.youtube.com/watch?v=UC6RYwYPnpU

\[3] https://usa.visa.com/run-your-business/small-business-tools/retail.html

\[4] https://en.bitcoin.it/wiki/Transaction_fees

\[5] https://bitcoin.org/bitcoin.pdf

\[6] http://docs.neo.org/en-us/

\[7] https://en.wikipedia.org/wiki/Know_your_customer

\[8] https://www.investopedia.com/terms/a/aml.asp
