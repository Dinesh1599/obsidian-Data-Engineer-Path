Sequences are used to generate unique numbers across sessions and statements, including concurrent statements. They can be used to generate values for a primary key or any column that requires a unique value.

Query:

Create sequence  my_seq
START  = 1
INCREMENT  = 1;

How is this useful?

Great for iteration
Normally used for default values.
![[Pasted image 20251115163429.png]]

