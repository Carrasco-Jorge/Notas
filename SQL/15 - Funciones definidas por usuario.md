# Funciones definidas por el usuario

Se pueden definir funciones que reciban un input y regresen un output para hacer más legibles las consultas de SQL. En MySQL Workbench, desplegar BD actual y en *Functions* dar clic derecho y *Create function*. Se abrirá una nueva pestaña donde se puede escribir la función.

Sintaxis:

```sql
CREATE DEFINER=`root`@`localhost` FUNCTION `get_fiscal_year`(
	calendar_date DATE
) RETURNS INT
DETERMINISTIC
BEGIN
	DECLARE fiscal_year INT;
    SET fiscal_year = IF(MONTH(calendar_date)>=9, YEAR(calendar_date)+1,YEAR(calendar_date));
	RETURN fiscal_year;
END
```

La palabra clave **DETERMINISTIC** significa que el output de la función dado un input, siempre será el mismo.

Las palabras clave **NOT DETERMINISTIC** significan que el output de la función dado un input, no siempre será el mismo.