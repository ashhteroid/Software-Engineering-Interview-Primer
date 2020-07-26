# Important python(2.7) operations and DS for Interviews

## Useful Python Functions that work across data structures


alist = [1, 2, 3]
astring = "This is a string"


<details><summary><b>reversed(ds)</b></summary>

+ returns an iterator
+ DS should have __len__() and __getitem__() Eg: tuple, string, list or range
```             
 seqString = 'Python'
 print(list(reversed(seqString)))
```

</details>

<details><summary><b>sorted(ds)</b></summary>

+ returns a sorted list
+ ds should be an iterable ( have __iter__ and __next__() )
               
Example:
```
# take second element for sort
def takeSecond(elem):
    return elem[1]
# random list
random = [(2, 2), (3, 4), (4, 1), (1, 3)]
# sort list with key
sortedList = sorted(random, reversed=False, key=takeSecond)
# Sorted list: [(4, 1), (2, 2), (1, 3), (3, 4)]
```
</details>

<details><summary><b>map(function, iterable, ...)</b></summary>
+ returns a map object.
+ You can pass more than one iterable to the map() function.

Exmaple:
```
def calculateSquare(n):
     return n*n
 numbers = (1, 2, 3, 4)
 result = map(calculateSquare, numbers)
 print(result)
 #<map object at 0x7f722da129e8>
 # converting map object to set
 numbersSquare = list(result)
 print(numbersSquare)
 # [16, 1, 4, 9]
```
</details>

<details><summary><b>enumerate(iterable, start=0)</b></summary>
+ The returned object is a enumerate object.
+ start (optional) - enumerate() starts counting from this number. If start is omitted, 0 is taken as start.

Example:
```
grocery = ['bread', 'milk', 'butter']
enumerateGrocery = enumerate(grocery)
print(type(enumerateGrocery))
# converting to list
print(list(enumerateGrocery))
# changing the default counter
enumerateGrocery = enumerate(grocery, 10)
print(list(enumerateGrocery))
<class 'enumerate'>
[(0, 'bread'), (1, 'milk'), (2, 'butter')]
[(10, 'bread'), (11, 'milk'), (12, 'butter')]
```
</details>

<details><summary><b>zip(iterable1, iterable2)</b></summary>
+ combines and returns a list of tuples
+ length is that of shortest
</details>    

<details><summary><b>sum(iterable)</b></summary>
+ returns sum(alist)
</details>

<details><summary><b>all(iterable)</b></summary>
+ returns True if all elements in an iterable are true
 
+ True - If all elements in an iterable are true
+ True - If Empty

Example:
```
# all values true
l = [1, 3, 4, 5]
print(all(l))
# True
```
</details>

<details><summary><b>any(iterable)</b></summary>

+ returns True if at least one element of an iterable is true
+ return false if all elements are false or if an iterable is empty

</details>

<details><summary><b>List/Dict/Set Comprehension</b></summary>

### List   
```
# Print only number if odd or "even" otherwise for all numbers 0 to 9. Do it two times. 
>>> [(i,x) if x%2 else (i,"even") for i in range(2) for x in range(10) if x%4]
[(0, 1), (0, 'even'), (0, 3), (0, 5), (0, 'even'), (0, 7), (0, 9), (1, 1), (1, 'even'), (1, 3), (1, 5), (1, 'even'), (1, 7), (1, 9)]
```
### Dict

```
# Create dict with numbers as values
>>> {str(i):i for i in [1,2,3,4,5]}
{'1': 1, '3': 3, '2': 2, '5': 5, '4': 4}
```

### Set 
```
# Create a set from List
>>> {s for s in [1, 1, 0, 4, 4, 3]}
set([0, 1, 3, 4])
```
</details>

<details><summary><b>lambda function</b></summary>
 
```
student_tuples = [
    ('john', 'A', 15),
    ('jane', 'B', 12),
    ('dave', 'B', 10),
]
sorted(student_tuples, key=lambda student: student[2])   # sort by age
[('dave', 'B', 10), ('jane', 'B', 12), ('john', 'A', 15)]
```
</details>

## Useful math operations

<details><summary><b>pow(x,y)</b></summary>
 + x to the power y



