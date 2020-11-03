# SQL Joins and Subqueries

## Joins

### Types of Join
![](https://www.dofactory.com/img/sql/sql-joins.png)

__Inner Join__ 
Joins the tables on matching rows
__Left Join__
Selects data from the (left) first table matching data on the left (second) table
__Right Join__
Select records from the second (right-most) table with matching left table records.
__Full Join__ Selects all records that match either left or right table records.

Outputs:
```
Inner => Mutual Data
Left => Both Inner and everything in left table
Right => Both Inner and everything in right table
Full => Everything
Full outer => Everything without inner
```

## Syntax:
```sql
SELECT table_B.column1
        table_A.column2
        table_C. column1 ... 
FROM table_A
INNER|FULL|LEFT|RIGHT JOIN tableB on table_A.column_name = table_B.column_name
INNER JOIN table_C 

-- When aliasing tables, you dont need `AS` you just put what you want the table to be called after, Example:
Select * 
FROM orders o -- adding a letter after the table aliases it
JOIN customers c ON o.customerID = c. customerID;

-- Example:
SELECT * 
FROM Orders 
INNER JOIN Customers 
ON Orders.CustomerID = Customers.CustomerID
WHERE  Customers.Country = 'Brazil';

-- Example 2:
SELECT  Suppliers.CompanyName, 
        AVG(Products.UnitsOnOrder) as 'Average Units Ordered'
FROM Products 
INNER JOIN Suppliers 
ON Suppliers.SupplierID = Products. SupplierID
GROUP BY Suppliers.Companyname
ORDER BY 'Average Units Ordered' DESC;

-- FORMAT can be used to format dates
SELECT FORMAT(date, 'dd/mm/yyyy')
FROM table_name;
```

## SUBQUERIES
```sql
-- allows you to take the result of one query and apply it to other
SELECT column_name
FROM table_A 
WHERE column_name NOT IN 
        (SELECT column_name FROM table_B);

-- Example: this would return customers who have not made an order
SELECT Customer_ID
FROM Customers
WHERE Customer_ID NOT IN
        (SELECT Customer_ID FROM Order);

-- Nested subquery 
SELECT order_ID