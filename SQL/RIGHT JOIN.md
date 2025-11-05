The RIGHT JOIN keyword returns all records from the right table (table2), and the matching records from the left table (table1). The result is 0 records from the left side, if there is no match.


SELECT _column_name(s)_  
FROM _table1_  
RIGHT JOIN _table2  
_ON _table1.column_name_ = _table2.column_name_;

![[Pasted image 20251105011529.png]]