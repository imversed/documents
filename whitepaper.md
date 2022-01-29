# Imversed white-paper

## Index

1. [Introduction](#Introduction)
2. [Verses](#Verses)
    1. Conception of verses
    2. Demand
    3. Use cases
    4. Verses layering
    5. Verse implementation
        1. Token
        2. Tokens exchange
        3. NFT Denomination
        4. Integrations
        6. Governance
4. [NFT Tokens as First-class Citizens](#NFT-Tokens-as-First-class-Citizens)
    1. NFT Denominations
    2. NFT Oracles
5. [On-Chain Tokenomic](#On-Chain-Tokenomic)
    2. IMV coins
    3. IMV coins initial distribution
    4. Liquidity pools
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

Great ideas come from brilliant minds. Some of these concepts are only possible with decentralized blockchain technology. However, the complexity of software development and the complexity of running community-based infrastructure are roadblocks to many of these good ideas. The Imversed network aims to eliminate barriers between entrepreneurs, communities, influencers, and blockchain. Imversed achieves this goal through leveraging a Proof of Stake blockchain engine with BFT consensus, allowing blockchain to perform operations quickly and securely. Imversed is a community-driven SaaS solution that empowers businesses, influencers, and communities to use blockchain technology. Among the most important characteristics are the following:

* Conception of Verses - crypto sub-spaces created by users
* Stable and secured implementation of Proof Of Stake (POS [[2]](https://www.investopedia.com/terms/p/proof-stake-pos.asp)) consensus
* All Verse tokens are interchangeable
* Possibility to use Oracles to establish ownership and copyright of NFT tokens
* Integrations with major e-commerce platforms enable the sale of NFTs in the same way that traditional products are sold
* Multiple levels of Verses, and the top-level Verses can benefit from the lower-level
* Infrastructure is propelled forward by a dependable engine (Imversed chain)

These extensive features are built on a dependable and secure foundation. Imversed is a blockchain application built on top of the COSMOS library that, when combined with Tendermint Core [[3]](https://github.com/tendermint/tendermint/wiki), provides a high-performance, consistent-in-use, and secure PBFT-like consensus engine with strict fork-accountability guarantees over malicious actors' behavior.

More information on PBFT-like consensus engines can be found in [[6]](http://pmg.csail.mit.edu/papers/osdi99.pdf). The BFT consensus algorithm from Tendermint Core is well-suited for scaling public proof-of-stake blockchains.

## Verse

Imversed were designed with ease of use in mind. More non-technical people should be able to enter the blockchain world and begin to thrive and grow. These individuals will contribute their enthusiasm and ideas to increase the value of the blockchain ecosystem. Unlike other blockchain projects, imversed allows users to create their own verses through an easy, consistent, and clear API. No-code, strong validation and simple UX significaly reduces human errors in critical steps.

Verse is a collection of the most important elements from the blockchain world. A blockchain network that is part of the larger Imversed network. Each verse comes with its own branded token. It can be exchanged for tokens from other verses as well as tokens from other networks within Imversed, either through the base IMV token or directly. The token can be used for financial transactions as well as community management by distributing tokens and holding public democratic votes. Along with the token, you can issue a collection of NFTs and add Oracle information to it, allowing buyers to verify the authenticity and rights to NFT tokens issued in this collection. Each verse is compatible with Imversed's web3 ecosystem. Among them are:

* NFT e-commerce
* Multi token Wallet
* Transaction explorer
* NFT certificates center
* HTTP/Unity/iOS/Android API

Verses can form a hierarchical structure, and higher level verses can benefit from growth in value in verse heirs via transaction fees or growth in the value of the heir's verse token.

## Conception of verse

Verse is a blockchain that has its own branding, currency, exchange, and integrations. However, it does not necessitate the involvement of engineers, servers, or the community in the technical aspects of the project. Verse is the purest form of business idea implementation.

### Demand

A rise in the degree of abstraction is a natural process that has accompanied man throughout his evolution. Not long ago, Internet servers were housed on physical servers that were monitored by specialized teams. The following step was to build data centers with unified equipment that could be rented. Then virtualization became the new norm, and modern information system architecture was no longer bound by physical servers.
The same is true for blockchain. From bitcoin mining on hobbyist physical computers to ASIC farms near power sources. The transition from proof of work to proof of stake was the next step, and the ability to create a distributed community of enthusiasts is much easier than before. Imvesred is a higher level of abstraction in which the benefits of a distributed blockchain can be accessed with a few mouse clicks in the web interface.

### Use cases

Imversed is a one-of-a-kind project that enables businesses to test their business strategies without incurring capital costs and to immerse themselves in the blockchain world. Imversed enables you to maximize a brand's potential on the blockchain with minimal effort. Scenarios possible:

* Metaverse economy based on token exchange between Verses
* Creation of a unique brand's NFT tokens - Traditional e-commerce store with goods in the form of NFT tokens
* Management of homeowner associations or other communities through public democratic voting
* A celebrity's or influencer's personal token

Of course, any project can outgrow Imversed's limitations and decide to move to its own platform. Imversed will implement mechanisms for migrating Verse into a full-fledged separated blockchain network to accomplish this.
### Verses layering

Layering in Imversed verses allows users to assign a hierarchical structure to verses created on the chain. Assume a holding corporation creates a verse that represents the entire organization as well as a few additional layers, such as two verses for each line of business, to diversify risks or for branding purposes. The top structure is intended to profit from sub-verses activity. These benefits can be obtained through a variety of means, including the following:

* A portion of each transaction made with the level 2 verses will be distributed to all holders of the main verse tokens.
* A portion of each sub-version tokens transaction will be remitted to a service account established in a level 2 verse denomination.
* A percentage of each transaction completed with a level 2 verse token will eventually be distributed to all holders of the level 1 verse token who have staked their tokens in validators

### Verse implementation

#### Token

Each verse token can be exchanged directly for another or, more typically, indirectly via the IMV token. Imversed uses a liquidity pooling approach to establish the exchange rate depending on numerous parameters listed in the next section. Additionally, the price is influenced by the IMV token’s exchange rate and its pricing on other exchanges like Binance or Osmosis.

#### Tokens exchange

Tokens from different Verse can be instantly and freely exchanged for tokens from other Verse or IMV coin. The value of a single Verse token is determined by the supply and demand for that token. Imversed employs the liquidity pools and GAMM mechanism to determine a fair exchange rate (for more details, see the Liquidity pools section). All tokens created in Verse have automatic access to exchanges where IMV coins are traded. Due to the lack of boundaries between Verses within Imversed, the withdrawal of a separate Verse token to an external exchange is possible but not required. Tokens can also be purchased and sold via the Imversed ecosystem's web3 and mobile applications.

#### NFT Denomination

You can create your own NFT denomination for Verse, and NFT will be issued in this Verse. A Verse service account that pays transaction fees could be a feature of this denomination. Denomination is not required in Verse, but it is recommended in order to simplify the process of automatic integration with the Imversed web3 application ecosystem. More denominations will be covered in greater detail in [NFT Tokens as First-class Citizens](#NFT-Tokens-as-First-class-Citizens).

#### Governance

It is not an easy task to manage a community. Imversed introduces an open democratic voting mechanism to help make decisions in order to increase openness and trust. Initially, the volume of tokens issued is distributed based on the weight of the voters. For example, based on the amount of owned land or, for example, 1 token per voter. Following that, the voters can dispose of the received tokens on their own, transferring them for trust management or selling them at their discretion. By paying a fee to the IMV, each token holder can put an issue to a vote, and the community will have a certain amount of time to express their opinion on the issue put to a vote. Voting results and vote distribution will be permanently recorded on the blockchain and will not be canceled or otherwise disputed.

#### Integrations

Imversed is surrounded by its own web3 project ecosystem and developer APIs. Furthermore, Imversed is compatible with a COSMOS-based ecosystem of other blockchain projects. The ecosystem currently includes, but is not limited to, the unique projects listed below:
- NFT e-commerce
- Multi token Wallet
- Transaction explorer
- NFT certificates center
- HTTP/Unity/iOS/Android API


## NFT as First-class Citizens

In Imversed NFT tokens are build-in as a part of the blockchain. As a result all tokens are unified, trustable, recognizable by all external services and perfectly trackable. Different types of NFT ownership and royalty programs are available and more features will be added with new versions of Imversed.

### NFT Denominations

NFT is typically delivered in the form of a series or group. There's something in common between the Punks and Kitties series. Imversed introduces a simple way to connect NFT tokens. Denomination is meta data about a group of NFT tokens. As a field, every NFT token contains the denomination's identity. Denomination is owned and can be changed by the owner. The change in denomination has no effect on NFT tokens that have already been issued. Because denomination is not restricted, anyone can mint NFT tokens with a specific denomination. Denomination contains strongly typed fields as well as data fields that can be filled with whatever information the owner desires. NFT tokens issued by an artist are a good example of a denomination. This artist might want to put his website in denomination to make himself more recognizable even after the NFT has changed hands multiple times.

### NFT Oracles

ETH [[4]](https://eth.wiki) is, probably, the most popular network for NFT and, in terms of copyright and security, it resembles the Wild West. The most widely used network for NFT is ETH, which appears to be a lawless wasteland in terms of copyright and ownership. Anyone has the ability to reissue and sell anything. Users can create an ERC-721-compliant contract and mint any NFT using it. Imversed defines denomination as a type of NFT user or corporation that is capable of producing and minting NFTs. The denomination is a set of metadata shared by all NFT issues in this denomination.
There is a holder of the inverted denomination. Although the creator of the denomination maintains ownership, it can be transferred to another location. The denomination may include the URL to the Oracle database. This URL should implement a specific HTTP contract that allows an Imversed network address to determine whether or not they have authorization to the URL of the NFT they wish to mint.

## On-Chain Tokenomic

Tokens are just bytes in blockchain transactions if no value is attached to them. Imversed allows on-chain tokens to be traded with one another. Tokens could be exchanged directly or indirectly thru the IMV coin (double conversion). The value of each token is determined by the amount of demand and supply within a given token pair. The amount of liquidity locked up in the token pair's liquidity pool defines the exchange rate within the token pair. Non-financial tokens can act as NFTs or allow users to participate in non-financial distribution and public voting.


### IMV coins

While Imversed is a distributed ledger that supports several assets, it is distinguished by its native token, the IMV, which is Imversed’s single staking token. IMVs are a sort of license that permits the holder to vote, validate, and delegate authority to additional validators. IMVs, like Ethereum’s ether, can be used to defray transaction costs, thus minimizing spam. Additional inflationary IMVs and block transaction fees are paid to validators and delegators who delegate to validators.


### IMV coins initial distribution

TBD

### Liquidity pools

A Liquidity Pool is a self-balancing weighted portfolio and price sensor that functions as an automated market maker [[9]](https://balancer.fi/whitepaper.pdf). The liquidity pool system calculates the exchange rate prior to the exchange, taking into account several factors such as the number of tokens requested to be exchanged, the number of tokens locked in the liquidity pool, the overall amount of each token participating in current exchanges, and other important factors. The algorithm may change, but it will always be a part of the blockchain code, and any changes must be democratically approved via voting. Tokens with no monetary value are also permitted in the Imversed ecosystem. Initially, the token's creator could provide liquidity for the pool, or other users could stack their tokens in the pool to profit from exchange fees.


## Imversed basement

The foundation for decentralized apps (dapps) is decentralized blockchain. Every dapp solves a specific problem for community members. Imversed implements Dapps as modules. Modules are a much more secure way to extend network functionality than smart contracts because they must be approved by the community and go through a governance process. Imversed also provides a lightweight client for querying blockchain nodes. The light client allows third-party developers to easily request data from the blockchain and build services for the Imversed ecosystem. Imversed blockchain is a multi-layered, community-driven decentralized network. The zero layer is a layer of real-world servers managed by the IMV coin community. Every server runs the exact version of an open source application, ensuring transparency and trust among community members. Full nodes could be promoted to validators, allowing them to add new blocks to the blockchain (details could be found in [Tendermint](#Tendermint) section of this whitepaper). Because zero layer logic guaranteesrules and principles, any layers based on it are decentralized and community driven. Decisions to change zero layer logic could only come from IMV token holders and should go through a democratic voting process (details could be found in [Governance Specification](#Governance Specification) section of this whitepaper). Imversed makes it simple and secure for anyone to create a verse. Every verse built on top of the Imversed network is decentralized and backed by the Imversed community. It ensures the independence and dependability of Imvesred-based tokens in conjunction with the democratic governance process. This token could be used in all Imversed dapps, mint NFT tokens, and be exchanged for other Imversed tokens or IMV coin (details could be found in [On-Chain tokenomic](#On-Chain tokenomic) section of this whitepaper). Not only can the complexity of development and infrastructure stymie the implementation of great ideas. Some blockchain networks choose to tie transaction fees to the value of a coin. High transaction fees and slow transaction completion may be a problem. Imversed addresses these challenges by introducing a governance-based mechanism for defining fees (details can be found in the [Transaction fees](#Transaction fees) section of this whitepaper) and fast transaction finality based on the implementation of the BFT consensus algorithm.

## Tendermint

This section briefly discusses Tendermint consensus method and the application development interface. Tendermint is underlying technology of Imversed blockchain responsible for implementing general distributed blockchain activities such as network communication, data exchange, transaction confirmation and in-app communication.

### Validators

In classical Byzantine fault-tolerant (BFT) algorithms, each node has the same weight. In Tendermint, nodes have a  non-negative amount of voting power, and nodes that have positive voting power are called validators. Validators participate in the consensus protocol by broadcasting cryptographic signatures, or votes, to agree upon the next block. Validators' voting powers are determined at genesis, or are changed deterministically by the blockchain, depending on the application. For example, in a proof-of-stake application such as the Cosmos Hub, the voting power may be determined by the amount of staking tokens bonded as collateral. NOTE: Fractions like ⅔ and ⅓ refer to fractions of the total voting power, never the total number of validators, unless all the validators have equal weight. >⅔ means "more than ⅔", ≥⅓ means "at least ⅓".

### Consensus

Tendermint is a partially synchronos BFT consensus protocol derived from the DLS consensus algorithm [[8]](http://groups.csail.mit.edu/tds/papers/Lynch/jacm88.pdf). Tendermint is notable for its simplicity, performance, and fork-accountability. The protocol requires a fixed known set of validators, where each validator is identified by their public key. Validators attempt to come to consensus on one block at a time, where a block is a list of transactions. Voting for consensus on a block proceeds in rounds. Each round has a round-leader, or proposer, who proposes a block. The validators then vote, in stages, on whether to accept the proposed block or move on to the next round. The proposer for a round is chosen deterministically from the ordered list of validators, in proportion to their voting power. Tendermint’s security derives from its use of optimal Byzantine fault-tolerance via super-majority (>⅔) voting and a locking mechanism. Together, they ensure that:

* ≥⅓ voting power must be Byzantine to cause a violation of safety, where more than two values are committed.
* if any set of validators ever succeeds in violating safety, or even attempts to do so, they can be identified by the protocol. This includes both voting for conflicting blocks and broadcasting unjustified votes. Despite its strongguarantees, Tendermint provides exceptional performance. In benchmarks of 64 nodes distributed across 7 datacenters on 5 continents, on commodity cloud instances, Tendermint consensus can process thousands of transactions per second, with commit latencies on the order of one to two seconds. Notably, performance of well over a thousand transactions per second is maintained even in harsh adversarial conditions, with validators crashing or broadcasting maliciously crafted votes. See the figure below for details.

### Light Clients

A major benefit of Tendermint's consensus algorithm is simplified light client security, making it an ideal candidate for mobile and internet-of-things use cases. While a Bitcoin light client must sync chains of block headers and find the one with the most proof of work, Tendermint light clients need only to keep up with changes to the validator set, and then verify the >⅔ PreCommits in the latest block to determine the latest state. Succinct light client proofs also enable inter-blockchain communication.

### Preventing Attacks

Tendermint has protective measures for preventing certain notable attacks, like long-range-nothing-at-stake double spends and censorship.

### ABCI

The Tendermint consensus algorithm is implemented in a program called Tendermint Core. Tendermint Core is an application-agnostic "consensus engine" that can turn any deterministic blackbox application into a distributedly replicated blockchain. Tendermint Core connects to blockchain applications via the Application Blockchain Interface (ABCI) [[7]](https://github.com/tendermint/abci). Thus, ABCI allows for blockchain applications to be programmed in any language, not just the programming language that the consensus engine is written in. Additionally, ABCI makes it possible to easily swap out the consensus layer of any existing blockchain stack. We draw an analogy with the well-known cryptocurrency Bitcoin. Bitcoin is a cryptocurrency blockchain where each node maintains a fully audited Unspent Transaction Output (UTXO) database. If one wanted to create a Bitcoin-like system on top of ABCI, Tendermint Core would be responsible for

* Sharing blocks and transactions between nodes
* Establishing a canonical/immutable order of transactions (the blockchain)
  Meanwhile, the ABCI application would be responsible for
* Maintaining the UTXO database
* Validating cryptographic signatures of transactions
* Preventing transactions from spending non-existent funds
* Allowing clients to query the UTXO database Tendermint is able to decompose the blockchain design by offering a very
  simple API between the application process and consensus process.

### Limitations on the Number of Validators

Unlike Bitcoin or other proof-of-work blockchains, a Tendermint blockchain gets slower with more validators due to the increased communication complexity. Fortunately, we can support enough validators to make for a robust globally distributed blockchain with very fast transaction confirmation times, and, as bandwidth, storage, and parallel compute capacity increases, we will be able to support more validators in the future.

### Penalties for Validators

There must be some penalty imposed on the validators for any intentional or unintentional deviation from the sanctioned protocol. Some evidence is immediately admissible, such as a double-sign at the same height and round, or a violation of "prevote-the-lock" (a rule of the Tendermint consensus protocol). Such evidence will result in the validator losing its good standing and its bonded IMVs as well its proportionate share of tokens in the reserve pool -- collectively called its "stake" -- will get slashed. Sometimes, validators will not be available, either due to regional network disruptions, power failure, or other reasons. If, at any point in the past ValidatorTimeoutWindow blocks, a validator's commit vote is not included in the blockchain more than ValidatorTimeoutMaxAbsent times, that validator will become inactive, and lose ValidatorTimeoutPenalty (DEFAULT 1%) of its stake. Some "malicious" behavior does not produce obviously discernible evidence on the blockchain. In these cases, the validators can coordinate out of band to force the timeout of these malicious validators, if there is a supermajority consensus. In situations where the Cosmos Hub halts due to a ≥⅓ coalition of voting power going offline, or in situations where a ≥⅓ coalition of voting power censor evidence of malicious behavior from entering the blockchain, the hub must recover with a hard-fork reorg-proposal. (Details in "Forks and Censorship Attacks").

## Transaction Fees

The blockchain economy is based on a dedicated community and cannot function without transaction fees. High transaction fees, on the other hand, limit development potential. Commissions for operations in Imversed can be reduced or increased based on community interests and are not tied to the value of the IMV token by some constant coefficient. The cost of a conventional unit of gas is determined by public voting through the governance mechanism. All commissions are paid in IMV by default, but the community can vote to add other coins from user-created Verses to the list of coins that can be used for commission payments. Furthermore, for certain types of transactions, the commission may be paid by the recipient or deducted from the service account.

## Governance Specification

A constitution and a governance framework should regulate distributed public ledgers. The Bitcoin Foundation and mining work together to improve Bitcoin. This, however, is a lengthy procedure. Due to the absence of a prior social contract or framework for making such decisions, Ethereum hard-forked into ETH and ETC following the DAO hack.

Validators and Imversed-delegated members can vote on proposals to adjust system defaults (such as the block gas limit), coordinate updates, and rewrite Imversed’s human-readable constitution. The constitution promotes stakeholder collaboration on theft and bugs (such as the DAO incident), resulting in a swifter and cleaner resolution.

Imversed is a decentralized organization that requires a well-defined governance structure in order to organize multiple blockchain adjustments such as system variables, software upgrades, and constitutional revisions. Each proposal must be voted on by all validators. If you do not swiftly vote on a proposal, then the validator will be deactivated for a period referred to as the “AbsenteeismPenaltyPeriod” (DEFAULT 1 week). Delegates automatically inherit the validator’s vote. Manual override of this vote is permitted and unbonded IMVs do not vote. Each proposal requires the deposit of “MinimumProposalDeposit” tokens, which can be any combination of tokens, including IMVs. The deposit for each plan is up to the voters to accept or reject. If more than half of voters accept the deposit (for instance, because the proposal was spam), then it is added to the reserve pool minus any burned IMVs. Voters may select one of the following options for each proposal:

* Yea
* Yea with Force
* Nay
* Nay with Force
* Abstain 

A simple majority of Yea or Yea with Force votes is required to pass (or fail) a proposal, but 1/3 or more of the vote may veto the majority decision by voting “with force.” When a strict majority decision is vetoed, all parties pay “VetoPenaltyFeeBlocks” (DEFAULT 1 day’s worth of blocks) in fees (excluding taxes, which remain unaffected), and the party that rejected the majority decision pays “VetoPenaltyIMVs” (DEFAULT 0.1 percent) of its IMVs.

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

