# Common Table Expressions

## WITH

Equivalente a "asignar" una query que regresa una tabla a una "variable" para luego usarla en otra query. El alcance o scope de esta "variable" solo llega hasta la query siguiente, después ya no se puede hacer referencia a ella.

```sql
WITH actors_age AS (
    SELECT
        name AS actor_name,
        YEAR(CURDATE()) - birth_year AS age
    FROM actors
)

SELECT actor_name, age
FROM actors_age
WHERE age > 70 AND age < 85
```

Se pueden "asignar" más de una "variable":

```sql
WITH
    cte1 AS (SELECT a, b FROM table1),
    cte2 AS (SELECT c, d FROM table2)

SELECT b, d FROM cte1 JOIN cte2 ON cte1.a = cte2.c
```

Se pueden sobreescribir los nombres de las columnas para usarse una vez que se use la CTE en otra query:

```sql
WITH actors_age (actor_name, actors_age) AS (
    SELECT
        name AS x,
        YEAR(CURDATE()) - birth_year AS y
    FROM actors
)
```

## Ejemplo

```sql
with
	more_than_500_profit as (
		select *
		from financials
		where 100 * (revenue - budget) / budget >= 500
    ),
    less_than_avg_movies as (
		select *
		from movies
		where imdb_rating < (select avg(imdb_rating) from movies)
    )
select
	*
from
	more_than_500_profit m join less_than_avg_movies l on m.movie_id=l.movie_id
```

## Beneficios de usar esta función

1. Query readability
2. Query reusability
3. Visibility for creating Data views (data transformed version of the table)