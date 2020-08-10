---
layout: post
title: FIX, Blockchain, and Distributed Transactions
tags: ["FIX","blockchain","distributed transactions","Pat Helland"]
---

Have you ever noticed how unlike a database transaction [FIX](https://www.fixtrading.org/) messages are? You don’t open a transaction, mutate some state, and then commit. Instead you send asynchronous messages and transition through a state machine. From the perspective of a participating agent in FIX, you are either initiating action (eg sending a new order) or accepting a fact of life (eg getting a fill from an exchange).

[Mitesh Pandey](https://www.linkedin.com/in/miteshpandey/) shared an interesting paper exploring this architectural dynamic, called “Life beyond Distributed Transactions: an Apostate’s Opinion” ([PDF](https://www.ics.uci.edu/~cs223/papers/cidr07p15.pdf)), by Pat Helland. “In general, application developers simply do not implement large scalable applications assuming distributed transactions”, Helland states. He has a particular focus on what he calls Almost-Infinite Scale applications - ones which will need to spread over a large set of machines and where load will need to scale almost linearly. For these reasons most of the protocols for distributed transactions are in practice irrelevant, no matter their nice computational properties. 

Helland lays out a number of “wild opinions” (fairly sensible opinions more loosely justified than usual for a CS paper) along these lines, which map very simply to FIX:
+ _Layers of the Application_. Multiple order managers, parent-child relationships, and internal trading desks correspond to architectural layers, and are often independently developed systems.
+ _Scalable Apps Use Uniquely Identified “Entities”_. FIX Orders and Executions are entities in this sense. They must live within a single scope of serializability, ie in a particular process on a particular machine.
+ _Atomic Transactions Cannot Span Entities_. FIX Orders and executions meet this, though you can argue that cases like busting imply a single Order+Executions entity.
+ _Messages Are Addressed to Entities_. Fields such as ClOrdId (11) are addressing mechanics.
+ _Entities Manage Per-Partner State_. elland here is referring to the fine-grained ownership of a co-ordinated activity between elements in a distributed system. FIX is both fine-grained in this way (it works at the individual order level) and has the same ownership property. You either own an order, or create executions for it. If you need your own independent child order to manage your interaction with downstream (such as an exchange), you create one, and control it, observing executions sent to you.
+ _Most Applications Use At-Least-Once Messaging_. FIX has straightforward duplicate detection and retransmission mechanics using unique order and execution identifiers.

<img style="float: right" src="/assets/JulianFIXApostate.jpg" alt="Julian, FIX Apostate" />

One more part of piece stands out from a FIX perspective. In a section called “Coping Without Atomicity”, Helland says “The absence of distributed transactions means we must accept uncertainty as we attempt to come to decisions across different entities. It is unavoidable that decisions across distributed systems involve accepting uncertainty for a while […] The uncertainty of the outcome is held in the business logic rather than in the record lock. This is simply workflow.” That’s the FIX state machine, and its Cancel Request / Pending Cancel mechanics, in a nutshell. We even called the front office order management team at BAML the workflow team for a while.

The FIX protocol was created by Bob Lamoureux and Chris Morstatt in 1992 or so, twenty years before this paper. No doubt they are both great technologists. I suspect they also learned from operational and institutional processes that existed in their financial firms at the time - organizations that needed to coordinate financial transactions in conditions of difficult latency and unreliable communication for decades.

Lastly, it’s interesting to note that blockchain, at least the ledger layer of say the Bitcoin protocol, takes an almost completely opposite approach. Proof of work triples down on distributed transactions. It’s not just a two-phase commit but a (50%+1 of the network)-phase commit. That’s why it’s a high-latency, low-throughput protocol. Now, blockchain advocates will say that’s an engineering trade off worth making to establish a ledger of anonymous electronic commodity money without a common central authority, and as a result it should be treated not as everyday cash, but little bars of gold bullion. That’s fair enough, or at least it identifies the right engineering tradeoff. It also points us at why low-latency, almost-infinite scale blockchain applications will need a more “apostatic” layer above it, like Lightning, that is based around fine-grained entities, and rejects distributed transactions.


----
_This article was originally published on [LinkedIn](https://www.linkedin.com/pulse/fix-blockchain-distributed-transactions-adam-burke/)._

