---
title: Odds & Ends - March 2015
date: 2015-03-01 00:00:00
tags:
- Random
- Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Avoid misunderstandings by making the implicit explicit
* API Design - Don't operate on one object if you can operate on many instead.  If you do something once, there is a good chance you will do it 100x times. [src](https://medium.com/google-developers/if-i-ve-told-you-once-a0ccdb083e08#.r10n0j9ap)
* A good tech leads shield engineers from distractions and give support when needed.  Enable people to do their jobs.
* A good software architect makes the complex simple.  Your job is to reduce complexity.
* Pretend you had to create a schedule before you knew the requirements or you needed to estimate how long it will take to solve an unsolved problem.
  * When you don't know what you are going to build then you cannot know how long it will take to build it.
  * You only really know for sure what you are going to build when you finish it.
  * A good way to document requirements is to create a user manual.
* Code can be divided into algorithms that do work on data or coordinators that coordinate external dependencies with algorithms.  Algorithms are easy to test.
* Agile - build a little, test a little.
* When you have a mess of short functions plagued by lots of behavior modifying arguments the boundary between component and layers is slowly dissolved, and nobody is sure what particular effect a change may have anymore.
* Once you get rid of accidental complexity you are left with essential complexity, which cannot be reduced without removing functionality.
* Reference equality, value equality and identity (PK) equality ... are not equal.
* One of the benefits of returning ASAP is the happy path isn't identically nested anymore.
* <u>Identity map pattern</u> - Ensures each object is only loaded once.  One copy of an entity will be loaded at a time per transaction.  One copy that everyone updates so, there are no update anomalies.
* <u>Immutable Infrastructure</u> - Infrastructure built from golden images.  Changes are made to the images, and the entire infrastructure should be redeployed by destroying the old deployment.