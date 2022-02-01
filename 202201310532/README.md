# Big O Notation: Examples

### 1
```java
void foo(int[] arr) {
    for (int ele : arr) {
        // do something
    }
    for (int item : arr) {
        // do something
    }
}
```
This will take O(N) time; iterating twice does not matter.

### 2
```java
void foo(int[] arr) {
    for (int ele : arr) {
        for (int inner : arr) {
            System.out.println(inner);
        }
    }
}
```
The inner loop takes O(N) time and is called N times; Time is O(N^2).

### 3
```java
void foo(int[] arr) {
    for (int i = 0; i < arr.length; i++) {
        for (int j = i + 1; j < arr.length; j++) {
            System.out.println(inner);
        }
    }
}
```
On the first pass, the inner loop runs N - 1 steps, on the second pass it runs
N -2 steps, and so on. In total, it runs (N - 1) + (N - 2) + ... + 2 + 1 total
steps. This is equal to (N(N -1)/2). Since we ignore non dominant terms and
constants, time complexity here is O(N^2).

### 4
```java
void foo(int[] a, int[] b) {
    for (int i = 0; i < a.length; i++) {
        for (int j = 0; j < b.length; j++) {
            // do something
        }
    }
}
```
For each element of a, the inner loop performs B iterations. if A = a.length,
then time is O(AB).

### 5
```java
void foo(int[] a, int[] b) {
    for (int i = 0; i < a.length; i++) {
        for (int j = 0; j < b.length; j++) {
            for (int k = 0; k < 10000; k++) {
                // do something
            }
        }
    }
}
```
Nothing has changed when compared to example 3, there is another nested loop,
but it always performs C * 10000 steps, where C is the number of operations in
the loop. So time is O(AB * C * 10000); since we drop the constants, time is
really O(AB).

### 6
Which of the following are equivalent to O(N)

* O(N + P) where P < N/2
* O(2N)
* O(N + log N)
* O(N + M)

All except the last are equivalent; in the first, we have a direct relationship
of P to N. We know we can drop P since it is non dominant. In the second case, we
drop the constant. In the third case, N dominates Log N. In the last case, there
is no relationship between N and M so we keep both.

### 7
```java
void foo(String[] arr) {
    for (String s : arr) {
        s.sort();
    }
    arr.sort();
}
```
Say the outer loop is length A and the longest string is length S. Sorting the
strings is going to be O(S Log S) performed A times; that block is then
O(A(S Log S)) total time. Then we sort the array, which takes O(A log A) time;
also taking into consideration that each string comparison takes a worst case
O(S) time (imagine comparing two strings that are identical except for the last
character). In total, this operation takes O(S(A Log A)). Combining the two, we
get O(A(S Log S) + S(A Log A)) or simply O(AS(A Log A + S Log S)).

### 8
```java
int sum(Node node) {
    if (node == null) {
        return 0;
    }
    return sum(node.left) + node.value + sum(node.right);
}
```

This code sums all the node values in a balanced binary search tree. Each node
is touched exactly one time, from that perspective, it is easy to see that the
runtime is O(N). However, it still holds to the recursive rule of O(branches^depth).
Consider that there are two branches, in a binary search tree, the depth is
approximately equal to Log2(N). Thus we come up with a runtime O(2^Log2(N)).
Let P = 2^Log2(N); Log2(P) = Log2(N) && P = N. Therefore 2^Log2(N) = N. The time
complexity is still O(N).

### 9
```java
int foo(int n) {
    for (int x = 0; x * x <= n; x++) {
        // do some stuff O(1)
    }
}
```
We can see that the loop will start at x = 0 and end when x * x = n. In other
words, it will end when x = SQRT(N). The time complexity is O(SQRT(N)).

### 10
```java
void permutation(String str, String prefix) {
    if (str.length() == 0) {
        // print prefix
    } else {
        for (int i = 0; i < str.length; i++) {
            String rem = str.substring(0, i) + str.subtring(i + 1);
            permutation(rem, prefix + str.charAt(i));
        }
    }
}
```
Let's consider this example carefully; first inspect the permutation recursive
call and consider how it works. If you start with str = "code", then it goes
like this for the first selected character:
```
          c
    /     |     \
   o      d      e
  / \    / \    / \
 d   e  o   e  o   d
 |   |  |   |  |   |
 e   d  e   o  d   o

```
There are N! permutations for the first character; we must perform this operation
for all characters of the string so there are N x N! total function calls. Now
we must consider how long each function call takes; we know that string concatenation
is O(N), we also know that printing a string is O(N). Therefore, each function
call corresponds to O(N) total time.The total runtime is O(N^2 * N!))

### 11
```java
int fib(int n) {
    if (n <= 1) {
        return n;
    }
    return fib(n - 1) + fib(n - 2);
}
```
This is a simple recursive algorithm is O(branches^depth) time complexity. There
are two branches and we must go as deep as N. Thus time is O(2^N).

### 12
```java
void allFib(int n) {
    for(int i = 0; i < n; i++) {
        fib(i);
    }
}
```
Naively, you may be led to believe that because the loop runs N times and each
fib() call takes O(2^N) that the total time is O(N 2^N). This is wrong. Lets
trace the algorithm:
```
fib(1) -> 2^1 steps
fib(2) -> 2^2 steps
fib(3) -> 2^3 steps
...
fib(n) -> 2^n steps
```
Therefore, the total work done is:
```
2^1 + 2^2 + 2^3 + ... + 2^n
```
We have seen before that this sum is 2^(n+1); thus the runtime here is O(2^N).

### 13
```java
void allFib(int n) {
    int[] memo = new int[n + 1];
    for (int i = 0; i < n; i++) {
        // some call to fib(i, memo)
    }
}

void fib(int n, int[] memo) {
    if (n <= 1) {
        return n;
    } else if (memo[n] > 0) {
        return memo[n];
    }
    memo[n] = fib(n - 1) + fib(n - 2);
    return memo[n];

}
```
Lets walk through the code:
```
allFib(4)

fib(0) -> return 0
fib(1) -> return 1
fib(2) -> memo[2] = fib(1) + fib(0) = 1; return 1;
fib(3) -> memo[3] = fib(2) + fib(1) = memo[2] + 1 = 2; return 2
fib(4) -> memo[4] = fib(3) + fib(2) = memo[3] + memo[2] = 3; return 5
```
All of these operations are O(1) time; we are able to do this by applying
memoization to optimize the recursion. We trade memory for time. We perform
O(1) time operations N times, the total runtime is O(N).

### 14
```java
int powersOf2(int n) {
    if (n < 1) {
        return 0;
    } else if (n == 1) {
        return 1;
    } else {
        int prev = powersOf2(n/2);
        int cur = prev * 2;
        return cur;
    }
}
```
Lets look at the recursive call stack for n = 50:
```
-f(50)
-----f(25)
---------f(12)
-------------f(6)
----------------f(3)
-------------------f(1)
                    return
                return
            return
        return
    return
return
```
The runtime is the number times we can divide 50 (or n) by 2 until we get to
the base case. This is equivalent to the ceiling of Log2(50). The runtime
is then O(Log N).

## Tags
#algorithms #bigO
