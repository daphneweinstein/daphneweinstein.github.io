---
layout: post
title:  "What Decentralized(ish) Data Storage Systems Tell Us About Scaling"
date:   2017-02-09 17:05:04 -0400
categories: decentralization
---
Scalability has been a central point of concern in the bitcoin and wider blockchain community for a while now. Decentralized data storage systems can be thought of as a microcosm of this discussion because of the increased scaling pressures faced by systems aimed at storing data. For example, one of the key insights that decentralized data storage projects have had that the rest of the cryptocurrency community is beginning to think about is delegation of certain roles off of the blockchain.

Few systems aimed at data storage employ a standard proof-of-work blockchain to store data because of the burden of replication this places on the nodes. I only know of [one proposal] [HDG] that seems to call for this (though the language is somewhat unclear).

Many properties of a blockchain outside of full replication are desirable for a decentralized data storage system. Byzantine fault tolerance, and especially robustness against Sybill attacks is key to any system where the data stored should have a low probability of being lost, stolen, or tampered with. Single points of failure in systems with code that serves an administrator function are also a concern, though one mitigated by the possibility of siloing such processes in an SGX enclave as [Town Crier] [towncrier] does. 

Instead of proof-of-work based blockchains, various systems have opted to use reputation-based protocols to secure and provide functionality for clients. Proof-of-stake has appreciated renewed interest in the context of Ethereum as a way of appending new blocks to the ledger. A similar approach to the work proposed by Vlad Zamfir for Casper (as of writing, there is still some confusion within the Foundation as to what form Casper will ultimately take as I understand) is proposed by [Enigma][Enigma]. 

Enigma nodes participate in blockchain appends, storage, and computation for a fee. The node to perform any one of these computations is chosen through a randomized function on the accrued reputation of the node and its availability. Bad behavior is disincentivized by the requirement of a security deposit to join the network. Though this is somewhat underspecified in the current iteration of the whitepaper, it would seem that this is in essence the same as the proposed work for Casper, with added storage functionality. 

There are ways to take advantage of the collective wisdom of the community outside of proof-of-stake based systems. [BigchainDB][bcdb] relies on paxos to secure the order of blocks in the ledger, but it shoves the soundness of the chain off of the ordering and onto validators. Instead of relying on the validity of all blocks in the chain, BigchainDB uses voting to designate the validity of blocks. When a block is proposed, its validity is considered undecided but it is still part of the chain. When validators have voted, the designation (valid or invalid) that the majority choose is given to the block. Invalid blocks stay in the chain, but are marked as such so that new transactions and auditors know that they are not considered valid. This is not a fully Byzantine Fault Tolerant system, but the low latency of such a network makes it attractive for non-mission-critical applications.

[IPFS][IPFS] uses reputation to regulate transfer of data. The IPFS BitSwap protocol allots reputational points to nodes who provide data to their peers. The protocol probabilistically decreases the priority of nodes that have a deficit (request more than they provide). 

A key to IPFS is that the reputation of a node can increase partially by its use of the network: the more items a node downloads, the more it has to offer to the network. We have seen that the users and miners of Bitcoin, Ethereum, and other networks are nearly disjoint on a practical level. This arguably lowers the tolerance of the network to Byzantine attacks, because those who provide key functionality have no interest in the network continuing to function other than their direct financial compensation, and nodes could extract all of their resources from the network prior to attacking it. Constructing networks in such a way that those who use them can also be those who perform the computation and even storage functions for the network should be a goal. 


[HDG]: https://www.ncbi.nlm.nih.gov/pubmed/27565509
[towncrier]: https://eprint.iacr.org/2016/168.pdf
[Enigma]: http://www.enigma.co/enigma_full.pdf
[bcdb]: https://www.bigchaindb.com/whitepaper/
[IPFS]: https://ipfs.io/ipfs/QmR7GSQM93Cx5eAg6a6yRzNde1FQv7uL6X1o4k7zrJa3LX/ipfs.draft3.pdf
