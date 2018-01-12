# Swift Protocol Whitepaper

The Swift Protcol is a DAO based protocol that implements the concept of Universal Basic Income (UBI)

**https://www.swiftdemand.com/**

## Abstract
The Swift Protocol is an implementation of a Decentralized Autonomous Organization (DAO) that provides Universal Basic Income. The Swift currency is desgined to be used a transactional currency and has been designed with nearly instant transaction times, ability to scale to thousands of transactions per second, low transaction fees, and protections for buyers and sellers. Income is distributed on a daily basis to all participants and represents the concept of UBI.

- [Account Types](#account-types)
  * [Swift Citizens](#swift-citizens)
  * [Delegated Nodes](#delegated-nodes)
  * [Identity Providers](#identity-providers)
- [Income Distribution](#income-distribution)
  * [Stages](#stages)
- [DAO based governance](#dao-based-governance)
  * [Elections](#elections)
  * [Election Durations](#election-durations)
  * [Delegated Node Voting](#delegated-node-voting)
- [Transaction Capabilities](#transaction-capabilties)
  * [Transactions Per Second](#transactions-per-second)
  * [Buyer / Seller Protections](#buyer---seller-protections)
  * [Speed of transactions](#speed-of-transactions)
  * [Low Transaction Fees](#low-transaction-fees)
- [Reserved Funds](#reserved-funds)
  * [Funding Proposals](#funding-proposals)
- [Consensus Protocol](#consensus-protocol)
  * [Selecting Forgers](#selecting-forgers)
  * [Consensus](#consensus)
- [Permissions](#permissions)
  * [Ability To Sign](#ability-to-sign)
- [Protections](#protections)
  * [Skip Attack ](#skip-attack)
  * [Incubation Periods](#incubation-periods)
  * [Sybil Attacks](#sybil-attacks)

## Account Types
The Swift Protocol uses a DAO to connect real world control with the blockchain. Different types of users have the ability to vote and change how the system functions based on real world events. This allows the Swift Protocol to remain decentralized  avoiding single points of failure while still enabling identity verification and financial controls.

### Swift Citizens
Swift Citizens are unique inidividuals that have been validated by an Idenity Provider. Citizens have the ability to add claim to the blockchain once every day (days begin and end at midnight UTC). Swifts will be awarded based on the amount of days passed with a maximum of 7. For example, if the 3 days have passed and a user makes a claim with the current production rate resting at 100 Swifts. 300 Swifts will be awarded.

### Delegated Nodes
Delegated Nodes are responsibile for maintaining full nodes and creating new blocks. Each election cycle Swift Citizens will sign votes to help choose which Delegated Nodes they would like to represent them. Delegated nodes have the capability to reach consensus on a daily basis to remove or add other Delegated Nodes and Identity Providers.

### Identity Providers
Identity Providers are responsible for validating the identity of Swift Citizens and creating new citizens by generating a keypair for each new Swift Citizen and including it on the blockchain. Identity Providers have the added responsibility of protecting the Swift Citizens whose keys they control with buyer and seller protections.

## Income Distribution
Swifts are distributed to users on a daily basis and will max out at 7 unclaimed days of Swifts.

### Stages
The total amount of Swifts that are targeted to be added to the economy in the initial stage is 80 Billion. After this stage has been reached stage 2 will kick in limiting the amount of new Swifts that enter the economy to a healthy inflation rate.

**Stage 1:**  In the first stage income will be generated at an accelerated rate so the economy can grow to maturity within a shorter time period. During this period Swift Citizens will receive Swifts dependent on the amount of Swift Citizens that are in the ecosystem. The formula to calculate the Income Distribution Multiplier is as follows: (781250 / (5^(log10(users)))) with a maximum value of 100, and minimum value of 1.

**Stage 2:** After the 80 Billion cap has been reached by following the formula of Stage 1, Stage 2 will come into effect. During this stage new Swifts will be given out to users at an inflation rate decided by the Delegated Nodes to all users in the ecosystem. The target inflation rate is ~5% per year to maintain a healhy economy.

**Region Multiplier:** Several different income tiers will exist based on cost of living associated with each region. The tiers and the multipliers associated with them will be decided by the Delegated Nodes. The region that each citizen belongs to will be validated by Identity Providers when added to the blockchain.

## DAO Based Governance
The Swift Protocol features an internal system that simulates a decentralized government. Swift Citizens have the responsibility to elect representitives that will have various powers within the government system. These Delegated Nodes are required to both maintain the blockchain while occasionally creating new blocks as well as active vote on important issues that occur.

### Elections
Each Swift Citizen has the ability to cast one vote on the network during elections. Nodes that receive the most votes will be elected to serve during that election cycle. The amount of nodes is decided by the following formula: (10 + (swift_citizens/100000))

### Election Durations
TODO

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

## Transaction Capabilities

### Transactions Per Second
TODO

### Buyer / Seller Protections
TODO

### Speed of transactions
TODO

### Low Transaction Fees
TODO

## Reserved Funds
20 Billion Swifts will be reserved, these Swifts are not controlled by any central source, but rather are under the control of the Delegated Nodes. It is the responsibility of the Delegated Nodes to assign these funds on an as needed basis to Identity Provider, or Swift Citizens in an effort to benefit the success of the Swift Protocol.

### Funding Proposals
When a Swift Citizen or Identity Provider requires funds to perform some task they must submit a public Fund Proposal. This proposal will be written in plain text and signed with the requester's private key and then added to the blockchain. Nodes will then have 1 week to vote on the given proposal. Non-votes are counted as Nos. A majority consensus is required for the funds to be transferred.

## Consensus Protocol
A new consensus mechanism is used in the Swift Protocol that allows for extremely fast block times while still being trustable. The consensus protocol is call Time Based Consensus. 

### Selecting Forgers
There is a pretermined order to Delegated Node ordered by the votes they received when elected. In a round robin order each node will have a 10 second window to forge a block. If no block is forged during this duration then the next Delegated Node on the list will also have permission to forge a new block.

### Consensus
Consensus is decided by following the longest chain. Delegated Nodes that attempt to perform a double spend attack by signing multiple blocks will promptly be voted out by other Delegated Nodes. (Insert math here about how many nodes have to be compromised to give a realistic attack vector). 

## Permissions

### Ability to sign
TODO

## Protections

### Skip Attack 
If nodes are in the following order \[Bad Node]\[Good Node]\[Bad Node] then the two bad nodes can collude to skip over the good node. When it is the first bad node’s time to create a block, they can create a block immediately, and only broadcast to the next bad node in the list. The second bad node can then wait 10 seconds, sign the node, and then broadcast it normally. The chain with the two bad nodes will be accepted since it is longer. While this attack is normally harmless it does allow colluding bad nodes to take control of the network with only 25% +1 of the nodes if the nodes happen to be optimally placed.

### Incubation Periods
All new Swift Citizens that join the Swift Protocol will be placed into an incubation period of one week. This prevents Identity Providers from creating fake accounts to quickly create a bunch of fake Swifts and gives Nodes sufficient time to ban the offending Identity Provider.

### Sybil Attacks
TODO
