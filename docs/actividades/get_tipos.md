### Descripcion
Esta función lo que permite es obtener la información básica relacionada a los tipos de actividades asociados al valor del parámetro key. En base a esta información se puede obtener la configuración de la estructura de datos de un determinado tipo de actividad ([get_configuracion_tipo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/get_configuracion_actividad_tipo.md)) con respecto a: perfiles generales de actividad, campos personales de actividad y etapas de actividad.
___

### URL
` https://ws.fidelitytools.net/v2/api/actividades/actividad/gettipos `
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
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
https://ws.fidelitytools.net/v2/api/actividades/actividad/gettipos
```
___
### Respuestas
***Petición exitosa***
```json
{
    "actividadesTipo": [
        {
            "id": "N5SDE",
            "nombre": "Turno",
            "fechaAlta": "2017-01-17T09:02:44.987",
            "estado": {
                "id": 1,
                "nombre": "Habilitado"
            }
        }
    ]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/bad_request.md)
