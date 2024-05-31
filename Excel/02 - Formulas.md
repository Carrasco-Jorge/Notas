# Fórmulas en Excel (español e inglés)

## Índice

1. [Manipulación de textos](#manipulación-de-textos)

2. [Buscar y coincidir datos](#buscar-y-coincidir-datos)

3. [Cálculos y Estadística básica](#cálculos-y-estadística-básica)

4. [Misceláneo](#misceláneo)

## Manipulación de textos

### ESPACIOS (TRIM)

Elimina los espacios adicionales del texto excepto el espacio normal que se deja entre palabras. Acepta celdas, cadenas, rangos.

Si se introduce una cadena con solo espacios, esta función regresa la cadena vacía `""`.

**Ejemplo:**

```
=ESPACIOS(Tabla[Col1])
```

### SUSTITUIR (SUBSTITUTE)

Sustituye un texto o cadena dentro de otra con la cadena que se especifique. Se puede especificar qué ocurrencia de la cadena se quiere sustituir, y si no se especifica se reemplazan todas.

**Ejemplo:**

```
=SUSTITUIR(A1,"#","")
```

## Buscar y coincidir datos

### BUSCARV (VLOOKUP)

Busca y hace match entre dos columnas de dos tablas distintas (la columna de la **1ra tabla** que uno elige y la **1ra columna** de la **2da tabla**), devolviendo otro valor de la segunda tabla que corresponda con el valor buscado.

**Argumentos:**

| Argumento | Descripción |
| --------- | ----------- |
| *Valor_buscado* | Es el valor buscado en la primera columna de la tabla y puede ser un valor, referencia o una cadena de texto |
| *Matriz_tabla* | Es una tabla de texto, números o valores lógicos en los cuales se recuperan datos. Matriz tabla en puede ser una referencia a un rango o un nombre de rango |
| *Indicador_columnas* | Es el número de columna de Matriz buscar en desde la cual debe devolverse el valor que coincida. La primera columna de valores en la tabla es la columna 1 |
| *Rango* | Es un valor lógico: para encontrar la coincidencia más cercana en la primera columna (ordenada de forma ascendente) indique VERDADERO u omita el argumento. Para encontrar la coincidencia exacta indique FALSO |

**Ejemplo:**

```
=BUSCARV([@[movie_id]],Financials[#Todo],2,FALSO)
```

### INDICE (INDEX)

Devuelve el valor de un elemento de una tabla o matriz seleccionado por los índices de número de fila y de columna. Use la forma matricial si el primer argumento de INDICE es una constante matricial.

**Argumentos:**

| Argumento | Descripción |
| --------- | ----------- |
| *Matriz* | Rango de celdas o constante de una matriz. Puede ser una fila o una columna |
| *Fila* | Selecciona la fila de la matriz desde la cual devolverá un valor. Si se omite número de fila, número de columna es obligatorio. Si se especifica como 0, entonces devolverá todas las filas |
| *Columna* | Selecciona la columna de la matriz desde la cual devolverá un valor. Si se omite número de columna, número de fila es obligatorio. Si se especifica como 0, entonces devolverá todas las columnas |

### COINCIDIR (MATCH)

Devuelve el índice del valor buscado en el rango especificado. No distingue entre mayúsculas y minúsculas.

- Usar el carácter “*” indicará que puede ir cualquier cosa ahí (por ejemplo: *.txt)

- Usar el carácter “?” indicará que coincidirá con cualquier carácter individual (por ejemplo: Proyecto_?)

- Para usar los caracteres “?” y “*” en una búsqueda como parte del texto o valor buscado use el carácter”~” antes de ellos.

**Argumentos:**

| Argumento | Descripción |
| --------- | ----------- |
| *Valor_buscado* | Es el valor que se quiere buscar en *Matriz_buscada* |
| *Matriz_buscada* | Es el rango de celdas en que se realiza la búsqueda |
| *Tipo_de_coincidencia* | Puede ser -1, 0, 1. Este argumento especifica el tipo de coincidencia con el valor buscado. **0** es coincidencia exacta, **1** es encontrar el valor menor o igual más cercano al valor buscado, **-1** es encontrar el valor mayor o igual al valor buscado. **Escala de orden:** …, -2, -1, 0, 1, 2, …, A-Z, Falso Verdadero |

### BUSCARX (XLOOKUP)

Busca una coincidencia en un rango o una matriz y devuelve el elemento correspondiente de un segundo rango o matriz. De forma predeterminada se usa una coincidencia exacta.

**Argumentos:**

| Argumentos | Descripción |
| ---------- | ----------- |
| *Valor_buscado* | Es el valor que se buscará |
| *Matriz_buscada* | Es la matriz o rango donde se buscará |
| *Matriz_devuelta* | Es la matriz o rango donde se devolverá |
| *Si_no_se_encuentra* | Valor devuelto si no se encuentra ninguna coincidencia |
| *Modo_de_coincidencia* |Especifica cómo comparar el valor buscado con los valores de la matriz buscada. **0** = coincidencia exacta; si no se encuentra devolver #N/D.  **-1** = coincidencia exacta; si no se encuentra devolver siguiente elemento más pequeño. **1** = coincidencia exacta; si no se encuentra, devolver siguiente elemento más grande. **2** = coincidencia comodín donde **\***, **?** y **~** tienen significado especial |
| *Modo_de_búsqueda* | **1** = realizar una búsqueda empezando por el primer elemento. *Valor predeterminado*. **-1** = realizar una búsqueda inversa empezando por el último elemento. **2** = realizar búsqueda binaria que se base en que *Matriz_buscada* se ordene en **orden ascendente**. Si no está ordenada, se devolverán resultados no válidos. **-2** = realizar búsqueda binaria que se base en que *Matriz_buscada* se ordene en **orden descendente**. Si no está ordenada, se devolverán resultados no válidos. |

## Cálculos y Estadística básica

### SUMA (SUM)

La función SUMA suma valores. Puede sumar valores individuales, referencias o rangos de celda o una combinación de las tres.

### SUMAR.SI (SUMIF)

Suma las celdas que cumplen determinado criterio o condición.

**Argumentos:**

| Argumentos | Descripción |
| ---------- | ----------- |
| *Rango* | Rango de celdas para filtrar el rango de suma |
| *Criterio* | Criterio para filtrar las celdas antes de la suma |
| *Rango_suma* | Son las celdas que se van a sumar. Si se omite, se usan las celdas de *Rango* en la suma |

### CONTAR (COUNT)

Cuenta el número de celdas que contienen números en el rango indicado.

### CONTAR.SI (COUNTIF)

Cuenta el número de celdas que cumplen el criterio indicado.

**Argumentos:**

| Argumentos | Descripción |
| ---------- | ----------- |
| *Rango* | Rango o matriz de celdas a tomar en cuenta para el conteo |
| *Criterio* | Criterio para filtrar las celdas antes del conteo |

### PROMEDIO (AVERAGE)

Devuelve el promedio o media artimética de los valores o rango indicados.

### PROMEDIO.SI (AVERAGEIF)

Devuelve el promedio o media artimética de los valores o rango indicados donde se cumpla el criterio indicado.

**Argumentos:**

| Argumentos | Descripción |
| ---------- | ----------- |
| *Rango* | Una o más celdas cuyo promedio se desea obtener que incluyan números, o nombres, matrices o referencias que contengan números |
| *Criterio* | Criterio en forma de número, expresión, referencia de celda o texto que determina las celdas cuyo promedio se va a obtener. Por ejemplo, los criterios pueden expresarse como 32, "32", ">32", "manzanas" o B4 |
| *Rango_promedio* | Conjunto real de celdas cuyo promedio se va a calcular. Si se omite, se utiliza un rango |

### MEDIANA (MEDIAN)

Devuelve la mediana de los valores o rango indicados.

### MODA (MODE)

Devuelve la moda de los valores o rango indicados.

### DESVEST.M (STDEV.S)

Devuelve la desviación estándar (fórmula para muestras) de los valores o rango indicados.

### VAR.S (VAR.S)

Devuelve la varianza (fórmula para muestras) de los valores o rango indicados.

### COEF.DE.CORREL (CORREL)

Devuelve el coeficiente de correlación **lineal** de los valores o rango indicados.

## Misceláneo

### INDIRECTO (INDIRECT)

Hacer referencia a una celda, una tabla, columna de una tabla, etc. Esta fórmula es útil para poder hacer referencias a distintas tablas o similares con un valor dinámico, lo cual normalmente no se puede hacer.

**Ejemplos:**

```
=INDIRECTO("Tabla1[Col1]")  ->  Se puede usar para crear una lista desplegable con los valores de la Tabla1, Col1; también se puede usar para crear una gráfica con estos valores.

=INDIRECTO(""&B4&"!"&D4&F4&"")  ->  Se puede usar para obtener el valor de la celda de la hoja con nombre el valor de la celda B4 que tiene por columna y fila los valores de las celdas D4 y F4, respectivamente.
```

### ESBLANCO (ISBLANK)

Devuelve verdadero si la celda especificada es vacía, es decir, no tiene contenido, "" ni " ".