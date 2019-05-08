### Descripcion
Permite eliminar una o más actividades que se encuentren previamente registradas en Fidelitytools.
___

### URL
` https://ws.fidelitytools.net/v2/api/actividades/actividad/delete `
___

### Método
DELETE
___
### Parámetros

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/autenticaci%C3%B3n.md). |


##### Body
```json
[
	{"id":985561, "actividadTipo": {"id": "52eWX1" } },
	{"idExterno":"77-TR-001", "actividadTipo": {"id": "52eWX1" } }
]
```
Como se detalla, este metodo recibe una matriz o colección de
actividades, donde por cada objeto Actividad, los parámetros requeridos obligatorios son los valores
asociados a las propiedades:
- id o idExterno.
- id de la propiedad actividadTipo (del objeto ActividadTipo).
En este ejemplo se detallan dos actividades a eliminar, una mediante el campo id y la otra mediante
el campo idExterno.
___
### Ejemplo
```bash

curl -XDELETE 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
-d "[{id:985561, actividadTipo: {id: \"8Op7\"}  },{idExterno:\"77-TR-001\", actividadTipo: {id: \"8Op7\" } }]" 
https://ws.fidelitytools.net/v2/api/actividades/actividad/delete
```
___
### Respuestas
***Petición exitosa***
```json
{
	"mensajes":[
    	{ "respuesta": "Actividad: id: 985561 - Eliminada exitosamente", "estado":true },
    	{ "respuesta": "Actividad: idExterno: COD001 - Eliminada exitosamente", "estado":true }
    ]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/bad_request.md)

