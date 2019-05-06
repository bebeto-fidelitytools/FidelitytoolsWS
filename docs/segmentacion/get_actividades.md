### Descripcion
Obtiene las actividades de una persona dentro de un rango de fechas.
___

### URL
` https://ws.fidelitytools.net/v2/api/segmentacion/persona/getActividades/{idPersona}/{offset}/{limit}?idTipoActividad=&fechaAltaDesde=&fechaAltaHasta=&fechaModificacionDesde=&fechaModificacionHasta= `
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
| idPersona | Si | Clave identificadora de la persona de la cual se va a buscar sus actividades. | 
| offset | Si | la posición desde donde arranca el rango de registros a obtener. |
| limit | Si | Limite de registros a obtener. El limite permitido por el sistema es de 100.|
| idTipoActividad | Opcional | Clave identificadora de un tipo de actividad. Si se utiliza se mostraran solo las actividades de ese tipo. |
| fechaAltaDesde | Opcional | Fecha de alta desde de una o más personas. **Formato dd/mm/aaaa**
| fechaAltaHasta | Opcional |Fecha de alta hasta de una o más personas. **Formato dd/mm/aaaa**
| fechaModificacionDesde | Opcional |Fecha de modificación desde de una o más personas. **Formato dd/mm/aaaa**
| fechaModificacionHasta| Opcional |Fecha de modificación hasta de una o más personas. **Formato dd/mm/aaaa**

Los parámetros de tipo fecha pueden utilizarse tanto por separado como en conjunto, pero es
obligatorio el uso **al menos de un conjunto** desde – hasta.
Los conjuntos son:
1. fechaAltaDesde – fechaAltaHasta.
2. fechaModificacionDesde – fechaModificacionHasta.

___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff"
"https://ws.fidelitytools.net/v2/api/segmentacion/persona/getActividades/1058794/0/100?idTipoActividad=Zxt&fechaAltaDesde=01/02/2019&fechaAltaHasta=04/05/2019&fechaModificacionDesde=01/02/2019&fechaModificacionHasta=06/05/2019"
```
___
### Respuestas
***Petición exitosa***
```json
{
    "personas": [
        {
            "idPersona": 7345372,
            "nombre": "Hernan",
            "apellido": "Alvarez",
            "dni": "44587954",
            "email": "halvarez@gmail.com",
            "actividades": [
                {
                    "id": 2052658,
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
                        "id": "Zxt",
                        "nombre": "Pago"
                    }
                },
                {
                    "id": 10879845,
                    "idExterno": "123-8BDR",
                    "nombre": "Pago Compra N.103451",
                    "descripcion": "",
                    "fechaAlta": "2019-04-25T10:08:07.93",
                    "fechaModificacion": "2019-05-05T17:25:52.163",
                    "estado": {
                        "id": 1,
                        "nombre": "Habilitado"
                    },
                    "actividadTipo": {
                        "id": "Zxt",
                        "nombre": "Pago"
                    }
                }
            ]
        }
    ],
    "paginador": {
        "total": 2,
        "limit": 100
    }
}
```

##### HTTP STATUS CODE: 200 (Ok)
Como se detalla, el metodo devuelve informacion basica de la persona (Si quiere obtener su informacion completa puede utilizar el metodo [get_persona](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_persona.md)). Ademas este metodo proporciona la informacion de sus actividades. Si queremos obtener mas informacion podemos utilizar el metodo [get_actividad](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/get_actividad.md), Este nos dará: 
* Campos personales de actividad
* Perfiles generales de actividad
* etapas

***Peticiones inválidas:*** [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/bad_request.md)
