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

### Asymptotic Notation

- We use asymptotic notation to generalise algorithms to classify how they would run on a theoretical machine.
- Big Oh notation is the upper bound (the worst case) - There exists a value C that will always make g(n) > f(n)
- Big Omega notation is the lower bound (the best case) - There exists a value C that will always make g(n) < f(n)
- Big Theta notation is the middle bound (the average case) - There exists values C1 and C2 - C1g(n) <= f(n) <= C2g(n)

The constant values can be anything that are positive or greater than 0.

- The notation is stated as - "There exists a value C that for significantly large n (input size)...."

### General Rules For Time Complexity

- You can remove the lower order terms and the constant multiplier for the remaining term for an equation for T(n)
- The run time of a loop is found by multiplying the times the loop runs against the time taken to execute the commands within the loop.
- You can find the runtime of a function by adding the fragments together.

```
someMethod() {
  int a;
  a = 5; // 1.
  a++;
  
  for (i = 0; i < n; i++) { // 2.
    // Some simple statements
  }
  
  for (i = 0; i < n; i++) { //3.
    for (j = 0; j < n; j++) {
      // Some simple statements
    }
  }
}
```

In the above code snippet, the runtime can be calculated by adding the time taken to execute steps 1, 2 and 3.

```
T(n) = O(1) + O(n) + O(n^2)
T(n) = O(n^2)
```

It is **O(n^2)** as the other terms will become insignificant as the value of n -> infinity.

This means that the largest fragement of a function will determine the maximum time taken for the function to run. 

- If the function we are dealing with contains **conditional statements**, the rule here to determine the worst case runtime complexity will be the condition that contains the worst case, we do not add them together.

```
function() {
  if (some condition) {
    for (i = 0; i < n; i++) { 1.
      // Some simple statements
    {
  }
  else {
    for (i = 0; i < n; i++) {  //2.
      for (j = 0; j < n; j++) {
        // Some simple statements
      }
    }
  }
}
```

The time complexity in the above snippet will be T(n) = O(n^2) as the **else** condition will be the one that takes longer to run.

### Space Complexity

- Is a measurement of how efficient the code uses memory, and is the same as how you would calculate time complexity.
- It is just the largest piece of memory that is used when the program is run.


