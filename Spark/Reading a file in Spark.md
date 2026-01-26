#NmE

Reading a CSV File

```python

df = spark.read.format("csv").option('inferSchema', True).option('header', True).load('/Volumes/workspace/default/tutorial/BigMart Sales.csv')

```

Reading a JSON file:

```python
df_json = spark.read.format('json').option('inferSchema', True)\
	.option('header', True)\
	.option('multiline',False)\
	.load('/Volumes/workspace/default/tutorial/drivers.json')
```

Typical way to display then is as simple as ```df.display()```

