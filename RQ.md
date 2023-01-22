# Range Queries
**What is a range query?**  
A query over a certain range in a set of elements. This includes range sum queries (calculating the sum of values) and range minimum queries (finding the minimum value).  
Range queries can be static, where the set of elements is not changes in between queries, or dynamic, where the set of elements can be updated.  

<br>

### Queries on static arrays
---------------------------
When the set of elements is static and not updated, preprocessing will be suffice to efficiently answering range queries.  

**Sum queries**  
A range sum query denotes the sum of array values in a specific range (e.g. 0-5).  

Sum queries can be easily processed using a **prefix sum array**, where every value is equal to the sum of values in the original array up to the corresponding position.  

A prefix sum array can be constructed in $O(n)$ time, using the formula: $$psa[i] = psa[i-1] + a[i]$$
This allows for calculation of any range sum query in $O(1)$ time. For example, when the queried range is (a, b):
$$sum = psa[b] - psa[a-1]$$

We can even calculate a two-dimensional range sum using a 2D prefix sum array (a.k.a. prefix sum matrix)!