The INNER JOIN keyword selects records that have matching values in both tables.

SELECT ProductID, ProductName, CategoryName  
FROM Products  
INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID;

![[Pasted image 20251105010647.png]]