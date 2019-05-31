* [Problemas de autorizacion](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#llave-de-acceso-inv%C3%A1lida)
* [Acceso Denegado](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#acceso-denegado)
* [No existen resultados de búsqueda](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#no-existen-resultados-de-b%C3%BAsqueda)
* [Límite de registros mayor al permitido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#l%C3%ADmite-de-registros-mayor-al-permitido)
* [Error interno de procesamiento](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#error-interno-de-procesamiento)
* [Parametro offset invalido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#par%C3%A1metro-offset-inv%C3%A1lido)
* [Parametro limit invalido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#par%C3%A1metro-limit-inv%C3%A1lido)
___
#### Parámetro idSegmento vacío
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro idSegmento vacío",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodos: [get_cant_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_cant_personas.md), [get_persona](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_persona.md), [get_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md)
___
#### fechaAltaDesde, fechaAltaHasta y fechaModificacionDesde, fechaModificacionHasta vacíos
```json
{
    "mensajes": [
        {
            "respuesta": "Error: fechaAltaDesde, fechaAltaHasta y fechaModificacionDesde, fechaModificacionHasta vacíos",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md), [get_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_actividades.md)
___
#### fechaAltaDesde o fechaAltaHasta vacíos
```json
{
    "mensajes": [
        {
            "respuesta": "Error: fechaAltaDesde o fechaAltaHasta vacíos",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md), [get_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_actividades.md)
___
#### fechaModificacionDesde o fechaModificacionHasta vacíos
```json
{
    "mensajes": [
        {
            "respuesta": "Error: fechaModificacionDesde o fechaModificacionHasta vacíos",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md), [get_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_actividades.md)
___
#### fechaAltaDesde o fechaAltaHasta con formato inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: fechaAltaDesde o fechaAltaHasta con formato inválido",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md), [get_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_actividades.md)

El formato de las fechas debe ser **dd/mm/yyyy**.
___
#### fechaAltaDesde y fechaAltaHasta con rango inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: fechaAltaDesde y fechaAltaHasta con rango inválido.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md), [get_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_actividades.md)

Este error hace referencia a que las fechas ingresadas para filtrar pedidos no pueden ser superiores al dia actual. Ademas, el rango máximo permitido entre fechaInicio y fechaFin es de 92 días (3 meses).
___

#### fechaModificacionDesde o fechaModificacionHasta con formato inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: fechaModificacionDesde o fechaModificacionHasta con formato inválido",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md), [get_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_actividades.md)

El formato de las fechas debe ser **dd/mm/yyyy**.
___
#### fechaAltaDesde y fechaAltaHasta con rango inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: fechaAltaDesde y fechaAltaHasta con rango inválido.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md), [get_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_actividades.md)

Este error hace referencia a que las fechas ingresadas para filtrar pedidos no pueden ser superiores al dia actual. Ademas, el rango máximo permitido entre fechaInicio y fechaFin es de 92 días (3 meses).
___
#### idPersona e idExterno vacios
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetros idPersona e idExterno vacios",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_persona](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_persona.md)
___
#### Colección de personas vacía
```json
{
    "mensajes": [
        {
            "respuesta": "Error: colección de personas vacía",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [set_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/set_personas.md)
___
#### Parámetro idPersona igual a cero.
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro idPersona igual a cero.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_actividades.md)
___
#### Parámetro idPerfilGeneral inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro idPerfilGeneral inválido",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_valores_perfil_general](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_valores_perfil_general.md)


