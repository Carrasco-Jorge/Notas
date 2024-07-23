# Insert, Update and Delete records

## Insert

```sql
INSERT INTO nombrebd.tabla
VALUES (
    val1, val2, val3, val4, val5
);
```

```sql
INSERT INTO nombrebd.tabla
(col2, col3, col5)
VALUES (
    val2, val3, val5
);
```

```sql
INSERT INTO nombrebd.tabla
VALUES (
    DEFAULT, val2, val3, NULL, val5
);
```
```sql
INSERT INTO nombrebd.tabla
VALUES 
    (DEFAULT, val2, val3, NULL, val5),
    (DEFAULT, val6, val7, NULL, NULL),
    (DEFAULT, val8, val9, NULL, NULL);
```

## Delete

```sql
DELETE FROM nombrebd.tabla
WHERE col1=val1;
```
```sql
DROP TABLE nombrebd.tabla
```

## Update 

```sql
UPDATE nombrebd.tabla
SET 
    col1=val1,
    col3=val3
WHERE (
    col2=val2
);
```