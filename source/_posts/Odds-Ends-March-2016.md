---
title: Odds & Ends - March 2016
date: 2016-03-01 00:00:00
tags:
- Random
- Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Data center power = 50% for Store/Retrieve/Transmit and 50% for cooling.
* <u>Social Signal</u> - A Like, +1, etc.
* Mixin = Small, specific, orthogonal
* This worked *for me*! The *for me* is silent.
* The standard you tolerate is the standard you accept.
* Localize related concerns.  Components that frequency interact should be kept close!  Avoid cross-network calls.  Chatty (fine grained) vs. Chunky (course-grained).
* Service vs. Libary - Service is updated at the same time as the client while a library can be updated independently.
* Don't start with generic - Concentrate on your features and specific use cases first.  Later you can think about a generic solution if it satisfies the rule of three.
* <u>Ad-hoc Analytics</u> - Issues dynamic queries on the data store and system responds.  Used to explore the dataset.
* <u>Streaming Analytics</u> - Issue static queries and system processes them as time ordered data comes in without storing.  Examples are windows, joins, counting, temporal event sequence detection.
* Store an immutable sequence of events.  Model data transformations as a series of materialized stages from the original input.  Can debug and test each state independently.  When code changes, you can re-run to get new output (Reprocessing/Regenerating output).
* <u>Time to first byte</u> - How to measure startup times
* <u>Environmental Viscosity</u> - When the dev environment is slow devs are tempted to make minimal changes, so they don't have to wait. Do what's easy instead of doing what's right.
* Are the portions of the code with highest fan-in (used in the most places) exercised by automated tests?
* Are there volatile parts of the codebase that get changed with every commit?
* <u>Testing Pyramid</u> - 70% unit tests / 20% integration tests / 10% end to end tests.
* 1/2 the world is 20000km and a ping is there and back (40000km) at the speed of light so 133ms minimum.
* Constructor injected dependencies and method arguments are both input arguments applied at different times in the application lifecycle.
* Represent side effects as *intents to perform actions* transparent objects that expose the details of side effects without actually performing them.
* It is impossible to completely decouple a code base without damaging coherence.  It is impossible to have fully cohesive code without introducing coupling.
* <u>Domain Events</u> - Bones of a domain model.  Stable because they only change if the business changes.  Many choices for how to implement behavior and represent in data.