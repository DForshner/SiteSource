---
title: Functional vs. Imperative Environments
date: 2013-02-23 00:00:00
tags:
- Functional Programming
---
What is the primary building block of your programs?

* *Functional*
  * Mostly functional with imperative where needed.  Managing what state is intrinsic, necessary, and appropriate.
  * The Basic building block is a referentially transparent function.  A function which returns the same output per given input every time.
  * The environment does not affect the output of a  referentially transparent function so we can reason about it independently.

* *Imperative*
  * The Basic building block is a stateful action (object in OO).
  * Without environmental knowledge it's impossible to reason about and test.
  * You must be able to control the environment in which the action occurs to know if it's being done right.
  * The environment is an *implicit* parameter on the action.  Making the environment explicit makes it referentially transparent.