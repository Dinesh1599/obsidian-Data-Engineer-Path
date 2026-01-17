Data Definition Language:

DDL (Data Definition Language) actually consists of SQL commands that can be used for defining, altering and deleting database structures such as tables, indexes and schemas. It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects in the database

| Command  | Description                                                                                  | Syntax                                                               |
| -------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| CREATE   | Create database or its objects (table, index, function, views, store procedure and triggers) | CREATE TABLE table_name (column1 data_type, column2 data_type, ...); |
| DROP     | Delete objects from the database                                                             | DROP TABLE table_name;                                               |
| ALTER    | Alter the structure of the database                                                          | ALTER TABLE table_name ADD COLUMN column_name data_type;             |
| TRUNCATE | Remove all records from a table, including all spaces allocated for the records are removed  | TRUNCATE TABLE table_name;                                           |
| COMMENT  | Add comments to the data dictionary                                                          | COMMENT ON TABLE table_name IS 'comment_text';                       |
| RENAME   | Rename an object existing in the database                                                    | RENAME TABLE old_table_name TO new_table_name;                       |
