basic way of using if - else

```python

a = 33  
b = 200  
if b > a:  
	print("b is greater than a")
else:
	print("a is greater than b")

```

- There are logical conditions of using if else as well
	- Equals: a == b
	- Not Equals: a != b
	- Less than: a < b
	- Less than or equal to: a <= b
	- Greater than: a > b
	- Greater than or equal to: a >= b

ELIF
	if the previous conditions were not true, then try this condition
`
```python
a = 33  
b = 33  
if b > a:  
  print("b is greater than a")  
elif a == b:  
  print("a and b are equal")

```

Short-hand if else
	When you have only 1 statement to execute (keeps the code a little clean)
```python

a = 2  
b = 330  
print("A") if a > b else print("B")

```

Logical Operators
	1. AND - must accept both conditions
	2. OR - returns true if one of the 2 conditions is true
	3. NOT  - reverse the result


PASS
	put in the `pass` statement to avoid getting an error when you have an IF statement empty
	

#MATCH (the switch case of python)

syntax:
match expression:
  case x:
    code block
  case y:
    code block
  case z:
    code block
case _ (unberscore):
	if there is an _ : this is basically default value that is returned...