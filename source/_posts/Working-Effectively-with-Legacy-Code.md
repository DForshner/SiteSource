---
title: Working Effectively with Legacy Code Review
date: 2015-01-01 00:00:00
tags:
- Books
- Review
- Testing
---
This book is about bringing your existing code under test so you can make changes without losing your mind.  Most books present a kind of clean room/fait accompli image of testing.  This book shows you how to crawl through the trenches struggling for some small incremental victory against the hordes of complexity and bit rot that surround your position.  I guess what I'm trying to say is you should buy this book.

[Goodreads](https://www.goodreads.com/book/show/44919.Working_Effectively_with_Legacy_Code?utm_medium=api&utm_source=blog_book)

**Chapter Notes**
* *Forward*
  * Requirements change.  Designs that cannot tolerate changing requirements are poor designs.
  * Turn systems that gradually degrade into systems that gradually improve.
* *Preface*
  * With tests we can change the behavior of our code quickly and verifiably.  Without them, we really don't know if our code is getting better for worse.
  * Don't be alarmed if some of the steps you take to cut out areas to start growing good code look ugly.  This is surgery.
1. *Changing Software*
  * Behavior is the most important thing about software.  It is what users depend on.
  * Programmers don't attempt to improve a design because it is easy to lose behavior or create bad behavior in the process of doing it.
  * Make a series of small structural modifications, supported by tests to make the code easier to change.
2. *Working with Feeback*
  * Changes in a system can be made in two primary ways: Edit and Pray or Cover and Modify.
  * <u>Software Vise</u> - The behavior or the code is fixed in place.  When we make changes, we can know that we are changing only one piece of behavior at a time.
  * Good tests are fast and allow you to localized problems quickly.
3. *Sensing and Separation*
4. *The Seam Model*
  * How often are small pieces reused independently?  Not very often.  Reuse is tough.
  * <u>Seam</u> - A place in the program where you alter behavior without editing that place.
5. *Tools*
6. *I Don't Have Much Time and I Have to Change It*
  * Navigating through code that contains decorators that decorate other decorators is a lot like peeling away the layers of an onion.  It is necessary work, but it does make your eyes water.
7. *It Takes Forever to Make a Change*
  * Interfaces typically change far less than the code that implements them.  It's better to depend on interfaces or abstract classes than on volatile concrete classes.
8. *How Do I Add a Feature*
  * <u>Normalized Hierarchy</u> - No class has more than one implementation of a method.  None of the derived classes have a method that overrides a concrete method it inherited from a superclass.
9. *I Can't Get This Class into a Test Harness*
  * Don't pass null in production code unless you have no other choice.  You will end up with checks for null all over the place and a lot of conditional code that you used to figure out what you have and what you can do with it.
10. *I Can't Run This Method in a Test Harness*
  * If we need to test a private method it probably means our class is going too much.  Private methods can be moved to a new class where they can be public.
  * <u>Command/Query Separation</u> - A method should be a command (modifies state and returns nothing) or a query (returns a value and doesn't modify state).  If something is a query we shouldn't have to look at its body to know we can call it several times in a row without causing some side effect.
11. *I Need to Make a Change.  What Methods Should I Test?*
  * Effects propagate in three ways
    * Return values that are used by the caller.
    * Modification of objects passed as parameters.
    * Modification of static or global data.
  * Programming gets easier as we narrow effects in a program.  We need to know less to understand the code.
  * Encapsulation helps us reason about our code.  There are fewer paths to follow as you try to understand it.
12. *I Need to Make Many Changes In One Area*
13. *I Need to Make a Change, but I Don't Know What Tests to Write*
  * <u>Characterization test<u/> - Characterizes the current behavior of a piece of code.
  * Use tests as a medium of communication.  People can look at them and get a sense of what they can and cannot expect from a method.  Living documentation.
  * All legacy code has bugs, usually in direct proportion to how little it is understood.
14. *Dependencies on Libraries Are Killing Me*
15. *My Application Is All API Calls*
  * Code grows and grows, and things aren't quite as simple anymore.  Over time, we might still be able to see areas of code that don't touch the API, but they are embedded in a patchwork of untestable code.
  * Nearly every system has core logic that can be peeled away from API calls.
  * <u>Skin and Wrap the API</u> - Make an interface that mirrors the API and then create wrappers around the API.  The wrappers will delegate to the API code but we can test using our interface.
  * <u>Responsibility-Based Extraction</u> - Identify responsibilities in the code and start extracting methods from them.
16. *I Don't Understand the Code Well Enough to Change It*
  * <u>Sketch refactoring</u> - Extract methods, move variables, refactor it whatever way you want to get a better understanding of it and then throw your changes away.
17. *My Application Has No Structure*
  * There is something mesmerizing about large chunks of procedural code: They seem to beg for more.
18. *My Test Code Is in the Way*
  * If you choose to separate test and production code, make sure it is for a good reason as it makes project navigation painful.
19. *My Project Is Not Object Oriented.  How Do I Make Safe Changes?*
20. *This Class is Too Big and I Don't Want It to Get Any Bigger*
  * When a class has 20 or so responsibilities, changes are, you'll have an incredible number of reasons to change it.
  * If there are too many private methods there may be another class inside that's dying to get out.
  * Are there sections of code that could change in the future (ex: Db connection)?
  * Are certain instance variables used by some methods and not others?
  * Can you describe the responsibility of this class in once sentence?
  * We care whether a class really does all the stuff in its interface or if it just delegates to a couple of other classes.  Facade classes which are a front end for a bunch of little classes don't violate SRP.
  * <u>Interface Segregation Principle</u> - When clients do not use all of the methods of a class try grouping the methods client used together into separate interfaces.  We can then start to move code from the big class to a new class that uses the original class.
21. *I'm Changing the Same Code All Over the Place*
  * When two methods look roughly the same, extract the differences to other methods.  When you do that, you can often make them exactly the same and get rid of one.
22. *I Need to Change a Monster Method and I Can't Write Tests For It*
  * It pays to make a series of changes using only a refactoring tool.  This gives you a clean separation between changes that known to be safe and changes that aren't.
  * When you have a conditional extract the condition and the body to two different methods to emphasize the logic.  Fixes the arrow head anti-pattern.
  *  When you have a conditional extract the condition and the body into the same method to emphasize common sequences of operations.  Fixes bulleted methods.
23. How Do I Know I'm Not Breaking Anything?
  * <u>Leaning on the compiler</u> - Taking advantage of type checking and using it to identify changes you need to make.
24. We Feel Overwhelmed.  It Isn't Going to Get Any Better*
25. Dependency-Breaking Techniques
  * Move towards interfaces that communicate responsibilities rather than implementation details.  This makes code easier to read and maintain.