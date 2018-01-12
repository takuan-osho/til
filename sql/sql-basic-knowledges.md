# SQL Basic Knowledges

## How to use SQL

I'm learning how to use SQL from the book of [SQL Drill 3rd edition](http://gihyo.jp/book/2016/978-4-7741-8066-3)(Japanese book)

I learned the phrases about SQL.

- `SELECT`
- `FROM`
- `AS`
- operators

### `SELECT` and `FROM`

```
SELECT
  CustomerName
FROM
  Customers
;
```


### `AS`

```
SELECT
  EmployeeName AS 社員名
FROM
  Employees
;
```

### operators

```
SELECT
  Height * 0.5 AS 身長の半分
FROM
  Employees
;
```