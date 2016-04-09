---
title: Odds & Ends - March 2014
date: 2014-03-01 00:00:00
tags:
  - Random
  - Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* 5 questions to ask when creating tests:
  * What if null?
  * What if zero?
  * What if one item?
  * What if three items?  (Bugs often show up on middle rows not the first/last)
  * What if many items?
* Don't add cross-cutting concerns via inheritance.  If you extend a class to add support for logging/caching you are adding a new responsibility (violating SRP).
* Update performance suffers from denormalization.  When you update a duplicated value on a 1NF table you will have to update every row that has that value instead of just one row in 3NF.  Solutions:
  * Don't update - It's not a problem if you are only inserting into an OLAP database.
  * Normalize your schema (3NF) - Why are you updating a denormalized data warehouse style database?
  * Accept inconsistent data - Update a few rows at a time in a commit.
  * Accept locking penalty - Page/Row locks will have to be taken out for the row being updated potentially blocking other sessions.
* Normalized Schema
  * Less storage used
  * Affect fewer records when updating
* Denormalized Schema
  * Possibly better at PK lookups as you may only need to hit one table.
  * Suffers from concurrency and deadlock issues if updating.
* Distributed Consensus Algorithm - Agreement on a single value by multiple nodes.