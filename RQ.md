# Range Queries
**What is a range query?**  
A query over a certain range in a set of elements. This includes range sum queries (calculating the sum of values) and range minimum queries (finding the minimum value).  
Range queries can be static, where the set of elements is not changes in between queries, or dynamic, where the set of elements can be updated.  

<br>

### Queries on static arrays
---------------------------
When the set of elements is static and not updated, preprocessing will be suffice to efficiently answering range queries.  

<br>

#### **Sum queries**  
A range sum query denotes the sum of array values in a specific range (e.g. 0-5).  

Sum queries can be easily processed using a **prefix sum array**, where every value is equal to the sum of values in the original array up to the corresponding position.  

A prefix sum array can be constructed in $O(n)$ time, using the formula: $$psa[i] = psa[i-1] + a[i]$$
This allows for calculation of any range sum query in $O(1)$ time. For example, when the queried range is (a, b):
$$sum = psa[b] - psa[a-1]$$

We can even calculate a two-dimensional range sum using a 2D prefix sum array (a.k.a. prefix sum matrix):
$$psa[i][j] = psa[i-1][j] + psa[i][j-1] - psa[i-1][j-1] + a[i][j]$$  

<br>

#### **Minimum queries**  
A range minimum query in the form of ($l, r$) denotes the minimum element in an array between $l$ and $r$ inclusive.  
There are many ways to efficiently solve range minimum queries, some of which even work when the array is dynamic (modifications to the array between queries).  

- **Sparse Table**  
A Sparse Table is a data structure that allows answering range queries in mostly $O(log(n))$ time, or $O(1)$ time for range minimum queries. However, this data structure can only be used on static/immutable arrays.  
<br>
<u>How it works:</u>  
Any non-negative number can be uniquely represented as a sum of decreasing powers of two e.g. $13 = 8 + 4 + 1$. Similarly, any interval can be uniquely represented as a union of intervals with lengths that are decreasing powers of 2.  
The main idea behind Sparse Tables is to precompute all answers for range queries with power of two length. Afterwards a different range query can be answered by splitting the range into ranges with power of two lengths, then combining precomputed answers to receive a complete answer.  
<br>
<u>Implementation:</u>  
We create a table $lookup$ such that $lookup[i][j]$ contains the minimum of range $i$ to $i+2^j-1$.  
Here is a C++ implementation:  
    ```c++
    #define MAX 5000 //arbitrary number
    int lookup[MAX][MAX];

    void init(int arr[], int n) {
        for(int i=0;i<n;i++) {
            lookup[i][0] = arr[i];
        }

        for(int j=1;(1<<j)<=n;j++) {
            for(int i=0;i+(1 << j)-1<n;i++) {
                lookup[i][j] = min(lookup[i][j-1], lookup[i+(1<<(j-1))][j-1]);
            }
        }
    }

    int query(int l, int r) {
        int len = r-l+1, j=0;
        while((l<<(j+1))<=len) {
            j++;
        }
        return min(lookup[l][j], lookup[r-(1<<j)+1][j]);
    }
    ```