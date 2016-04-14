---
title: Odds & Ends - June 2014
date: 2014-06-01 00:00:00
tags:
- Random
- Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* There is no such thing as "plain text".  Text is binary data plus an encoding scheme.
  * When someone says "plain text" always ask "what encoding?"
  * Try to use UTF-8 if possible.
  * Try to always make encoding explicit in code.  Don't rely on the platform/system default encoding.  String text = convert(byte[] byteArray, Encoding.UTF);
  * Glyph - Visual representation (a).
  * Code Point - Numeric representation in character set being used (65).
  * Code Unit - Binary representation determined by the encoding scheme (0100001).
* Slow Database Table Scans - Query requests a row or range of rows and there are no available indexes to support it.  This causes a sequential scan from to bottom of the table.
  * Any routine query that takes more than second will be a problem eventually.
  * A table scan might not be noticeable if the table is small enough to fit in memory or disk cache but as it grows it will increasingly be pulled from disk (slow).  This also adds to the disk contention with any other running queries.
* Database Concurrency Contention -  Too many users competing for the same resources.   Sometimes caused by table scans.
  * Database locks up resources waiting to serve requests.
  * Transactions lock row/tables for writes and other users cannot read from those rows.
  * Transactions that span too many rows cause problems if a query has a table scan or update.  Resources are locked for the duration of the transaction so try to limit it to under 1 second.
  * There is a limited number of connections to the RDMS available and it's possible to have them all blocked waiting on resources.
* Slow Database Writes - As the table grows in size they often show a "hockey stick" curve for write speeds.
  * The typical culprit are table indexes.  This is especially true when there are multiple indexes on a single large table.
  * B-Tree requires more computational and disk resources as they index tree grows in size.
  * Limit indexes to what is required and use caution when data gets big.