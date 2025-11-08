How does snowflake know which is the file format is needed to load

When running the query: DESC STAGE db.schema.stage_name, There is a property called "property_type" and "property_default". If "property_type" is not provided, "property_default" is taken into consideration.

![[Pasted image 20251107200507.png]]

Possible to overrule with the following:
file_format (type = [the_file_type]);


