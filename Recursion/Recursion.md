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

### Call Stack
When a recursive function is called, it goes on top of the "call stack".
This "call stack" uses a Last In First Out (LIFO) method like a regular stack. This means that functions called last will be executed first.

<br><br>
### References
- [Recursion (geeksforgeeks)](https://www.geeksforgeeks.org/recursion/)
- [Recursion in Programming (course by freeCodeCamp.org on youtube)](https://youtu.be/IJDJ0kBx2LM)
- [How Recursion Works (freecodecamp)](https://www.freecodecamp.org/news/how-recursion-works-explained-with-flowcharts-and-a-video-de61f40cb7f9/)
- [Memoization (wikipedia)](https://en.wikipedia.org/wiki/Memoization#cite_note-Norvig1991-1)
