# Stored procedures

Se pueden definir procesos que reciban un input y regresen un output para automatizar procesos o consultas de SQL. En MySQL Workbench, desplegar BD actual y en *Stored procedures* dar clic derecho y *Create stored procedure*. Se abrirá una nueva pestaña donde se puede escribir la función.

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_monthly_gross_sales`(
	customer_code_var INT
)
BEGIN
SELECT 
	s.date, 
    ROUND(SUM(s.sold_quantity * g.gross_price), 2) AS gross_sales
FROM fact_sales_monthly s JOIN fact_gross_price g ON 
		s.product_code=g.product_code AND
        g.fiscal_year=get_fiscal_year(s.date)
WHERE s.customer_code=customer_code_var
GROUP BY s.date
ORDER BY date ASC;
END
```

Se puede hacer lo siguiente para usar el proceso con una consulta de SQL: 

```sql
call nombrebd.nombre_proceso(argumentos);
```