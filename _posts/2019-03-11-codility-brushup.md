---
layout: post
title:  "[Codility] Lessons"
date:   2019-03-11 23:00:00
categories: Algorithm
tags: Algorithm Codility
author: Hailey Gu
---

* content
{:toc}

## Lesson 1 : Iterations
[Link](https://codility.com/media/train/Iterations.pdf){:target="_blank"}

### 1.1. For loops
### 1.2. While loops
### 1.3. Looping over collections of values

## Lesson 2 : Arrays
[Link](https://codility.com/media/train/0-Arrays.pdf){:target="_blank"}

### 2.1. Creating an array
### 2.2. Accessing array values
### 2.3. Modifying array values
### 2.4. Iterating over an array
### 2.5. Basic array operations



## Lesson 3 : Time Complexity

[Link](https://codility.com/media/train/1-TimeComplexity.pdf){:target="_blank"}

### 3.1. Comparison of different time complexities
3.2: Constant time — O(1).
3.3: Logarithmic time — O(log n).
3.4: Linear time — O(n).
3.5: Quadratic time — O(n2).
3.6: Linear time — O(n + m).
Exponential and factorial time
factorial time O(n!) and exponential time O(2n).

### 3.2. Time limit
Nowadays, an average computer can perform 10^8 operations in less than a second.
The time limit set for online tests is usually from 1 to 10 seconds.
This is usually a great convenience because we can look for a solution that works in a specific complexity instead of worrying about a faster solution.
For example, if:
• n <= 1 000 000, the expected time complexity is O(n) or O(n log n),
• n <= 10 000, the expected time complexity is O(n2),
• n <= 500, the expected time complexity is O(n3).
Of course, these limits are not precise. They are just approximations, and will vary depending
on the specific task.

### 3.3. Space complexity





## Lesson 4 : Counting Elements

[Link](https://codility.com/media/train/2-CountingElements.pdf){:target="_blank"}





## Lesson 5 : Prefix Sums

[Link](https://codility.com/media/train/3-PrefixSums.pdf){:target="_blank"}
5.1: Counting prefix sums — O(n).
5.2: Total of one slice — O(1)





## Lesson 6 : Sorting
[Link](https://codility.com/media/train/4-Sorting.pdf){:target="_blank"}

### 6.1: Selection sort — O(n2).

### 6.2: Counting sort — O(n + k)

### 6.3. Merge sort
The idea: Divide the unsorted array into two halves, sort each half separately and then just
merge them. After the split, each part is halved again.
We repeat this algorithm until we end up with individual elements, which are sorted by
definition. The merging of two sorted arrays consisting of k elements takes O(k) time; just
repeatedly choose the lower of the first elements of the two merged parts.
The length of the array is halved on each iteration. In this way, we get consecutive levels
with 1, 2, 4, 8, . . . slices. For each level, the merging of the all consecutive pairs of slices requires
O(n) time. The number of levels is O(log n), so the total time complexity is O(n log n) (read
more at http://en.wikipedia.org/wiki/Merge_sort).

### 6.4. Sorting functions
6.3: Built-in sort — O(n log n)

## Lesson 7 : Stacks and Queues

[Link](https://codility.com/media/train/5-Stacks.pdf){:target="_blank"}

### 7.1. Stack
7.1: Push / pop function — O(1).

### 7.2. Queue
7.2: Push / pop / size / empty function — O(1).

## Lesson 8 : Leader
[Link](https://codility.com/media/train/6-Leader.pdf){:target="_blank"}

### 8.1. Solution with O(n2) time complexity
### 8.2. Solution with O(n log n) time complexity
### 8.3. Solution with O(n) time complexity

## Lesson 9 : Maximum slice problem

[Link](https://codility.com/media/train/7-MaxSlice.pdf){:target="_blank"}

### 9.1. Solution with O(n3) time complexity
### 9.2. Solution with O(n2) time complexity
### 9.3. Solution with O(n) time complexity

## Lesson 10 : Prime and composite numbers

[Link](https://codility.com/media/train/8-PrimeNumbers.pdf){:target="_blank"}

### 10.1. Counting divisors
### 10.2. Primality test
### 10.3. Exercises

## Lesson 11 : Sieve of Eratosthenes

[Link](https://codility.com/media/train/9-Sieve.pdf){:target="_blank"}

### 11.1. Factorization

## Lesson 12 : Euclidean algorithm

[Link](https://codility.com/media/train/Iterations.pdf){:target="_blank"}

### 12.1. Euclidean algorithm by subtraction
### 12.2. Euclidean algorithm by division
### 12.3. Binary Euclidean algorithm
### 12.4. Least common multiple

## Lesson 13 : Fibonacci numbers

[Link](https://codility.com/media/train/11-Fibonacci.pdf){:target="_blank"}

 13.1: Finding Fibonacci numbers recursively.
 13.2: Finding Fibonacci numbers dynamically.
###13.1. Faster algorithms for Fibonacci numbers

## Lesson 14 : Binary search algorithm

[Link](https://codility.com/media/train/12-BinarySearch.pdf){:target="_blank"}

### 14.1. Intuition
### 14.2. Implementation
14.1: Binary search in O(log n).


### 14.3. Binary search on the result
### 14.4. Exercise

14.2: Binary search in O(log n).
14.3: Greedily check in O(n).

## Lesson 15 : Caterpillar method

[Link](https://codility.com/media/train/13-CaterpillarMethod.pdf){:target="_blank"}

### 15.1. Usage example
15.1: Caterpillar in O(n) time complexity.


### 15.2. Exercise
15.2: The number of triangles in O(n2).


## Lesson 16 : Greedy algorithms

[Link](https://codility.com/media/train/14-GreedyAlgorithms.pdf){:target="_blank"}

### 16.1. The Coin Changing problem
### 16.2. Proving correctness
### 16.3. Exercise
16.2: Canoeist in O(n) solution.
16.3: Canoeist in O(n) solution.



## Lesson 17 : Dynamic programming

[Link](https://codility.com/media/train/15-DynamicProgramming.pdf){:target="_blank"}

### 17.1. The Coin Changing problem

17.1: The dynamic algorithm for finding change.
17.2: The dynamic algorithm for finding change with optimized memory.


### 17.2. Exercise
17.3: Solution in time complexity O(n · k) and space complexity O(k).


Enjoy it!!!
