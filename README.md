# mindDump
A repository of random thoughts yet to be organised

## Time Complexity

- Time complexity is a measure of how long it takes a computer to run a particular piece of code.

- It is important to understand this because it can be the difference between a good and bad algorithm

- Big-Oh notation defines the maximum or longest possible time it will take an algorithm to run (AKA - worst case)

- With Time Complexity, we only care about how the time taken to run the algorithm increases when the input size increases. We do not care about the speed of the computer, its architecture or other external factors.

- The point of it is to define a generic computer that will have the following properties:

All the steps in the code are executed line by line (sequentially)
It takes 1 time unit to do arithmetic (+ / * - ) and logical (OR AND) operations
It takes 1 time unit to assign something to a variable or return from a function

This time unit can be assumed as any value but generally is Time Unit = 1

- To calculate the run time complexity we can do a Cost, Number of Times, where the cost is the time unit taken to execute the line of code, and the number of times is the number of times that the line is executed. When we work out the time complexity we do **Cost * Number of Times**, to identify the type of equation it is.

```
SumOfList(int[] array, int size)
{
  total = 0;          // Line 1.
  for (int i = 0 ; i < size ; i++) { // Line 2.
    total = total + array[i]; // Line 3.
  }
  return total; // Line 4
}
```
| Line Number | Cost | Number of Times  |
| :---------: |:----:| :---------------:|
| 1           |  1   | 1                |
| 2           |  2   | n + 1            |
| 3           |  2   | n  (within loop) |
| 4           |  1   | 1                |

For the above snippet of code, the Time Complexity would be - 

```
TsumOfList = (1*1) + (2 * (n+1)) + (2*n) + (1*1) 
           = 1 + 2(n+1) + 2n + 1
           = 1 + 2n + 2 + 2n + 1
           = 4 + 4n
           = n
```

The reason that we reduce to n is because for significantly large inputs, the constants will be largely irrelevant. As the time complexity of this algorithm is O(n) we can say that it is a **linear time** algorithm.

```
Sum (int a, int b) 
{
  return a + b; // Line 1.
}
```

| Line Number | Cost | Number of Times  |
| :---------: |:----:| :---------------:|
| 1           |  2   | 1                |

For the above snippet the time complexity will be -

```
TSum = 2 * 1
     = 2
```

Because there is no n, we can say that for all types of input, it will always take a constant time unit of 2. This means that this algorithm is O(1) so we can say that it is a **constant time** algorithm.
