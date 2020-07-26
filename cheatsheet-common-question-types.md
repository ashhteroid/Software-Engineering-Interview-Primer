# Some Common Patterns and Facts

## Common Problem Patterns:

### Strings/Arrays
  1. Palindromes
        - Two pointers
        - exploit palindrome properties
  2. Brackets 
        - Uses stacks to track state
        - Usually a counter that tracks open brackets is enough to determine valid bracket sequences
  3. Pointer Problems 
  4. Longest increasing subsequence
  5. Run Length Encoding (https://leetcode.com/problems/expressive-words/solution/)

### Math
  1. Usually exploits some math property.
     ``` Example 2Sum problem exploits 'complements' ```

### 2D Grid
  1. Usually exploit some sort of DFS/BFS search
     ``` Example number of island problem ```
     
### Greedy
  1. Usually exploits a greedy choice to make the problem easier (Usually Optimization problems). 
  2. The greedy problem will most likely be one the popular ones or a derivation of it.

### Backtracking
  1. Usually exploits some property to reduce brute force computation by a bit
  2. Using recursion makes it easier to solve.
  
      Example: https://leetcode.com/problems/generate-parentheses/

## Graph
  1. DFS (Use Recursion)
      - Find Path to Node
  2. BFS (Use Deque)
      - Shortest part to Node
  3. Euler Path (Use modified DFS)
      - Travel every path only once
      <details>
  
      1. In Eulerian paths, there must exist a start node and a end node.   
      2. End node can be start node or another node.
            - end node is start node iff all nodes has even degree.
            - end node is another node iff there is another odd degree node and start node has an odd degree.      
      
      </details>
  4. Discussion about other types of problems/algorithms that can show up:
      <details> https://www.quora.com/What-graph-topics-should-I-study-in-order-to-be-adequately-prepared-for-a-Google-software-engineer-interview-Would-it-be-worthwhile-to-also-study-algorithms-for-minimum-spanning-trees-maximum-network-flows-bipartite-matching-etc
      </details>
---
## DS Facts

### Signed Integers
- For a 32 bit integer stored as twos complement the range is −2<sup>31</sup> through −2<sup>31</sup> − 1 [2's complement is complement(num-1)]
- Python uses infinite number of bits so -5 is treated by bitwise operators as if it were written "...1111111111111111111011"

### Strings
- There can only be O(n^2) possible sub-strings. n(n+1)/2 to be exact

### Graph
- Number of paths from A to B in a graph - just say exponential. Dont dweleve on it.
- It is a NP hard problem to find all paths as there will be exponetial paths.

Applications:
- 2D Grid problem 

---
## Paradigms Facts

### Recursion

A recursive function must have:
  - A input/state thats passed down thats unique to every call (if not use global)
  - A Base case
  - Value thats computed and passed up.
  
### Dynamic programming

DP must have:
  - Optimal substructure
  - Overlapping subproblems ( One way to intuitively figure this out would be to see if there
                              is a memoization table whos size < number of leafs)

  Notes:   
         1. For some problems iterative approach might be easier to implement and might also reduce space complexity. (https://www.algoexpert.io/questions/Max%20Subset%20Sum%20No%20Adjacent)
### Greedy Algorithms

Makes a greedy choice(Follows an invariant) every step that gives local optimum. Best suited for optimazation problems with natural choices to select from.
  - Need not always yield the most optimal solution but can give insight/serve as a heuristic
  - Choosing the right greedy algorithm can be not obvious/hard. It is more an Art.
  - Easier to conceptualize as recursion

## References:
- Leetcode.com
- algoexpert.io