```
print bin(8) # '0b1000' a string
# binary number to base 10 intiger
print int("111", 2) # 7
```
</details>

<details><summary><b>float(“inf”)</b></summary>  
+ For infinity and negative infinity 
```
float(“inf”)
float("-inf")
```
</details>


## Useful Libraries

<details><summary><b>Regex</b></summary>  

Class
1. ```[akm$]``` will match any of the characters 'a', 'k', 'm', or '$'
2. ```[a-c]``` will match any of the characters a, b, or c; this is the same as ```[abc]```
3. ```[^5]``` will match any character except '5'
4. ```[5^]``` will match either a '5' or a '^'
5. To match a ```[ or \```, you can precede them with a backslash to remove their special meaning: ```\[ or \\```
Special
6. ```\w``` matches any alphanumeric character. Equivalent to the class [a-zA-Z0-9_]
7. ```\d``` Matches any decimal digit; this is equivalent to the class ```[0-9]```
8. ```\D``` Matches any non-digit character; this is equivalent to the class ```[^0-9]```
9. ```\s``` Matches any whitespace character; this is equivalent to the class ```[ \t\n\r\f\v]```
10. ```\S``` Matches any non-whitespace character; this is equivalent to the class ```[^ \t\n\r\f\v]```
11. ```\w``` Matches any alphanumeric character; this is equivalent to the class ```[a-zA-Z0-9_]```
12. ```\W```Matches any non-alphanumeric character; this is equivalent to the class ```[^a-zA-Z0-9_]```
Qualifiers
13. ```*``` Matches 0 or more character. ```ca*t`` will match 'ct' (0 'a' characters), 'cat' (1 'a'), 'caaat' (3 'a' characters) etc.
14. ```+``` Matches 1 or more character. ```ca.t``` will match 'cat' (1 'a'), 'caaat' (3 'a' characters) etc.
15. ```?``` Matches 1 or 0 characters. ```home-?brew``` matches either ```homebrew or home-brew```
16. ```{m,n}``` at least m repetitions, and at most n. a/{1,3}b will match 'a/b', 'a//b', and 'a///b'. It won’t match 'ab'


```
import re
p = re.compile('[a-z]+')
>>> p
re.compile('[a-z]+')

>>> print(p.match(""))
None



```
</details>

<details><summary><b>random</b></summary>  
```
import random
choice = random.choice([5,2,3])
random_number = random.randrange(0,10)
```
</details>


<details><summary><b>copy</b></summary>  
             
```
import copy
lista = copy.copy(listb)
# Recursive. Eg: List of lists
lista = copy.deepcopy(listb)
```
</details>

<details><summary><b>bisect</b></summary>  

+ Returns the position of insertion for a new element in a sorted array

+ bisect.bisect(array, ele)/bisect.bisect_right(array, ele)
      All the elements that are equal to ele are on the left of the insert position.
+ bisect.bisect_left(array, ele)
      All the elements that are equal to ele are on the right of the insert position(or at the insert position).
```
import bisect
a = [1, 2, 3, 5]
bisect.bisect(a, 4) # ans = 3, compatible with a.insert(pos, ele)

```
</details>

<details><summary><b>time</b></summary>  

+ time.time() → float
+ Return the time in seconds since the epoch as a floating point number.

```
>>> import time
>>> time.time()
1572381749.513094

```
</details>

<details><summary><b>logging</b></summary> 

+ Default level is 'Warning'
+ https://realpython.com/python-logging/
+ Use the below to print log to stdout

```
import logging
logging.basicConfig(level=logging.DEBUG) 
logging.info("lol")
```
</details>

### Collections

<details><summary><b>namedtuple</b></summary>      
 - it can be used everywhere a tuple is used without breaking. Follows Liskov substitutability.

```
from collections import namedtuple
Point = namedtuple('Point', 'x y')
pt1 = Point(1.0, 5.0)
pt2 = Point(2.5, 1.5)

>>> pt1.x
1.0
```
</details>

<details><summary><b>defaultdict</b></summary>      
    - Same as dict, except sets a default value if key is not present

```
from collections import defaultdict
d = defaultdict(list)
d['python'].append("awesome")
d['something-else'].append("not relevant")
d['python'].append("language")
for i in d.items():
    print i

('python', ['awesome', 'language'])
('something-else', ['not relevant'])
```
</details>

<details><summary><b>OrderedDict</b></summary>      
 
- Same as dict, except also keeps tracks of order of element inserts using a doubly LL
- This operation differs from normal dict:

  ```.popitem(last=True)  # Return LIFO if last=True or FIFO if last=False```

- New Operation:   
  ```.move_to_end(key, last=True) # Moves the key to end of the ordered dict. Right end if last=True or left end if last=False```
    
```
>>> from collections import OrderedDict
>>> d = OrderedDict.fromkeys('abcde')
>>> d
OrderedDict([('a', None), ('b', None), ('c', None), ('d', None), ('e', None)])
>>> d.move_to_end('b', last=True)
>>> d
OrderedDict([('a', None), ('c', None), ('d', None), ('e', None), ('b', None)])
>>> d.move_to_end('d', last=False)
>>> d
OrderedDict([('d', None), ('a', None), ('c', None), ('e', None), ('b', None)])
>>> d['z'] = None
>>> d
OrderedDict([('d', None), ('a', None), ('c', None), ('e', None), ('b', None), ('z', None)])
>>> d.popitem(last=True)
('z', None)
>>> d
OrderedDict([('d', None), ('a', None), ('c', None), ('e', None), ('b', None)])
>>> d.popitem(last=False)
('d', None)
>>> d.popitem(last=False)
('a', None)
>>> d
OrderedDict([('c', None), ('e', None), ('b', None)]) 
```
</details>

### Itertools

<details><summary><b>combinations/permutations</b></summary>      

 - Returns iterator of tuples
 - to convert to list do list(your_iterator)   
 
 Operations:
 - itertools.combinations(list, number to choose)
 - itertools.permutations(list, number to arrange)
 - itertools.combinations_with_replacement(list, number to choose) # in python3
 - itertools.product(list, repeat=n) # For cartisian product
```                    
# Example: Generate powerset

import itertools

stuff = [1, 2, 3]
for L in range(0, len(stuff)+1):
    for subset in itertools.combinations(stuff, L):
        print(subset)
# 

a = ['A', 'B', 'C']
for x in itertools.product(a, repeat=2):
    print x
'''
('A', 'A')
('A', 'B')
('A', 'C')
('B', 'A')
('B', 'B')
('B', 'C')
('C', 'A')
('C', 'B')
('C', 'C')
'''
```
</details>

## Python Common Datastructures

<details><summary><b>list for array</b></summary>      

```
array = list()
```

### Important Operations:

```
[a:b]  Slice from index a upto, but including, b
.pop()                          O(1)
.append()                       O(1)
.extend()                       O(k)
.insert(index, element)         O(n)    
.remove(element)                O(n)
.index(element)                 O(n)
del alist[1]                    O(n) 
```
### Complexity:

All list operation in python have same average and amortized worst case complexity:

```
O(1)        : Append[1], pop from last, By index get or chance element, length
O(n)        : Insert by index, Pop/delete by index, Del Slice, min/max, reverse
O(k)        : Get Slice, Extend[1], 
O(nlogn)    : Sort
```

</details>

<details><summary><b>str for strings</b></summary> 

### Common Operations:

```

str.split([separator [, maxsplit]])         returns list, maxsplit default is -1
str.splitlines()
'#'.join(iterable)                          joins the iterable into a string with # as the separator


str.endswith(suffix[, start[, end]])        Returns True/False
str.startswith(prefix[, start[, end]])      Returns True/Falsedfd
str.strip() .lstrip() .rstrip()  

str.isupper(), islower(), lower(), upper(), isdigit()  Check/Convert to uppercase/lowercase

```

### Other Operations

ASCII/UNICODE operations:

```
ord(char)                                   Returns the unicode of the character as intiger   
chr(intiger)  #Range(0-255)                 Returns a ascii character for the given intiger    
unichr(intiger) #Range (0-65536)            Returns a unicode character for the given intiger    

>>> chr(98)
'b'
>>> unichr(98)
u'b'
>>> ord('b')
98
```

Substring Operations:
```
string.replace(oldvalue, newvalue, count)
txt = "one one was a race horse, two two was one too."
x = txt.replace("one", "three")

string.count(substring, start=..., end=...) Count substring occurance
str.find(sub[, start[, end]] )              returns -1 if not found
    First occurence
str.rfind
    Right most occurance                    returns -1 if not found
```

string library:
```
import string
string.ascii_letters                        Returns string: concatenation of the ascii_lowercase and ascii_uppercase
string.ascii_lowercase                      Returns string: lowercase letters 'abcdefghijklmnopqrstuvwxyz'
string.ascii_uppercase                      Returns string: uppercase letters 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'. 
string.digits                               Returns string: '0123456789'.
```

</details>

<details><summary><b>dict for hash tables</b></summary> 


- No duplicate
- only immutable types can be added as key.

### Most used:   

```
.values/keys/items()        returns a list of all the values/keys/items available in a given dictionary.   
.update(dict2)              Adds dictionary dict2’s key-values pairs to dict   
.get(key,                   "default value if no key in dict")  
.pop(key)                   Removes and returns an element from a dictionary having the given key.   
```

### Some interesting operations:   

```
.copy()             They copy() method returns a shallow copy of the dictionary.   
.clear()            The clear() method removes all items from the dictionary.   
.popitem()          Removes the arbitrary key-value pair from the dictionary and returns it as tuple.   
```

### Operations and Complexity:
 
```
                  Average Case      Amortized Worst Case
mydict[key]       O(1)              O(n)        
mydict[key]="aa"  O(1)              O(n) 
del mydict[key]   O(1)              O(n)
iterate           O(n)              O(n)
```   

```
knights = {'gallahad': 'the pure', 'robin': 'the brave'}
for k, v in knights.iteritems():
    print k, v
```
### How hash table is implemented:  
    - An array is used   
    - Hashing fuction to compute a hash code( int or long)   
    - hash code % array length to index it into an array   
    - collisions: two keys can have same hash code or two hash   
      codes can map to same index   
    - Linked list is used at the index in case of collisions   
    - Good hashing functions prevent collision   




</details>

<details><summary><b>set for sets</b></summary> 

- No duplicates, unordered
- Implemented similar to dict
- only immutable types can be added as members.

### Common Operations:

```
# Can also be {"a", "b","c"} 
example_set = set(["a", "b","c"]) 
  
example_set.add("d")
example_set.remove("a")
```

### Operations:

Same oprations and complexity as dict() except for the following:

```
                                            Average case                    Worst Case
- set1.union(set2)                          O(len(s)+len(t))                
- set1.intersection(set2)                   O(min(len(s), len(t))           O(len(s) * len(t)) very and can be ignored
- set1.difference(set2)                     O(len(s))
- set1.clear()
```

### More Examples:

```
# A frozen set 
frozen_set = frozenset(["a", "b","c"]

# Following not allowed on frozen set
# frozen_set.add("z")

result_set = set1.union(set2) 
result_set = set1.intersection(set2)
result_set = set1.difference(set2)

set1.clear()

```


</details>

<details><summary><b>deque for Linked Lists</b></summary> 

- Can be created using collections.deque

### Operations
```
from collections import deque

adq = deque() #  also can be dequeue([1,2,3])

adq.append("right last")            # O(1)
adq.appendleft("first")             # O(1)

adq.popleft()                       # O(1)
adq.pop()                           # O(1)

# Others
#
# extend(iterable)                  # O(k)
# extendleft(iterable)              # O(k)
# rotate(n=1)                       # O(k)
# remove(value)                     # O(n)
# reverse()                         # O(n)



# Only in Python 3
#
# count(x)                          # O(n)
# index(x[, start[, stop]])         # O(n)
# insert(i, x)                      # O(n)
# copy()       Shallow copy         # O(n)
```

</details>

<details><summary><b>deque for Stacks</b></summary> 

Can use a python list for all stack operations like:
Pop
Peek
Insert
Push
'''

</details>

<details><summary><b>deque for Queues</b></summary> 

Can use a python deque for all queue operations like:
Enqueue
Dequeue

</details>

<details><summary><b>heapq for Binary Heap</b></summary> 

-In python, default implimentation is Min heap

Binary Heap Properties

- Is a complete binary tree
- The root is min/max (also recursively true)

Operations:

    - Get Min               O(1)
    - insert                O(logn)         Insert at end and siftUp from bottom to root
    - ExtractMin            O(logn)         Replace with last element and SiftDown from root to bottom
    - Heapify/BuildHeap     O(n)            Start from last element and SiftDown from bottom to root
    - Heap sort             O(nlogn)        O(n) for Heapify + O(nlogn) for SiftDowm from root to bottom after delete

Applications:

    - Heap Sort
    - Priotiy Queue (https://docs.python.org/3/library/heapq.html#priority-queue-implementation-notes)

Complexity:
https://stackoverflow.com/questions/9755721/how-can-building-a-heap-be-on-time-complexity


```
from heapq import heappush, heappop, heapify

key = 20
heap = []
heappush(heap, key)
top_elem = heappop(heap)
un_ord_list = [1, 12, 2, 3, 15]
heapify(un_ord_list)
smallest = un_ord_list[0]
```

</details>


## Python Custom Data Structures

<details><summary><b>BST</b>

```
class Node:
    def __init__(self, val, parent):
        if not isinstance(val, numbers.Real):
            raise ValueError("BST only supports Rational Numbers")
        self.val = val
        self.parent = parent # Optional
        self.left = None
        self.right = None
        self.count = 1 # To handle duplicates
    
    # For easier recursive implementation use the following signature 
    # root = insert(root, 50) root = deleteNode(root, 20)
```
</summary> 

#### Operations:

Search          Worst case: O(n)
Insert          Worst case: O(n)
Delete(rare)    Worst case: O(n)

</details>


<details><summary><b>Tries</b>

   - Is a sub type of n-ary tree
   - has a special node/null value to indicate end of word
   ```
   class TrieNode:

       def __init__(self, key):
           self.key = key
           self.children = dict()
           self.isEndofWord = False
   ```
</summary> 

Operations:
    - insert            O(M) M is the length of string
    - Search            O(M) M is the length of string
    - Delete            Probably wont be asked

Important space complexity considerations"
    w = number of words
    m = average word length
    n = Alphabet length
    
    Correct complexity O(w*m) 

    If O(n**m) - this is assuming all nodes with all children

Example:
        root
     a         l
    s n       o  i
    h d      l   o
      y          n

</details>

<details><summary><b>Graphs</b>

- Directed / Undirected
- a tree is a connected acyclic undirected graph

```
graph = defaultdict(set)

# Key:   A vertive
# Value: Set of vertices it is connected to
```
</summary>

Operations:
    
    Operation                                   Adjacency Matrix        Adjacency Lists (Array of LL)  Adjacency dictonary of sets
    
    - Add edge                                  O(1)                    O(1)                           O(1)                         
    - Delete edge                               O(1)                    O(V)                           O(1)
    - Check for an edge                         O(1)                    O(V)                           O(1)
    - Add vertice                               O(V)/O(V^2)             O(1)                           O(1)
    - Delete Vertice                            O(V^2)                  O(V^2)                         O(1)
    
    - Find neighbours                           O(V)                    O(neighbours)                  O(neighbours)

    - space                                     O(V^2)                  O(V^2)                         O(V^2)

    V is total number of vertices

Adjacency Matrix vs Lists
    - List better for edge sparce graph as it takes up less space 
    - Adj better at time comlexity in every operation expcept for adding a Vertice
    - List slightly better at finding neighbours

</details>

<details><summary><b>N-arry trees</b>

   - Rarely asked
   - Traversals may be asked

``` Node implementation similar to BST```

</summary> 
</details>

<details><summary><b>Binary Trees</b>

- Rarely asked as not many practical applications
- Traversals/Serialization may be asked

``` Node implementation similar to BST```

</summary> 
</details>


<details><summary><b>Balanced Binary Trees</b> 

   - Only need to know how they work (AVL or Red Black)
   - Rarely asked

``` Node implementation similar to BST. Operations' implementations wont be asked```

</summary> 

#### AVL Tree - A balanced BST
 - At every node, right subtree and left subtree heigt difference is maintained
 - Insertion
     - LL and RR - one rotation to fix the height
     - LR and RL - two rotations to fix the height (One to make them LL/RR and another to fix LL/RR)
     - https://www.youtube.com/watch?v=YKt1kquKScY
 - Deletion 
     - Similarish to deletion from BST
     - https://www.youtube.com/watch?v=g4y2h70D6Nk

 - Search/Inserion/Deletion  O(logn) 
</details>

## Python Custom Compare Functions

Just need to supply ```__eq__``` and one other like ```__lt__```. Rest is supplied by ```@functools.total_ordering```

```
import functools

@functools.total_ordering
class Element:
    def __init__(self, count, word):
        self.count = count
        self.word = word
        
    def __lt__(self, other):
        if self.count == other.count:
            return self.word > other.word
        return self.count < other.count
    
    def __eq__(self, other):
        return self.count == other.count and self.word == other.word
```

## Python Multithreading

 - Lock vs Mutex vs Semaphore - https://stackoverflow.com/questions/2332765/lock-mutex-semaphore-whats-the-difference
 - Thread vs Process  - Threads share the heap (https://www.backblaze.com/blog/whats-the-diff-programs-processes-and-threads)
 - Locks, RLocks, Semaphores, Conditions and Queues - https://www.laurentluce.com/posts/python-threads-synchronization-locks-rlocks-semaphores-conditions-events-and-queues
 - Daemon - A thread that runs in the background. Unlike normal threads, the main process will not wait for it to complete unless .join() is called explictly.
 - With statement does .acquire() and .release()
 

   <details><summary><b>Threading class implementation</b></summary>

   ```
   class FetchUrls(threading.Thread):
      """
      Thread checking URLs.
      """

      def __init__(self, urls, output):
          """
          Constructor.

          @param urls list of urls to check
          @param output file to write urls output
          """
          threading.Thread.__init__(self)
          self.urls = urls
          self.output = output

      def run(self):
          """
          Thread run method. Check URLs one by one.
          """
          while self.urls:
              url = self.urls.pop()
              req = urllib2.Request(url)
              try:
                  d = urllib2.urlopen(req)
              except urllib2.URLError, e:
                  print 'URL %s failed: %s' % (url, e.reason)
              self.output.write(d.read())
              print 'write done by %s' % self.name
              print 'URL %s fetched by %s' % (url, self.name)

   # Taken From https://www.laurentluce.com/posts/python-threads-synchronization-locks-rlocks-semaphores-conditions-events-and-queues/      
   ```
   </details>
 
 ### Locks
  - Only between threads of same process 
  
    <details><summary><b>Example</b></summary>

    ```
    import threading
    lock = threading.Lock()
    self.lock.acquire()
    # Critical section
    self.lock.release()
    ```
    </details>

 ### RLock
 - Same as lock except acquire() can be called by same thread multiple times without blocking. (Need to be released the same number of times)
 
   <details><summary><b>Example</b></summary>

    ```
    import threading
    rlock = threading.RLock()
    ```
   </details>

 ### Condition
 - Produces/ Consumer act on a condition. One lock for both so either producer or consumer can get lock at once

   <details><summary><b>Details</b></summary>

    - https://docs.python.org/2.0/lib/condition-objects.html) (https://www.agiliq.com/blog/2013/10/producer-consumer-problem-in-python/

    - Producer
        1. Get lock using aquire()
        2. Add resource to queue
        3. notify() of new item
        4. Release lock

    - Consumer
        1. Get lock using aquire()
        2. Work on items in queue until empty 
        3. wait() until notify() for new item ( lock is released when wait() is entered)
        4. reawake and aquire lock when notify() is called and do consumption
        5. release() condition after consumption is complete so that producer can get it to add data/resource to queue.
   </details>

 ### Semaphore
 
 - Counter to manage resource pool
 - aquire() decrements
 - release() increments
 
   <details><summary><b>Example</b></summary>

   ```
   semaphore = threading.Semaphore(10) # Default is 1 pool size
   semaphore.acquire()
   # Critical section 
   semaphore.release()
   ```
   </details>
 
 ### Queues 
 
  - Better approach for producer/consumer problems   
  - HAVE to call .task_done() after every get is complete - its used by .join() to determine completion     
  
    <details><summary><b>Example</b></summary>

      ```
      from queue import Queue
      def worker():
        while True:
            item = q.get()
            do_work(item)
            q.task_done()

      q = Queue()
      for i in range(num_worker_threads):
           t = Thread(target=worker)
           t.daemon = True
           t.start()

      for item in source():
          q.put(item)

      q.join()       # block until all tasks are done

      # Source: https://docs.python.org/2/library/queue.html
      ```
    </details>
    
## Decorators:

  - Think them as factory fucntions which produce custom functions for us
  - *args and \**kwargs are arguments that are passed through (they match any signature)
  - https://jeffknupp.com/blog/2013/11/29/improve-your-python-decorators-explained/

  
    <details><summary><b>Basic Example</b></summary>
 
    ```
    from functools import wraps
    def decor(func):
       def wrapper():
           print("Outer")
           func()
           print("Outer")
       return wrapper

    def inner_f():
        print("Inner")

    # This is function decoration
    inner_f = decor(inner_f)

    # Syntactic suger for the above
    @decor
    def inner_f2():
        print("Inner")

    """
    >>> inner_f()
    Outer
    Inner
    Outer
    >>> inner_f2()
    Outer
    Inner
    Outer
    """

    ```
  
    </details>
    
    <details><summary><b>Example with arguments to inner function</b></summary>

    ```
    from functools import wraps

    def decor(func):   
       def wrapper(*args, **kwargs):
           print("Outer")
           func(*args, **kwargs)
           print("Outer")
       return wrapper

    def inner_f(i):
        print("Inner",i)

    # This is function decoration
    inner_f = decor(inner_f)

    # Syntactic suger for the above
    @decor
    def inner_f2(i):
        print("Inner",i)

    """
    >>> inner_f(2)
    Outer
    ('Inner', 2)
    Outer
    >>> inner_f2(2)
    Outer
    ('Inner', 2)
    Outer
    >>> 
    """

    ```

    </details>
    
    <details><summary><b>Example with arguments to inner function and decorator function</b></summary>
        
    - Essentially one more layer of function. (https://stackoverflow.com/questions/5929107/decorators-with-parameters)
    - The outer most layer HAS to be a function that returns a decorator
    - Essentially the availability of outer args to inner functions is the advantage here.

    ```
    from functools import wraps

    def decor_with_args(ar):
        def decor(func):   
           def wrapper(*args, **kwargs):
               print("Outer ", ar)
               func(*args, **kwargs)
               print("Outer ", ar)
           return wrapper
        return decor

    def inner_f(i):
        print("Inner",i)

    # This is function decoration
    inner_f = decor_with_args("with arg")(inner_f)

    # Syntactic suger for the above
    @decor_with_args("with arg")
    def inner_f2(i):
        print("Inner",i)

    """
    >>> inner_f(1)
    ('Outer ', 'with arg')
    ('Inner', 1)
    ('Outer ', 'with arg')
    >>> inner_f2(1)
    ('Outer ', 'with arg')
    ('Inner', 1)
    ('Outer ', 'with arg')
    >>> inner_f2(2)
    ('Outer ', 'with arg')
    ('Inner', 2)
    ('Outer ', 'with arg')
    """

    ```
  
    </details>
  
## Python Gotchas
- Copies of list all point to the same object
- lista[1::-1] doesnt work, use lista[1:][::-1] instead
- Variable scope in nesteled function needs 'nonlocal' for non mutable types (https://stackoverflow.com/questions/2609518/unboundlocalerror-with-nested-function-scopes)
- for defaultdict always use list(d.items()) instead of d.items() (https://stackoverflow.com/questions/8762819/runtimeerror-dictionary-changed-size-during-iteration-during-iteration-with-i) 
- Defualt return value of python function in None not True

## Cool Links

https://bradfieldcs.com/algos/


## Foot Notes:
[1] : Amortized, indivisual operation might take long

## References:
    * Python.org
    * Geeksforgeeks.com
    * leetcode.com
    * google.com
    * stackoverflow.com
    * hackerrank.com
    * realpython.com
    * www.laurentluce.com
    * www.agiliq.com
    * jeffknupp.com
    * Lots of Random websites, thanks to google. 
