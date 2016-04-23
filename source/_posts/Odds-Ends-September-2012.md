---
title: 'Odds & Ends - September 2012'
date: 2012-09-01 00:00:00
tags:
- Random
- Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* <u>The three virtues of programmers</u> - Hubris, Impatience, and Laziness. [src](http://c2.com/cgi/wiki?LazinessImpatienceHubris)
* <u>The curse of the gifted</u> - A tendency to lean on your natural ability too much, because you have always been rewarded for doing that and self-discipline would take actual work.   [src](https://lwn.net/2000/0824/a/esr-sharing.php3)
* <u>Classic 3 Tier</u> - Presentation / Buisness Logic (rules) / Data Source (queries)
* Typing Types
  * <u>Exact typing</u> - Only ducks are ducks
  * <u>Interface typing</u> - If it says it's a duck, 
  * <u>Duck typing</u> - If it quacks like a duck then we don't care as long as it has the fields/methods we need.
* <u>Mark and Sweep GC</u> - Pause, find all variables in current scope, find all resources that are reachable from variables in scope and free the rest.  AKA "stop the world GC".
* <u>Reference counting GC</u> - Each resource has a count of # of places it's being used (references).  When the code is done with the resource, the count will decrease to zero so it can't be freed. Vulnerable to circular references because counts will never reach zero.
* <u>Dynamic Dispatch</u> - Not knowing what function you will call until runtime.
* <u>Encoding Scheme</u> - Encodes data for a specific purpose (easier to transmit, read, convert to new format).
* More code = Harder to fit in IL cache so more cache evictions and harder to inline.
* More branches = more branch predictions = more branch mispredictions.
* <u>Dependancy Inversion Principle</u> - program to interfaces or abstract base classes.
* <u>System call</u> - Userspace request of a kernel service.
* <u>High Cohesion</u> - Keeping parts of a codebase that are related to each other in single place.
* <u>Low coupling</u> - Separating unrelated parts of the codebase as much as possible.
* <u>Domain Event</u> - Anything that happens that is of interest to a domain expert.
* You call a library, a framework calls you.  A library is a tool ... A framework is a way of life. [src](https://stackoverflow.com/questions/148747/what-is-the-difference-between-a-framework-and-a-library)
* Pure functions > Functions with state > Functions with side effects > Factory functions.
* A member function has a hidden argument called ''this'' that is the specific object we are operating on (the context of the function call).