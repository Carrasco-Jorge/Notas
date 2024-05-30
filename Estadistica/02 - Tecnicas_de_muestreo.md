# Técnicas de muestreo

- **Qué es el muestreo**: Un conjunto de métodos para obtener muestras

## Muestreo aleatorio simple

Este método de muestreo consiste en extraer de una población finita de $N$ unidades, subpoblaciones de un tamaño fijado de antemano. Este método es un muestreo **sin reemplazo**.

> El muestreo aleatorio simple se recomienda cuando las características de interés presentan gran homogeneidad. En caso contrario, su uso requeriría muestras grandes para lograr una precisión aceptable

Para realizar este método, los individuos o unidades se eligen de forma aleatoria, todos con la misma probabilidad de ser elegidos, sin reemplazo, uno por uno, hasta completar la muestra o subpoblación del tamaño fijado de antemano.

## Muestreo estratificado

Cuando se tiene una población que puede ser dividida en varias subpoblaciones y se cumplen las siguientes condiciones:

- La población **se divide** en subpoblaciones denominadas **estratos**, en las cuales los integrantes de cada uno cumplen ciertas propiedades comunes y se tiene que los estratos son una partición de la población, es decir, son disjuntos disjuntos uno a uno y su unión es igual a la población total

- Seleccionar una muestra en forma independiente de cada estrato. No hay reglas determinantes para elegir el tamaño de cada estrato, pero se sugiere que sea de forma proporcional a los tamaños de los estratos con respecto al tamaño de la población total

- Los estimadores para los parámetros de la población completa se proponen como una combinación de los correspondientes a los parámetros de los estratos

Se puede plantear un muestreo estratificado.

### Muestreo estratificado aleatorio

Si el muestreo independiente de cada uno de los estratos se realiza por el método [Muestreo aleatorio simple](#muestreo-aleatorio-simple), este se llama **muestreo estratificado aleatorio**.

### Características del muestreo estratificado

- Los tamaños de la población completa y de cada uno de los estratos deben ser conocidos

- Este método es flexible en cuanto a la selección de la muestra en cada estrato

- Proporciona estimadores para la población más precisos cuando se construyen estratos lo más homogéneos posible

- Proporciona información de los estratos

- Permite una mejor organización del muestreo

- Permite una mejor administración de la encuesta

- Permite una mejor administración de la población

- Este tipo de muestreo se recomienda cuando se desea tener en la muestra representantes de cada subpoblación o estrato

## Muestreo sistemático con iniciación aleatoria

En este método, la primera unidad o individuo se selecciona de forma aleatoria, después, los elementos restantes se toman siguiendo un patrón establecido para formar la muestra del tamaño requerido.

### Ejemplos del muestreo sistemático con iniciación aleatoria

1. En una línea de producción que esté trabajando en forma continua, se puede hacer un muestreo de tamaño determinado cada 200 unidades

2. En la línea de producción anterior el muestreo puede llevarse a cabo cada determinado tiempo. Por ejemplo, cada hora se selecciona una muestra para su análisis

3. En el estudio de árboles de un bosque, en el que podemos establecer un patrón de revisión, elegir el primero aleatoriamente y después seleccionar un árbol de cada 100 para su estudio

4. Cuando se requiere llevar a cabo encuestas a los usuarios del metro, el mejor muestreo es el sistemático

### Características del muestreo sistemático con iniciación aleatoria

- Es más fácil de realizar en el campo y en la oficina

- Se eliminan errores de los enumeradores, en especial cuando se tiene un marco de muestreo defectuoso

- Extiende la muestra a toda la población, se distribuye mejor y de manera uniforme sobre la población

- No precisa la distinción entre muestreo sin reemplazo y con reemplazo

- Recoge el posible efecto de la estratificación debido al orden en que figuran las unidades en la población

- Si la disposición de las unidades en la población es **aleatoria**, la selección sistemática equivale a un [muestreo aleatorio simple](#muestreo-aleatorio-simple)

### Muestra sistemática de cada $k-$ésima unidad

Se realiza el mismo método de muestreo que en el [muestreo sistemático con iniciación aleatoria](#muestreo-sistemático-con-iniciación-aleatoria) sobre una población de tamaño $N$, pero para seleccionar una muestra de $n$ unidades se toma una al azar de las primeras $k$ unidades. Luego, se elige la unidad que viene $k$ unidades después y así sucesivamente.

Por ejemplo, si $k=30$ y la primera unidad elegida es la $19$, las subsiguientes unidades serán los números $49$, $79$, $109$, etc. 

## Muestreo por conglomerados

En este tipo de muestreo se divide a la población en subpoblaciones o estratos, pero en este **no se requiere** un representante de cada estrato en la muestra, puesto que en primer lugar se se elige una muestra de estratos, y en segundo, se selecciona una muestra de cada estrato para conformar la muestra deseada.

```
Población
 |
 --- [Estrato 1]
 |     |
 |     --- [muestra 1]
 |
 --- Estrato 2
 |
 --- Estrato 3
 |
 --- [Estrato 4]
 |     |
 |     --- [muestra 2]
 |
 --- [Estarto 5]
 |     |
 |     --- [muestra 3]
 |
 --- Estrato 6
```

### Características del muestreo por conglomerados

- Se usa en poblaciones en **extremo grandes**

- No requiere de un marco de muestreo que liste las unidades con anterioridad

- Proporciona un mayor ahorro de recursos

- Se pierde precisión

- Útil cuando los individuos o unidades se encuentran muy dispersas geográficamente o alguna situación equivalente