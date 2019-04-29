#### Llave de acceso inválida
```json
{
    "mensajes": [
        {
            "respuesta": "Llave de acceso inválida.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 401 (Unauthorized)
La llave de acceso que se paso por el header key es invalido.
___
#### Llave de acceso inexistente
```json
{
    "mensajes": [
        {
            "respuesta": "Llave de acceso inexistente.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 401 (Unauthorized)
No existe el header key en la peticion.
___
#### Llave de acceso vacía
```json
{
    "mensajes": [
        {
            "respuesta": "Llave de acceso vacía.",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 401 (Unauthorized)
El header key esta vacio.
___
#### Token caducado
```json
{
    "mensajes": [
        {
            "respuesta": "Token caducado",
            "estado": false
        }
    ]
}
```
##### HTTP STATUS CODE: 401 (Unauthorized)
El token ingresado mediante el header Authorization es invalido.
___
#### No existe header Authorization
```json
{
    "Message": "Authorization has been denied for this request."
}
```
##### HTTP STATUS CODE: 401 (Unauthorized)
No se especifico el header Authorization.
