Unloading data from a table to the stage.
![[Pasted image 20251111221942.png]]
To get the file after unloading:

1. External Stage:
	1. go to the cloud provider and download the file
2. Internal Stage:
	1. use the GET Command

Query for GET Command:

```sql
GET @internal_stage file://<path_to_file>/<filename>
```

Refer [[Copy Options]] for unloading parameters

Table queries can also be possible:
![[Pasted image 20251111221707.png]]

prefix and suffix is also used here to avoid duplicate names
eg: COPY INTO @<stage_name>/myfile

where
	myfile is the prefix
	data_ is the default if nothing is mentioned.

Note: 
Delete the file from the stage or else charges can occur.