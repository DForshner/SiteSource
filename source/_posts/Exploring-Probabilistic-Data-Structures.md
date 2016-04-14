---
title: Exploring Probabilistic Data Structures
date: 2014-05-25 00:00:00
tags:
- Exploring
- Data Structures
---
The Bloom filter and Count-Min Sketch data structures keep cropping while I'm reading so I figured I would try to implement them.  They are both part of a family of probabilistic data structures that give up accuracy to store a lot of information in a tiny amount of space.

[Bloom Filter](https://en.wikipedia.org/wiki/Bloom_filter) - Could I have seen this before?
[Count–Min Sketch](https://en.wikipedia.org/wiki/Count%E2%80%93min_sketch) - What's the maximum number of times I could have seen this?

It's also worth looking at:
[HyperLogLog](https://en.wikipedia.org/wiki/HyperLogLog) - Approximately how many unique elements have I seen?
[Great post on probabilistic data structures](https://highlyscalable.wordpress.com/2012/05/01/probabilistic-structures-web-analytics-data-mining/)

[Bloom Filter code](https://github.com/DForshner/CSharpExperiments/blob/master/BloomFilter.cs)
[Count-Min Sketch code](https://github.com/DForshner/CSharpExperiments/blob/master/CountMinSketch.cs)