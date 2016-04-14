---
title: Odds & Ends - June 2013
date: 2013-06-01 00:00:00
tags:
- Random
- Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Information-theoretic security - Derives security from informational theory instead of computational complexity.  It cannot be broken even when the adversary has unlimited computing resources as they do not have enough information to break the encryption.
  * Example: Onetime pad.
* Computationally secure - Secure assuming adversary is computationally limited.
  * Example: RSA, Diffie-Hellman
* **API Design**
  * Don't make the return type of method depend on the value of an argument.  It makes it hard to figure out relationships.
  * Avoid flag arguments intended to change the behavior of a method in some way.  The call is more readable if the API has two separate methods.
  * Avoid confusion as to whether a method returns a new object or modifies (mutates) an object in place.  Show intent!
   * Ex: foo.sort() doesn't return value so it must modify in place.
* *When to assert*
  * Defensive programming
  * Run-time checks on program logic (poor man's unit testing)
  * Checking contracts (pre-conditions/post-conditions)
  * Program invariants
  * Check for "won't happen" edge cases
  * Confirm documentation
  * Never use if failure is likely because asserts will get compiled away in release builds.