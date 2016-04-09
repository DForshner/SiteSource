---
title: Odds & Ends - June 2015
date: 2015-06-01 00:00:00
tags:
  - Random
  - Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Attention is the currency of our age
* Innovation is found at the boundaries between disciplines, not by narrowly focusing in one sphere.
* Many developers derive pleasure from removing bugs that they should not have created in the first place.  Instead, structure code so it correct the first time and make it as easy to debug as possible.
* Losing 20% of your data is worse than losing 100% because you don't know what you have lost.
* Aside from making reasonable algorithm choices, cache misses are the main thing you need to worry about for performance.  Compared to cache misses, minor efficiency improvements just don't matter.
* If you are waiting for the network it probably doesn't matter how slow your network is.
* Idiomatic code: what the language wants you to do.
* If a language puts all your allocations on the heap it's likely causing cache misses since you can't decide how objects are organized in the heap.
* Each reference is 8 bytes on a 64-bit machine.
* Tell don't ask - Rather than asking an object for data and acting on it, just tell the object what to do.  Let the object make its own decisions based on its own data.
* Interfaces break dependencies.
  * Runtime dependency - Flow of control leaves one module and enters another.
  * Source code dependency - A name declared in one module appears in another module.
  * If ModuleA.MethodA() calls ModuleB.MethodB() then ModuleA needs ModuleB to compile (source + runtime).
  * If ModuleA.MethodA() calls InterfaceB.MethodB() then ModuleB need not exist to compile A (source only).
* Acceptable Response Times
  * Loading - 1000mn - A splash screen helps
  * Respond to finger down - 100ms
    * Users notice less than 100-150ms
    * Remember that we may schedule a response but the engine may not get to it right away!
    * Try for 100ms as it will be increased by scheduler delays.
  * Animation chunks - 6ms
    * 60Hz so all work must take ~16ms (4ms for OS so 6ms left for work).
    * Work must be schedulable in the 6ms available!
  * Idle/Cleanup - 50ms
* Trees
  * Every path is a tree.  
  * Trees are allowed to branch.  
  * A tree is connected and n vertices have n-1 edges.
  * Trees have unique chains of edges joining two vertices
  * [A-B-C-D] Tree
  * [A-B] [C-D] A forest containing two trees
  * [A]→[B] Not a tree because there are 2 paths from A to D.
     ↓   ↓
    [C]→[D]
* A chair is a resource.  A teammate is a human being.
* Projections - A piece of code that takes a series of events and produces a transient state from them.
* React - state flows down via properties and events flow up via callbacks.
* You only get one shot at encoding facts into a type system, and once you do you are stuck with them, so don't try to encode too much, and make sure what you encode is fundamental (won't change) about your business domain.
* ECMAScript Debugging tips: console.Table([1,2,3], [2,3,4]); object.observe(foo); console.trace(foo);
* Algorithm Correctness - Does it do what it is supposed to do?
* Algorithm Efficiency - Does it have a run-time that is polynomially bounded?
* Types of Equality - Reference equality, Identity Equality (same pk in DB), Logical Equality (value objects with identity fields)
* A hash is a fingerprint for data.  It takes data of any length and gives you a small fixed sized identifier that you can use to compare or identify the data.