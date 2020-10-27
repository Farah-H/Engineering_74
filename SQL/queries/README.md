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


### WHERE

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
SELECT * FROM table_name WHERE column_name BETWEEN 0 

-- To display headings differently at the output
SELECT column_name AS pretty_column_name WHERE ... ;
-- a more complex AS example:
SELECT CompanyName AS 'Company Name', 
    City + ', ' + Country  AS 'City'
    FROM Customers;

```

### Number operators:
```sql
<> -- Not equal to
!= -- Not equal to
< -- Less than
> -- Greater than
<= -- less than or equal to
>= -- greater than or equal to
```

### Wildcards

```sql
% -- substitute for zero or more characters
_ -- substitute for a single character
[charlist] -- substitute for any single character within the brackets
[^charlist] -- represents any character not in the brackets
- -- represents a range of characters