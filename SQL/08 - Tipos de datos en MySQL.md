# Tipos de datos

## Numéricos

**Enteros / Integer**

- Modificadores
    - Unsigned: solo valores no negativos
    - Tiny: 1 byte
    - Small: 2 bytes
    - Medium: 3 bytes
    - --- : 4 bytes
    - Big: 8 bytes

**Flotantes / Float**

- Float: 4 bytes

- Double: 8 bytes

- Decimal: `(precision, scale)`
    - Cuántos dígitos representar
    - Cuántos dígitos de `precision` son después del punto

## String

**Longitud fija**

- `CHAR(x)`: `x` es la longitud de la cadena de texto


**Longitud variable**

- `VARCHAR(x)`: `x` es la longitud máxima que puede tomar la cadena de texto

**Enum**

- `ENUM('cat1','cat2','cat3')`: donde `'cati'` son los valores u opciones que puede tomar la cadena de texto. Se deben saber y definir estas categorías de antemano.

## Date - Time

**DATETIME**

yyyy mm dd hh:mm:ss

**DATE**

yyyy mm dd

**TIME**

hh:mm:ss

**YEAR**

yyyy : 1901 - 2155

**TIMESTAMP**

yyyy-mm-dd hh:mm:ss

- Mín: 1970-01-01 00:00:01
- 2038-01-19 03:14:07

## JSON: JavaScript Object Notation

Conjunto de Key - value pairs. Para poder hacer consultas y filtrar la BD por un atributo tipo JSON se puede hacer de la siguiente manera:

```sql
SELECT * FROM superstore_db.items
WHERE properties->"$.gluten_free"=1;
```

Los que no tienen el atributo / key:

```sql
SELECT * FROM superstore_db.items
WHERE ISNULL(properties->"$.gluten_free");
```

Otra manera para no usar `->` es usar la función:

```sql
JSON_EXTRACT(properties,"$.property") = valor
```

## Spatial

Normalmente se almacenan en tipo BLOB, pero se puede usar la función

```
AT_ASTEXT(columna)
```

Para imprimir el objeto espacial como texto.