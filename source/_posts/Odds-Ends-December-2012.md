---
title: 'Odds & Ends - December 2012'
date: 2012-12-01 00:00:00
tags:
- Random
- Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* <u>Write in terms of services</u> - independent, concurrent objects behind well-defined, consistent interfaces.
* <u>Eliminate effects between unrelated things</u> - Design components to be self-contained, independent, and have a single well-defined purpose.
* <u>Program close the problem domain</u> - Design and code in your user's language.
* <u>Test state coverage, not code coverage</u> - Identify and test significate program states.  Just testing lines is useless.
* <u>Test early, test Often, test automatically</u> - Tests that run with every build are much more effective than test plans that sit on a shelf.
* <u>Always design for concurrency</u> - Cleaner interfaces with fewer assumptions.
* <u>Put abstractions in code, details in metadata</u> - Program fro the general case, and put specifics outside the compiled code base (config files).
* <u>Keep knowledge in plain text</u> - Won't become obsolete.
* <u>Use blackboards to coordinate workflow</u> - Use to coordinate disparate facts and agents, while maintaining independence and isolation among parts.
* <u>Use a project glossery</u> - Single source for specific terms and vocabulary for a project.
* <u>Find bugs once</u> - Once a human finds a bug, it should be the last time a human finds that bug.  Automated tests should check for it from then on.
* <u>Crash early</u> - A dead program normally does less damage than a corrupt one.
* <u>Organize teams around functionality</u> - Build teams the way you build code (designers + coders + testers + data modelers).
* <u>Design to contracts</u> - Use contracts to document and verify code does no more and no less than it claims.
* <u>Don't use return values for errors</u> - Eventually a component will ignore a value and an error will silently be ignored.  Dead software doesn't lie.