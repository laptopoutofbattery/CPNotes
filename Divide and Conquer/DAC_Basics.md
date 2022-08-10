# Divide and Conquer algorithms
**Divide and Conquer** is a technique used to solve large problems by breaking the problem into smaller subproblems, solving these subproblems individually and combining them to get the desired output. Therefore, this technique is divided into 3 parts:
1. Divide: divide problem into smaller subproblems
2. Conquer: solve sub-problems by calling recursively until solved
3. Combine: combine the sub-problems to get the solution

Contrary to popular belief, **Binary Search is NOT an example of Divide and Conquer**. Binary Search compares the middle value of the input element with that of the middle of the subarray. If the value is not the same, the algorithm recurs for the corresponding side of the sorted subarray. Since there is only 1 subproblem in each step, it is a **Decrease and Conquer** algorithm. Divide and Conquer algorithms must have 2 or more subproblems in each step.

**Divide and Conquer to find the maximum**
```c++
int max(int arr[], int l, int r) {
    // base case
    if(l == r) {
        return arr[l];
    }

    else {
        int m = (l+r)/2;
        int lm = max(arr, l, m);
        int rm = max(arr, m+1 , r);

        return (lm > rm) ? lm : rm;
    }
}
```

**Examples of algorithms that use Divide and Conquer**
1. Quicksort  
The algorithm picks a pivot element and rearranges the array elements so that all elements smaller than the picked pivot element move to the left side of the pivot, and all greater elements move to the right side. Finally, the algorithm recursively sorts the subarrays on the left and right of the pivot element.
2. Merge Sort  
The algorithm divides the array into two halves, recursively sorts them, and finally merges the two sorted halves.

<br><br>
### References
- [Divide and Conquer Algorithm: Introduction (geeksforgeeks)](https://www.geeksforgeeks.org/divide-and-conquer-algorithm-introduction/)
- [Divide and Conquer Algorithm (programiz)](https://www.programiz.com/dsa/divide-and-conquer)
