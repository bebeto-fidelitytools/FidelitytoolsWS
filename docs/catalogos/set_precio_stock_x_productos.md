### Descripcion
Existen 2 funciones para actualizar datos de productos ya registrados en el catálogo de productos de
Fidelitytools.
La primera opción es utilizar el metodo que crea un catálogo de productos [set](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/set.md) ya que dicha función permite crear un catálogo o actualizarlo.
Los productos a actualizar se actualizan mediante la propiedad codigoInterno.
La segunda opción es la función wsSetPrecioStockxProducto que permite actualizar las propiedades
precio, stock, precio2 y stock2 de uno o más productos, siempre y cuando cada producto a actualizar posea
en su propiedad codigoInterno el valor correspondiente.

Ambas funciones priorizan los datos del producto ingresado en el JSON sobre los datos ya
registrados, por ende si se desea actualizar solo algunos datos de un producto, deben enviarse todos los
datos del producto, tanto los que se desean actualizar como los que no, ya que si algún valor de la
propiedad del producto, de la estructura del JSON, se encuentra vacío se reemplazará al valor de la
propiedad previamente registrada en la base de datos de Fidelitytools.
___

### URL
` https://ws.fidelitytools.net/v2/api/catalogos/catalogo/SetPrecioStockxProductos/{idCatalogo} `
___

### Método
POST
___
### Parámetros

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/autenticaci%C3%B3n.md). |

##### URL

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| idCatalogo | Si | Clave identificadora que representa el catalogo donde se encuentran los productos a modificar.|
##### Body
```json
[
	{
	    "codigoInterno": 156760,"precio":1000.00, "stock":800.00, "precio2":500, "stock2":100.00
	}
]
```
Cabe aclarar que con esta función pueden actualizarse tanto productos principales como sub
productos ya que lo que determina el producto a actualizar es el campo codigoInterno.
___
### Ejemplo
```bash
curl -XPOST 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
-d "[{\"codigoInterno\": 156760,\"precio\":1000.00, \"stock\":800.00, \"precio2\":500, \"stock2\":100.00}]" 
https://ws.fidelitytools.net/v2/api/catalogos/catalogo/SetPrecioStockxProductos/NzI5OQ
```
___
### Respuestas
***Petición exitosa***
```json
{
    "mensajes": [
        {
            "respuesta": "Producto: Cod. Interno: 156760 - Titulo:  - Actualización Exitosa.",
            "estado": true
        }
    ]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/bad_request.md)
