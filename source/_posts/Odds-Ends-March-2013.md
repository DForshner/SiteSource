---
title: Odds & Ends - March 2013
date: 2013-03-01 00:00:00
tags:
- Random
- Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Lines of code represent an expenditure, not an accomplishment.
* In large systems interfaces matter.  There is a danger that people will start playing fast and loose with interfaces by passing around nested maps and lists and then expecting the other side to understand the encoding.  Be explicit!
* In ECMAScript one should use an object not an array for a set of key/value pairs.  If you use an array all you are getting is the extra baggage of an array's methods what won't work.
* Functions without side-effects are pure data transformations.  Something comes in and something comes out.  The results are predictable.  Functions that rely on side effects or additional inputs (databases) are complicated.
* Doing proper single responsibility principal often results in a class with one method ... aka a function.
* *Collections vs. Streams*
  * Collection - (eager, a full warehouse) data structure which holds all values in memory.  Each element must be computed before it can be added.
    * Values are spread out in space (computer memory) (which all exist at one point in time).
  * Streams - (lazy, just in time) data structure where elements are computed on demand.  Liked producer/consumer or lazy version of a collection.
    * Values are spread out in time (which repeatedly appear at the same point.
* User interaction -> data change -> view render
  * Render on the data change, not the user interaction!  The model is a single source of truth!
* Layers Pattern
  1. UI - Views and models
  2. Controller - Application composition
  3. Service Layer - Business composition and coordination.
  3. Repositories (data access), Calculators (algorithms), and Query Objects (helpers).
* *C# Anonymous functions*
  * Can declare a variable with the same name as static/instance variable of the outer class.
  * Can access static/instance variables of enclosing class
  * Cannot access any ref/out variables inside an anonymous method.
  * Cannot declare a variable with the same name as a variable in the outer method.
* *Closure* - Is not a concrete element or synonym for an anonymous function or lambda expression!  It's a behavior that allows us to declare an anonymous function that refers to local variables outside said function and not worry about that variables lifespan.
* *Abstract Base Class vs. Interface*
  * Abstract Base Class - "Is a"
    * Ex: Dog is a mammal
    * This is core functionality of this class
    * Adds constraint that there can be only one base class
  * Interface - "acts like", "is verb"
    * Ex: Book is IWritable, Dog acts like an IEater
    * This is trait of an object, not necessarily its core functionality
* The key principal of HTTP is that resources are sent in the message body, using content negotiation to specify the representation of the resource.
* In C++ ptr[3] means *(ptr + 3) which can be written as *(3 + ptr) or 3[ptr] :-)
* To reduce stalls due to the GC we circumvented it by replacing all heap allocations with the use of pre-allocated arrays of values types, effectively implementing manual memory management inside a managed language.