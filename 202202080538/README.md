# Technical Interview: Algorithms

## Binary Search [ iterative ]
* Time Complexity: O(logn)
* Space Complexity: O(1)
* Note: Container elements must be in sorted order
```java
// return index of target if found; otherwise index where it would be inserted
int binarySearch(int[] nums, int target) {
    int lo = 0, hi = nums.length - 1;

    while (lo <= high) {
        int mid = (lo + hi) / 2;
        if (nums[mid] == target) {
            return mid;
        } else if (target > nums[mid]) {
            lo = mid + 1;
        } else {
            hi = mid - 1;
        }
    }

    return lo;
}
```
Example:
```
You are a product manager and currently leading a team to develop a new product.
Unfortunately, the latest version of your product fails the quality check. Since
each version is developed based on the previous version, all the versions after'
' a bad version are also bad.

Suppose you have n versions [1, 2, ..., n] and you want to find out the first
bad one, which causes all the following ones to be bad.

You are given an API bool isBadVersion(version) which returns whether version is
bad. Implement a function to find the first bad version. You should minimize the
number of calls to the API.
```

Sample:
```
Input: n = 5
Output: 4
Explanation:
call isBadVersion(1) -> false
call isBadVersion(2) -> false
call isBadVersion(3) -> false
call isBadVersion(4) -> true
call isBadVersion(5) -> true
Then 4 is the first bad version.
```

Implementation
```java
int firstBadVersion(int n) {
    int lo = 1, mid = 1, hi = n;

    while (lo < hi) {
        mid = (lo + hi) / 2; // or mid = lo + (hi - lo) / 2 (int overflow)
        if (isBadVersion(mid)) {
            hi = mid; // mid may be the first bad version
        } else {
            lo = mid + 1; // everything mid and earlier is a good version
        }
    }
    return lo;
}
```

## Binary Search [ recursive ]
* Time Complexity: O(logn) 
* Space Complexity: O(logn) -> call stack
* Note: Container elements in sorted order
```java
int binarySearch(int[] nums, int target) {
    return binarySearchHelper(nums, 0, nums.length - 1, target);
}

int binarySearchHelper(int[] nums, int lo, int hi, int target) {
    if (lo > hi) {
        return -1;
    }
    int mid = (lo + hi) / 2;
    if (target == nums[mid]) {
        return mid;
    } else if (target > nums[mid]) {
        return binarySearchHelper(nums, mid + 1, hi, target);
    } else {
        return binarySearchHelper(nums, lo, mid - 1, target);
    }
}
```

## Binary Search [ BST iterative ]
* Time Complexity: O(H) where H = tree height: average -> O(logn) worst -> O(N)
* Space Complexity: O(1)
* Note: Container should be a BST
```java
boolean binarySearch(Node root, int target) {
    Node current = root;
    while (current != null) {
        if (target == current.data) {
            return true;
        } else if (target > current.data) {
            current = current.right;
        } else {
            current = current.left;
        }
    }
    return false;
}
```

## Binary Search [ BST recursive ]
* Time Complexity: O(H) where H = tree height: average -> O(logn) worst -> O(N)
* Space Complexity: O(H) where H = tree height: average -> O(logn) worst -> O(N)
* Note: Container elements in sorted order
```java
boolean binarySearch(Node root, int target) {
    if (root == null) {
        return false;
    } else if (target > root.data) {
        return binarySearch(root.right, target);
    } else if (target < root.data) {
        return binarySearch(root.left, target);
    }
    return true;
}
```

## Tags
#interview #algorithms
