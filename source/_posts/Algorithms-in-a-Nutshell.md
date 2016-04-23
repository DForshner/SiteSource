---
title: Algorithms in a Nutshell Review
date: 2015-06-01 00:00:00
tags:
  - Books
  - Reviews
  - Algorithms
---
For a desktop reference book, this is a surprisingly fun read.  It gives a broad overview of different algorithms focusing on when you would want to use them and any tradeoffs compared to other solutions.  The book's small size is convenient if you want something to read on the plane.  It also has one of the best chapters on network flow problems I've come across.

[Goodreads](https://www.goodreads.com/book/show/4229486-algorithms-in-a-nutshell?utm_medium=api&amp;utm_source=blog_book)

**Chapter Quotes & Nodes**
* *Preface*
1. *Algorithms Matter*
  * Start with the big picture: understand the problem, identify potential causes, and then dig into the details.  If you decide to try to solve the problem because you *think* you know the cause, you may solve the wrong problem.
  * Various algorithms have "sweet spots" in which their performance has no equal and designers can take advantage of specific information about the problem to improve performance.
2. *The Mathematics of Algorithms*
  * <u>Logarithmic algorithms</u> are extremely efficient because they rapidly converge on a solution.  In general, these algorithms succeed because they reduce the size of the problem by about half each time.
  * Not every operation can be optimized; in fact, optimizing one operation may degrade the execution of another operation.
3. *Patterns and Domains*
  * <u>Patterns</u> are a great way to communicate precisely and concisely well-formed concepts.
  * A pattern is not a template where you simply fill in the blanks *(except the template method ☺)*.   It is an approach, or a plan, for solving a particular class of problems.
  * A test suite is composed of a set of *k* individual trials (typically *k*≥10).  The best and worse performers are discarded as outliers, the remaining *k*-2 trials are aggregated, and the average and standard deviations are computed.
  * <u>Domains</u> are application areas that share common traits.  Each domain has its own vocabulary that provides a language to describe the domain.
  * a <u>floating-point number</u> is a finite representation that is designed to approximate a real number whose representation may be infinite.
  * The most common way of describing floating-point error is to use the term <u>relative error</u>, which computes the ratio of the absolute error (desired - approximation) with the desired value.
  * The stack grows "downward" and the heap grows upward ... if the stack grows too large, a program crashes because the memory for the individual stack frames will overwrite memory that should be safely protected in the heap.
  * Dynamic types languages are often interpreted and variable values are known only at runtime, and therefore cannot be checked statically.
4. *Sorting Algorithms*
  * <u>Pointer-based storage</u> - A contiguous array of information contains pointers to the actual information rather than storing the information itself.
  * <u>Value-based storage</u> - Packs a collection of *n* elements into record blocks of a fixed size.
  * Information is written to secondary storage usually a value-based contiguous collection of bytes.
  * <u>total ordering</u> - For any two elements *p* and *q* in a collection, exactly one of the following three predicates is true: *p=q, p<q, p>q*.
  * No algorithm that sorts by comparing elements can do better than O(*n* log *n*) performance in the average or worst case.
  * <u>Insertion sort</u>
    * Use when you have a small number of elements to sort or the elements in the initial collection are already "nearly sorted".
    * Inefficient for value-based data because of the amount of memory that must be shifted to make room for a new value.
  * <u>Quick Sort</u>
    * Use when you want a good average-case result*
    * Further computation to identify the proper pivot (beyond median-of-3/5) is rarely able to provide beneficial results because of the incurred costs.
  * <u>Counting Sort</u>
    * Can only be used in limited situations because of the constraints that the elements in the array being sorted are drawn from a limited set of *k* elements.
  * <u>Bucket Sort</u>
    * Use when the elements are drawn from a dense universe.
    * The fastest sort when the elements to be sorted can be uniformly partitioned using a fast hashing function.
    * Reduces its processing costs at the expense of extra space.
    * Data must be uniformly distributed, so it's evenly partitioned between buckets and an ordered hash function must be used so all elements in bucket b<sub>i</sub> are lexicographically smaller than all elements in bucket b<sub>i+1</sub>.
    * Once all the elements are sorted into buckets the values can be extracted in sorted order using insertion sort on each bucket.
5. *Searching*
  * <u>Sequential Search</u>
    * If the predominant result of a sequential search is false, you may want to consider a different search algorithm, even when the collection is relatively small.
    * Move element up/to the front on a successful sequential search to exploit an increased likelihood that the item will be searched for again.  Like Most-Recently-Used (MRU).
  *  <u>Binary Search</u>
    * Using secondary storage, the time required to search for an element is dominated by the costs to access the storage.
    * Can incrementally search for a word as it is being typed.
  * <u>Hash-based Search</u>
    * Use a *hash function* to transform one or more characteristics of the searched-for item into a value that is used to index into an indexed hash table.
    * A poorly designed hash function will leave many of the slots in hash table empty (wasting space) and there will be many collisions where keys map to the same slot (bad performance).
    * Java's .hashCode() tries to be efficient and caches the value of the computed hash to avoid recomputation.
    * <u>Perfect hash function</u> guarantees no collisions for a specific set of keys.
    * The size of A is typically chosen to be a prime number but we can use any number when we are not using open addressing.
    * As the load factor goes down, the average length of each slot's linked list also goes down improving performance.
    * Open addressing reduces storage overhead, such as pointers to the next element in a list of collisions.
    * <u>Perfect hashing<u/> uses a standard hash function to index into a primary table, A.  Each slot, A[*i*], points to a smaller secondary hash table, S<sub>i</sub>, that has an associated hash function h<sub>i</sub>.  The selection of appropriate hash functions guarantees that there are no collisions in the secondary tables giving O(1) performance.
  * <u>Binary Tree Search</u>
    * Prefer over arrays when the underlying data in the search set changes (lots of inserts/deletes) frequently.
    * Prefer over hash-based solution when the set size is unknown, the set is highly dynamic (lots of inserts/deletes), and you want to traverse the data in ascending/descending order.
    * B-tree variation that minimizes the number of disk accesses.
6. *Graph Algorithms*
  * <u>Adjacency matrices</u>
    * Fixed upper limit beyond which no matrix can be constructed with the available memory.
    * Unsuitable when there are multiple relationships between a pair of elements.  We end up storing a list at each matrix element which is nearly an adjacently list.
  * <u>Adjacently list</u>
    * Vertices could be stored in sorted order to enable rapid failure when searching if an edge exists.
  * <u>Breadth First Search</u>
    * Guaranteed to find the shortest path
    * Stores "to be visited" vertices so there may be a non-trivial amount of storage space required for very large graphs.
  * <u>Dijkstra's algorithm</u> - Single source shortest path
    * Runs forever if a negative edge weight exists.
    * Uses priority queue to keep track of the vertice with the shortest distance for the current path.
  * The <u>most reliable path</u> is the path with the greatest value when each step on the path's probability of success is multiplied together.  Convert to the log probability of success so they can be added instead.
  * <u>Bellman-Ford</u> - Single source shortest path
    * Avoid using for dense graphs or it degenerates to O(V<sup>3</sup>)
    * Works with negative edge weights as long as no negative cycle exists.
    * Detect negative edge weight by executing primary loop one extra time and looking for changes in values.
 * <u>Floyd-Warshall</u> - All pairs shortest paths
    * To detect negative edge weights scan the diagonal (i==j) at the end and any -ve values indicate that a -ve cycle exists.
    * Only need to keep track of matrix of subproblems because we are concerned with the total distance, not the path that involves the fewest number of vertices.
  * <u>Prim's Algorithm</u> - Minimum spanning tree
    * Intuition is that the edge(*u,v*) with the lowest weight between the current minimum subgraph and the remaining elements must belong to the minimum spanning tree.
7. *Path Finding in AI*
  * Construct a <u>Game tree</u> to find a path from the current game state to some future game state that ensures victory or a draw.
  * Search tree can be greatly reduced by detecting and eliminating identical states that may simply be rotated or reflected.
  * <u>A* Search</u>
    * Variation of Dijkstra's algorithm that directs search with heuristic information when approximate answers are acceptable.
8. *Network Flow Algorithms*
  * You could apply linear programming to network flow problems but specialized algorithms with outperform it by several orders of magnitude.
9. *Computational Geometry*
10. *When All Else Fails*
11. *Epilogue*
  * <u>Know your data</u> - without specific knowledge of your data, it is only possible to recommend algorithms in the most general way.
  * <u>Decompose the problem into smaller problems</u>
  * <u>Choose the right data structure</u>
  * <u>Add storage to increase performance</u> - Many algorithms are optimizied by storing information that reflects the results of past computations.
  * <u>If not solution is evident, construct a search</u> - Convert the problem into a search over a very large graph.
  * <u>If no solution is evident, reduce your problem to another problem that has a solution</u>
  * <u>Writing algorithms is hard -- testing algorithms is harder</u>