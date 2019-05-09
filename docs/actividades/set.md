### Descripcion
Permite registrar o actualizar una o más actividades de una o más personas.
Si la actividad contiene valores en los campos **id** o **idExterno**, el servicio web intentará actualizar la actividad con los valores provistos. De lo contrario, si la actividad no posee valores en dichos campos o los valores provistos no existen previamente, el servicio web intentará registrar la actividad.
___

### URL
` https://ws.fidelitytools.net/v2/api/actividades/actividad/set `
___

### Método
POST
___
### Parámetros

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/usuario/autenticaci%C3%B3n.md). |


##### Body
```json
[
      {
            "idPersona":"1015454",
            "segmento":{"idSegmento":"5X5Oi1"},
            "actividades":[{
           	  "idExterno":"777-8BDR",
                  "nombre":"Pago Compra N.789982",
                  "estado":{"id":1,"nombre":"Habilitado"},
                  "ActividadTipo":{"id":"111"},
                  "perfilesGenerales":
                  [{
                    	"id":66, "nombre": "TipoCompra", 
                        "pgActividadValores": [ {"id":0, "nombre":"Contado"} ]
                    }],
                  "camposPersonales":
                  [ { "cpActividad": {"id":46, "nombre":"Codigo"}, "valor":"789982"} ],
                  "etapas":
                  [ {"id":1, "nombre":"Pendiente"} ]
            },
            {
                  "nombre":"Pago Compra N.101982",
                  "estado":{"id":1,"nombre":"Habilitado"},
                  "ActividadTipo":{"id":"111"},
            }]
        },
        {
            "idPersona":"10301056",
            "segmento":{"idSegmento":"5X5Oi1"},
            "actividades":[{
                "nombre":"Pago Compra N.233982",
                "estado":{"id":1,"nombre":"Habilitado"},
                "ActividadTipo":{"id":"111"},
            }]
	}
]
```
Como se detalla, este metodo recibe una matriz o colección de
personas, donde por cada objeto Persona, los parámetros requeridos obligatorios son los valores asociados
a las propiedades:
- idExterno o idPersona.
- idSegmento (del objeto Segmento).

Por cada actividad asociada a la persona, los parámetros requeridos obligatorios son los valores asociados a
las propiedades:
- id o idExterno (del objeto Actividad). Siempre y cuando la intención sea actualizar una actividad. Si la intención es registrar una nueva actividad, el valor del campo id debe ser igual a 0 y el valor de
idExterno debe ser vacío o un valor que no exista previamente.
- id (del objeto ActividadTipo). En el caso de la imagen esta incluido el campo nombre solo para
identificar el tipo de actividad procesada, pero no es requisito obligatorio el uso del mismo.
- id (del objeto Estado). El valor puede ser 1 (Habilitado) o 2 (Deshabilitado).
Por cada actividad asociada a la persona pueden incluirse opcionalmente los parámetros:
- nombre.
- descripción.
- perfilesGenerales.
- campoPersonales.
- etapas.
En el caso de utilizar estos parámetros opcionales, los parámetros requeridos obligatorios son los
valores asociados a las propiedades:
1. perfilesGenerales:
	- id (del Objeto ActividadPG).
	- id o nombre por cada elemento de la propiedad pgActividadValores (del objeto PGActividadValor).
2. camposPersonales:
	- id (del Objeto CPActividad). 
	- En este caso está incluido el campo nombre solo para
identificar sobre el campo personal de actividad procesado, pero no es requisito obligatorio el
uso del mismo.
	- valor (del objeto ActividadCP).
3. etapas:
	- id (del Objeto Etapa).
	- La propiedad nombre se detalla solo para identificar sobre la etapa de actividad
procesada, pero no es requisito obligatorio el uso del mismo.
___
### Ejemplo
```bash
curl -XPOST 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
-d "[{idPersona:\"1015454\",segmento:{idSegmento:\"5X5Oi1\"},actividades:[{idExterno:\"777-8BDR\",estado:{id : 1},nombre:\"Pago Compra N.789982\",estado:{id:1,nombre:\"Habilitado\"},ActividadTipo:{id:\"111\"},perfilesGenerales:[{id:66, nombre: \"TipoCompra\", pgActividadValores: [ {id:0, nombre:\"Contado\"} ]}],camposPersonales:[ { cpActividad: {id:46, nombre:\"Codigo\"}, valor:\"789982\"} ],etapas:[ {id:1, nombre:\"Pendiente\"} ]}}]" 
https://ws.fidelitytools.net/v2/api/actividades/actividad/set
```
___
### Respuestas
***Petición exitosa***
```json
{
    "mensajes": [
        {
            "respuesta": "Persona: idPersona: 1015454 - Segmento: idSegmento: Mzc4Mg - Actualizada exitosamente",
            "estado": true,
            "clase": "persona",
            "id": "1015454"
	    
        },
        {
            "respuesta": "Actividad: Pago Compra N.789982 id: 2081344 - Agregada exitosamente",
            "estado": true,
            "clase": "actividad",
            "id": "2081344"
        },
        {
            "respuesta": "Actividad: Pago Compra N.789982 id: 2081326 - Agregada exitosamente",
            "estado": true,
            "clase": "actividad",
            "id": "2081326"
        }
	]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/bad_request.md)
 
