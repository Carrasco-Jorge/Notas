# Subqueries

Se refiere a usar una query dentro de otra query.

Se pueden usar queries que devuelvan un solo valor, una lista de valores o una tabla.

## Co-related queries

```sql
SELECT
	actor_id, name,
    (SELECT count(*) FROM movie_actor WHERE actor_id=actors.actor_id) AS movie_count
FROM actors
ORDER BY movie_count DESC;
```