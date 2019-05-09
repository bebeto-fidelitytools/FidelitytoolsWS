  ### Descripcion
Permite obtener todos los perfiles generales registrados.
___

### URL
` https://ws.fidelitytools.net/v2/api/segmentacion/perfilgeneral/get `
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
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHR0cHM6Ly93cy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff"
https://ws.fidelitytools.net/v2/api/segmentacion/perfilgeneral/get
```
___
### Respuestas
***Petición exitosa***
```json
{
    "perfilesGenerales": [
        {
            "idPerfilGeneral": 3265,
            "nombre": "P - Formas de Pago",
            "tipoPerfil": "Múltiple",
            "perfilGeneralValores": [
                {
                    "idPerfilGeneralValor": 30870,
                    "nombre": "MASTERCARD"
                },
                {
                    "idPerfilGeneralValor": 30871,
                    "nombre": "VISA CREDITO"
                },
                {
                    "idPerfilGeneralValor": 30872,
                    "nombre": "VISA DÉBITO"
                }
            ],
            "segmentos": [
                {
                    "idSegmento": "NDA2NQ",
                    "nombre": "P - Clientes"
                }
            ]
        },
        {
            "idPerfilGeneral": 3266,
            "nombre": "P - Tipo",
            "tipoPerfil": "Múltiple",
            "perfilGeneralValores": [
                {
                    "idPerfilGeneralValor": 30868,
                    "nombre": "Local"
                },
                {
                    "idPerfilGeneralValor": 30869,
                    "nombre": "Gondola"
                }
            ],
            "segmentos": [
                {
                    "idSegmento": "NjE1OA",
                    "nombre": "P - Locales"
                }
            ]
        }
        
	]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/bad_request.md)
