* [Problemas de autorizacion]()
* [Acceso Denegado]()
* [No existen resultados de búsqueda]()
* [Límite de registros mayor al permitido]()
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
Metodo: [set_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set_actividades.md), [delete_actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/delete_actividades.md) 

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
