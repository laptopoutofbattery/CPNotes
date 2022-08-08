# Divide and Conquer algorithmns
**Divide and Conquer** is a technique used to solve large problems by breaking the problem into smaller subproblems, solving these subproblems individually and combining them to get the desired output. Therefore, this technique is divided into 3 parts:
1. Divide: divide problem into smaller subproblems
2. Conquer: solve sub-problems by calling recursively until solved
3. Combine: combine the sub-problems to get the solution

Contrary to popular belief, **Binary Search is NOT an example of Divide and Conquer**. Binary Search compares the middle value of the input element with that of the middle of the subarray. If the value is not the same, the algorithmn recurs for the corresponding side of the sorted subarray. Since there is only 1 subproblem in each step, it is a **Decrease and Conquer** algorithmn. Divide and Conquer algorithmns must have 2 or more subproblems in each step.

<br><br>
### References
- [Divide and Conquer Algorithm: Introduction (geeksforgeeks)](https://www.geeksforgeeks.org/divide-and-conquer-algorithm-introduction/)
- [Divide and Conquer Algorithm (programiz)](https://www.programiz.com/dsa/divide-and-conquer)
