---
layout: page
title: Algorithms
permalink: /algorithms/
usemathjax: true
---

# Useful Aglorithms
Just some random algorithms that can be useful.

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