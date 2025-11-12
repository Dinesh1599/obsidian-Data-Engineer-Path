It is another parameter used in the [[COPY INTO]].

It does not copy to data, instead it validates the data.

Query will look like this:

```sql
COPY INTO <table_name>
FROM externalStage
FILES = ('<file_name>')
VALIDATION_MODE = RETURN_n_ROWS | RETURN_ERROS
```



