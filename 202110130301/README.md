# Bubble Sort Algorithm
* Bubble sort has a time complexity: O(N^2)
* This algorithm is called bubble sort because we "bubble" things to the "top"
of their container

## How does it work
1. First, we make a pass over the entire list, a.k.a. a sweep
1. We compare pairs of items and check if they are in the right order or if they
need to be swapped
1. After one pass, it is guaranteed that the largest item will be at the front
of the list
1. We go back to the beginning of the list and restart the process

There are two conditions where we know we are finished:
1. We go through the entire list and nothing needs to be swapped
1. If we have an list of size n and do n-1 sweeps, then it is guaranteed to be
sorted


## Optimizations
* Do not need to compare pairs once they are bubbled up to the top. For example,
after the first pass, the largest element is bubbled to the front of the list;
in the second pass, there is no need to compare with the front of the list.


## Related
[202110071918](../202110071918) - Bitwise Operators \
[202110090311](../202110090311) - Newton-Raphson Method \
[202110130353](../202110130353) - Insertion Sort Algorithm


## Tags
#computerscience
