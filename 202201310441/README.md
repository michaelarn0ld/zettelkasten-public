# Big O Notation: Space Complexity
Time is not the only concern for an algorithm, we also must consider the amount   │~
of memory required by an algorithm. Space complexity is a parallel concept to     │~
time complexity. An array of size n take O(N) space; a 2d array of n x n takes    │~
O(N^2) space. Stack space in recursive calls counts too! Consider the following:  │~

```java                                                                           │~
int sum(int n) {                                                                  │~
    if (n <= 0) {                                                                 │~
        return n;                                                                 │~
    }                                                                             │~
    return n + sum(n - 1);                                                        │~
}                                                                                 │~
```                                                                               │~
This takes O(N) space; However, n additional calls doesn't always mean O(N)       │~
additional space. The calls only take extra space when they simutaneously exist   │~
on the call stack:                                                                │~

```java                                                                           │~
int pairSumSequence(int n) {                                                      │~
    int sum = 0;                                                                  │~
    for (int i = 0; i < n; i++) {                                                 │~
        sum += pairSum(i, i + 1);                                                 │~
    }                                                                             │~
    return sum;                                                                   │~
}                                                                                 │~
```                                                                               │~

Even though there are roughly O(N) additional calls to `pairSum`, they            │~
do not exist on the call stack at the same time; each one returns before the      │~
next one is called. This takes O(1) space.

## Tags
#algorithms #bigO
