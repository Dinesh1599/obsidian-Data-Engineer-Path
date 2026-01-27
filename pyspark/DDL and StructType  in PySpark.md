The same thing as [[DDL]] in SQL

Code that does DDL in Pyspkark

-  Say you have a CSV file you want to load as a DF
- option inferSchema does help with setting up datatype for a DF in pyspark
- but when creating a custom schema its done in these ways
### 1. The DDL Method

```python
my_ddl_schema = '''
                    Item_Identifier STRING,
                    Item_Weight STRING,
                    Item_Fat_Content STRING, 
                    Item_Visibility DOUBLE,
                    Item_Type STRING,
                    Item_MRP DOUBLE,
                    Outlet_Identifier STRING,
                    Outlet_Establishment_Year INT,
                    Outlet_Size STRING,
                    Outlet_Location_Type STRING, 
                    Outlet_Type STRING,
                    Item_Outlet_Sales DOUBLE 
                '''
```

```python
df = spark.read.format("csv").schema(my_ddl_schema).option('header', True).load('/Volumes/workspace/default/tutorial/BigMart Sales.csv')
```

we mention the schema in ```.schema()``` option
### 2. StructType method
```python
from pyspark.sql.types import * 
from pyspark.sql.functions import *

my_strct_schema = StructType([
		StructField('Item_Identifier',StringType(),True),
		StructField('Item_Weight',StringType(),True),
		StructField('Item_Fat_Content',StringType(),True),
		StructField('Item_Visibility',StringType(),True),
		StructField('Item_MRP',StringType(),True),
		StructField('Outlet_Identifier',StringType(),True),
		StructField('Outlet_Establishment_Year',StringType(),True),
		StructField('Outlet_Size',StringType(),True),
		StructField('Outlet_Location_Type',StringType(),True), 
		StructField('Outlet_Type',StringType(),True),
		StructField('Item_Outlet_Sales',StringType(),True)
])

```

```python
df = spark.read.format("csv").schema(my_ddl_schema).option('header', True).load('/Volumes/workspace/default/tutorial/BigMart Sales.csv')
```

Syntax: 
```python
StructType([
	StructField(name, dataType, nullable)
])
```

Note: DDL is a little more easier cuz honestly, you don't have to type much. Gives the same result 

