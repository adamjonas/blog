---
layout: post
title: "Computer Science according to Spencer"
date: 2016-04-27 13:07
comments: true
categories: cs
---

## What is it
  - [cs versus programming](http://stackoverflow.com/questions/1062811/difference-between-a-computer-scientist-and-computer-programmer)

## Big O
  - used to classify algorithms by changes to the inputs
  - O(1) - constant time - kilometers to millimeters
  - O(log n) - opposite of exponential growth, searching binary tree
  - O(n) - iterating over an array
  - O(n log n) - good sorting algorithms
  - O(n^2) - bubble sort (bad algoritms)
  - O(2^n) - the chess board, example doubling something

## Exercises

```java
  1.
  int rectangle_area(height, width) {
    int area = 0; // 1
   
    for(int i = 0; i < height; i++) { // 2*height + 1
      for(int j = 0; j < width; i++) { // 2*height*width + height
        area++; // height*width
      }
    }
   
    return area; // 1
  }

  complexity: 3*height*width + 2*height + 3
  order: O(height*width)


  2.
   
  Constant time. O(1).

  3.
  int halves(n) {
    int count = 0; // 1
   
    if(n % 2 == 1) { // n
      n = n - 1; // n
    }
   
    for(int i = n; i > 1; i = i / 2;) { // n + n + n
      count++; // n
    }
   
    return count; // 1
  }

  Complexity: 6n + 2
  Order O(log n)

  4. 
  int bacteria_generation(days) {
    int total_population = 1; // 1
    int current_population = total_population; // 1
   
    for(int i = 0; i < days; i++) { // 1 + days - 1 + days - 1
      current_population = total_population; // days - 1
   
      for(int j = 0; j < current_population; j++) { 
        total_population++;
      }
    }

    return total_population;
  }

  Order: O(2n)

  5.
  int max(array) {
    int max = array[0]; // 1
   
    for(int i = 1; i < array.length; i++) { //n + 1, [cost of determining array length](http://stackoverflow.com/questions/5872570/is-fixed-array-size-on-or-o1-in-space)
      if(array[i] > max) { // n
        max = array[i]; // potential n
      }
    }
   
    return max; // 1
  }

  [3n + 3 complexity]

  OR

  int max(array) {
    int temp; // 1
   
    // sort the array in ascending order
    for(int i = 0; i < array.length; i++) { // n + 1
      for(int j = 0; j < array.length - 1; j++) { // (n + 1)(n + 1) -> n^2 + 2n + 2
        if( array[j] > array[j+1]) { // potentially n(n + 1) -> n^2 + 2n + 2
          temp = array[j+1]; // 1(n + 1)
          array[j+1] = array[j]; // potentially n(n + 1) -> n^2 + 2
          array[j] = temp; // 1(n + 1)
        }
      }
    }
   
    return array[array.length-1]; // 1
  }

  [3n^2 + 7n + 9 complexity]

  The first is more efficient.

  6. Which algorithm, foo or bar, is faster when when n is 10? 100? 1000?

  int foo(n) {
    int sum = 0
 
    for(int i = 0; i < n + 500; i++) { // 510, 600, 1500 operations
      sum++;
    }
 
    return sum;
  }

  foo(10) = 130,305
  foo(100) = 180,300
  foo(1000) = 1,125,750

  int bar(n) {
    int sum = 0
 
    for(int i = 0; i < n; i++) { // 10
      for(int j = 0; j < n; j++) { // 10
        sum++; // 1
      }
    }
 
    return sum;
  }

  100, 10,000, 1,000,000

  bar is less work at 10, foo for the others
```
