#### Acceso Denegado
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Acceso denegado" ,
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Esta respuesta ocurrirá cuando se intente hacer una accion para la cual su usuario no tiene permisos.
___
#### No existen resultados de búsqueda
```json
{
    "mensajes": [
        {
            "respuesta": "No existen resultados de búsqueda",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
Esta respuesta ocurrirá cuando se intente obtener una lista de objetos y no se encuentren registros en la base de datos.
___
#### Límite de registros mayor al permitido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Límite de registros mayor al permitido",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
El limite de registros tanto para obtener registros como para registrar o actualizar es de 100. Esta respuesta ocurrirá cuando se especifique un numero mayor a este.
___
#### Error interno de procesamiento.
```json
{
    "mensajes": [
        {
            "respuesta": "Error interno de procesamiento. Contactese con Soporte de Fidelitytools: soporte@fidelitytools.com",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 500 (Internal Server Error)
Cuando se devuelva esta respuesta contactese con soporte, especifiquenle la situacion y se le proporcionara una solución.
___
#### Parámetro offset inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro offset inválido",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)

El parametro offset acepta valores que sean mayores o iguales a cero.
___
#### Parámetro limit inválido
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetro limit inválido",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 400 (BadRequest)
El limite indicado tiene que ser mayor que cero.
