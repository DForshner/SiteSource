---
title: Introduction to the Theory of Computation Review
date: 2015-02-01 00:00:00
tags:
  - Books
  - Reviews
---
A friend was cleaning our their bookshelf and gave me their spare copy of this book.  If you are interested in turning machines, intractability, P = NP or P != NP this is probably the textbook for you.  Not having a formal compute science background I had a hard time following some sections.

[GoodReads](https://www.goodreads.com/book/show/22077089-introduction-to-the-theory-of-computation-by-sipser?utm_medium=api&amp;utm_source=blog_book)

** Chapter Notes & Quotes **
1. *Regular Languages*
  * Pretend to be an automaton, you receive and input string and must determine whether it is a member of the language the automaton is supposed to recognize.  You see the symbols in the string one by one and after each, you must decide whether the string so far is in the language.
  * <u>Deterministic finite automaton (DFA)</u> - When the machine is in a given state and given the next symbol we know with 100% certainty what the next state will be.
  * <u>Nondeterministic finite automaton (NFA)</u> - When the machine is in a given state and given the next symbol several choices may exist for the next state.
  * After an NFA reads a symbol it splits into multiple copies of itself and follows all possible paths in parallel.  Each copy proceeds as before, and if there are subsequent choices, it splits again.  If the next symbol doesn't appear on any of the arrows exiting this path's state, the copy dies.  If any copy are in the accept state then the input string is considered accepted.
  * NFAs are like a parallel computation where several processes are running concurrently.
  * Every deterministic finite automaton is automatically a nondeterministic finite automaton.
  * Every NFA can be converted into an equivalent DFA.
2. *Context-Free Languages*
  * <u>Pushdown automata</u> - Like a nondeterministic finite automata but have a stack.
3. *The Church-Turing Thesis*
4. *Decidability*
  * Certain problems are algorithmically solvable and others are not.
  * Knowing a problem is unsolvable is useful because you know it must be simplified or altered before you can find a solution.
  * Even some ordinary problems that people want to solve turn out to be computationally unsolvable.
5. *Reducibility*
  * Primary method for proving that a problem is computationally unsolvable.
  * <u>Reduction</u> - Converting one problem to another problem so the solution to the first problem can be used to solve the second.  Ex: Problem of measuring rectangle's area reduced to measuring its width and height.
6. *Advanced Topics in Computability Theory*
  * Any incompressible string has roughly an equal number of 0s and 1s.
7. *Time Complexity*
  * Exponential time algorithms typically arise when we search through a space of solutions (brute-force search).
  * <u>Polynomially Equivalent</u> - The algorithm can simulate another with only a polynomial increase in running time.
  * <u>Polynomially Verifiablity</u> - Verifying the answer can be done in polynomial time.
  * If a polynomial time algorithm exists for an NP-complete problem then all problems in NP would be polynomial time solvable.
  * <u>P</u> = membership can be decided quickly.
  * <u>NP</u> = membership can be verified quickly.
8. *Space Complexity*
9. *Intractability*
10. *Advanced topics in complexity theory*
  * <u>Optimization problems</u> seek to find the best solution among a set of possible solutions.
  * <u>Fermat test</u> provides a probabilistic test for primality.   We call a number <u>pseudoprime</u> if it passes all Fermat tests.
  * Gain evidence of a code's security by showing that the complexity of breaking the code is linked to a the complexity of some other problem for which there is compelling evidence of intractability.
  * <u>Private-Key Cryptosystem</u> - The same key is used for both encryption and decryption.
  * <u>Public-Key Cryptosystem</u> - The private decryption key is different than the public encryption key.