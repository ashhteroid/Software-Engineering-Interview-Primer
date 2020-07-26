# Important Algos for Interviews

## Graph Algos

### DAG Topological Sort

To get order of nodes from a DAG graph.

```
Coding:

 1. Keep a result stack and visited node list
 2. For every node 0 to N: 
        Mark visited. 
        Recursivly call Tsort on children (aka add all children to stack before itself)
        Add itself to result stack.
 3. Print out stack from top to bottom.

```
https://www.geeksforgeeks.org/topological-sorting/

### DAG Verify no cycle in DAG

DFS over all nodes while marking visited. Can take mutiple DFS - cycle exists if child node visited during current DFS.
```
Coding:

 1. Initialize Visited (global) and cur_dfs_stack (resets each DFS, it essentially stores DFS stack's parent visited nodes)
 2. For every node 0 to N: Mark visited and call DFS. Recursivly call DFS on every children and check for cycle by checking cur_stack.

```
https://www.geeksforgeeks.org/detect-cycle-in-a-graph/

## References:
    * Python.org
    * Geeksforgeeks.com
    * leetcode.com
    * google.com
    * stackoverflow.com
    * hackerrank.com
    * realpython.com
    * Lots of Random websites, thanks to google. 
