# Primary and Foreign keys

## Primary key

Un valor que identifica a una entidad o registro de manera única e irrepetible. Ejemplo: CURP. Es el identificador en la tabla padre o dimension table.

### Natural key

Un identificador que está incluido naturalmente en el conjunto de datos

### Surrogate key

Un identificador que fue generado de manera artificial. Por ejemplo, la matrícula de una universidad no se genera con los datos del alumno, sino de forma artificial.

### Composite key

Un identificador creado a partir de múltiples identificadores.

## Foreign key

Es el identificador en la tabla hija o fact table. Definir relaciones entre Primary keys y Foreign keys permite evitar el ingreso incorrecto o defectuoso de los datos.

### Tipos de relaciones entre tablas

**1:1 Non-Identifying relationship**

Relación inyectiva que va de la tabla padre a la tabla hija, la cual mapea la primary key con la foreign key. En este caso, la foreign key también es el identificador principal de la tabla hija, por lo que esta también tiene uno y solo un registro por identificador.

Ejemplo: conectar las tablas `financials` y `movies` mediante la columna `movie_id`. Cada una de estas tablas tiene uno y solo un registro para cada identificador de película, el cual sirve como primary key de ambas tablas.

**1:n Non-Identifying relationship**

Relación entre dos tablas, la tabla padre con un solo registro para cada identificador principal y la tabla hija, la cual puede contener más de un registro por identificador.

Ejemplo: las tablas `language` y `movies` relacionadas con la columna `language_id`. Aquí la tabla `movies` puede tener más de un registro para cada id de idioma, pero la tabla `language` tiene un solo registro para cada idioma.

**1:1 Identifying relationship**




**1:n Identifying relationship**



**n:m Identifying relationship**



### Foreign key options

**Restrict**
No permite la acción.

**Cascade**
Realiza los cambios del valor en las tablas hijas.

**Set Null**
Cambia el valor a Null en las tablas hijas.

**No action**
No realiza acciones.