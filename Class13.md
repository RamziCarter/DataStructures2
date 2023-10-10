Sorting Continued

> Merge Sort



> Quick Sort
- we use pivots to start the sorting algorithm
- Quick sort is generally quick. Depending on the algorthim, even if you picked the worst possible pivot. 
Each time you are pulling out the maximum. In the worst case scenario the time complexity is O(n^2)
most of the time quick sort will be n log (n)

__Example Below__

```
      10 2 4 7 12 16 8 6 3 5 17 20 9
      
                  8
      
      2 4 7 3 6 5   10 12 16 17 20
      
          6                17
      
 2 4 3 5    7     10 12 16    20
            
    3

2     4 5 7

```
---

Binary Search
- this only works on a sorted array
- consider that when we search sorted array A of size n for value t. We search from indexwa 0 to n-1.
- Suppose I jump to an intermediate index x. If

Run time
- each step of recursion you are dividing the problem by two
- log (n)

__for binary search__
Best case is O(1)
Worst case is O(log n)
__for linear search__
Best case is O(1)
Worst case is O(n)


```Java
public boolean binarySearch(int [] list, int target, int start, int end)
{
// start of the aray is 0
// end of array is n - 1
// (end - start) / 2 is mid

if (list.length == 0)
{
      return false
}

if(start > end)
{
      return false;
}

// find half the length, add start so offset is correct
int mid = ((end - start) / 2) + start;
if(list [mid] == target
{
return mid;
}

else if(list[mid] < target)
{
      return binarySearch(list. target, mid + 1, end)
}
else
{
      return binarySearch(list. target, start, mid + 1)
}
```


