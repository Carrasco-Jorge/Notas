# Power Pivot

## Habilitar Power Pivot

1. Archivo > Opciones > Complementos

2. Administrar: Complementos COM > Ir

3. Habilitar Microsoft Power Pivot

4. Aceptar

## Pasos para usar Power Pivot en Excel con tabla dinámica

1. Tener query en Power Query

2. Guardar y cargar conexión a query y seleccionar **Add this to the Data Model**

3. Ir al menú Insertar, seleccionar tabla dinámica > Desde Modelo de Datos

## Usar Power Pivot

### Measures y DAX

La opción de crear **measures** ...

Para crear estas métricas se utiliza en "lenguaje" llamado **DAX** (Data Analytics Expression)

### Data Modelling

En un modelo de datos se muestran las conexiones de unas tablas con otras a través de sus características, columnas o features.

Para crear las conexiones de una tabla a otra, se necesitan definir:

- **Dimension table:** Contiene las claves / keys primarias, con una ocurrencia única por clave.

- **Fact table:** Contiene las claves / keys externas o *foreign*, con las cuales se busca en la Dimension table para obtener el valor o los valores correspondientes.

#### Agregar tabla de Excel al modelo de datos

1. En el menú de Power Pivot, dar clic en **Manage**

2. De regreso en el libro de trabajo de Excel, en la hoja con la tabla en cuestión, en la pestaña de Power Pivot, dar clic en **Add to Data Model**

#### Diagrama del modelo de datos

- En la ventana de Power Pivot, en el menú **Home**, dar clic en **Diagram view**

## Fórmulas DAX

### RELATED

Hace referencia a una tabla relacionada o conectada a la tabla actual como se ve en el diagrama de datos de Power Pivot. 

Conesta función se pueden referenciar columnas de otras tablas.

### DISTINCT

Regresa los valores únicos o **"distinct"** de la columna especificada.

### SUMX

Regresa la suma de una **expresión** evaluada para cada **fila** en una tabla.

### CALCULATE

Aplica **filtros** a la expresión indicada. La sintaxis de esta expresión es:

```
=CALCULATE(expression, filter1, filter2, ...)
```

Ejemplo:

```
=CALCULATE([Net Sales],dim_date[FY]=2019)
```