# Power Query

Te permite crear *Data pipelines* en Excel con las cuales puedes limpiar, manipular y transformar tus datos sin cambiar los datos originales.

Power Query utiliza un lenguaje de fórmulas llamado **M**.

## Usar Power Query en Excel

1. Ir a la pestaña **Datos** en el menú (Ribbon) de Excel

2. Dar clic en una opción de la función **Obtener datos**

    - Para usar datos de una de las hojas de Excel, elegir la opción **De una tabla o rango**

## Organizar pipeline en Power Query

### Agregar "separadores" entre pasos

Se pueden agregar pasos "vacíos" o que no hagan nada y cambiarles el nombre a algo como

> ------- Data cleaning -------

para llevar un mejor orden en la lista de pasos del Query / Data pipeline.

### Renombrar pasos de pipeline en Power Query

Para tener una mejor organización en el proceso de los datos o data pipeline se pueden renombrar los pasos que se vayan haciendo en Power Query.

1. Dar clic derecho en paso del data pipeline

2. Seleccionar renombrar

3. Cambiar nombre

4. Dar enter

## Limpieza de datos en Power Query

### Cambiar nombre de columna

1. Dar coble clic en el nombre de la columna

2. Cambiar nombre

### Cambiar tipo de dato de columna

1. Dar clic en el símbolo al lado del nombre de la columna

2. Elegir tipo de dato

### Quitar duplicados

1. Dar clic derecho en la columna que se quieren quitar duplicados

2. Dar clic en **Remove duplicates**

### Reemplazar valores

1. Dar clic derecho en la columna que se quieren reemplazar valores

2. Dar clic en **Replace values**

3. Definir el valor que se quiere cambiar y el nuevo valor en los campos correspondientes

4. Dar clic en **Ok**

### Quitar espacios adicionales

1. Seleccionar la columna en cuestión

2. Ir a la pestaña **Transform**

3. Ir al desplegable **Format**

4. Seleccionar **Trim**

### Misceláneo

- En Power Query, el término **Distinct** se refiere al número de valores únicos que hay en una columna, mientras que el término **Unique** se refiere a los valores "unitarios" o que solo tienen una aparición en la columna

## Data Merging en Power Query

1. Preparar y limpiar las dos fuente de datos que se quieren juntar (opcional)

2. Seleccionar el menú **Home**

3. Seleccionar el desplegable **Merge queriees**

4. Seleccionar la opción **Merge queries** o **Merge queries as new** dependiendo de lo que se necesite

5. Seleccionar las fuentes de datos que se juntarán / fusionarán (merge)

6. Seleccionar las columnas mediante las cuales se hará el merge (una de cada fuente de datos)

7. Seleccionar el tipo de merge

8. Dar clic en **Ok**

## Transformación de datos en Power Query

### Separar columna

1. Seleccionar columna en cuestión

2. Ir a la pestaña **Transform**

3. Ir al desplegable **Split Column**

4. Seleccionar la forma de separar la columna

5. Configurar el formato a usar

6. Dar clic en **Ok**

### Agregar columna condicional

Una columna condicional es una columna cuyos valores dependerán de otra u otras.

1. Ir al menú **Add Column**

2. Seleccionar la opción **Conditional column**

3. Agregar condiones, sus parámetros y valor **else**

4. Dar clic en **Ok**

### Agregar columna personalizada

1. Ir al menú **Add Column**

2. Seleccionar la opción **Custom column**

3. Agregar fórmula que calculará los valores de la nueva columna
    
    - Por ejemplo: `if [currency]="USD" then [budget_mill]*80 else [budget_mill]`

4. Dar clic en **Ok**