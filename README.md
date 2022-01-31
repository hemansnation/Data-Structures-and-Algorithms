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
