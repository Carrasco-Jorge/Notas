# Funciones de resumen

## MIN

```sql
SELECT MIN(columna) from nombrebd.tabla
```

## MAX

```sql
SELECT MAX(columna) from nombrebd.tabla
```

## AVG

```sql
SELECT AVG(columna) from nombrebd.tabla
```

## SUM

```sql
SELECT SUM(columna) from nombrebd.tabla
```

## ROUND

```sql
SELECT ROUND(AVG(columna)) from nombrebd.tabla
```

## GROUP BY

```sql
SELECT columna, COUNT(*) FROM nombrebd.tabla GROUP BY columna
```

## Ejemplo de query

```sql
SELECT 
	TRIM(studio) AS studio_trimmed,
    COUNT(*) AS count,
    MIN(imdb_rating) AS min_rating,
    MAX(imdb_rating) AS max_rating,
    ROUND(AVG(imdb_rating),1) AS avg_rating 
FROM moviesdb.movies
WHERE studio!=""
GROUP BY studio_trimmed
ORDER BY avg_rating DESC;
```

Se obtiene la tabla siguiente:

| studio_trimmed | count | min_rating | max_rating | avg_rating |
| -------------- | ----- | ---------- | ---------- | ---------- |
| Estudio A      | 35    | 1.5        | 8.4        | 5.3        |
| Estudio B      | 12    | 2.4        | 9.3        | 7.6        |
| ...            | ...   | ...        | ...        | ...        |