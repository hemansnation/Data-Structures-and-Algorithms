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


## Complexity classes
The following list contains common time complexities of algorithms:

- O (1) The running time of a constant-time algorithm does not depend on the input size. A typical constant-time algorithm is a direct formula that calculates the answer.
- O (log n ) A logarithmic algorithm often halves the input size at each step. The running time of such an algorithm is logarithmic, because log 2 n equals the number of times n must be divided by 2 to get 1.
- O (root(n) ) A square root algorithm is slower than O (log n ) but faster than O ( n ). A special property of square roots is that n = n / root(n) , so the square root n lies, in some sense, in the middle of the input.
- O ( n ) A linear algorithm goes through the input a constant number of times. This is often the best possible time complexity, because it is usually necessary to access each input element at least once before reporting the answer.
- O ( n log n ) This time complexity often indicates that the algorithm sorts the input, because the time complexity of efficient sorting algorithms is O ( n log n ). Another possibility is that the algorithm uses a data structure where each operation takes O (log n ) time.
- O ( n^2 ) A quadratic algorithm often contains two nested loops. It is possible to go through all pairs of the input elements in O ( n^2 ) time.
- O ( n^3 ) A cubic algorithm often contains three nested loops. It is possible to go through all triplets of the input elements in O ( n^3 ) time.


- O (2^n ) This time complexity often indicates that the algorithm iterates through all subsets of the input elements. For example, the subsets of {1, 2, 3} are: {1}, {2}, {3}, {1, 2}, {1, 3}, {2, 3} and {1, 2, 3}.
- O ( n !) This time complexity often indicates that the algorithm iterates through all permutations of the input elements. For example, the permutations of {1, 2, 3} are (1, 2, 3), (1, 3, 2), (2, 1, 3), (2, 3, 1), (3, 1, 2) and (3, 2, 1).


- An algorithm is polynomial if its time complexity is at most O ( n^k ) where k is a constant. All the above time complexities except O (2^n ) and O ( n!) are polynomial. In practice, the constant k is usually small, and therefore a polynomial time complexity roughly means that the algorithm is efficient. Still, there are many important problems for which no polynomial algorithm is known, i.e., nobody knows how to solve them efficiently. 
- NP-hard problems are an important set of problems, for which no polynomial algorithm is known
