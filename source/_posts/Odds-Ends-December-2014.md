---
title: Odds & Ends - December 2014
date: 2014-12-01 00:00:00
tags:
- Random
- Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Kruskal's minimum spanning tree algorithm
  * O(Elog(V)) for sparse graphs (typical case).
  * Better constants than Prims because built with simpler data structures (union-find).
  * Add shortest (min weight) edge that does not create a cycle each pass.  Risks a cycle being created so much check for cycle each pass.
  * If you stop early you may have disconnected tree/forests.
* Prim's minimum spanning tree algorithm
  * O(E + Vlog(V)) if use Fibonacci heap
  * Best for dense graphs (E >>V).
  * Adds one vertex at a time and the next vertex is always the nearest to the current one on the graph.
  * If you stop early you will still have a connected graph.
* GUIDs hurt RDMS inserts because the data isn't ordered which causes a lot of I/O work to re-arrange the B-Tree leafs.
* Dynamic Content Management System
  * Dynamically generate website each request.
  * Each request eats CPU which allows DDos attacks.
  * The server shouldn't be executing any code on behalf of the user until they are logged on!
  * Use static stylesheets, graphics, movies, etc. that can be pre-generated and stored as files.
  * Static Objects (graphics/Js/CSS) can be marked as cacheable and CDN can distribute them across their network.
* Database generated ids may hurt insert performance.  To auto-generate a PK id it has to take a lock.  Shows up during multi-row or bulk inserts.
* Await Keyword - Turns the rest of the method into a closure that will asynchronously execute upon completion of the task being awaited without blocking the executing thread.
* Why Microservices?  Independent scaling, service isolation, and separate service life-cycles.
* Flake Ids - Unique semi-time sorted ids.  The top bits are time and the bottom bits are the node.  Example: 41 bits ms since epoch + 10 bits node id + 12 bits sequential counter
* Big O is not about time.  It's a tool that describes how a function grows with respect to some input.
* You want a small pool saturated with threads waiting for connections.    
  * More threads only perform better when blocking creates opportunities for executing.  Less blocking needs fewer threads.
  * Example: Connections = (# Cores * 2) + # HDDs
  * It's not about how many threads but how few threads we can get away with.  Limited by disk and network blocking.
* Improving performance
  * Motivation - Money, personal growth, make a difference.
  * Plan Smarter - Focus on important tasks first.  Remove unnecessary to-do lists, reduce the number of tasks on to-do lists (1-week window).
  * Do not interrupt - Try to minimize interruptions as much as possible.   You want to achieve flow.
  * Minimise overhead - Fewer meetings, fewer chats, and avoid checking email.  Water cooler chats about code are fine.
* The longer architects stay in their role decoupled from implementations, the less qualified they are to judge the maturation and risk profile of new tools, processes, and paradigms.
* Comprehensions (map, fold, each) - Operates on entire data structures.  Higher order functions.
* Properties - Values that change over time (time-varying values) bound to an expression or relationship.
* Constructors can't reveal intent
  * Limit to building objects and not to connecting to external resources.
  * Limit to specific behavior so you can guess intent.
  * Only initialize new instances of a class to a rational state.
  * Don't let it invoke an instance method on the instance being creating.  The existence of this method call shows the constructor is doing two things.
* Factories - Create object while hiding exact class instantiated.
* Static creation method - Static method on a class that returns an instance.
* Architecture is concerned with aspects that are hard to change (i.e. the important stuff).  Irreversibility is a core driver of complexity.  Past decisions cannot be reversed and we are constantly working around limitations.  Try to make your decisions reversible when possible.