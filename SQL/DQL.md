DQL is used to fetch data from the database. The main command is SELECT, which retrieves records based on the query. The output is returned as a result set (a temporary table) that can be viewed or used in applications.

| Command    | Description                                                              | Syntax                                                                                                  |
| ---------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| **SELECT** | It is used to retrieve data from the database                            | SELECT column1, column2, ...FROM table_name WHERE condition;                                            |
| FROM       | Indicates the ****table(s)**** from which to retrieve data.              | SELECT column1  <br>FROM table_name;                                                                    |
| WHERE      | Filters rows ****before**** any grouping or aggregation                  | SELECT column1  <br>FROM table_name  <br>WHERE condition;                                               |
| GROUP BY   | Groups rows that have the same values in specified columns.              | SELECT column1, AVG_FUNCTION(column2)  <br>FROM table_name  <br>GROUP BY column1;                       |
| HAVING     | Filters the results of GROUP BY                                          | SELECT column1, AVG_FUNCTION(column2)  <br>FROM table_name  <br>GROUP BY column1  <br>HAVING condition; |
| ORDER BY   | Sorts the result set by one or more columns                              | SELECT column1  <br>FROM table_name  <br>ORDER BY column1 [ASC \| DESC];                                |
| LIMIT      | By default, it sorts in ****ascending order**** unless specified as DESC | SELECT * FROM table_name LIMIT number;                                                                  |
| DISTINCT   | Removes ****duplicate rows**** from the result set                       | SELECT DISTINCT column1, column2, ...  <br>FROM table_name;                                             |
