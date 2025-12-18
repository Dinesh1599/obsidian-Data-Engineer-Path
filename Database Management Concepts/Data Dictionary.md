A **data dictionary** is **documentation** that _describes_ the table and its columns in human terms. Basically the metadata description of the table and its data elements.

## Key difference between a Data Dictionary and Schema

|Aspect|Schema|Data Dictionary|
|---|---|---|
|Purpose|Storage & enforcement|Understanding & governance|
|Enforced by DB|✅ Yes|❌ No|
|Business meaning|❌ Minimal|✅ Detailed|
|Used by|DB engine|Humans|
|Changes break code|✅ Yes|❌ No|

## Example

Query:
Create table human
	license ID int PRIMARY KEY,
	surname varchar(20) not null,
	first Name varchar (20),
	address VARCHAR(50),
	phoneno varchar(10)
	dob date not null;

This shows:
	What columns exist?
	What types?
	What constraints?

Now a Data Dictionary:
![[Pasted image 20251217220309.png]]

This shows:
	What does this column mean?
    What values are valid?
    Where does it come from?
    How should analysts use it?