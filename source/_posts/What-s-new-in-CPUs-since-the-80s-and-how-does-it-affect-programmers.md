---
title: "What's new in CPUs since the 80s and how does it affect programmers?"
date: 2015-03-15 00:00:00
tags:
 - Optimization
---
Amazing post about how CPU and memory architecture has changed over the years.

>  using predictable memory access patterns and operating on chunks of data that are smaller than your CPU cache will get you most of the benefit of modern caches.

* Processor speed has increased much more than memory speed.  To work around this CPUs use:
  * Caching - Fast access to frequently used data.
  * Prefetching - Fast access by pre-loading data into the cache if the access pattern is predictable.  Example: sequential access of 8 bytes in a loop can achieve 22Gb/sec on 3Ghz processor out of a maximum 24Gb/sec (3Ghz * 8 bytes = 24,000,000,000 bytes/sec).
* Out of order execution - Speculatively execute and re-order executions to avoid stalling on a single resource.  Instructions with dependencies will execute in the correct order with respect to one another.
* There are no guarantees that interactions between cores will be ordered unless serializing instructors or memory fences are used.

[Post](http://danluu.com/new-cpu-features/)