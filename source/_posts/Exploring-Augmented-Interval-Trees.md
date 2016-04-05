---
title: Exploring Augmented Interval Trees
date: 2016-02-29 00:00:00
tags:
  - Exploring
  - Data Structures
---
Interval trees store a set of intervals and can be used to find all intervals that overlap with the query interval.  In the augmented variant, each node maintains the maximum end value of the node and all of its children.  We can use this extra information during searches to rule out subtrees that cannot possibly contain the query interval.

[The Code](https://github.com/DForshner/CSharpExperiments/blob/master/AugmentedIntervalTree.cs)