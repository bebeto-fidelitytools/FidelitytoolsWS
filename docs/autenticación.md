### Descripción:

Obtiene el token de acceso usando usuario y contraseña otorgados por Fideliytools.

### URL:

`https://ws.fidelitytools.net/v2/api/user/authenticate/{username}/{password}`

### Método: GET

### Parámetros:

|Parámetro |Requerido |Descripción                 |Ejemplo         |
|----------|----------|----------------------------|----------------|
|username  |SI        |Nombre de usuario           |usuario-123     |
|password  |SI        |Contraseña de usuario       |password-123    |

### Ejemplo:
```bash
curl -XGET 'https://ws.fidelitytools.net/v2/api/user/authenticate/usuario-123/password-123'
```
### Respuestas:

***Credenciales válidas***

```json
{
    "mensajes": [
        {
            "respuesta": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6ImNlbnRyby1kZWwtcGVpbmFkb3IiLCJuYmYiOjE1NTU0NDUwMDksImV4cCI6MTU1NTUzMTQwOSwiaWF0IjoxNTU1NDQ1MDA5LCJpc3MiOiJodHRwczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHR0cHM6Ly93cy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9.cUCn5wJ1C2zB4eM1JyQH7zV_eIKgMCtGDPqgZqIzJAY",
            "estado": true
        }
    ]
}
```

###### HTTP STATUS CODE: 200 (Ok)


***Credenciales inválidas***

```json
{
    "mensajes": [
        {
            "respuesta": "Credenciales de acceso inválidas",
            "estado": false
        }
    ]
}
```
###### HTTP STATUS CODE: 401 (Unauthorized)

