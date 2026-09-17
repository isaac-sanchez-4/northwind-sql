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
