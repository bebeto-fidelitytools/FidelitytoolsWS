### Descripcion
Permite obtener todos los campos personales registrados.
___

### URL
` https://ws.fidelitytools.net/v2/api/segmentacion/campopersonal/get `
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

___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 122e343fdaddsb94e18fff" 
https://ws.fidelitytools.net/v2/api/segmentacion/campopersonal/get
```
___
### Respuestas
***Petición exitosa***
```json
{
    "camposPersonales": [
        {
            "idCampoPersonal": 1542,
            "nombre": "CUIL-CUIT",
            "valor": "",
            "segmentos": [
                {
                    "idSegmento": "Mzc4Mg",
                    "nombre": "Fidelity"
                },
                {
                    "idSegmento": "NDU1MQ",
                    "nombre": "G - Clientes"
                },
                {
                    "idSegmento": "NTIzNA",
                    "nombre": "Proveedores"
                }
            ]
        },
        {
            "idCampoPersonal": 1594,
            "nombre": "HS - Campo Personal 1",
            "valor": "",
            "segmentos": [
                {
                    "idSegmento": "Mzc4Mg",
                    "nombre": "Fidelity"
                }
            ]
        }
        
	}
]
```

##### HTTP STATUS CODE: 200 (Ok)

***Petición inválida***
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
