# Statements básicos

## USE

```sql
USE nombrebd;
```

Indica que se use la base de datos `nombrebd` por defecto para los statements siguientes.

## SELECT

```sql
SELECT columna1, columna2 FROM nombrebd.tabla;
```

Selecciona y regresa las columnas indicadas (el símbolo `*` selecciona todas las columnas) de la tabla `tabla` de la base de datos `nombrebd`. Si se usa la query `USE` primero, no es necesario indicar la base de datos y luego el nombre de la tabla, se puede escribir solo el nombre de la tabla.

## WHERE

```sql
SELECT *
FROM nombrebd.tabla
WHERE columna1="Tipo A"
```

La sentencia `WHERE` filtra los resultados del query `SELECT` con el filtro indicado (en el ejemplo: `columna1="Tipo A"`).

### Encontrar y filtrar valores faltantes

#### Valores numéricos

Si el filtro aplicado es `columna IS NULL`, se encontrarán los valores nulos o faltantes. Por el contrario, si el filtro es `columna IS NOT NULL`, entonces se encontrarás los valores no nulos.

#### Valores de texto

Si el filtro aplicado es `columna=""`, se encontrarán los valores vacíos o faltantes. Por el contrario, si el filtro es `columna<>""`, entonces se encontrarás los valores no vacíos.

## COUNT

```sql
SELECT COUNT(*) FROM nombrebd.tabla;
```

Regresa el número de filas o registros en la selección.

## DISTINCT

```sql
SELECT DISTINCT columna FROM nombrebd.tabla;
```

Regresa los valores únicos o distintos en la columna de la tabla indicada.

## LIKE y "Wild card search"

```sql
SELECT *
FROM nombrebd.tabla
WHERE columna LIKE "formato";
```

Filtra las filas por columna y el formato indicado. El formato puede incluir el símbolo `%` antes y / o después de una cadena de texto para indicar que puede haber cualquier caracter antes o después de la cadena, respectivamente.

Ejemplos:

```sql
SELECT *
FROM peliculasbd.peliculas
WHERE titulo LIKE "%mente%";
```

Intensamente, La mente maestra, Mente: el misterio.

```sql
SELECT *
FROM peliculasbd.peliculas
WHERE titulo LIKE "mente%";
```

Mente: el misterio.

```sql
SELECT *
FROM peliculasbd.peliculas
WHERE titulo LIKE "%mente";
```

Intensamente.

## AND

```sql
SELECT *
FROM nombrebd.tabla
WHERE columna1>3 AND columna2="Tipo A";
```

Se usa para hacer un filtro con dos o más condiciones simultáneas que se deben cumplir al mismo tiempo.

## BETWEEN

```sql
SELECT *
FROM nombrebd.tabla
WHERE columna BETWEEN 6 AND 8;
```

Filtra los resultados que tengan un valor de `columna` entre 6 y 8 (inclusivo).

## OR

```sql
SELECT *
FROM nombrebd.tabla
WHERE columna1>3 or columna2="Bollywood";
```

Se usa para hacer un filtro con dos o más condiciones simultáneas, donde solo debe cumplirse al menos una para seleccionar las filas o registros.

## IN

```sql
SELECT *
FROM nombrebd.tabla
WHERE columna IN(2016,2020,2024);
```

Filtra los resultados que tengan un valor contenido en el conjunto de valores indicado. Pueden ser valores numéricos o de texto.

## ORDER BY

```sql
SELECT *
FROM nombrebd.tabla
where columna1="Tipo A"
ORDER BY columna2;
```

Regresa los registros ordenados de forma ascendente por defecto usando la columna indicada. Se puede indicar `DESC` o `ASC` después de indicar la columna para ordenar de forma descendente o ascendente, respectivamente.

## LIMIT

```sql
SELECT *
FROM nombrebd.tabla
where columna1="Tipo A"
ORDER BY columna2 DESC
LIMIT 5;
```

Limita el número de registros mostrados al ejecutar la query.

## OFFSET

```sql
SELECT *
FROM nombrebd.tabla
where columna1="Tipo A"
ORDER BY columna2 DESC
LIMIT 5 OFFSET 1;
```

Los registros mostrados inician desde el índice indicado después de la sentencia `OFFSET`. Los índices inician en `0`; es análogo a `df[offset:]` en python.

## AS

```sql
SELECT MAX(columna) AS max_columna FROM nombrebd.tabla;
```

Se usa para nombrar o renombrar columnas en el resultado del query.

## Having

```sql
SELECT columna1, COUNT(*) as nueva_columna
FROM nombrebd.tabla
GROUP BY columna1
HAVING nueva_columna>2
```

La sentencia `HAVING` se utiliza para filtrar después de realizar operaciones como `GROUP BY`. Solo puede utilizars con columnas indicadas en la sentencia `SELECT`.

## EXPLAIN ANALYZE

Devuelve el orden de ejecución de una query y el tiempo de ejecución que tardó.

```sql
EXPLAIN ANALYZE
SELECT columna1, COUNT(*) as nueva_columna
FROM nombrebd.tabla
GROUP BY columna1
HAVING nueva_columna>2
```