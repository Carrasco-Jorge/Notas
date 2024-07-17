## ALL

```sql
SELECT * FROM movies
WHERE imdb_rating > ALL (
	SELECT imdb_rating FROM movies WHERE studio="Marvel Studios"
)
```

## ANY

```sql
SELECT * FROM actors
WHERE actor_id = ANY (
    SELECT actor_id FROM movie_actor
    WHERE movie_id in (101,110,121)
)
```