# Columnas condicionales

## IF

```sql
SELECT
    *,
    IF(condicion, valor_verdadero, valor_falso) as nuevo_nombre
FROM nombrebd.tabla;
```

## CASE

```sql
SELECT
	*,
    CASE
		WHEN condicion1 THEN valor1
        WHEN condicion2 THEN valor2
        WHEN condicion3 THEN valor3
        ELSE valor_por_defecto
    END AS nuevo_nombre
FROM nombrebd.tabla;
```
