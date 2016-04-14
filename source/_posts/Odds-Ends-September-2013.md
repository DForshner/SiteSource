---
title: Odds & Ends - September 2013
date: 2013-08-01 00:00:00
tags:
- Random
- Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* An entity is identified by an ID whereas a value object is identified by its value.
* Enumerators flatten a collection so that the members can be accessed sequentially.
* The heart of OO is the encapsulation of data and members in a coherent class/object.
  * A class should fulfill the contact implied by its interface(s) so the caller need not know how it's implemented.
  * Objects communicate by sending each other messages through method calls.
* Critique code, not people.  Teach people they are not their code.
* Null return values should be avoided.  It leads to null guard clauses at the top of every method which clutters the code.
* String and int make good hashmap keys because they are immutable.  If the key could be altered in a way the changed its hashcode we wouldn't be able to find the object in the hashmap anymore!
* Building software is the process of finding solutions to complex problems, which involves perspective (understanding the problem) and heuristics (a means of solving it).  Experts tend to have similar viewpoints while novices bring new ways of thinking.  
* Give novices projects that involve:
  * Autonomy - Something to be responsible for.  Don't just leave novices alone in the corner to "figure it out".
  * Mastery - People are incentivized by a challenge.
  * Purpose - a meaningful part of the project.  Not just a pile of IE6 bugs to slog through.
* Cache Lines - Get the byte you asked for and the rest of the 64-byte block for free.
* Async/Await gives the illusion of sequential behavior.  Await marks the position where a task should resume.  It may not resume on the same thread of execution which causes GUI to blow up.