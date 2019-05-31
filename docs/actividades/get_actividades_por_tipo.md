### Descripcion
Obtiene actividades segun un tipo de actividad.
___

### URL
` https://ws.fidelitytools.net/v2/api/actividades/Actividad/getActividadesPorTipo/{idTipoActividad}/{offset:int}/{limit:int} `
___

### Método
GET
___
### Parámetros

##### URL

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/usuario/autenticaci%C3%B3n.md). |

___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff"
https://ws.fidelitytools.net/v2/api/actividades/Actividad/getActividadesPorTipo/TRp2/0/1
```
___
### Respuestas
***Petición exitosa***
```json
{
    "actividades": [
    {
        "id": 1012658,
        "idExterno": "777-8BDR",
        "nombre": "Pago Compra N.789982",
        "descripcion": "",
        "fechaAlta": "2019-04-26T10:08:07.93",
        "fechaModificacion": "2019-05-03T17:25:52.163",
        "estado": {
            "id": 1,
            "nombre": "Habilitado"
        },
        "actividadTipo": {
            "id": "xtK",
            "nombre": "Pago"
        },
        "perfilesGenerales": [
            {
                "id": 66,
                "nombre": "Tipo de pago",
                "pgActividadValores": [
                    {
                    "id": 16650,
                    "nombre": "CONTADO"
                    }
                ]
            },
            {
                "id": 51,
                "nombre": "Condicion frente a IVA",
                "pgActividadValores": [
                    {
                    "id": 2771,
                    "nombre": "R.I."
                    }
                ]
            }
        ],
        "camposPersonales": [
            {
                "id": 76,
                "valor": "875463214"
            }
        ],
        "etapas": [
            {
                "id": 1,
                "nombre": "Pendiente",
                "fecha": "2019-04-26T10:32:20.5"
            }
        ]
    }],
    "paginador": {
        "total": 10,
        "limit": 1
    }
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/bad_request.md)***
