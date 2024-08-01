# Window function

## OVER

Usar la palabra clave `over()` después de una columna calculada que utilice una función de agregación aplicará esta fórmula a todas las filas. Por ejemplo:

```sql
SELECT 
	*,
    amount*100/SUM(amount) OVER() AS pct
FROM random_tables.expenses;
```

Si se usan las palabras `PARTITION BY` dentro de los paréntesis de `OVER()`, se puede especificar una columna categórica con la cual tomar el total respecto a ella. Por ejemplo:

```sql
SELECT 
	*,
    amount*100/SUM(amount) OVER(PARTITION BY category) AS pct
FROM random_tables.expenses;
```

Donde se calculan los porcentajes de los gastos con respecto al total de la categoría a la que pertenecen en vez de al total general.

Esta funcionalidad también se puede utilizar para calcular de forma acumulada, por ejemplo, la suma de los gastos con respecto a la fecha como se muestra en el siguiente ejemplo:

```sql
SELECT
	*,
    sum(amount) OVER(
		PARTITION BY category
        ORDER BY date
    ) as total_expense_till_date
FROM expenses
ORDER BY category, date;
```

## ROW_NUMBER

Se puede utilizar para asignar un número de fila único a los registros dado cierto orden y cierta partición.

```sql
WITH tmp AS (
    SELECT 
        *,
        ROW_NUMBER() OVER(PARTITION BY category ORDER BY amount DESC) AS rn
    FROM random_tables.expenses
    ORDER BY category
)
SELECT *
FROM tmp
WHERE rn<=2;
```

## RANK

Asigna un rango o una jerarquía númérica a los registros basado en un criterio donde exista un orden, por ejemplo, la cantidad de gasto. Este número puede repetirse si hay empate pero se saltará números. Por ejemplo, si hay empate en 2do lugar, los rangos quedarían **1, 2, 2, 4**, saltándose el **3**.

```sql
WITH tmp AS (
    SELECT 
        *,
        RANK() OVER(PARTITION BY category ORDER BY amount DESC) AS rnk
    FROM random_tables.expenses
    ORDER BY category
)
SELECT *
FROM tmp
WHERE rnk<=2;
```

## DENSE_RANK

Lo mismo que `RANK`, pero no se salta números al asignar cuando hay empates.

```sql
WITH tmp AS (
    SELECT 
        *,
        DENSE_RANK() OVER(PARTITION BY category ORDER BY amount DESC) AS drnk
    FROM random_tables.expenses
    ORDER BY category
)
SELECT *
FROM tmp
WHERE drnk<=2;
```