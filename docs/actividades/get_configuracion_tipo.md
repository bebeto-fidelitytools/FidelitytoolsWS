### Descripcion
Permite obtener toda la configuración de la estructura de datos de un determinado tipo de actividad
mediante los parámetros key e idActividadTipo. Ademas de su información básica obtiene sus perfiles generales, campos personales y etapas.
___

### URL
` https://ws.fidelitytools.net/v2/api/actividades/actividad/getconfiguraciontipo/{idTipo} `
___

### Método
GET
___
### Parámetros

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/autenticaci%C3%B3n.md). |

##### URL
|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| idTipo | Si | Id del tipo de actividad del cual se quiere saber su configuracion.|
___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
https://ws.fidelitytools.net/v2/api/actividades/actividad/getconfiguraciontipo/YSrrA2
```
___
### Respuestas
***Petición exitosa***
```json
{
    "actividadesTipo": [
        {
            "id": "YSrrA2", "nombre": "Turno", "fechaAlta": "2017-01-17T09:02:44.987",
            "actividadesTipoPG": [
                {
                    "pgActividad": {
                        "id": 66,"nombre": "Especialidad",
                        "estado": {"id": 1, "nombre": "habilitado"},
                        "pgActividadValores": [
                            {
                                "id": 3278, "nombre": "Clínica Medica",
                                "estado": {"id": 1, "nombre": "habilitado"}
                            },
                            {
                                "id": 5946, "nombre": "Traumatología",
                                "estado": {"id": 1, "nombre": "habilitado"}
                            }
                        ]
                    },
                    "tipoSeleccion": {"id": 2, "nombre": "selección múltiple"}
                }
            ],
            "actividadesTipoCP": [
                {
                    "cpActividad": {
                        "id": 76, "nombre": "Codigo",
                        "estado": {"id": 1, "nombre": "habilitado"}
                    },
                    "tipoCampo": {
                        "id": 5, "nombre": "código único"
                        }
                },
                {
                    "cpActividad": {
                        "id": 73, "nombre": "Observaciones",
                        "estado": {"id": 1, "nombre": "habilitado"}
                    },
                    "tipoCampo": {
                        "id": 1, "nombre": "texto"
                    }
                }
            ],
            "actividadTipoEtapa": {
                "tipoSeleccion": {
                    "id": 1, "nombre": "selección simple"
                },
                "etapas": [
                    {
                        "etapa": {
                            "id": 1, "nombre": "Pendiente",
                            "estado": {"id": 1, "nombre": "habilitado"}
                        },
                        "orden": 1
                    },
                    {
                        "etapa": {
                            "id": 3, "nombre": "Finalizada",
                            "estado": {"id": 1, "nombre": "habilitado"}
                        },
                        "orden": 3
                    }
                ]
            }
        }
    ]
}
```
El tipo de actividad obtenido contiene información relacionada a:
- Perfiles generales de actividad mediante la propiedad actividadesTipoPG.
- Campos personales de actividad mediante la propiedad actividadesTipoCP.
- Etapas de actividad mediante la propiedad actividadTipoEtapa.
##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/bad_request.md)
 
