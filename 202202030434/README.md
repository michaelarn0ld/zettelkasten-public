# Technical Interview Guidelines: I

## Core Data Structures, Algorithms, Concepts

|   Data Structures         |   Algorithms           |  Concepts
|   -                       |   -                    |  -
|   Linked Lists            |   Breadth First Search |  Bit Manipulation
|   Trees, Tries, Graphs    |   Depth First Search   |  Memory (Stack vs Heap)
|   Stacks & Queues         |   Binary Search        |  Recursion
|   Heaps                   |   Merge Sort           |  DP
|   Vectors                 |   Quick Sort           |  Big O Time & Space
|   Hash Tables             |                        |

## Walking Through a Problem
1. Listen closely to all the details; you probably need everything for an optimal
solution
1. Come up with an example; most examples are too small or are special cases. 
Make sure you have a good example and then draw it
1. Brute force ASAP; state a naive algorithm and its runtime, then optimize from
there
1. Optimize your solution with BUD or try some of these ideas
    * Look for any unused info
    * Solve it manually on an example, then reverse engineer your thought process
    * Make a Time/Space tradeoff; hash tables are handy here
1. Now that you have an optimal solution, walk through your approach in detail;
thouroughly understand your solution before you code it
1. Implement your algorithm; write beautiful and modular code
1. Test in this order:
    * Conceptual test
    * Unusual or non-standard code
    * Hot spots like arithmetic and null nodes
    * Small test cases
    * Special cases (empty array, zeroes, null nodes, etc)

## Optimize & Solve Technique #1: Look for BUD

#### Bottlenecks
These are parts of the code that slow the overall runtime. Say for example
we are looking in an array for two elements that sum to an target k. A naive
approach would be to iterate through the entire array and then for each
element, iterate through the remaining elements to the right to check if there
are any that sum to the target. This gives us O(N^2). Instead, we recognize the
bottleneck, and make a time-space tradeoff; we make one pass through the array
and add elements to a hashtable, then we check if its match is in the hashtable.
The resultant time complexity is O(N)

#### Uneccessary Work
Say we want to find all solutions from 1 to 1000 that satisfy a^3 + b^3 = c^3 + d^3.
A naive approach would be
```
for a from 1 to n
    for b from 1 to n
        for c from 1 to no
            for d from 1 to n
                if a^3 + b^3 = c^3 + d^3
                    print a,b,c,d
```
But, if we recognize that for any combination of a,b,c there is only a single
solution d such that d = (a^3 + b^3 - c^3)^1/3, then we can rewrite our algorithm:
```
for a from 1 to n
    for b from 1 to n
        for c from 1 to n
            d = (a^3 + b^3 - c^3)^1/3
            if a^3 + b^3 = c^3 + d^3
                print a,b,c,d
```
We removed the unneeded work and reduced our runtime from O(N^4) to O(N^3)

#### Duplicate Work
In the above example, we are essentially generating all (c, d) pairs for each
(a, b) pair. Instead, should simply generate a hashtable of 
`result -> [...pairs, (c, d)]` and then go through (a, b) pairs, compute their
a^3 + b^3 result and find the matching (c, d) pairs in the hashtable with the 
same result
```
for c from 1 to n
    for d from 1 to n
        result = c^3 + d^3
        map[result] = [...pairs, (c,d)]

for a from 1 to n
    for b from 1 to n
        result = a^3 + b^3
        pairList = map[result]
        for [c, d] in pairList
            print a,b,c,d
```
We have reduced our time complexity from O(N^3) to O(N^2) (ignore iterating
through pairList because it is so small in size compared to n)

## Tags
#interview #algorithms
