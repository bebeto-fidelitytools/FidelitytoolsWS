* [Problemas de autorizacion]()
* [Acceso Denegado]()
* [No existen resultados de búsqueda]()
* [Límite de registros mayor al permitido]()
* [Parámetro offset inválido]()
* [Parámetro limit inválido]()
___
#### Parámetro idCatalogo vacío
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro idCatalogo vacío",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodos: [get_catalogo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/get_catalogo.md), [delete_catalogo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/delete_catalogo.md), [set_catalogos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/set_catalogos.md)

Esta respuesta ocurrirá cuando no se especifique el parametro requerido idCatalogo.
___
#### Lista de productos vacia
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Lista de productos vacia",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodos: [set_catalogos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/set_catalogos.md), [set_precio_stock_x_productos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/set_precio_stock_x_productos.md)

La lista de productos a actualizar o registrar no puede estar vacia.
