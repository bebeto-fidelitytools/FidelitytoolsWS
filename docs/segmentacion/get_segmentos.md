### Descripcion
Permite obtener todos los segmentos registrados.
___

### URL
` https://ws.fidelitytools.net/v2/api/segmentacion/segmento/get `
___

### Método
GET
___
### Parámetros

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. | 
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/usuario/autenticaci%C3%B3n.md). | 


___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkeyJ1bmltZSI6InVzZXJBY2Nlc3NDb25maWciLCJuYmYiOjE1NTYxMTk0MDcU1NjIwNTgwNywiaWF0IjoxNDA3LCJpc3MizovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHR0cHM6Ly93cy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9" 
-H "key: 5c2e343fda123ars1234" 
https://ws.fidelitytools.net/v2/api/segmentacion/segmento/get
```
___
### Respuestas
***Petición exitosa***
```json
{
    "segmentos": [
        {
            "idSegmento": "M214Mh",
            "nombre": "Fidelity"
        },
        {
            "idSegmento": "Nj44N4",
            "nombre": "Clientes"
        }
    ],
    "paginador": {
        "total": 2
    }
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/bad_request.md)
 
