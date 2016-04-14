---
title: Coverage Is Not Strongly Correlated With Test Suite Effectiveness
date: 2015-12-01 18:31:15
tags:
- Empirical Studies
- Software Development Practices
---
No great surprises here.  I think people's time is better spent testing the common paths through their code and capturing important functional requirements.  I found the ideas in [Functional Core, Imperative Shell](https://www.destroyallsoftware.com/screencasts/catalog/functional-core-imperative-shell) and [There Are Only Two Roles of Code](http://simpleprogrammer.com/2012/10/21/there-are-only-two-roles-of-code/) were helpful in figuring out how to spend my test writing budget.

> We found that there is a low to moderate correlation between coverage and effectiveness when the number of tests in the suite is controlled for. In addition, we found that stronger forms of coverage do not provide greater insight into the effectiveness of the suite. Our results suggest that coverage, while useful for identifying under-tested parts of a program, should not be used as a quality target because it is not a good indicator of test suite effectiveness.

[Study](http://www.linozemtseva.com/research/2014/icse/coverage/)