# Analysis of Algorithms

## Exercise I

Give an analysis of the running time of each snippet of
pseudocode with respect to the input size n of each of the following:

```python
a)  a = 0
    while (a < n * n * n):  # O(n) --> max, less if n negative
      a = a + n * n         # O(1) --> single calculation/reassignment  
                            # O(n * 1) ==> O(n)
```


```
b)  sum = 0
    for i in range(n):  # O(n)
      j = 1             # O(1)
      while j < n:      # O(n) --> max, less if n < 1
        j *= 2          # O(log n) --> Each pass of while loop reduces n by a factor of 2. Does not reset to 1 for each i in range n because while loop finishes before next i in range
        sum += 1        # O(1) --> single calculation/reassignment
                        #  |for......|while
                        # O(n * (1 + n * (log n + 1))) --> remove constants
                        # O(n * (log n)) --> remove all but worst case operation
                        # O(n log n)
```

```
c)  def bunnyEars(bunnies):
      if bunnies == 0:
        return 0                        # O(1 * 1) --> test if stmt/single return

      return 2 + bunnyEars(bunnies-1)   # O(1 + c^n-1) --> 
                                        # O(1 * 1) + O(1 + c^n-1) --> remove constants
                                        # O(1) + O(c^n) --> leave worst case operation 
                                        # O(c^n)
```

## Exercise II

Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode AND give the runtime complexity of your solution.


To solve this problem I would use iterative binary search which has O(log n) time complexity.

Pseudocode:


def find_f(n):
    # create array of floors 
    floors = [] * range(n)          # O(n)

    # track lowest floor that breaks the egg
    lowest = 0

    # set  initial pointers for array
    mid = n // 2
    high = n
    low = 0

    throw egg from mid floor:       #O(1)
    if breaks:                      #O(1)
        lowest == mid               #O(1)
        high = mid -1               #O(1)
        find_f(mid)                 


    
    




