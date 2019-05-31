### Descripcion
Obtiene el listado de valores de un perfil general filtrado por su id.
___

### URL
` https://ws.fidelitytools.net/v2/api/segmentacion/perfilgeneral/getvalores/{idPerfilGeneral} `
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


##### URL
|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| idPerfilGeneral         | Si		 | Id del perfil general del cual se quieren obtener sus valores. |
___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
https://ws.fidelitytools.net/v2/api/segmentacion/perfilgeneral/getvalores/111
```
___
### Respuestas
***Petición exitosa***
```json
{
    "perfilesGenerales": [
        {
            "idPerfilGeneral": 3198,
            "perfilGeneralValores": [
                {
                    "idPerfilGeneralValor": 29187,
                    "nombre": "Aerolineas"
                },
                {
                    "idPerfilGeneralValor": 29188,
                    "nombre": "Agricultura"
                },
                {
                    "idPerfilGeneralValor": 29189,
                    "nombre": "Bazar"
                },
                {
                    "idPerfilGeneralValor": 29190,
                    "nombre": "Call Center"
                },
                {
                    "idPerfilGeneralValor": 33372,
                    "nombre": "Seguridad"
                },
                {
                    "idPerfilGeneralValor": 33373,
                    "nombre": "Cooperativa"
                },
                {
                    "idPerfilGeneralValor": 34285,
                    "nombre": "Administración/Oficina"
                }
            ]
        }
    ]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/bad_request.md)***
