Similar to [[DML]]  - INSERT and UPDATE query.

There is INSERT OVERWRITE - This query truncates the whole table and then only inserts the values provided

Query: 
INSERT OVERWRITE INTO 'dbo.schema.table'  (<col1>,<col2>) vales
	(1,'abc'),
	(2,'def');