# Creación de bases de datos

## Etapas

1. Modelo conceptual

2. Diagrama de relación de entidades (Etity Relationship Diagram / ERD)

3. Esquema de base de datos (Database Schema)

## Integridad de datos / Data integrity

La medida de consistencia y precisión de los datos en su ciclo de vida.

The measure of consistency and accuracy of data over its life cycle.

### Tabla enlace / Link table

Es un tipo de tabla que funge como enlace entre otras dos tablas.

### Normalización

Es el proceso de organizar una base de datos para evitar la duplicación de datos y mejorar la integridad de estos.

## Diagramas ERD

Se pueden crear este tipo de diagramas en MySQL workbench en:

```
File > New model > Add Diagram (doble clic)
```

## Características de columnas / features en MySQL

- Primary key (PK)

- Not Null (NN)

- Unique Index (UQ)

- Is Binary column (B)

- Unsigned data type (UN)

- Zero fill (ZF)

- Auto incremental (AI)

- Generated column (G)

## Crear base de datos a partir de diagrama ERD (Forward engineer)

```
Abrir diagrama > Database > Forward Engineer
```

## Crear diagrama ERD a partir de base de datos extistente (Reverse engineer)

```
Abrir conexión > Database > Reverse Engineer
```

## Insertar datos en BD desde CSV

Definir la BD en la que se quieren insertar los datos como BD por defecto. Primero, Insertar todas las tablas padre primero y luego las tablas hijas.

1. Import records from external file

2. Browse for file

3. Select existing table / create new table, **truncate table**: elimina todos registros antes de insertar CSV

4. Map table columns with CSV columns

5. Next > Next > ... > Finish