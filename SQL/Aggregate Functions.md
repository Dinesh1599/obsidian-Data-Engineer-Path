Aggregate functions are often used with the ==GROUP BY== clause of the SELECT statement.

- MIN() - returns the smallest value within the selected column
- MAX() - returns the largest value within the selected column
- COUNT() - returns the number of rows in a set
- SUM() - returns the total sum of a numerical column
- AVG() - returns the average value of a numerical column

Aggregate functions ignore null values (except for COUNT(*)).


1. MIN() and MAX()

	SELECT MIN(_column_name_)  
	FROM _table_name_  
	WHERE _condition_;
	
	SELECT MAX(_column_name_)  
	FROM _table_name_  
	WHERE _condition_;

2. COUNT()
	 SELECT COUNT(*)  
	FROM Products;