### Pregunta 1 — Catálogo comercial activo
El equipo de ventas prepara la tarifa de la próxima campaña y necesita el catálogo depurado.

**Enunciado**
Obtén los productos que **no** están descatalogados y cuyo precio unitario esté entre 10 y 50 euros, ambos incluidos. Muestra el nombre del producto y su precio redondeado a dos decimales, ordenado de mayor a menor precio.

**consulta**
```
Select product_id, unit_price
from products
where discontinued = 0 and 
unit_price between 10 and 50
order by unit_price DESC;
```


![Resultado pregunta1](imagenes/preg1.png)

**comentario**
He utilizado where para filtrar primero por los prosuctos descatalogados y despues con el `between`filtro por los que estan en el rango que buscamos


Pregunta 2 — Concentración geográfica de la carteraEl equipo de ventas prepara la tarifa de la próxima campaña y necesita el catálogo depurado.

**Enunciado**
Dirección quiere saber en qué mercados está realmente concentrada la base de clientes antes de decidir dónde abrir delegación.

Cuenta cuántos clientes hay en cada país y muestra únicamente aquellos países con **5 o más clientes**, ordenados de mayor a menor. Indica también cuántas ciudades distintas hay en cada uno de esos países.

**consulta**
```
select country as pais ,
count(customer_id) as total_clientes,
COUNT(DISTINCT city) AS ciudades_distintas
from customers 
group by country
HAVING COUNT(customer_id) >= 5
ORDER BY 
    total_clientes DESC;
```


![Resultado pregunta1](imagenes/preg2.png)

**comentario** con count(customer_id) cuento todos los clientes que existen despues con count(distinct city ) cuento cuantas ciudades diferentes tienen registros de un mismo cliente mediante group by country se realiza una agrupacion de los resultados para que las funcines de conteo sirvan para cada pais y mediante having count filtramos para mostar solo aquellos con 5 o mas 


### Pregunta 3 — Alerta de reposición

Logística necesita detectar qué referencias están en riesgo de rotura de stock

**Enunciado**
Localiza los productos activos cuyas unidades en stock sean inferiores o iguales a su nivel de reposición. Muestra el nombre, las unidades en stock, el nivel de reposición, las unidades ya pedidas al proveedor y una columna de texto que indique 'CRÍTICO' cuando el stock sea 0 y 'AVISO' en el resto de casos.

**consulta**
```
SELECT 
    product_name AS producto,
    units_in_stock AS stock,
    reorder_level AS nivel_reposicion,
    units_on_order AS pedido_a_proveedor,
    CASE 
		when units_in_stock = 0 THEN ' critico'
		ELSE 'AVISO'
	End as situacion
FROM Products
```


![Resultado pregunta1](imagenes/preg3.png)

**comentario** utilizo case when porque como nos pide indicar si critico o aviso segun el stock disponible y con where filtramos por su disponivilidad buscando solo porductos activos 
