# Imversed white-paper

## Index

1. Introduction
2. Imversed Outline
3. Blockchain for Users
4. NFT Tokens as First-class Citizens
    1. NFT Denominations
    2. NFT Oracles
5. On-Chain Tokenomic
    1. Types of tokens
        1. IMV coins
        2. Liquidity tokens
        3. NFT tokens
        4. Governance tokens
    2. Liquidity pools
    3. On-chain layering
6. Tendermint
    1. Validators
    2. Consensus
    3. Light clients
    4. Preventing Attacks
    5. ABCI
    6. Limitations
    7. Penalties
7. Transaction fees
8. Governance Specification
9. Appendix 1 - Roadmop
10. Appendix 2 - Tendermint details
    1. Fork Accountability
    2. Tendermint Consensus details
    3. Tendermint Light Clients details
    4. Preventing Long Range Attacks
    5. Overcoming Forks and Censorship Attacks
11. Appendix 3 - Links

## Introduction

Imversed is a blockchain surrounded by a ecosystem of projects which are enables the simple creation, trading, and
transfer of tokens and non-fungible tokens (NFTs [[1]](https://ethereum.org/en/nft)) without the need for coding or
engineering. Imversed is a community-driven SaaS solution that empowers businesses, influencers, and communities to use
blockchain technology. Among the most important characteristics are the following:

* Stable and secured implementation of Proof Of Stake (
  POS [[2]](https://www.investopedia.com/terms/p/proof-stake-pos.asp)) consensus
* A graphical user interface and an API for creating user tokens
* All tokens on Imversed are interchangeable
* Non-monetary tokens are supported
* Possibility to use NFT Oracles to establish ownership and copyright.
* Integrations with major e-commerce platforms enable the sale of NFTs in the same way that traditional products are
  sold.
* Multiple token levels, and the top-level tokens can benefit from the lower-level tokens
* Infrastructure is propelled forward by a dependable engine (Imversed chain)

These extensive features are built on a dependable and secure foundation. Imversed is a blockchain application built on
top of the COSMOS library that, when combined with Tendermint Core [[3]](https://github.com/tendermint/tendermint/wiki),
provides a high-performance, consistent-in-use, and secure PBFT-like consensus engine with strict fork-accountability
guarantees over malicious actors' behavior. More information on PBFT-like consensus engines can be found
in [[6]](http://pmg.csail.mit.edu/papers/osdi99.pdf). The BFT consensus algorithm from Tendermint Core is well-suited
for scaling public proof-of-stake blockchains.

## Imversed Outline

A lot of great ideas come from brilliant minds. Some of these concepts are only possible with decentralized blockchain
technology. However, the complexity of software development and the complexity of running community-based infrastructure
are roadblocks to many of these good ideas. The Imversed network aims to eliminate barriers between entrepreneurs,
communities, influencers, and blockchain tokens. Imversed achieves this goal through leveraging a Proof of Stake
blockchain engine with BFT consensus, allowing blockchain to perform operations quickly and securely. The foundation for
decentralized apps (dapps) is decentralized blockchain. Every dapp solves a specific problem for community members.
Imversed implements Dapps as modules. Modules are a much more secure way to extend network functionality than smart
contracts because they must be approved by the community and go through a governance process. Imversed already includes
pre-built modules for the vast majority of blockchain-based tokenoconomy and NFT use cases. Imversed also provides a
lightweight client for querying blockchain nodes. The light client allows third-party developers to easily request data
from the blockchain and build services for the Imversed ecosystem. Imversed blockchain dapps are already supported by a
few open source services, such as NFT e-commerce and transaction explorer. Imversed blockchain is a multi-layered,
community-driven decentralized network. The zero layer is a layer of real-world servers managed by the IMV coin
community. Every server runs the exact version of an open source application, ensuring transparency and trust among
community members. Full nodes could be promoted to validators, allowing them to add new blocks to the blockchain (
details could be found in [Tendermint](#Tendermint) section of this whitepaper). Because zero layer logic guarantees
rules and principles, any layers based on it are decentralized and community driven. Decisions to change zero layer
logic could only come from IMV token holders and should go through a democratic voting process. Imversed makes it simple
and secure for anyone to create a crypto token. Every token built on top of the Imversed network is decentralized and
backed by the Imversed community. It ensures the independence and dependability of Imvesred-based tokens in conjunction
with the democratic governance process. This token could be used in all Imversed dapps, mint NFT tokens, and be
exchanged for other Imversed tokens or IMV coin (details could be found in [On-Chain tokenomic](#On-Chain tokenomic)
section of this whitepaper). Not only can the complexity of development and infrastructure stymie the implementation of
great ideas. Some blockchain networks choose to tie transaction fees to the value of a coin. High transaction fees and
slow transaction completion may be a problem. Imversed addresses these challenges by introducing a governance-based
mechanism for defining fees (details can be found in the [Transaction fees](#Transaction fees) section of this
whitepaper)
and fast transaction finality based on the implementation of the BFT consensus algorithm.

## Blockchain for Users

Imversed were designed with ease of use in mind. More non-technical people should be able to enter the blockchain world
and begin to thrive and grow. These individuals will contribute their enthusiasm and ideas to increase the value of the
blockchain ecosystem. Unlike other blockchain projects, imversed allows users to create their own tokens through an
easy, consistent, and clear API. Instead of writing a smart contract, debugging it, ensuring its safety, or looking for
a technical person you can trust. A person can open a web interface or a mobile client and create their own token with
rich functionality already built in. Imversed ecosystem includes a web project that allows users to create their own
token after answering a few simple questions. Depending on the requirements, the created token could have a variety of
functions such as governance, NFT, or liquidity (details could be found in Types of tokens section of this whitepaper).
Imversed ecosystem projects' strong validation and simple UX reduce human errors in critical steps such as token
creation. In the Imversed transaction explorer, all operations on newly created tokens are visible. Imversed wallet
natively supports newly tokens as well as it supports zero level IMV coin.

## NFT Tokens as First-class Citizens

In Imversed NFT tokens are build-in as a part of the blockchain. As a result all tokens are unified, trustable,
recognizable by all external services and perfectly trackable. Different types of NFT ownership and royalty programs are
available and more features will be added with new versions of Imversed.

### NFT Denominations

NFT is typically delivered in the form of a series or group. There's something in common between the Punks and Kitties
series. Imversed introduces a simple way to connect NFT tokens. Denomination is meta data about a group of NFT tokens.
As a field, every NFT token contains the denomination's identity. Denomination is owned and can be changed by the owner.
The change in denomination has no effect on NFT tokens that have already been issued. Because denomination is not
restricted, anyone can mint NFT tokens with a specific denomination. Denomination contains strongly typed fields as well
as data fields that can be filled with whatever information the owner desires. NFT tokens issued by an artist are a good
example of a denomination. This artist might want to put his website in denomination to make himself more recognizable
even after the NFT has changed hands multiple times.

### NFT Oracles

ETH [[4]](https://eth.wiki) is, probably, the most popular network for NFT and, in terms of copyright and security, it
resembles the Wild West. The most widely used network for NFT is ETH, which appears to be a lawless wasteland in terms
of copyright and ownership. Anyone has the ability to reissue and sell anything. Users can create an ERC-721-compliant
contract and mint any NFT using it. Imversed defines denomination as a type of NFT user or corporation that is capable
of producing and minting NFTs. The denomination is a set of metadata shared by all NFT issues in this denomination.
There is a holder of the inverted denomination. Although the creator of the denomination maintains ownership, it can be
transferred to another location. The denomination may include the URL to the Oracle database. This URL should implement
a specific HTTP contract that allows an Imversed network address to determine whether or not they have authorization to
the URL of the NFT they wish to mint.

## On-Chain Tokenomic

Tokens are just bytes in blockchain transactions if no value is attached to them. Imversed allows on-chain tokens to be
traded with one another. Tokens could be exchanged directly or indirectly thru the IMV coin (double conversion). The
value of each token is determined by the amount of demand and supply within a given token pair. The amount of liquidity
locked up in the token pair's liquidity pool defines the exchange rate within the token pair. Non-financial tokens can
act as NFTs or allow users to participate in non-financial distribution and public voting.

### Types of tokens

￼ ￼![Types of tokens](assets/images/token-types.png?raw=true "Types of tokens")

### IMV coins

While Imversed is a distributed ledger that supports several assets, it is distinguished by its native token, the IMV,
which is Imversed’s single staking token. IMVs are a sort of license that permits the holder to vote, validate, and
delegate authority to additional validators. IMVs, like Ethereum’s ether, can be used to defray transaction costs, thus
minimizing spam. Additional inflationary IMVs and block transaction fees are paid to validators and delegators who
delegate to validators.

### Liquidity tokens

Each liquidity token can be exchanged directly for another or, more typically, indirectly via the IMV token. Imversed
uses a liquidity pooling approach to establish the exchange rate depending on numerous parameters listed in the next
section. Additionally, the price is influenced by the IMV token’s exchange rate and its pricing on other exchanges like
Binance or Osmosis.

### NFT tokens

NFT tokens are special type of tokens which could be issued for branding or recognition purposes. This type of token are
not exchangeable with other types of tokens and has no value. Initial minting and transferring fees of this type of
token supposed to be paid from a service account of token owner. NFT tokens are not participate in liquidity pools.

### Governance tokens

Governance tokens are exclusively utilized for voting procedures that take place outside the network (for example,
public/anonymous voting in classes or communities). IMV coins are the only currency that can be used for on-chain
self-governance.

### Liquidity pools

A Liquidity Pool is a self-balancing weighted portfolio and price sensor that functions as an automated market
maker [[9]](https://balancer.fi/whitepaper.pdf). The liquidity pool system calculates the exchange rate prior to the
exchange, taking into account several factors such as the number of tokens requested to be exchanged, the number of
tokens locked in the liquidity pool, the overall amount of each token participating in current exchanges, and other
important factors. The algorithm may change, but it will always be a part of the blockchain code, and any changes must
be democratically approved via voting. Tokens with no monetary value are also permitted in the Imversed ecosystem.
Initially, the token's creator could provide liquidity for the pool, or other users could stack their tokens in the pool
to profit from exchange fees.

### On-chain layering

Layering in Imversed tokens allows users to assign a hierarchical structure to tokens created on the chain. Assume a
holding corporation creates a token that represents the entire organization as well as a few additional layers, such as
two tokens for each line of business, to diversify risks or for branding purposes. The top structure is intended to
profit from sub-token activity. These benefits can be obtained through a variety of means, including the following:

* A portion of each transaction made with the level 2 token will be distributed to all holders of the main token.
* A portion of each sub-token transaction will be remitted to a service account established in a level 2 token
  denomination.
* A percentage of each transaction completed with a level 2 token will eventually be distributed to all holders of the
  level 1 token who have staked their tokens in validators.

## Tendermint

This section briefly discusses Tendermint consensus method and the application development interface. Tendermint is
underlying technology of Imversed blockchain responsible for implementing general distributed blockchain activities such
as network communication, data exchange, transaction confirmation and in-app communication. The Appendix contains
further information.

### Validators

In classical Byzantine fault-tolerant (BFT) algorithms, each node has the same weight. In Tendermint, nodes have a
non-negative amount of voting power, and nodes that have positive voting power are called validators. Validators
participate in the consensus protocol by broadcasting cryptographic signatures, or votes, to agree upon the next block.
Validators' voting powers are determined at genesis, or are changed deterministically by the blockchain, depending on
the application. For example, in a proof-of-stake application such as the Cosmos Hub, the voting power may be determined
by the amount of staking tokens bonded as collateral. NOTE: Fractions like ⅔ and ⅓ refer to fractions of the total
voting power, never the total number of validators, unless all the validators have equal weight. >⅔ means "more than ⅔",
≥⅓ means "at least ⅓".

### Consensus

Tendermint is a partially synchronos BFT consensus protocol derived from the DLS consensus
algorithm [[8]](http://groups.csail.mit.edu/tds/papers/Lynch/jacm88.pdf). Tendermint is notable for its simplicity,
performance, and fork-accountability. The protocol requires a fixed known set of validators, where each validator is
identified by their public key. Validators attempt to come to consensus on one block at a time, where a block is a list
of transactions. Voting for consensus on a block proceeds in rounds. Each round has a round-leader, or proposer, who
proposes a block. The validators then vote, in stages, on whether to accept the proposed block or move on to the next
round. The proposer for a round is chosen deterministically from the ordered list of validators, in proportion to their
voting power. Tendermint’s security derives from its use of optimal Byzantine fault-tolerance via super-majority (>⅔)
voting and a locking mechanism. Together, they ensure that:

* ≥⅓ voting power must be Byzantine to cause a violation of safety, where more than two values are committed.
* if any set of validators ever succeeds in violating safety, or even attempts to do so, they can be identified by the
  protocol. This includes both voting for conflicting blocks and broadcasting unjustified votes. Despite its strong
  guarantees, Tendermint provides exceptional performance. In benchmarks of 64 nodes distributed across 7 datacenters on
  5 continents, on commodity cloud instances, Tendermint consensus can process thousands of transactions per second,
  with commit latencies on the order of one to two seconds. Notably, performance of well over a thousand transactions
  per second is maintained even in harsh adversarial conditions, with validators crashing or broadcasting maliciously
  crafted votes. See the figure below for details.

### Light Clients

A major benefit of Tendermint's consensus algorithm is simplified light client security, making it an ideal candidate
for mobile and internet-of-things use cases. While a Bitcoin light client must sync chains of block headers and find the
one with the most proof of work, Tendermint light clients need only to keep up with changes to the validator set, and
then verify the >⅔ PreCommits in the latest block to determine the latest state. Succinct light client proofs also
enable inter-blockchain communication.

### Preventing Attacks

Tendermint has protective measures for preventing certain notable attacks, like long-range-nothing-at-stake double
spends and censorship. These are discussed more fully in the Appendix 2.

### ABCI

The Tendermint consensus algorithm is implemented in a program called Tendermint Core. Tendermint Core is an
application-agnostic "consensus engine" that can turn any deterministic blackbox application into a distributedly
replicated blockchain. Tendermint Core connects to blockchain applications via the Application Blockchain Interface (
ABCI) [[7]](https://github.com/tendermint/abci). Thus, ABCI allows for blockchain applications to be programmed in any
language, not just the programming language that the consensus engine is written in. Additionally, ABCI makes it
possible to easily swap out the consensus layer of any existing blockchain stack. We draw an analogy with the well-known
cryptocurrency Bitcoin. Bitcoin is a cryptocurrency blockchain where each node maintains a fully audited Unspent
Transaction Output (UTXO) database. If one wanted to create a Bitcoin-like system on top of ABCI, Tendermint Core would
be responsible for

* Sharing blocks and transactions between nodes
* Establishing a canonical/immutable order of transactions (the blockchain)
  Meanwhile, the ABCI application would be responsible for
* Maintaining the UTXO database
* Validating cryptographic signatures of transactions
* Preventing transactions from spending non-existent funds
* Allowing clients to query the UTXO database Tendermint is able to decompose the blockchain design by offering a very
  simple API between the application process and consensus process.

### Limitations on the Number of Validators

Unlike Bitcoin or other proof-of-work blockchains, a Tendermint blockchain gets slower with more validators due to the
increased communication complexity. Fortunately, we can support enough validators to make for a robust globally
distributed blockchain with very fast transaction confirmation times, and, as bandwidth, storage, and parallel compute
capacity increases, we will be able to support more validators in the future.

### Penalties for Validators

There must be some penalty imposed on the validators for any intentional or unintentional deviation from the sanctioned
protocol. Some evidence is immediately admissible, such as a double-sign at the same height and round, or a violation
of "prevote-the-lock" (a rule of the Tendermint consensus protocol). Such evidence will result in the validator losing
its good standing and its bonded IMVs as well its proportionate share of tokens in the reserve pool -- collectively
called its "stake" -- will get slashed. Sometimes, validators will not be available, either due to regional network
disruptions, power failure, or other reasons. If, at any point in the past ValidatorTimeoutWindow blocks, a validator's
commit vote is not included in the blockchain more than ValidatorTimeoutMaxAbsent times, that validator will become
inactive, and lose ValidatorTimeoutPenalty (DEFAULT 1%) of its stake. Some "malicious" behavior does not produce
obviously discernible evidence on the blockchain. In these cases, the validators can coordinate out of band to force the
timeout of these malicious validators, if there is a supermajority consensus. In situations where the Cosmos Hub halts
due to a ≥⅓ coalition of voting power going offline, or in situations where a ≥⅓ coalition of voting power censor
evidence of malicious behavior from entering the blockchain, the hub must recover with a hard-fork reorg-proposal. (
Details in "Forks and Censorship Attacks").

## Appendix 1 - Roadmap

￼![Roadmap](assets/images/roadmap.png?raw=true "Roadmap")

## Appendix 2 - Tendermint details

### Fork Accountability

A well designed consensus protocol should provide some guarantees in the event that the tolerance capacity is exceeded
and the consensus fails. This is especially necessary in economic systems, where Byzantine behaviour can have
substantial financial reward. The most important such guarantee is a form of fork-accountability, where the processes
that caused the consensus to fail (ie. caused clients of the protocol to accept different values - a fork) can be
identified and punished according to the rules of the protocol, or, possibly, the legal system. When the legal system is
unreliable or excessively expensive to invoke, validators can be forced to make security deposits in order to
participate, and those deposits can be revoked, or slashed, when malicious behaviour is
detected [[5]](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm/). Note this is unlike
Bitcoin, where forking is a regular occurrence due to network asynchrony and the probabilistic nature of finding partial
hash collisions. Since in many cases a malicious fork is indistinguishable from a fork due to asynchrony, Bitcoin cannot
reliably implement fork-accountability, other than the implicit opportunity cost paid by miners for mining an orphaned
block.

### Tendermint Consensus

We call the voting stages PreVote and PreCommit. A vote can be for a particular block or for Nil. We call a collection
of >⅔ PreVotes for a single block in the same round a Polka, and a collection of >⅔ PreCommits for a single block in the
same round a Commit. If >⅔ PreCommit for Nil in the same round, they move to the next round. Note that strict
determinism in the protocol incurs a weak synchrony assumption as faulty leaders must be detected and skipped. Thus,
validators wait some amount of time, TimeoutPropose, before they Prevote Nil, and the value of TimeoutPropose increases
with each round. Progression through the rest of a round is fully asynchronous, in that progress is only made once a
validator hears from >⅔ of the network. In practice, it would take an extremely strong adversary to indefinitely thwart
the weak synchrony assumption (causing the consensus to fail to ever commit a block), and doing so can be made even more
difficult by using randomized values of TimeoutPropose on each validator. An additional set of constraints, or Locking
Rules, ensure that the network will eventually commit just one block at each height. Any malicious attempt to cause more
than one block to be committed at a given height can be identified. First, a PreCommit for a block must come with
justification, in the form of a Polka for that block. If the validator has already PreCommit a block at round R_1, we
say they are locked on that block, and the Polka used to justify the new PreCommit at round R_2 must come in a round
R_polka where R_1 < R_polka <= R_2. Second, validators must Propose and/or PreVote the block they are locked on.
Together, these conditions ensure that a validator does not PreCommit without sufficient evidence as justification, and
that validators which have already PreCommit cannot contribute to evidence to PreCommit something else. This ensures
both safety and liveness of the consensus algorithm. The full details of the protocol are described here.

### Tendermint Light Clients

The need to sync all block headers is eliminated in Tendermint-PoS as the existence of an alternative chain (a fork)
means ≥⅓ of bonded stake can be slashed. Of course, since slashing requires that someone share evidence of a fork, light
clients should store any block-hash commits that it sees. Additionally, light clients could periodically stay synced
with changes to the validator set, in order to avoid long range attacks (but other solutions are possible). In spirit
similar to Ethereum, Tendermint enables applications to embed a global Merkle root hash in each block, allowing easily
verifiable state queries for things like account balances, the value stored in a contract, or the existence of an
unspent transaction output, depending on the nature of the application.

### Preventing Long Range Attacks

Assuming a sufficiently resilient collection of broadcast networks and a static validator set, any fork in the
blockchain can be detected and the deposits of the offending validators slashed. This innovation, first suggested by
Vitalik Buterin in early 2014, solves the nothing-at-stake problem of other proof-of-stake cryptocurrencies (see Related
Work). However, since validator sets must be able to change, over a long range of time the original validators may all
become unbonded, and hence would be free to create a new chain from the genesis block, incurring no cost as they no
longer have deposits locked up. This attack came to be known as the Long Range Attack (LRA), in contrast to a Short
Range Attack, where validators who are currently bonded cause a fork and are hence punishable (assuming a
fork-accountable BFT algorithm like Tendermint consensus). Long Range Attacks are often thought to be a critical blow to
proof-of-stake. Fortunately, the LRA can be mitigated as follows. First, for a validator to unbond (thereby recovering
their collateral deposit and no longer earning fees to participate in the consensus), the deposit must be made
untransferable for an amount of time known as the "unbonding period", which may be on the order of weeks or months.
Second, for a light client to be secure, the first time it connects to the network it must verify a recent block-hash
against a trusted source, or preferably multiple sources. This condition is sometimes referred to as "weak subjectivity"
. Finally, to remain secure, it must sync up with the latest validator set at least as frequently as the length of the
unbonding period. This ensures that the light client knows about changes to the validator set before a validator has its
capital unbonded and thus no longer at stake, which would allow it to deceive the client by carrying out a long range
attack by creating new blocks beginning back at a height where it was bonded (assuming it has control of sufficiently
many of the early private keys). Note that overcoming the LRA in this way requires an overhaul of the original security
model of proof-of-work. In PoW, it is assumed that a light client can sync to the current height from the trusted
genesis block at any time simply by processing the proof-of-work in every block header. To overcome the LRA, however, we
require that a light client come online with some regularity to track changes in the validator set, and that the first
time they come online they must be particularly careful to authenticate what they hear from the network against trusted
sources. Of course, this latter requirement is similar to that of Bitcoin, where the protocol and software must also be
obtained from a trusted source. The above method for preventing LRA is well suited for validators and full nodes of a
Tendermint-powered blockchain because these nodes are meant to remain connected to the network. The method is also
suitable for light clients that can be expected to sync with the network frequently. However, for light clients that are
not expected to have frequent access to the internet or the blockchain network, yet another solution can be used to
overcome the LRA. Non-validator token holders can post their tokens as collateral with a very long unbonding period (
e.g. much longer than the unbonding period for validators) and serve light clients with a secondary method of attesting
to the validity of current and past block-hashes. While these tokens do not count toward the security of the
blockchain's consensus, they nevertheless can provide strong guarantees for light clients. If historical block-hash
querying were supported in Ethereum, anyone could bond their tokens in a specially designed smart contract and provide
attestation services for pay, effectively creating a market for light-client LRA security.

### Overcoming Forks and Censorship Attacks

Due to the definition of a block commit, any ≥⅓ coalition of voting power can halt the blockchain by going offline or
not broadcasting their votes. Such a coalition can also censor particular transactions by rejecting blocks that include
these transactions, though this would result in a significant proportion of block proposals to be rejected, which would
slow down the rate of block commits of the blockchain, reducing its utility and value. The malicious coalition might
also broadcast votes in a trickle so as to grind blockchain block commits to a near halt, or engage in any combination
of these attacks. Finally, it can cause the blockchain to fork, by double-signing or violating the locking rules. If a
globally active adversary were also involved, it could partition the network in such a way that it may appear that the
wrong subset of validators were responsible for the slowdown. This is not just a limitation of Tendermint, but rather a
limitation of all consensus protocols whose network is potentially controlled by an active adversary. For these types of
attacks, a subset of the validators should coordinate through external means to sign a reorg-proposal that chooses a
fork (and any evidence thereof) and the initial subset of validators with their signatures. Validators who sign such a
reorg-proposal forego their collateral on all other forks. Clients should verify the signatures on the reorg-proposal,
verify any evidence, and make a judgement or prompt the end-user for a decision. For example, a phone wallet app may
prompt the user with a security warning, while a refrigerator may accept any reorg-proposal signed by +½ of the original
validators by voting power. No non-synchronous Byzantine fault-tolerant algorithm can come to consensus when ≥⅓ of
voting power are dishonest, yet a fork assumes that ≥⅓ of voting power have already been dishonest by double-signing or
lock-changing without justification. So, signing the reorg-proposal is a coordination problem that cannot be solved by
any non-synchronous protocol (i.e. automatically, and without making assumptions about the reliability of the underlying
network). For now, we leave the problem of reorg-proposal coordination to human coordination via social consensus on
internet media. Validators must take care to ensure that there are no remaining network partitions prior to signing a
reorg-proposal, to avoid situations where two conflicting reorg-proposals are signed. Assuming that the external
coordination medium and protocol is robust, it follows that forks are less of a concern than censorship attacks. In
addition to forks and censorship, which require ≥⅓ Byzantine voting power, a coalition of >⅔ voting power may commit
arbitrary, invalid state. This is characteristic of any (BFT) consensus system. Unlike double-signing, which creates
forks with easily verifiable evidence, detecting commitment of an invalid state requires non-validating peers to verify
whole blocks, which implies that they keep a local copy of the state and execute each transaction, computing the state
root independently for themselves. Once detected, the only way to handle such a failure is via social consensus. For
instance, in situations where Bitcoin has failed, whether forking due to software bugs (as in March 2013), or committing
invalid state due to Byzantine behavior of miners (as in July 2015), the well connected community of businesses,
developers, miners, and other organizations established a social consensus as to what manual actions were required by
participants to heal the network. Furthermore, since validators of a Tendermint blockchain may be expected to be
identifiable, commitment of an invalid state may even be punishable by law or some external jurisprudence, if desired.

## Appendix 3 - Links

* 1 NFT: https://ethereum.org/en/nft
* 2 POS: https://www.investopedia.com/terms/p/proof-stake-pos.asp
* 3 Tendermint: https://github.com/tendermint/tendermint/wiki
* 4 Ethereum: https://eth.wiki
* 5 Slasher: https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm
* 6 PBFT: http://pmg.csail.mit.edu/papers/osdi99.pdf
* 7 ABCI: https://github.com/tendermint/abci
* 8 DLS: http://groups.csail.mit.edu/tds/papers/Lynch/jacm88.pdf
* 9 Balancer: https://balancer.fi/whitepaper.pdf
