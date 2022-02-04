# Technical Interview Guidelines II

## Techniques for Solving Problems

### DIY (Do it Yourself)
* Before you start coding, think of a large example of the problem and 
intuitively - manually, that is - solve it for a specific example
* Think about how you solved it with your brain and reverse engineer your
approach

### Simplify and Generalize
* Example: A ransom note can be formed by cutting words out of a magazine to
form a new sentence; given a ransom note and a magazine, determine if it is
possible to create the note from the magazine.
* Simplify the above to this: A string is formed from characters; given a two
strings a and b, determine if it is possible that b could be formed by using the
characters from a
* Approach: iterate through a and store the frequency of all characters in a 
hash map; then use the results from this to determine if string b uses only 
characters in a at less than or equal to the appropriate frequency.
* SIMPLIFY & GENERALIZE: We modified the problem so we are cutting characters
out of a magazine instead of whole words (simplify)

### Base Case and Build
* Solve the problem for a base case (n = 1) and then try to build up from there;
when you get to something more interesting (n = 3 || n = 4), try and build that
using prior solutions. This often leads to recursive algorithms.
* Example: Design an algorithm to print all permutations of a string, assume all
characters are unique
* Consider: test string "abcdef"
    * Case "a" --> {"a"}
    * Case "ab" --> {"ab", "ba"}
    * Case "abc" --> ?
* How did we get from Case "a" to Case "ab"? We simply inserted b at all possible
positions in "a" - those being the beginning of the string, and the end. Do the 
same for subsequent cases.
* Case "abc" --> ...
    * P("abc") = insert "c" at all locations of "ab" --> {"abc", "acb", "cab"}
    * P("abc") = insert "c" at all locations of "ba" --> {"bac", "bca", "cba"}
    * Then P("abc") = {"abc", "acb", "cab", "bac", "bca", "cba"}

### Data Structure Brainstorm
* Simply run through a list of data structures and try to apply each one to the
problem that you have. This approach is useful because sometimes a problem may
be trivail once it occurs to us to use a specific data structure.
* Think about your problem, its mechanics and what you need to solve it, what would
make it easier to solve. Once you have that, go through your list of data structures
and find the one that has characteristics that suit the problem mechanics.

### Best Conceivable Runtime
* BCR is literally the ***best*** runtime you could ***concieve*** of a solution
to a problem

Suppose you have two sorted arrays of equal length and you want to know all elements
in common:

```
[13,17,25,40] --> A
[10,12,17,25] --> B
```

The brute force algorithm is O(N^2), where we iterate through one array and for
each element, we check each element the other to see if there is a match; for
each of N elements in array A, we have to do an O(N) search in B.

The BCR is O(N) because we absolutely know that we will have to look at each
element of both arrays at least once, or 2N elements to look at. Since we
can conceive of a better runtime, it gives us an opportunity to at least check
for BUD in our current algorithm.

* TIP: When deriving runtime, never take a guess. You MUST understand the runtime
of your program. When it is non-obvious, those are the times when you are likely
to have a less common runtime, so it is imperative you actually derive it.

* TIP: If you can reduce your brute force algorithm to the BCR, you should then
start focusing on how you can reduce space. First reduce time, then reduce space.

## Write Good Code
* Write code that is simple, readable, maintainable, flexible, and modern.

## Tags
#interview
