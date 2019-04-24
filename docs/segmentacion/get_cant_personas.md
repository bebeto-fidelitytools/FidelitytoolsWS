### Descripcion
Obtiene la cantidad de personas registradas en un segmento específico.
___

### URL
` https://ws.fidelitytools.net/v2/api/segmentacion/persona/getCantPersonas/{idSegmento} `
___

### Método
GET
___
### Parámetros obligatorios

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. | 
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/autenticaci%C3%B3n.md). | 

##### URL
|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| idSegmento | Si | Id del segmento del que se desea saber la cantidad de personas que contiene. | 

___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkeyJ1bmltZSI6InVzZXJBY2Nlc3NDb25maWciLCJuYmYiOjE1NTYxMTk0MDcU1NjIwNTgwNywiaWF0IjoxNDA3LCJpc3MizovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHR0cHM6Ly93cy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9.RDDpMHEB4SsmY0j87OcS5mbxeBWbyKqg2XxSAY" 
-H "key: 5c2e343fda123ars1234" 
https://ws.fidelitytools.net/v2//api/segmentacion/persona/getCantPersonas/MYc5M5
```
___
### Respuestas
***Petición exitosa***
```json
{
    "paginador": {
        "total": 17
    }
}
```
##### HTTP STATUS CODE: 200(Ok)

***Petición inválida***
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

##### HTTP STATUS CODE: 400(BadRequest)
