# SQL Queries 

## __SELECT Query Structure__

```sql
SELECT column1, column2 FROM table_name WHERE condition ORDER BY ASC / DESC;
```

### Select processing sequence
1. SELECT
2. DISTINCT or COUNT()
3. FROM
4. WHERE
5. GROUP BY
6. HAVING
7. ORDER BY


### SQL QUERYING SYNTAX

```sql
-- * means 'all'
SELECT * FROM table_name;

-- WHERE allows us to narrow down the search
SELECT * WHERE column_name = specific_thing;

-- COUNT counts the number of entries matching the constraint(s)
SELECT COUNT(*) FROM table_name WHERE column_name = specific_thing;

-- Returns top 100 results.
SELECT TOP 100 column1, column2, FROM table_name WHERE column_name = specific_thing;

-- AND can be used to add another WHERE condition
-- OR, either side needs to be fullfilled

-- DISTINCT removes duplicates from your data, it returns unique entries in that catagory. 
SELECT DISTINCT column_name from table_name WHERE column_name = specific_thing;

-- Count the number of distinct entries 
SELECT COUNT(DISTINCT animals) FROM eating_things;

-- IN makes an array and checks if its in there
SELECT * FROM table_name WHERE column_name IN (condition1, condition2);

-- BETWEEN is another way to do ranges, usually for numbers
SELECT * FROM table_name WHERE column_name BETWEEN 0 AND 999;

-- To display headings differently at the output
SELECT column_name AS pretty_column_name FROM table_name WHERE condition = something;

-- a more complex AS example:
SELECT CompanyName AS 'Company Name', City + ', ' + Country  
AS 'City'
FROM Customers;

-- ORDER BY
SELECT * FROM table_name ORDER BY column_to_order_by ASC / DESC;

--DATEDIFF allows you to find the difference between two dats
SELECT DATEDIFF(interval, DATE1, DATE2) FROM table_name AS 'new name';

-- NULL is not a value , nor is it = 0 or anything for that matter so you need to use IS or IS NOT (not =)
SELECT * FROM table_name WHERE column IS NULL;

-- You can carry out operators in SQL
SELECT column_with_numbers + another_column_with_numbers AS 'new name' FROM table_name;



-- Example of Ordering by a newly created column. 
SELECT  TOP 2
        OrderID, 
        UnitPrice*Quantity*(1-Discount) AS 'Net Total' 
FROM [Order Details]
ORDER BY 'Net Total' DESC;


```

## Alter Syntax Structure
```sql
-- ALTER can be used to ADD, DROP or MODIFY columns.
ALTER table_name ADD new_column DATATYPE;
### Number operators:
```

## Operators:
```sql
<> -- Not equal to
!= -- Not equal to
< -- Less than
> -- Greater than
<= -- less than or equal to
>= -- greater than or equal to
+ -- add
- -- subtract
* -- multiply (best practice to use alias)
/ -- devide
% -- returns the remainder
```

## Wildcards:

```sql
% -- substitute for zero or more characters
_ -- substitute for a single character
[charlist] -- substitute for any single character within the brackets
[^charlist] -- represents any character not in the brackets
- -- represents a range of characters
```
## String Functions 
```sql
SUBSTRING -- (str, start, length)
CHARINDEX -- (arg1, str) "find arg1 in str" returns 0 if it cant find it
LEFT|RIGHT -- (str,n) nth characters from left or right
LTRIM|RTRIM --(str) Remove spaces at the beginning or end
LEN -- (str) returns length of thing
REPLACE -- (str, char1, char2) replace char 1 in string with char2
UPPER|LOWER -- (str) converts all to upper / lower case

-- Example of using CHARINDEX and escaping a string
-- Note you cannot use Alias in WHERE but you can just put the condition there
SELECT ProductName, CHARINDEX( '''', ProductName) AS 'Apostrophe Index'
FROM Products
WHERE CHARINDEX( '''', ProductName) != 0;
```




## Joins: 
[Types of Joins](https://www.w3schools.com/sql/sql_join.asp)

### Inne Join Syntax:

```sql
SELECT table_name.column_name,
        table_name.another_column_name
FROM TableA
INNER JOIN TableB ON TableA.CustomerID = TableB.CustomerID
ORDER BY table_name.column_name ASC|DESC
```
