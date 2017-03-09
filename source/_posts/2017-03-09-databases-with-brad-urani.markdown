---
layout: post
title: "Databases with Brad Urani"
date: 2017-03-09 08:42
comments: true
categories: databases
---

Brad Urani @confoo

### ACID ->
atomicity: all or nothing. If one of 3 writes fails it rolls it back
Consistency:
Isolation:
Durability: DB survives

  - no-sql aren't faster because of algorithms, they are faster because they did it because they did away with the guarantees

google spanner - reliable network because it's with in their own fiber optics

### SQL is declarative language
 - don't give the computer exact instructions. Giving the comp a rough outline and the DB.


### index is a tree
  - binary tree
  - doubled the size of the tree but only increased by 33%  - O(log n)
  - balanced tree -> rebalancing in order to make it as fast as possible
  - why not add indexes to everything
    - disk space and inserts

### Quick sort
  - fastest, but not that fast for records on disk

### Merge sort
  - divide and conquor algorithm
  - O(n log n)

### Joins:
  - nested loop JOINs - O(n^2)

### Hash Join -> O(n)
  - Hash tables -> values are pointers because they are in linked lists
    - building the hash table from the beginning is expensive.
    - MD5? go with a bit key that doesn't guarantee no collisions
  - good for lots of duplicates

### Merge Join -> O(m log n)
  - lists are already sorted.

### Query plans
  - explain or explain analyze -> can tune the query to be faster

### natural selection process for finding the best query plan
  - like genetic selection
  - doing all this in milliseconds
  - Evaluation -> selection -> crossover -> mutation

### Caching
  - cache warmup period
  - Least recently used (LRU) in memory cache
