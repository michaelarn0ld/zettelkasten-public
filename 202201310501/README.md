# Big O Notation: Common Runtimes (Log N & Recursive)

## O(Log N)
Consider binary search in an ordered array; we are looking for element x in
an N item array. We start in the middle of the array; if x is greater than the
middle value we forget about the left side and only focus on the right side,
if x is less than this value, we choose to only search the left side. Each time
time we narrow our search space, we reevalutate what our new middle value is
and repeat the narrowing until we find our target x.

We start off with an N-element array; after the first step, the array is
size N/2; after the second step the array is size N/4. We repeat this until
we find the target or the array has just one element.

```
N = 16
N = 8
N = 4
N = 2
N = 1

4 is the maxmimum number of steps to search an ordered array of size N = 16 
```

* The maximum number of steps required to search for a given element in an
ordered array is proportional to the base 2 logarithm of its size.

* T = K * LOG2(N)

* Since all logarithms are related to other logarithms by some constant, we may
factor that out of the expression and obtain a more general form

* T = K * LOG(N)

## Recursive Runtimes
Consider the following:
```java
int f(int n) {
    if (n <= 1) {
        return n;
    }
    return f(n - 1) + f(n - 1);
}
```

Suppose you call f(4):
```
            ______f(4)_____
           /               \
          /                 \
         f(3)                 f(3)
       /     \              /     \  
      f(2)    f(2)        f(2)     f(2)
     /   \    /   \      /   \     /   \
 f(1)   f(1) f(1) f(1)  f(1) f(1) f(1) f(1)
```
In this example, there will be `2^0 + 2^1 + 2^2 + 2^3` calls. For a depth N,
there will be a total of 2^N - 1 calls, one for each node. So, for this
recursive problem, we say it runs in O(2^N) time. In general, when you
have a recursive function, the runtime is often (but not always)
O(branches^depth).

In the case of exponents, constants do matter. If instead of 2 branches there
were 8, the time complexity would be O(8^N) which is O(2^3N); 8^N and 2^N are
different by a factor of 2^3N, very much not a constant factor.

Space complexity in the above is still only O(N). For f(4), at any given time,
there are only 4 calls on the stack; for f(n), there would only be f(n) calls on
the stack.

## Tags
#algorithms #bigO
