
# ECLAT Algorithm
The ECLAT algorithm stands for **Equivalence Class Clustering and bottom-up Lattice Traversal**. It is one of the popular methods of Association Rule mining. It is a more efficient and scalable version of the Apriori algorithm. While the Apriori algorithm works in a horizontal sense imitating the Breadth-First Search of a graph, the ECLAT algorithm works in a vertical manner just like the Depth-First Search of a graph. This vertical approach of the ECLAT algorithm makes it a faster algorithm than the Apriori algorithm.   

The basic idea is to use Transaction Id Sets(tidsets) intersections to compute the support value of a candidate and avoiding the generation of subsets which do not exist in the prefix tree. In the first call of the function, all single items are used along with their tidsets. Then the function is called recursively and in each recursive call, each item-tidset pair is verified and combined with other item-tidset pairs. This process is continued until no candidate item-tidset pairs can be combined.                                                                                                                                                                                     

Consider the following transactions record:-

![alt text](https://media.geeksforgeeks.org/wp-content/uploads/20190611105423/Data3.png)
The above-given data is a boolean matrix where for each cell (i, j), the value denotes whether the j’th item is included in the i’th transaction or not. 1 means true while 0 means false.

We now call the function for the first time and arrange each item with it’s tidset in a tabular fashion:-

**k = 1, minimum support = 2**

![alt text](https://i.postimg.cc/NfqKjpdb/11-09-2022-22-03-13-REC.png)
We now recursively call the function till no more item-tidset pairs can be combined:-

**k = 2**

![alt text](https://i.postimg.cc/CKNTTLzb/11-09-2022-21-55-54-REC.png)

**k=3**

![alt text](https://i.postimg.cc/GpB7zLvc/11-09-2022-21-57-54-REC.png)

**k=4**

![alt text](https://i.postimg.cc/mDyQyJpL/11-09-2022-21-59-43-REC.png)

We stop at k = 4 because there are no more item-tidset pairs to combine.   
Since minimum support = 2, we conclude the following rules from the given dataset:-
![alt text](https://i.postimg.cc/8P2jswwt/11-09-2022-22-01-00-REC.png)

## Advantages of ECLAT Algorithm
- Eclat algorithm has low memory requirements compared to Apriori as it uses the Depth-First Search approach.
- The Eclat algorithm does not repeatedly scan the data to discover frequent itemsets, thus, is generally faster than the Apriori algorithm.
- Eclat algorithm outdoes the Apriori algorithm provided the dataset is not too big.
- Eclat algorithm scans only the currently generated dataset that is scanned in the Eclat algorithm. This is unlike in Apriori where the original dataset is scanned at each stage.
## Disadvantages of ECLAT Algorithms
- If the tidlist is too large, the Eclat algorithm may run out of memory.
