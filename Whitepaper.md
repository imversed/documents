# Imversed whitepaper

## Table of contents

1. [Introduction](#Introduction)
2. [Verses](#Verses)
    1. The Concept of Verse
    2. Demand
    3. Use Cases
    4. Verses Layering
    5. Verse Implementation
        1. Token
        2. Tokens Exchange
        3. NFT Denomination
        4. Integrations
        6. Governance
4. [NFT as First-class Citizen](#NFT-as-First-class-Citizen)
    1. NFT Denominations
    2. NFT Oracles
5. [On-Chain Tokenomics](#On-Chain-Tokenomics)
    2. IMV Coins
    3. IMV Coins Initial Distribution
    4. Liquidity Pools
6. [Tendermint](#Tendermint)
    1. Validators
    2. Consensus
    3. Light clients
    4. Preventing Attacks
    5. ABCI
    6. Limitations
    7. Penalties
7. [Transaction fees](#Transaction-fees)
8. [Governance Specification](#Governance-Specification)
9. [Roadmap](#Roadmap)
10. [Links](#Links)

## Introduction

Great ideas come from brilliant minds. Some of these concepts are only rendered possible with decentralized blockchain technology. However, complexity of software development and intricacy of running a community-based infrastructure can become  roadblocks to success for many prominent ideas. The Imversed network aims to eliminate barriers between entrepreneurs, communities, influencers, and blockchain technology. Imversed achieves this goal through leveraging a Proof-of-Stake blockchain engine with BFT consensus, allowing blockchain to perform operations quickly and securely. Imversed is a community-driven SaaS solution that empowers businesses, influencers, and communities to use blockchain technology. Among its most important characteristics are the following:

* Introduction of the concept of verses - crypto sub-spaces created by users
* Stable and secured implementation of Proof-of-Stake (POS [[2]](https://www.investopedia.com/terms/p/proof-stake-pos.asp)) consensus
* All verse tokens are interchangeable
* Possibility to use Oracles to establish ownership and copyright for NFT tokens
* Integrations with major e-commerce platforms enable NFT sales similar to those of traditional products
* Multiple levels of verses, and the top-level verses can benefit from the lower-level ones
* Infrastructure is propelled forward by a dependable engine (Imversed chain)

These extensive features are built on a solid and secure foundation. Imversed is a blockchain application built on top of the COSMOS library that, once combined with Tendermint Core [[3]](https://github.com/tendermint/tendermint/wiki), provides a high-performance, consistent-in-use, and secure PBFT-like consensus engine with strict fork-accountability guarantees over malicious actors' behavior.

More information on PBFT-like consensus engines can be found in [[6]](http://pmg.csail.mit.edu/papers/osdi99.pdf). The BFT consensus algorithm from Tendermint Core is well-suited for scaling public Proof-of-Stake blockchains.

## Verses

Imversed was designed with ease of use in mind. More non-technical people should be able to enter the blockchain world and begin to thrive and grow. These individuals will contribute their enthusiasm and ideas to increase the value of the blockchain ecosystem. Unlike other blockchain projects, Imversed allows users to create their own verses through a simple, consistent, and clear API. No-code, strong validation and accessible UX significantly reduces human errors at critical steps.

What verse technology presents to a business is a collection of the most useful elements from the blockchain world. It is, in a way, a blockchain network within the larger Imversed network. Each verse comes with its own branded token. It can be exchanged for tokens from other verses as well as tokens from other networks within Imversed either through the basic IMV token or directly. The token can be used for financial transactions as well as for community management by distributing tokens and holding democratic public votes. Along with the token, you can issue a collection of NFTs and add Oracle information into it, which would allow buyers to verify authenticity and rights for the NFT tokens issued in this collection. Each verse is compatible with Imversed web3 ecosystem including:

- NFT e-commerce
- Multi-token Wallet
- Transaction explorer
- NFT certificates center
- HTTP/Unity/iOS/Android API

and many more.

Verses can form a hierarchical structure, with higher-level verses profiting from worth increase of heir verses through transaction fees or through value increase of heir verse tokens.


## The Concept of Verse

Verse is a blockchain that has its own branding, currency, exchange, and integrations. At the same time, it does not necessitate involvement of engineers, servers, or community in technical aspects of a project. Verse provides pure actualization of business ideas.

### Demand

Advancing into abstraction of higher levels is a natural process in the history of human evolution. It was not so long ago that Internet servers were housed in physical bare-metal servers overseen by teams of specialists. The following step was data centers with unimodal equipment that could be rented. Later virtualization became a new form, and the architecture of today’s information systems is no longer tied to physical servers.

Blockchain is going through the same phases. From enthusiasts mining Bitcoin on their physical computers to ASIC mining farms near power sources. The next step was moving from Proof-of-Work to Proof-of-Stake and finding the possibility to create a decentralized enthusiast community much easier than before. Imvesred is a higher degree abstraction that makes the benefits of a distributed blockchain accessible with a few clicks in a web interface.


### Use Cases

Verse is a unique project that allows a company to test its business strategies without capital expenditures and diving into the world of blockchain. Imversed allows to unlock the potential of a brand in blockchain with minimal effort. Possible scenarios include:

- Metaverse economy with token exchange between verses
- Sale of uniquely branded NFT tokens
- Traditional e-commerce shop with NFT tokens as goods
- Management of landlord communities and any other communities through democratic public voting
- Personal token of a celebrity or an influencer

Of course, any project could grow beyond the limits of Imversed and make the decision to move to its own platform. For such cases, Imversed will have mechanisms for verses migration to a self-sufficient, separate blockchain network.

### Verses Layering

Layering verses in Imversed allows users to assign a hierarchical structure to the verses created on the chain. To illustrate this point, imagine that a holding company creates a verse representing the entire corporation plus a few additional layers, e.g., two verses for each line of business to diversify risks or for branding purposes. The top-level structure is designed to benefit from sub-verses' activity. These benefits can be obtained through a variety of means, including the following:

* A portion of each transaction made with the level 2 verses will be distributed to all holders of the main verse tokens
* A portion of each sub-verse token transaction will be remitted to a service account established in a level 2 verse denomination
* A percentage of each transaction performed using lower-level verse tokens will eventually be distributed to all holders of the top-level verse tokens who have staked their tokens in validators

### Verse Implementation

#### Token

Each verse token can be exchanged directly for another one or, more typically, indirectly via the IMV token. Imversed uses liquidity pooling to establish the exchange rate depending on numerous parameters listed in the next section. Additionally, the price is influenced by the IMV token’s exchange rate and its pricing on other exchanges like Binance or Osmosis.

#### Tokens Exchange

Various verse tokens may be exchanged for tokens of other verses or IMV coins immediately and without restriction. The value of an individual verse token is defined by the balance of supply and demand for that token. The fair exchange rate in Imversed is determined by liquidity pools and GAMM (see the Liquidity Pools section for more details). All tokens created in verses automatically have access to all exchanges that offer the IMV coin for trading. So, a particular verse token can be released in an external exchange, but this is not necessary as there are no boundaries between verses within Imversed. Moreover, you can buy and sell tokens via web3 and mobile applications of the Imversed ecosystem.

#### NFT Denomination

As part of a verse, you can set up an NFT denomination where NFTs would be issued in the given verse. A verse service account that pays transaction fees may become a special feature of that denomination. A denomination is not an essential component of a verse. However, it is recommended to create one to simplify the process of automatic integration with the Imversed apps web3 ecosystem. We will take another look at denominations in [NFT as First-class Citizen](#NFT-as-First-class-Citizen).

#### Governance

Community management is a complex process. To increase transparency and trust, Imversed offers an open democratic voting tool that is a great help in decision making. The initial number of tokens issued is divided among voters according to their weight. This can depend on the size of one's territory or be, for example, 1 token per voter. After that, voters have full control over the tokens they have received and may hand them into trust management or sell them at their discretion. Each token holder can pay a fee in IMV and ask a question in a poll.

Within a certain period of time, community members can give their opinion on the question put to the vote. Voting results and records of vote distribution remain documented in the blockchain forever and cannot be cancelled or otherwise compromised.


#### Integrations

Imversed is surrounded by its own web3 ecosystem of projects and APIs for developers. In addition, Imversed is compatible with other COSMOS-based ecosystems of blockchain projects. Currently, the ecosystem includes, but is not limited to, the following unique projects:

- NFT e-commerce
- Multi token Wallet
- Transaction explorer
- NFT certificates center
- HTTP/Unity/iOS/Android API


## NFT as First-class Citizen

In Imversed, NFT tokens are integrated as part of the blockchain. This makes all tokens uniform, trustworthy, recognizable by all external services, and perfectly traceable. Different types of NFT ownership and royalty programs are available and more features will be added with new versions of Imversed.

### NFT Denominations

NFT typically comes in the form of a series or group. There is something in common between the Punks and Kitties series. Imversed introduces a simple way to associate NFT tokens. Denomination is metadata about a group of NFT tokens. As a field, each NFT token contains the identity of the denomination. Denomination is owned and can be changed by the owner. New changes do not affect NFT tokens that have already been issued. Since the denomination is not restricted, anyone can mint NFT tokens with a specific denomination. Denomination contains both strictly typed fields and data fields that can be filled with whatever information the owner desires. NFT tokens issued by an artist are a good example of a denomination. This artist may want to specify their site in the denomination to make themself more recognizable even after the NFT has changed hands several times.

### NFT Oracles

ETH [[4]](https://eth.wiki) is probably the most popular network for NFT, but in terms of copyright and security it resembles the Wild West. This network seems to be a lawless wasteland when it comes to trademarks and ownership. Anyone may reissue and sell anything. Users can create an ERC-721-compliant contract and mint any NFT. Imversed defines denomination as a type of NFT user or company that is able to produce and mint NFTs. A denomination is a set of metadata common to all NFTs issued in that denomination.

The Inversed denomination has a holder. Although the creator of the denomination maintains ownership, it can be transferred to another location. Denomination may contain a URL to the Oracle database. This URL should implement a special HTTP contract that allows an Imversed network address to determine whether or not they have  authorization for the URL of the NFT they wish to mint.

## On-Chain Tokenomics

In case no value is attached to them, tokens are just bytes in blockchain transactions. Imversed allows on-chain tokens to be traded with one another. Tokens could be exchanged directly or indirectly through the IMV coin (double conversion). The value of each token is determined by the amount of demand and supply within a given token pair. The amount of liquidity locked up in the token pair's liquidity pool defines the exchange rate within the token pair. Non-financial tokens can act as NFTs or allow users to participate in non-financial distribution and public voting.


### IMV Coins

While Imversed is a distributed ledger that supports multiple assets, it is distinguished by its native token, the IMV, which is Imversed's single staking token. IMVs are a sort of license that allows the holder to vote, validate, and delegate authority to additional validators. IMVs, like Ethereum's ether, can be used to defray transaction costs, thus minimizing spam. Additional inflationary IMVs and block transaction fees are paid to validators and delegators who delegate to validators.


### IMV Coins Initial Distribution

TBD

### Liquidity Pools

A liquidity pool is a self-balancing weighted portfolio and price sensor that acts as an automatic market maker [[9]](https://balancer.fi/whitepaper.pdf). The liquidity pool system calculates the exchange rate prior to the exchange taking into account several important factors such as the number of tokens requested for exchange, the number of tokens locked in the liquidity pool, the total amount of individual tokens participating in current exchanges, and other. The algorithm may change, but it will always be part of the blockchain code, and any change must be democratically approved by vote. Tokens without monetary value are also allowed in the Imversed ecosystem. Initially, the creator of a token can provide liquidity for the pool, or other users may stack their tokens to the pool to benefit from the exchange fees.


## Imversed Basement

The decentralized blockchain is the foundation for decentralized apps (dapps). Each app solves a specific problem for community members. Imversed implements dapps as modules. Modules are a much more secure way to extend network functionality compared to smart contracts, as they must be approved by the community and go through governance process. Imversed also provides a lightweight client for querying blockchain nodes. The light client allows third-party developers to easily query data from the blockchain and develop services for the Imversed ecosystem. The Imversed blockchain is a multi-tiered, community-driven decentralized network. The zero tier is a layer of physical servers managed by the IMV coin community. Each server runs the exact version of an open-source application, ensuring transparency and trust among community members. Full nodes can be promoted to validators so they can add new blocks to the blockchain (see the [Tendermint](#Tendermint) section of this whitepaper for details). Since zero layer logic guarantees rules and principles, all layers based on it are decentralized and community-driven. Decisions to change zero layer logic can only be made by IMV token holders and must go through a democratic voting process (details could be found in the [Governance Specification](#Governance-Specification) section of this whitepaper).

Imversed makes it easy and safe for anyone to create a verse. Each verse built on the basis of Imversed network is decentralized and backed by the Imversed community. This ensures independence and reliability of Imversed-based tokens in conjunction with the democratic governance process. These tokens can be used in all Imversed dapps, mint NFT tokens, and be exchanged for other Imversed tokens or IMV coin (see the [On-Chain tokenomics](#On-Chain-tokenomics) section of this whitepaper for details). It is not just the complexity of development and infrastructure that hinders the implementation of great ideas. Some blockchain networks choose to tie transaction fees to the value of a coin. High transaction fees and slow transaction completion may be a problem. Imversed addresses these challenges by introducing a governance-based mechanism for setting fees (details can be found in the [Transaction Fees](#Transaction-Fees) section of this whitepaper) and fast transaction finality based on the implementation of the BFT consensus algorithm.

## Tendermint

This section briefly discusses the Tendermint consensus method and the application development interface. Tendermint is the underlying technology of the Imversed blockchain that is responsible for implementing general distributed blockchain activities such as network communication, data exchange, transaction confirmation, and in-app communication.

### Validators

In classical Byzantine fault-tolerant (BFT) algorithms, each node has the same weight. In Tendermint, nodes have a non-negative voting weight, and nodes with positive voting weights are called validators. Validators participate in the consensus protocol by broadcasting cryptographic signatures or votes to agree upon the next block. The voting power of validators is determined at creation or is deterministically changed by the blockchain depending on the application. For example, in a Proof-of-Stake application such as Cosmos Hub, voting power can be determined by the amount of staking tokens deposited as collateral. NOTE: Fractions such as ⅔ and ⅓ refer to fractions of the total voting power, never to the total number of validators, unless all validators have equal weight. >⅔ means "more than ⅔", ≥⅓ means "at least ⅓".

### Consensus

Tendermint is a partially synchronous BFT consensus protocol derived from DLS consensus algorithm [[8]](http://groups.csail.mit.edu/tds/papers/Lynch/jacm88.pdf). Tendermint stands out for its simplicity, performance, and fork-accountability. The protocol requires a fixed number of validators, with  each validator identified by its public key. The validators try to come to consensus on one block at a time, where a block is a list of transactions. Voting on a block proceeds in rounds. Each round has a round leader or proposer who proposes a block. The validators then vote incrementally on whether to accept the proposed block or move on to the next round. The proposer for a round is deterministically selected from the list of validators ranked in proportion to their voting power. Tendermint's security is based on the use of optimal Byzantine fault-tolerance through super-majority voting (>⅔) and a locking mechanism. In combination, they ensure that:

* ≥⅓ voting power must be Byzantine to cause a violation of safety, where more than two values are committed.
* If any group of validators ever succeeds in violating safety, or even attempts to do so, they can be identified by protocol. This includes both voting on conflicting blocks and transmission of unjustified votes. Despite the strong guarantees it ensures, Tendermint provides exceptional performance. In benchmarks of 64 nodes spread across 7 data centers on 5 continents on commodity cloud instances, Tendermint consensus can process thousands of transactions per second, with commit latencies on the order of one to two seconds. Remarkably, the performance of well over a thousand transactions per second is maintained even under challenging conditions when validators crash or broadcast maliciously crafted votes. See the figure below for details.

### Light Clients

A major advantage of Tendermint's consensus algorithm is the simplified security of the light client, making it an ideal candidate for mobile and Internet-of-Things use cases. While a Bitcoin light client must synchronize chains of block headers and find the one with the most Proof-of-Work, Tendermint light clients only need to keep up with changes to the validator set and then verify the >⅔ PreCommits in the latest block to determine the latest state. Succinct light client proofs also enable inter-blockchain communication.

### Preventing Attacks

Tendermint guarantees protective measures that prevent certain notable attacks, such as long-range-nothing-at-stake double spends and censorship.

### ABCI

The Tendermint consensus algorithm is implemented in a program called Tendermint Core. Tendermint Core is an application-agnostic "consensus engine" that can turn any deterministic blackbox application into distributed, replicated blockchain data. Tendermint Core connects to blockchain applications via the Application Blockchain Interface (ABCI) [[7]](https://github.com/tendermint/abci). Thus, ABCI allows for blockchain applications to be programmed in any language, not just the programming language in which the consensus engine is written. Additionally, ABCI allows easy replacement of the consensus layer of any existing blockchain stack. We draw an analogy to the well-known Bitcoin cryptocurrency. Bitcoin is a cryptocurrency blockchain where each node maintains a fully audited Unspent Transaction Output (UTXO) database. If one wanted to create a Bitcoin-like system based on ABCI, Tendermint Core would be responsible for

* Sharing blocks and transactions between nodes
* Establishing a canonical/immutable order of transactions (the blockchain)

Meanwhile, the ABCI application would be responsible for

* Maintaining the UTXO database
* Validating cryptographic signatures of transactions
* Preventing spending non-existent funds in transactions
* Allowing clients to query the UTXO database

Tendermint is able to decompose the blockchain design by providing a very simple API between the application process and the consensus process.

### Limitations on the Number of Validators

Unlike Bitcoin or other Proof-of-Work blockchains, a Tendermint blockchain gets slower with more validators due to increased communication complexity. Fortunately, we can support enough validators to make for a robust, globally distributed blockchain with very fast transaction confirmation times. With increasing bandwidth, storage capacity, and parallel computing capabilities, we will be able to support more validators in the future.

### Penalties for Validators

For any intentional or unintentional deviation from the sanctioned protocol, a penalty must be imposed on the validators. Some evidence is immediately admissible, such as a double sign at the same height and round, or a "prevote-the-lock" violation (a rule of the Tendermint consensus protocol). Such evidence will cause the validator to lose its good standing. Moreover, its bonded IMVs as well as its proportionate share of tokens in the reserve pool, collectively referred to as its "stake", will get slashed.

Sometimes, validators may be unavailable, whether due to regional network disruptions, power outages or other reasons. If at any time in the past "ValidatorTimeoutWindow" blocks a validator's commit vote, and it is not recorded in the blockchain more than "ValidatorTimeoutMaxAbsent" times, that validator becomes inactive and loses "ValidatorTimeoutPenalty" (DEFAULT 1%) of its stake. Some "malicious" behaviors do not result in obviously discernible evidence in the blockchain. In these cases, validators can coordinate out-of-band to enforce the timeout of these malicious validators if there is supermajority consensus. In situations where the Cosmos Hub goes offline due to a ≥⅓ coalition of voting power going offline, or in situations where a ≥⅓ coalition of voting power censor evidence of malicious behavior to prevent it from entering the blockchain, the hub must recover with a hard-fork reorg-proposal.

## Transaction Fees

The blockchain economy is based on an enthusiastic/engaged community, and this economy does not work without transaction fees. On the other hand, high transaction fee costs become a restraint for developmental potential. In Imversed, transaction fees can be lowered or raised depending on the interests of the community and are not tied in a constant proportion to the value of the IMV token. The price of the gas unit is determined by a public vote through the governance tool. All transaction fees are paid in IMV by default. However, the community can vote to add other user-created verse coins to the list of coins eligible for transaction fee payment. In addition, for some types of transactions, the fee can be paid by the recipient, or it may be paid from a service account.

## Governance Specification

Constitution and governance framework should regulate distributed public ledgers. The Bitcoin Foundation and mining work together to improve Bitcoin. However, this is a lengthy process. Due to the lack of a prior social contract or framework for such decisions, Ethereum hard-forked into ETH and ETC following the DAO hack.

Validators and Imversed delegated members can vote on proposals to adjust system specifications (such as the block gas limit), coordinate updates, and rewrite Imversed's human-readable constitution. The constitution encourages collaboration on theft and bugs (such as the DAO incident) among stakeholders, leading to a faster and cleaner resolution.

Imversed is a decentralized organization that requires a well-defined governance structure in order to organize multiple blockchain adjustments such as system variables, software upgrades, and constitutional changes. Each proposal must be voted on by all validators. Failure to vote expeditiously on a proposal will disable the validator for a period of time referred to as the "AbsenteeismPenaltyPeriod" (DEFAULT 1 week). Delegates automatically inherit the validator's vote. Manual override of this vote is allowed and unbound IMVs do not vote. Each proposal requires the deposit of "MinimumProposalDeposit" tokens, which can be any combination of tokens, including IMVs. It is up to voters to accept or reject the deposit for each plan. If more than half of the voters accept the deposit (e.g., because it is a spam proposal), it is added to the reserve pool minus the burned IMVs. Voters can choose one of the following options for each proposal:

* Yea
* Yea with force
* Nay
* Nay with force
* Abstain

A simple majority of "Yea" or "Yea with force" votes is required to approve (or reject) a proposal, but 1/3 or more of  the votes may veto the majority decision by voting “with force.” If a strict majority decision is vetoed, all parties  pay “VetoPenaltyFeeBlocks” (DEFAULT 1 day’s worth of blocks) in fees (except taxes, which are unaffected), and  the party that vetoed the majority's decision pays “VetoPenaltyIMVs” (DEFAULT 0.1 percent) of their IMVs.

## Roadmap

￼![Roadmap](assets/images/roadmap.png?raw=true "Roadmap")

## Links

* 1 NFT: https://ethereum.org/en/nft
* 2 POS: https://www.investopedia.com/terms/p/proof-stake-pos.asp
* 3 Tendermint: https://github.com/tendermint/tendermint/wiki
* 4 Ethereum: https://eth.wiki
* 5 Slasher: https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm
* 6 PBFT: http://pmg.csail.mit.edu/papers/osdi99.pdf
* 7 ABCI: https://github.com/tendermint/abci
* 8 DLS: http://groups.csail.mit.edu/tds/papers/Lynch/jacm88.pdf
* 9 Balancer: https://balancer.fi/whitepaper.pdf

