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
Metodo: [set_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set.md), [delete_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/delete.md) 

Indica que la lista de personas que se pasó como parametro para eliminar, actualizar o registrar esta vacia.
##### HTTP STATUS CODE: 400 (BadRequest)
___
#### Parámetro idTipo vacío
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro idTipo vacío",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_configuracion_tipo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/get_configuracion_tipo.md) .

Se refiere a que no se especifico el tipo de actividad del cual se quiere obtener su configuracion. 
