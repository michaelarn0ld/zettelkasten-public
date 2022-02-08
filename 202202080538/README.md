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

## Tags
#interview #algorithms
