Reusable blocks of code.

Basic Syntax and how the function is called
```python

def my_function():  
  print("Hello from a function")  
  
my_function()

```

Arguments and Parameters
- A parameter is the variable listed inside the parentheses in the function definition.
- An argument is the value that is sent to the function when it is called.

Arguments:
```python

def my_function(fname, lname):  
  print(fname + " " + lname)  
  
my_function("Emil", "Refsnes")

```

Now, If you don't now how many arguments are gonna be passed into the function, add a `*` to the arguments

```python

def add_numbers(*args):
	print (args[1])    # 2
    total = sum(args)
    return total

print(add_numbers(1, 2, 3))       # 6
print(add_numbers(5, 10, 15, 20)) # 50

```

The are for keyword arguments and arbitrary keyword arguments:

Keyword Arguments
```python

def my_function(child3, child2, child1):  
  print("The youngest child is " + child3)  
  
my_function(child1 = "Elon", child2 = "Toby", child3 = "Linus")

```

Arbitrary Keyword Arguments (Here you can use `**`)
```python

def my_function(**kid):  
  print("His last name is " + kid["lname"])  
my_function(fname = "Toby", lname = "Danny")

```

Default Parameter Value
```python

def my_function(country = "Norway"):  
  print("I am from " + country)  
  
my_function("Sweden")  
my_function("India")  
my_function()  
my_function("Brazil")

```


There is this other way of doing functions called [[Lambda]]

When do we use them?

|Use **`def` function** when…|Use **`lambda` function** when…|
|---|---|
|You’re building a reusable data transformation step in your pipeline.|You need a quick, inline transformation for something like `map()`, `filter()`, or `sorted()`.|
|The logic spans **multiple lines** (e.g., parsing, validation, cleaning).|The logic is **a single expression** (one-liner).|
|The function will be **called in multiple scripts or jobs**.|It’s used **immediately and only once** in a small context.|
|You need to **debug or add comments** for clarity.|It’s self-explanatory and temporary.|
|Example: Normalizing column names, validating records, handling exceptions.|Example: Sorting by a field length or extracting a key from a tuple.|

## ==A Data Engineer's perspective==
- **`def`** → Ideal for **ETL steps, UDFs (user-defined functions) in Spark/Pandas**, and anything part of your core data flow.
- **`lambda`** → Ideal for **inline column transformations** in `df.apply()` or when defining small key functions for `sorted()` or `groupby()`.