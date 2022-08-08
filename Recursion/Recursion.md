# Recursion
**Recursion** is a method of solving problems by solving smaller instances of itself. Essentially, recursion is a process where a function calls itself.  
A recursive function solves problems by calling a copy of itself and solving smaller subproblems of the original problems. Many more recursive calls can be generated if needed. Recursion performs the same operations multiple times with different inputs. It makes the input smaller each time to make the problem smaller and easier.  
The **Base condition/case** of recursion is the stopping condition of recursion, to stop the growth of the number of recursive calls. This helps prevent an infinite loop.  

<br>

**Why use recursion?**  
- Significantly reduces the length of code and make it easier to read. It provides elegance in complex data structures and algorithmns.
- Reduces the need for complex loops and auxiliary data structures. Similar to the first point, simplifies your code.
- Reduces time complexity with **memoization**. Memoization is an optimization technique used to speed up programs by returning the cached result when the same input occurs again.
- Works well with trees and graphs. Important in graph theory.

<br>

**Issues with using recursion**  
- Can incur CPU overhead and cause slowness.
- Can lead to out of memory errors and stack overflow exceptions.
- Can cause unnecessarily complex code if poorly constructed. Make sure recursion is used well and not unnecessarily.

<br>

**Call Stack**  
When a recursive function is called, it goes on top of the "call stack".
This "call stack" uses a Last In First Out (LIFO) method like a regular stack. This means that functions called last will be executed first.  
In recursion, function calls are nested until the base case is reached. Without the base case, there would be infinite nested function calls.  
The depth of recursion is the maximum degree of nesting the function calls over the course of computation. The programming environment has to maintain a pushdown stack of size proportional to the depth of the recursion. For huge problems, the space needed for this stack might prevent the use of plain recursion.

<br>

**Recursion VS Iteration**


|        | Recursion     | Iteration  |
| -------|:-------------:| :---------:|
| 1      | Terminates when base case becomes true | Terminates when loop condition becomes false      |
| 2      | Uses functions      |  Uses loops      |
| 3      | Each recursive call needs additional memory in the stack memory | Each iteration does not use extra memory|
|4| Smaller code size, more elegant| Larger code size|

<br>

**Applications of recursion**  
Recursion is obviously very important and has widespread use.
In competitive programming, recursion is used for:
1. Divide and conquer
2. Dynamic programming
3. Graphs
4. Trees

<br>

**Examples**  
Factorial function:
```c++
int factorial(int n) {
    // base case
    if(n==0) {
        return 1;
    }

    return n*factorial(n-1);
}
```
Fibonacci Sequence function:
```c++
int fibonacci(int n) {
    // base case
    if(n==1 || n==2) {
        return 1;
    }

    else return fibonacci(n-1)+fibonacci(n-2);
}
```
Euclidean Algorithmn function:
```c++
int euclid(int a, int b) {
    // base case
    if(b == 0) {
        return a;
    }

    else return euclid(b, a % b);
}
```

<br><br>
### References
- [Recursion (geeksforgeeks)](https://www.geeksforgeeks.org/recursion/)
- [Recursion in Programming (course by freeCodeCamp.org on youtube)](https://youtu.be/IJDJ0kBx2LM)
- [How Recursion Works (freecodecamp)](https://www.freecodecamp.org/news/how-recursion-works-explained-with-flowcharts-and-a-video-de61f40cb7f9/)
- [Memoization (wikipedia)](https://en.wikipedia.org/wiki/Memoization#cite_note-Norvig1991-1)
