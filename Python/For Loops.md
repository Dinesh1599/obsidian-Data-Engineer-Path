Syntax:

```python

fruits = ["apple", "banana", "cherry"]  
for x in fruits:  
  print(x)

```

There is a more cleaner way of using for loops as well

1. List comprehension
```python

# Traditional for loop
squares = []
for i in range(5):
    squares.append(i**2)

# List comprehension
squares = [i**2 for i in range(5)]

```

2. Generator expression
```python

# Generator expression
even_numbers = (i for i in range(10) if i % 2 == 0)
for num in even_numbers:
    print(num)

```

A little more sophisticated example is used in [[Data Types and Structures]]