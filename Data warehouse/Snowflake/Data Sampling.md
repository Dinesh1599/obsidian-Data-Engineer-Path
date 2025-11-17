What it is...

1. Data Sampling is the process of selecting a **smaller portion** of a large dataset so you can analyze it **faster**, **cheaper**, or **more efficiently**—while still getting results that represent the whole dataset.


Snowflake Sampling method:

1. Row or Bernoulli
	1. Select * from table 
		SAMPLE ROW (p) SEED(n)
2. Block or System method
	1. Select * from table 
		SAMPLE SYSTEM (p) SEED(n)

Where **p** is the percentage of rows needed and **n** is the seed value

Difference


| Row                                         | System                               |
| ------------------------------------------- | ------------------------------------ |
| Every row is chosen with percentage p       | Every block is chosen with partition |
| More random                                 | More efficient partitioing           |
| Best for smaller tables and real randomness | for Larger Tables                    |


