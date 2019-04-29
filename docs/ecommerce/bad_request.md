* [Problemas de autorizacion](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_autorizacion.md)
* [Acceso Denegado](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#acceso-denegado)
* [No existen resultados de búsqueda](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#no-existen-resultados-de-b%C3%BAsqueda)
* [Límite de registros mayor al permitido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#l%C3%ADmite-de-registros-mayor-al-permitido)
* [Error interno de procesamiento](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#error-interno-de-procesamiento)
* [Parametro offset invalido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#par%C3%A1metro-offset-inv%C3%A1lido)
* [Parametro limit invalido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#par%C3%A1metro-limit-inv%C3%A1lido)
___
#### Parámetro idEcommerce vacío
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro idEcommerce vacío",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodos: [get_pedidos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/get_pedidos.md), [set_estados](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/set_estados.md)
___
#### Parámetro fechaInicio y/o fechaFin vacíos
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro fechaInicio y/o fechaFin vacíos",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_pedidos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/get_pedidos.md)
___
#### Parámetro fechaInicio y/o fechaFin con formato inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro fechaInicio y/o fechaFin con formato inválido",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_pedidos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/get_pedidos.md)

El formato de las fechas es **dd/mm/yyyy**.
___
#### fechaInicio y fechaFin con rango inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: fechaInicio y fechaFin con rango inválido",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodos: [get_pedidos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/get_pedidos.md), [set_estados](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/set_estados.md)

Este error hace referencia a que las fechas ingresadas para filtrar pedidos no pueden ser superiores al dia actual. Ademas, el rango máximo permitido entre fechaInicio y fechaFin es de 92 días (3 meses).
___
#### Listado de pedidos vacío
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Listado de pedidos vacío",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)

Metodo: [set_estados](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/set_estados.md)

El parametro listado de productos, a actualizarles el estado esta vacio.
