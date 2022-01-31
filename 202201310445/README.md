# Big O Notation: Considerations
* Drop the constants when describing the runtime of an algorithm; for all
our purposes, O(N) is the same as O(2N); they both scale linearly on the size
of input. This pattern holds for other time complexities.

* Drop non-dominant terms; O(2N^2) is the same as O(N^2 + N^2). If we are
dropping the additional quadratic term then we do the do same thing if it is
a linear term: O(N^2 + N) is just O(N^2). At the limits, the quadratic term
dominates. This pattern holds for other time complexities

* Suppose you have an algorithm that loops over two unrelated lists of
A and B number elements respectively. If we do not know the relationship
between A and B, then the time complexity is O(A + B), not O(N). Similarly,
if looping through list containing B number elements is nested in the loop
over A number elements, then time complexity is O(A * B), not O(N^2).

* Amoritized time is best described with an example. Consider `ArrayList` which
is a dynamic array. The array could be full. If it contains N elements, then 
insertion of a new element takes O(N) time. You have to make a new array of size
2N and copy N elements over, taking O(N) time; however, when the array is not
full, then no resizing/copying occurs and insertion takes O(1) time. Over X
elements, we double capacity from `1 + 2 + 4 + 8 + ... + X`, the sum is
approximately 2X. Therefor X insertions takes O(2X) time. The amoritized time
for each insertion is O(1).

## Tags
#algorithms #bigO
