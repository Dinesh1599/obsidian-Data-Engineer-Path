1. Started
2. Suspended
3. Resizing

Key Points:
1. When a Vwh is created its automatically started
2. Can be suspended or resumed with a SQL command or with UI
		- ALTER WAREHOUSE MY_WH SUSPEND/RESUME;

**Auto SUSPEND**:
	Syntax:
		CREATE WAREHOUSE my_med_wh
		==AUTO_SUSPEND=300;== (5min)
	Note: 
		- If AUTO_SUSPEND IS SET TO 0: WH will never suspend
		- default suspend value is at 600 (10min)

- if suspended, caching is removed. Hence querying take longer when resumed.
- if a vm is suspended in several intervals, it billed for 60 seconds minimum for every resume

**Auto RESUME**:
	Specifies whether to automatically resume a wh when a SQL statement is submitted to it.
	CREATE WAREHOUSE my_wh
	AUTO_RESUME = TRUE (only accepts boolean.)

**Initially Suspended**:
CREATE WAREHOUSE my_wh
	INITIALLY_SUSPENDED = TRUE (only accepts boolean)

Tells to create a vh to get created and set at suspend.

