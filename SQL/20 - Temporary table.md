# Temporary table

Se pueden crear tablas temporales que se guardan en memoria y que duren al tiempo de la sesión. Estas tablas pueden ser más convenientes que una Common Table Expression porque no se tiene que ejecutar una consulta para crear la tabla cada vez que se quiere utilizar en esa sesión, y al mismo tiempo, no se crea una nueva tabla permanente.

```sql
CREATE TEMPORARY TABLE tabla2
    SELECT
        *
    FROM tabla1
    WHERE (col1<20) AND (col2 LIKE "%.txt")
```