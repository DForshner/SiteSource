---
title: Unit Testing
date: 2013-02-31 00:00:00
tags:
- Testing
---
Notes from a .Net user group talk on unit testing.

* Ideal Test
  * Automated
  * No complex dependencies
  * Independent of each other.  No sequences!
  * Describes intention.
  * Shows you how the code should be used.
  * Written at the same time or before the code being tested.  Code -> Test -> Code -> Test -> ...
  * No loops, no conditionals
  * Hide any elaborate setup in a base fixture or private method.
  * Avoid complex setup & teardown (code smell!)
* Obvious Benefits
  * Reduce time between code change and bug (test failing).  You want to reduce your feedback loop.
  * Block regression bugs.
  * Fewer bugs in next phase.
* Hidden Benefit: Exerts design pressures on code
  * Avoid the debugger!  If you can't tell what is wrong from the test maybe you need smaller more focused tests!
  * Less coupling
  * Explicit dependencies (elaborate setup is a code smell)
  * Interface use for dependencies
  * Keeping tests focused encourages single responsibility
  * Smaller classes & shorter methods
  * Enables refactoring -> Readable code
  * You can gut your classes and refactor legacy code.
* What to test
  * public methods (use a consumer's point of view)
  * pure functions
* Clean tests
  * Have a standard naming scheme.  Ex: Method_Scenario_Result()
  * Organise into sections Arrange / Act / Assert (TripleA Style)
  * Ideally one assert per test
  * Can you share private setup method over multiple tests?
  * Can you put shared setup in test initialization method or base class?
*  Testing styles
  * State Verification (Good) - Verify state of the object.  Given these inputs, I expect these outputs.
  * Behavior Verification (Bad) - Verify calls between SUT and collaborators using mocks.  Test code is coupled to code under test so it tends to be brittle and break whenever you change the code being tested.
* Isolation
  * Avoid "new"
  * Dependancy injection (Good)
    * Create collaborators outside of SUT and pass in (usually via constructor).
    * Service container IOC usually used to create dependencies in code.
  * Service Location (Bad)
    * Have to setup global state of singleton factory for each test.
    * Injecting the container into a parameter and then using it to new up is still a service locator.
  * Interception Frameworks (Bad)
    * Invasive testing that leads to test code that is tightly coupled to code under test.
    * You lose the benefits of design pressure encouraging interface use and small classes.
    * "Pointy tool" - Use with extreme caution
* Service Containers (IOC container)
  * Controls lifecycle of its objects.  Not just a service locator.
  * Lazy - The first instance is new and the rest are copies.
  * Being forced to write to interfaces is a design pressure that forces decoupling.
* Test Doubles
  * Stub (Good) - Just works with minimal behavior.  Null and real objects with fake data are stubs. 
  * Mock (Meh) - Can set expectations and can tell you when they aren't met.
  * Fake (Meh) - Behaves like the real thing (more or less).  Created by hand.
  * Spy (Bad) - Tells you what happened by recording calls and checking what SUT did.  Very brittle.
* Mocks design pressure
  * Easier to check edge cases
  * Wrap static methods
  * Composed - Pressure away from deep inheritance
  * Uses targeted interfaces
  * Considers requests.  What kind of supported classes are needed?
  * One object many interfaces
  * Start coding anywhere!  Mock out what hasn't been coded yet.
* Mocking pros
  * Can record expected calls
  * Have interface of expected object
  * Can return expected call values.
  * Can verify calls have been made.
  * Fluent API
* Mocking cons
  * Premature composition
  * Premature interface injection