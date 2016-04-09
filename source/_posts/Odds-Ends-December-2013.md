---
title: Odds & Ends - December 2013
date: 2012-12-01 00:00:00
tags:
  - Random
  - Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Objects on the stack are much more likely to be in the cache than arbitrary heap lines.
* Closure - A function closes over the area it is defined in so it can access variables that are not in its parameter list.
* Anonymous functions (ECMAScript) - Functions that do not have a name associated with them.  Used to manage the scope of objects, modules, and namespaces.
* Control Technique (testing) - A method by which you control your test by factoring out the portion of your program which has side effects outside the scope of control of the code you intend to test.  You need to control the side effects when testing.  Example: stubbing external dependencies.
* Mutable - Can change contents without changing identity.
* Immutable - Cannot change contents without changing identity.  Values are unchangeable once they are created.
* Good C++: Avoid mutation, avoid side effects, don't use raw loops, avoid class hierarchy and inheritance (basically be more functional).
  * The worse case is side effects with global scope.
  * Same principal apply to fields, properties, parameters, and variables.  Don't mutate unless you have a good reason.
  * Increase reliability by removing side effects so the code is easier to compose and integrate.  Side-effect free code works in all environments!