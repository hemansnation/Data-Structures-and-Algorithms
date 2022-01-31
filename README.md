# Data-Structures-and-Algorithms


## Time Complexity

The time complexity of an algorithm estimates how much time the algorithm will use for some input. 

By calculating the time complexity, we can find out whether the algorithm is fast enough without implementing it.

### How Calculation works?

O(n)- If the input is an array of numbers, n will be the size of the array, and if the input is a string, n will be the length of the string.

#### Loops

If the algorithm have k nested loops then the complexity is O(n^k).

```python
for i in range(3):
  # code

```

It will be O(n^2) if:

```python
for i in range(3):
  for j in range(3):
      # code

```

#### Order of magnitude

A time complexity does not tell us the exact number of times the code inside a loop is executed, but it only shows the order of magnitude.

All the 3 code inside the loop is executed 3 n , n + 5 and [n/2] times, but the time complexity of each code is O ( n ).


```python
for i in range(3*n):
  # code
 
for i in range(n + 5):
  # code

for i in range(n / 2):
  # code

```

#### Phases
If the algorithm consists of consecutive phases, the total time complexity is the largest time complexity of a single phase. The reason for this is that the slowest phase is usually the bottleneck of the code.

For example, the following code consists of three phases with time complexities O ( n ), O ( n^2 ) and O ( n ). Thus, the total time complexity is O ( n^2 ).


```python
for i in range(n):
  # code
 
for i in range(n):
  for j in range(n):
      # code

for i in range(n):
  # code

```

#### Several variables

Sometimes the time complexity depends on several factors. In this case, the time complexity formula contains several variables. 

For example, the time complexity of the following code is O ( n^m ):

```python
for i in range(n):
  for j in range(m):
      # code
```

#### Recursion
The time complexity of a recursive function depends on the number of times the function is called and the time complexity of a single call. The total time
complexity is the product of these values.

The call f ( n ) causes n function calls, and the time complexity of each call is O (1). Thus, the total time complexity is O ( n ).
```python
def f(n):
  if (n == 1) return
  f(n-1)
```

In this case each function call generates two other calls, except for n = 1. Let us see what happens when g is called with parameter n .

```python
def f(n):
  if (n == 1) return
  f(n-1)
  f(n-1)

```
The time complexity will be:
1 + 2 + 4 + · · · + 2^(n − 1) = 2^(n − 1) = O (2^n ).



