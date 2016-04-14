---
title: Testable JavaScript Presentation
date: 2013-11-11 00:00:00
tags:
- Random
- ECMAScript
- Testing
---
Mark Trostler has a [great presentation](http://www.infoq.com/presentations/javascript-testing) on creating testable JavaScript.

* Create all of the objects the system will ever need at the start (composition root) by building a tree of dependencies.  
   * Create general objects at application start and user/session specific objects at the request start.
  * Use an IOC/DI framework that is configured once at the start to constructor inject the dependencies.
* Cross-cutting concerns - Concerns that affect many areas of your application.  They cut across your application and do not align with modules.
  * Keep orthogonal responsibilities separate.
  * Examples: Logging, validation, auditing, caching, security, profiling, exception handling, retry logic, authentication, authorization, encryption, etc.
  * Use decorator pattern to create wrappers around your business objects that handle the cross-cutting concerns.
  * Use your IOC container to wire up decorator chains.
* Run-time (short-lived) dependancies - Can't pass into constructor because we don't know what they will need until run-time (user has to pick).
  * Pass run-time values into a factory pattern to get dependencies.
  * Factory implementation is created at composition root and injected as a dependency via the constructor.
* Program and test to interfaces.  
  * Interfaces are the API.
  * Don't worry about hiding via closures (revealing module pattern) just use the interfaces.
  * Create many small interfaces that have a single responsibility.

[Presentation Link](http://www.infoq.com/presentations/javascript-testing)