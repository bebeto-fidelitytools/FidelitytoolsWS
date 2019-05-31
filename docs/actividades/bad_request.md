* [Problemas de autorizacion](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/bad_request_general.md#llave-de-acceso-inv%C3%A1lida)
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
#### Parámetro idActividad inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro idActividad inválido",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [get_actividad](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/get_actividad.md)
___
#### No existe una actividad con ese id
```json
{
    "mensajes": [
        {
            "respuesta": "Error: No existe una actividad con ese id.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [set_archivos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set_archivos.md)
___
#### No existe una actividad con ese id
```json
{
    "mensajes": [
        {
            "respuesta": "Error: No existe una actividad con ese id.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [set_archivos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set_archivos.md)
___
#### No es posible obtener los archivos
```json
{
    "mensajes": [
        {
            "respuesta": "Error: No es posible obtener los archivos.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [set_archivos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set_archivos.md)
___
#### No se encontraron archivos a registrar
```json
{
    "mensajes": [
        {
            "respuesta": "Error: No se encontraron archivos a registrar",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [set_archivos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set_archivos.md)
___
#### No se pudieron guardar los archivos
```json
{
    "mensajes": [
        {
            "respuesta": "Error: No se pudieron guardar los archivos",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [set_archivos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set_archivos.md)
___
#### No se enviaron correctamente los archivo
```json
{
    "mensajes": [
        {
            "respuesta": "Error: No se enviaron correctamente los archivos",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Metodo: [set_archivos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set_archivos.md)
