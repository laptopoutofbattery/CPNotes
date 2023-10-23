# Useful Aglorithms
Just some random algorithms that can be useful.

### Binary Search
[**Binary Search**](https://cp-algorithms.com/num_methods/binary_search.html) is a searching algorithm that allows for finding the index of an element in an array in $O(logn)$ time.  
How it works:
- sort the array arr in ascending order
- set a left index $l$ to be the first element of the array, set a right index $r$ to be the last element of the array
- set the middle index $mid$ to be the average of these 2 indexes
    - if arr[mid]==target element, then the value has been found
    - if arr[mid]<target element, then set $r$ to be $mid-1$
    - if arr[mid]>target element, then set $l$ to be $mid+1$
- repeat previous step until value has been found or $r < l$

Implementation (copied from [cp-algorithms.com](https://cp-algorithms.com)):
```c++
//a is the sorted array
int l = -1, r = n;
while(r - l > 1) {
    int m = (l + r) / 2;
    if(k < a[m]) {
        r = m; // a[l] <= k < a[m] <= a[r]
    } else {
        l = m; // a[l] <= a[m] <= k < a[r]
    }
}
```  
Usage:
- used to find
    - lower bound: index of the first element that is >= a given value
    - upper bound: index of the first element that is > a given value
- Binary Search on The Answer (BSTA)
    - binary search can be used to find the answer $x$ of a function $f(x)$ such that $f(x)=true$
    - only works on monotonic functions (functions that are always non-decreasing/always non-increasing)
    - more info [here](https://cp-algorithms.com/num_methods/binary_search.html#binary-search-on-the-answer)

<br>

### Kadane's Algorithm
[**Kadane's Algorithm**](https://cp-algorithms.com/others/maximum_average_segment.html#algorithm-2) solves the largest contiguous subarray problem: given an array of size N, find the sum of the contiguous subarray within the array with the largest sum.  
How it works:
- go through the array and accumulate:
    - the current partial sum in some variable $s$
    - the maximum sum of contiguous subarray found so far in some variable $m$
- if $s<0$ at any point, we assign $s=0$
- if $s>m$ at any point, we assign $m=s$

Implementation (copied from [cp-algorithms.com](https://cp-algorithms.com)):
```c++
int ans = a[0], ans_l = 0, ans_r = 0;
int sum = 0, minus_pos = -1;

for (int r = 0; r < n; ++r) {
    sum += a[r];
    if (sum > ans) {
        ans = sum;
        ans_l = minus_pos + 1;
        ans_r = r;
    }
    if (sum < 0) {
        sum = 0;
        minus_pos = r;
    }
}
```
