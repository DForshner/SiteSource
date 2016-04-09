---
title: Odds & Ends - December 2015
date: 2015-12-01 00:00:00
tags:
  - Random
  - Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Think about the period of time when we are waiting for followers to acknowledge a write as your uncertainty window.  As followers acknowledge the write we are increasingly certain that our write has been captured and eventually we can advance our uncertainty window.
* Cores are black boxes that instructions go in and come out in a sequential manner.  Inside the black box instructions can run in any order.
* Out of order execution
  * Fetch multiple instructions each cycle and decode into µ-ops.
  * µ-ops are put into the re-order buffer (ROB) where they can be processed out of order if data is ready.
  * To prevent pipeline stalls speculative execution runs all the conditional branches in parallel until the core figures out which branch to take.
* Hyperthreading - Provides two virtual processors that share a reorder buffer.  Provides the core with more data during general workloads to keep execution units busy.
* Pipelines improve performance but can cause nightmares if they stall!
  * CPUs run best when instructions and data are in order.
  * Keep data in order, adjacent, and consecutive to prevent data stalls.
  * Don't jump around because it won't be able to predict where you want to go.
  * Take comparisons out of loops to prevent mispredicted branches. For { If { ... } } => If { For { ... } }