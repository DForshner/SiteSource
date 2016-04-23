---
title: Designing Data-Intensive Applications Review
date: 2016-04-04 00:00:00
tags:
- Books
- Reviews
- Distributed Systems
- Databases
---
This [book](https://www.goodreads.com/book/show/23463279-designing-data-intensive-applications?utm_medium=api&utm_source=blog_book) is still in pre-release so I've only been able to go through the first nine chapters.  It breaks a confusing field into logical pieces and then shows you how they fit together.  I'd recommend it to anyone who interested in databases or distributed systems.

- Does an amazing job of explaining the algorithms and data structures used to implement systems and what problems they are best at solving.
- Focuses on concepts and avoids the mistake of only talking about particular products or implementations.
- Explains different guarantees and the tradeoffs made in providing them.
- Lots of references and examples.  The author has pulled together a lot of material for this book.

**Chapter Notes**
1. *Reliable, Scalable, and Maintainable Applications*
  * Think of response time not a single number but as a distribution of values you can measure.
  * The mean is not a good metric if you want to know your "typical" response time because it doesn't tell you how many users actually experience that delay.
  * The architecture of large scale systems is usually highly specific to the application.  There is not such thing as **magic scaling sauce** (a generic one-size-fits-all scalable architecture).
2. *The Battle of the Data Models*
  * <u>Many to one relationships</u> - Prefer relational model
  * <u>One to many (hierarchy) relationships</u> - Prefer document model
  * <u>Many to many relationships</u> - Prefer graph model
  * The advantage of using and ID is that it has no reason to change even in the information it identifies changes.
  * Document databases don't need joins to work with one-to-many tree structures, and support for joins if often weak.
3. *Storage and Retrieval*
  * Storage engines fall into two broad categories:
    * <u>Transaction processing systems</u> - Many queries each accessing a small number of records using some kind of key.  Disk seek time is often the bottleneck.
    * <u>Analytic system</u> - Few queries each accessing a large number of records.  Disk bandwidth is often the bottleneck.  Column databases work best for computing aggregated statistics.
   * Two major implementations of storage engines are:
    * <u>log-structured</u> - Only ever appends to files (Cassandra).
    * <u>update-in-place</u> - Treat disk as fixed size pages that can be overwritten (Traditional RDMS/B-Trees).
   * The performance of in-memory databases is more because they avoid the overhead of encoding the data into data structures that can be written to disk than the actual reading from disk.
   * Easier to maintain sorted order in memory with Red-Black/AVL trees which allow keys to be inserted in any order and read back in sorted order.
   * The star schema divides data into facts and dimensions.  Each row in a <u>fact table</u> represents and event that occurred at a particular time.  Each row in a <u>dimension table</u> represents the who, what, where, when, how, and why of the event.  Visually the fact table is in the middle, surrounded by its foreign keys to dimension tables like rays of a star.
   * The key idea of log-structured storage engines is to turn random-access writes into sequential writes on disk which are faster on HDD/SSD.
   * When queries involve sequentially scanning across a large number of rows, indexes are much less relevant.  Instead, it becomes important to encode data compactly, to minimize the amount of data the query needs to read from disk.
4. *Encoding and Evolution*
  * Data flow:
    * <u>Databases</u> - Different applications read/write to a shared database.
    * <u>REST/RPC</u> - Clients connect to a server that exposes API (service).  The server may talk to other servers to handle client request (microservices).
    * <u>Message Passing</u> - Asynchronous message passing systems (Message brokers or distributed actors) where nodes send each other messages.
  * During rolling upgrades different nodes will be running different versions of code so we need the data flowing in the system to have both backward compatibility and forward compatibility.
5. *Replication*
  * Reasons to replicate:
    * Keep working even when machines go down (availability)
    * Continue to work during network partitions (availability)
    * Place data geographically close to users (latency)
    * Handle higher volume of writes than possible with one machine (scalability).
  * Replication types:
    * <u>Single-leader</u> - Clients sent all writes to single leader node which streams changes to followers.  Can read from any node but followers may be stale.
    * <u>Multi-leader</u> - Clients send each write to one of several leader nodes.  Leaders send streams of changes to each other and followers.   Need to handle write concurrency conflicts.
    * <u>Leaderless replication</u> - Clients read and write to/from several nodes in parallel.   Need to handle write concurrency conflicts.
  * Consistency models:
    * <u>Read-after-write</u> - User should see the latest copy of any data they submitted themselves.
    * <u>Monotonic reads</u> - After user sees data from one point in time they should never see data from an earlier point in time.
    * <u>Consistent prefix reads</u> - Users see data in casual order.  Should not see the answer before the question.
6. *Partitioning*
  * Partitioning Strategies:
    * <u>Key</u> Range - assign a continuous range of keys.  Allows efficient range queries but increases the risk of hot spots.
    * <u>Hash</u> - assign based on the hash of the key.  Uniformly distribute skewed data preventing hot spots but inefficient range queries.
    * <u>Compound Key</u> -  Hybrid approach. The first part of the key is hashed to determine partition and the second part is used to sort the data within the partition.  Allows efficient range queries on the columns in the second part of the key.
7. *Transactions*
  * An abstraction layer that allows applications to pretend certain types of concurrency problems and faults don't exist.
8. *The Trouble with Distributed Systems*
  * Typical partial failures include:
    * Both the sent packet and its reply can be lost or delayed.
    * Node clocks being out of sync with each other.
    * Clocks jumping forward or back in time due to NTP.
    * Processes pausing for long periods and not realizing they have been paused when resumed.
  * To tolerate faults you first need to detect them and the only tool we have is timeouts which tell us nothing about the nature of the fault.
9. *Consistency and Consensus*
  * Shows how the CAP theorem is misleading when applied to real-world systems.  The author also has a [Blog Post](https://martin.kleppmann.com/2015/05/11/please-stop-calling-databases-cp-or-ap.html).  Before this, I thought that quorum style systems with a majority were consistent but it turns out I didn't even understand what the word consistent means.

[Goodreads](https://www.goodreads.com/book/show/23463279-designing-data-intensive-applications?utm_medium=api&utm_source=blog_book)