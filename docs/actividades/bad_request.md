* [Problemas de autorizacion](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_autorizacion.md)
* [Acceso Denegado](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#acceso-denegado)
* [No existen resultados de búsqueda](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#no-existen-resultados-de-b%C3%BAsqueda)
* [Límite de registros mayor al permitido](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#l%C3%ADmite-de-registros-mayor-al-permitido)
* [Error interno de procesamiento](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#error-interno-de-procesamiento)

___
#### Coleccion de personas vacia
```json
{
    "mensajes": [
        {
            "respuesta": "Error: coleccion de personas vacia",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodos: [set_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set.md), [delete_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/delete.md) 
___
#### Parámetro idTipoActividad vacío
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro idTipoActividad vacío",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_configuracion_tipo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/get_configuracion_tipo.md), [get_actividad](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/get_actividad.md) 
___
#### Parámetro idActividad es igual a cero
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro idActividad es igual a cero.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo:[get_actividad](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/get_actividad.md)
