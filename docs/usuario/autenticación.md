### Descripcion
Recibe como parametro un token caducado y retorna un nuevo token.
___

### URL
` https://ws.fidelitytools.net/v2/api/user/gettokenrefresh `
___

### Método
GET
___
### Parámetros

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| token | Si | el token que se quiere regenerar. |

___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
https://ws.fidelitytools.net/v2/api/user/gettokenrefresh
```
___
### Respuestas
***Petición exitosa***
```json
{
    "mensajes": [
        {
            "respuesta": "101JhbGciOiJIUz664hdg2YaRInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAttsa",
            "estado": true
        }
    ]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas:*** [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/usuario/bad_request.md)

 

