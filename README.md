# AdventureWorksLT-Sales-Data-Analysis-An-End-to-End-BI-Solution-in-Power-BI
Connect data to SQL server, convert BAK file into database in sql
Import data into powerBI through SQL queries
------------------------------------------------------------------------------------------------
SELECT	a.CustomerID, a.CompanyName, a.NameStyle, a.Title, a.FirstName, a.LastName, a.SalesPerson,
		c.AddressLine1, c.AddressLine2, c.City, c.StateProvince, c.CountryRegion, c.PostalCode 
FROM	SalesLT.Customer AS a
INNER	JOIN SalesLT.CustomerAddress AS b ON a.CustomerID = b.CustomerID
INNER	JOIN SalesLT.[Address] AS c ON b.AddressID = c.AddressID
WHERE	b.AddressType = 'Main Office'
-----------------------------------------------------------------------------------------------
SELECT	b.CustomerID, a.SalesOrderID, a.SalesOrderDetailID, b.RevisionNumber, b.SalesOrderNumber,
		e.Name AS MainCategory, d.Name AS SubCategory, c.ProductID, c.Name AS Product, 
		a.OrderQty, c.ListPrice, 
		b.OrderDate, b.DueDate, b.ShipDate, b.SubTotal 
FROM	SalesLT.SalesOrderDetail AS a
INNER	JOIN SalesLT.SalesOrderHeader AS b ON a.SalesOrderID = b.SalesOrderID 
INNER	JOIN SalesLT.Product AS c ON a.ProductID = c.ProductID 
INNER	JOIN SalesLT.ProductCategory AS d ON c.ProductCategoryID = d.ProductCategoryID
INNER	JOIN SalesLT.ProductCategory AS e ON d.ParentProductCategoryID = e.ProductCategoryID
----------------------------------------------------------------------------------------------------
Transform and clean the data, Finally visualize it.
<img width="635" alt="image" src="https://github.com/user-attachments/assets/88b67462-5d88-4446-8836-662c7d501913" />
<img width="630" alt="image" src="https://github.com/user-attachments/assets/69fa644c-82d8-4316-81fb-7f53530bfa59" />

