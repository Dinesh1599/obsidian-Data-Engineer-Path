### LEN() or LENGTH()
- Counts how many characters
- LENGTH() is instead used in Postgresql
- Syntax
	- LEN([column_name])
	- LEN(first_name)
### LEFT 
- Extract specific Number of Characters from the start
- Syntax
	- LEFT([column_name],no.ofCharacters)
	- LEFT([first_name],3)
### RIGHT 
- Extract specific Number of Characters from the end
- Syntax
	- RIGHT([column_name],no.ofCharacters)
	- RIGHT([first_name],3)
### Substring
- Extracts a part of string at a specific position
- Syntax
	- SUBSTR([column_name],offset,no.ofCharacters)
	- SUBSTR('Dinesh',2,2) -- Returns "in"