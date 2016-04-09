---
title: Odds & Ends - September 2014
date: 2014-09-01 00:00:00
tags:
  - Random
  - Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Errors are values.
* DRY - Is having a single source of truth not avoiding copying and pasting code.
* When you cross a service boundary things that appear to be the same may have a different context and different data store.  Avoid sharing code between boundaries that have different contexts (Microservices).
* Repository Pattern - Layer that exists between business logic and data store.  Isolates your code that interacts with your data store in one place.
* Decorator Pattern - Enabling a chain of behavior determined by composition not inheritance.
* A bad test breaks in response to any change in production code without verifying correct behavior.
* Map - Go over a large data set without mutating it.
* Reduce - Aggregate or merge results
* Scope - Where variables and functions are accessible and in what context they are being executed.
* Closures - Expressions (usually functions) that work with variables set within a certain context.  An inner function referring to local variables of its outer function.
{% codeblock lang:js %}
function add(x) {
  return function(y) {
    return x + y; // When returned this closes over the value of x = 5
  }
}
var add5 = add(5);
console.log(add5(3)); // 8
{% endcodeblock %}
* Enumerable - Pull-based.  The consumer pulls from the producer.
* Observable - Push-based.  The producer pushes new values to the consumer.
* Functional Reactive Programming
  * Properties - Values that change over time.  Every property is a function f(t) that gives a value at a given moment in time.
  * Functional - Compose together functions to create complex behavior.  Functions can have time dependant relationships.
  * Immutable - Values are something that happened in the past so they need not change.
  * Event streams - Events at a particular point in time.  Capture event changes in a discrete manner.  Operators (map/filter/reduce) create new streams out of old streams (no mutation).
  * Switching - Change the system in response to events.  A stream of streams (meta-stream).  Ex: stream URLs, map to requests, return responses in future stream of promises.
* 68-95-99.7 Rule - 68% of values at one standard deviation, 95% at two, and 99.7% of values at three.
* Fit indexes in RAM if possible.  Index on the hash of a string instead of the string itself.
* Use cache as write-back to do batched database writes to the back-end.
* Use locking to make sure that when the cache expires the database doesn't get slammed with multiple copies of the same query.
* You can decouple a sender and receiver with the command pattern and observer pattern but to decouple them in time you will want to use an event queue.
* Keep data structures flat and linear (array > linked list).  Every pointer you have to chase to find data adds a likely cache miss while flat arrays can be pre-fetched by the memory system.
  * Adding/Removing values from the middle of std::vector is faster than std::list if the elements are POD types and no bigger than 64 bytes (one cache line).  Lists have too many cache misses.
  * For larger POD types, non-POD types, or if you already have a pointer into the list then std::list will win.