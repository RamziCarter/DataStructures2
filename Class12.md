
> I was late to class by 20 mins, but I cam in and we were discussing Big(O) notation


#### Algorithm testing to see which is faster
* lean log (n) & n log (n)
 * will be tested on this material


---

Algorithms are most frequently rated in terms of their worst case run time
```
Big Omega

we are saying it requires at least that much time/space
```

```
Big Theta

we are saying no matter what the data looks like the algoritm always runs within a constant multiplier of that complexity
```

Choosing your data struture
- when analyzing and comparing data structures it is good to look at how efficient each of their operations are
  - consider a linked list __How efficient is it to search for an element? Best case? Worst Case?__
  - __How about inserting?__
- when choosing a data structure you need to think of the operations your program and data will be doing

---
Selection Sort
O(n^2)

for every item in the array:
  find the minimu, element in the unsorted part of the array (subaarray)
  swaw the minimum element for the first one in the unsorted array
  // the unsorted array is now one smaller


  Psuedo code:
  set min)index to the first item in the sup array
  loop through sub array
    if the current item is amaller than the item at the minimum index
    set min_index to currrent index
  (< Slide 21)

> What about a dataset that was in reverse order?
* How fast would it finish on a dataset that was already sorted
  * Because all of these cases have the same run time, we can say that Selection sort run time is O(n^2)

#### Space Complexity

what is the space complexiity of selection sort?
* constant: only created variables
* not dependent on the size of an array

>Recursion

Base Case
---

> Divide & Conquer
Merge Sort:
* The idea behind divide and conquor is to split
* n log (n)
  
--- 
Quicksort
 
