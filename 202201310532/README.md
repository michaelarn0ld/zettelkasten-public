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


## Tags
#algorithms #bigO
