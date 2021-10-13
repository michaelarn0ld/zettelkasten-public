# Insertion Sort Algorithm
* Insertion sort has a time complexity: O(NlogN)
* This algorithm is called insertion sort because we choose an element from an
original list and insert it into its proper place in a new list


## How does it work
* Create a new list, that is guaranteed to always be sorted
* Make a pass over the original list and choose each element; time is O(N)
* Use binary search on the sorted list to figure out where to insert the chosen
element; time is O(logN)

Pseudocode looks something like this:

```
function InsertionSort(list):

    sorted = []
    for each element of list:
        sorted = addToList(sorted, element)
    return sorted



function addToList(sortedList, element):

    left = 0
    right = len(sortedList) - 1

    while left <= right:

        middle = (left + right) // 2
        if element is >= than the middle element:
            left = middle + 1
        otherwise the element is less than the middle element:
            right = middle - 1

    add element to sortedList at index left
    return sortedList
```


## Related
[202110071918](../202110071918) - Bitwise Operators \
[202110090311](../202110090311) - Newton-Raphson Method \
[202110130301](../202110130301) - Bubble Sort Algorithm


## Tags
#computerscience
