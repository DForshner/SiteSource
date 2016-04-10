---
title: SortedList vs. SortedDictionary
date: 2013-02-13 00:00:00
tags:
  - Data Structures
---
Both are useful if you need to iterate over elements in sorted order.  As a rule of thumb if you creating it once and not modifying it than a SortedList has a faster construction time and uses less memory than a SortedDictionary.

| Operation | SortedList  | SortedDictionary |
| - | - | - |
| retrieval by key | O(log(n)) | O(log(n)) |
| insert and remove elements | O(n) | O(log(n)) |
| contains key | O(log(n)) | O(log(n)) |

**Sorted Dictionary**
* Implemented as binary search tree for fast lookups while keeping elements in sorted order.

**Sorted List**
* Implemented as two arrays (keys, values) kept in sorted order.
* Faster construction time when being populated in one go.