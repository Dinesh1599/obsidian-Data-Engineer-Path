
## Overview
**Lazy Evaluation** is Spark’s execution strategy where **transformations are not executed immediately**.  
Instead, Spark records operations, builds an optimized execution plan (DAG), and only executes when an **action** is triggered.
--- 
## What lazy Evaluation mean?

When writing a spark transformation
```python
df = spark.read.csv("data.csv")
df2 = df.filter("age > 25")
df3 = df2.select("name","city")
```

Data isn't processed here. Instead Spark
- Records the transformation
- Builds a logical plan
The Execution only happens when a [[Spark Action]] is called.
eg:  df3.show()

At that point, Spark:
- Finalizes the DAG
- Optimizes the plan
- Splits work into [[Job, Stages and Tasks]]
- Executes tasks on executors.
--- 
## Why use Lazy Evaluation
- Optimize the entire computation plan
- Eliminate unnecessary operations
- Combine transformations into fewer execution steps
- Reduce disk I/O and shuffles
- Improve overall performance
---
## DAG and Lazy Evaluation
Lazy evaluation enables Spark to:
- Build a **Directed Acyclic Graph (DAG)** of transformations
- Understand dependencies between operations
- Schedule tasks efficiently
- Recompute lost data using lineage ([[Fault Tolerance]])
