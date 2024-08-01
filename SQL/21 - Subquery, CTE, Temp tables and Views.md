# 

## Subquery

- Can be used to obtain single aggregated values (eg. average) with queries to use them within a query
    - Can be used in `SELECT` clause
    - Can be used in `WHERE` clause
- Valid within the scope of the statement
- Low readability

## CTE

- More readable compared to subquery
- CTEs are reusable within the statement
- Can be used to build recursive queries
- Valid within the scope of the statement

## Temporary tables

- Valid within the scope of the session
- High readability
- Perform multi pass processing steps on a dataset

## Views

- Valid within the database and across sessions
- High readability
- Derived tables that will be used in multiple queries