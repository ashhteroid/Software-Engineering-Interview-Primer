# Important python(2.7) operations and DS for Interviews

## Time Complexities of all Sorting Algorithms

|               | Best  | Average | **Worst** |
|---------------|------|---------|------|
Selection Sort	| Ω(n^2)	| θ(n^2)	| **O(n^2)**
Bubble Sort	| Ω(n)	| θ(n^2)	| **O(n^2)**
Insertion Sort	| Ω(n)	| θ(n^2)	| **O(n^2)**
Heap Sort	| Ω(n log(n))	| θ(n log(n))	| **O(n log(n))**
Quick Sort	| Ω(n log(n))	| θ(n log(n))	| **O(n^2)**
Merge Sort	| Ω(n log(n))	| θ(n log(n))	| **O(n log(n))**
Bucket Sort	| Ω(n+k)	| θ(n+k)	| **O(n^2)**
Radix Sort	| Ω(nk)	| θ(nk)	| **O(nk)**

https://www.geeksforgeeks.org/time-complexities-of-all-sorting-algorithms/

## How Sorting Algorithms Work

### Selection Sort

Select and move smallest to front.

```Coding: Two loops```

### Bubble Sort

Compare with next and swap until largest is at the end - n times.

```Coding: Two loops```

### Insertion Sort

Start from second element and put every element to correct position behind it.

```Coding: Two loops. First loop for every element. Second one to shift element until correct position is found.```

### Heap Sort

Use min heap to push all and then pop all.

```Coding: Use heapq```

### Quick Sort

Select last element as pivot. Use ```low``` to track >pivot element that need to be swapped right. Use ```high``` to track <pivot element that need to be swapped left. Do this until low and high cross. Now swap pivot to low postion (aka middle of partition). Call QuickSort recursively on left and right partitions. 

```Coding: Recursion for QuickSort. Two pointers (low and high) in a while loop for partioning given array. ```

https://opendsa-server.cs.vt.edu/embed/quicksortAV

### Merge Sort

Split into single elements and recursively merge two arrays at a time.

```Coding: Split array and recursively call MergeSort on two halves. ```

### Bucket Sort / Counting Sort

Sort into fixed buckets, sort each bucket using insertion sort if needed.

```Coding: Sort into list of deques based on indices. Sort each deque. Merge. ```

https://www.interviewcake.com/concept/java/counting-sort
https://www.geeksforgeeks.org/bucket-sort-2/

### Radix Sort

From least significant to most signigicant digit - Count sort based on that digit as key. 

```Coding: List of size 10 where each element is a list of int.```

https://brilliant.org/wiki/radix-sort/#:~:text=Radix%20sort%20is%20an%20integer,sort%20an%20array%20of%20numbers.

## References:
    * Python.org
    * Geeksforgeeks.com
    * leetcode.com
    * google.com
    * stackoverflow.com
    * hackerrank.com
    * realpython.com
    * Lots of Random websites, thanks to google. 
