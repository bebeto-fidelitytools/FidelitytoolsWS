* [Problemas de autorizacion](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_autorizacion.md)
* [Acceso Denegado](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#acceso-denegado)
* [No existen resultados de búsqueda](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#no-existen-resultados-de-b%C3%BAsqueda)
* [Límite de registros mayor al permitido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#l%C3%ADmite-de-registros-mayor-al-permitido)
* [Error interno de procesamiento](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#error-interno-de-procesamiento)
* [Parametro offset invalido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#par%C3%A1metro-offset-inv%C3%A1lido)
* [Parametro limit invalido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#par%C3%A1metro-limit-inv%C3%A1lido)
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
Metodos: [get_catalogo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/get_catalogo.md), [delete_catalogo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/delete.md), [set_catalogos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/set.md)

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
Metodos: [set_catalogos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/set.md), [set_precio_stock_x_productos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/set_precio_stock_x_productos.md)

La lista de productos a actualizar o registrar no puede estar vacia.
