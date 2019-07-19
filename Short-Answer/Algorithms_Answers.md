# Analysis of Algorithms

## Exercise I

Give an analysis of the running time of each snippet of
pseudocode with respect to the input size n of each of the following:

```
a)  a = 0
    while (a < n * n * n):
      a = a + n * n
```
(n^3)/(n^2) = O(n), Linear time.

```
b)  sum = 0
    for i in range(n):
      i += 1
      for j in range(i + 1, n):
        j += 1
        for k in range(j + 1, n):
          k += 1
          for l in range(k + 1, 10 + k):
            l += 1
            sum += 1
```
4 nested loops, but only 3 are dependent on n. Loop depth is 3, so time complexity is O(n^3), Cubic time.

```
c)  def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
```
our function is dependant on only the number of bunnies, so our time complexity is O(bunnies), which is equivalent to O(n), Linear time.

## Exercise II

Suppose that you have an _n_-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor _f_ or higher, and doesn't get broken if dropped off a floor less than floor _f_. Devise a strategy to determine the value of _f_ such that the number of dropped eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode and give the runtime complexity of your solution.

function drop_egg(return result), where result is either broken or unbroken

function binary_search(arr, n, f):
    Min := 0
    Max := n − 1
    while Min <= Max:
        Mid := drop_egg((Min + Max) / 2)
        if A[Mid] < f:
            Min := Mid + 1
        else if A[Mid] > f:
            Max := Mid - 1
        else:
            return Mid
    return unsuccessful

    Time complextiy of binary search is O(Log n), Logarithmic time.