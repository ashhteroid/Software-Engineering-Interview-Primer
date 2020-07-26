# Meta

## Thinking from a problem creators perspective.

General Pattern seems to be:  

**Take an exponential problem, add a way to reduce problem/solution space and add a twist.**
```
Exponential problem = Usually has a bad brute force solution.   

Reducer = Usally some condition/exploit/limitation/ds/algo/paradigm that eliminates some problem/solution space.

Twist = What makes problems look different. Might be hard to guess right away without help.  
        - Look for some sort of inefficiency.  
        - Use intuition/common sense.
```

#### Examples
1. DS reducer:

```

Example: https://leetcode.com/problems/decode-string/
        Exponential problem = O(n**2) time and space  

        DS = O(n) space, reduces the problem to linear time

        Twist = Lots of different cases to handle
```

## Tips on speed

Speed seems to depend on:
1. Ability to come up with a psedocode fast
2. Ability to translate the pseudocode into code

### Ability to come up with a psedocode fast (Time management and practice)
- Seems to depend on choosing the approach - always choose the approach that can be turned into psuedocode by '20mins left' mark.  
        ```Better to a have a less efficient approach that to have one that cant be implemented in time.```
- More practice gives more tools to do make solutions efficient and fast.   
        ```After solving a problem, figure out how to make that logic faster/shorter.```

### Ability to translate the pseudocode into code
- Seems to depend on code mastery and knowledge of code libraries   
        ```After solving a problem, figure out how to use libraries to make logic faster/shorter.```
- Practice implementing tons of problems and this should be natural   
        ```After solving a problem, figure out how to use tricks/standard practices to make logic faster/shorter```
        
### In Essence

While solving:
```
      Find an efficient-ish approach can be implemented in time. ( There is always at least a brute force solution)
      Always have complete psedocode figured out before implementation.
```
After Solving (during prep):
```
      Figure out how to make that logic faster/shorter
      Figure out how to use libraries to make logic faster/shorter
      Figure out how to use tricks/standard practices to make logic faster/shorter
```

