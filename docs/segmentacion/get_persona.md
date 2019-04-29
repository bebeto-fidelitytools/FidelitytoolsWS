### Descripcion
Obtiene una persona determinada por el idSegmento, idPersona o idExterno.
___

### URL
` https://ws.fidelitytools.net/v2/api/segmentacion/persona/getpersona/{idSegmento}?idPersona=&idExterno= `
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
| idSegmento | Si | Id del segmento en donde se encuentra la persona que se está buscando. |
| idPersona | Opcional | Id de la persona que se quiere buscar. |
| idExterno | Opcional | IdExterno de la persona que se quiere buscar.| 

No es necesario que esten ambos valores(idPersona, idExterno) de una persona para buscarla. Pero al menos uno es necesario. Si se introducen ambos valores el metodo priorizara la busqueda por idPersona.

___
### Ejemplo
```bash
curl -XGET
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff"
"https://ws.fidelitytools.net/v2/api/segmentacion/persona/getpersona/N8X8Na?idPersona=7102269&idExterno=COD-0002"
```
___
### Respuestas
***Petición exitosa***
```json
{
    "personas": [
        {
            "idPersona": 2102507,
            "nombre": "Alberto",
            "apellido": "Pozada",
            "dni": "1231231",
            "fechaNac": "1999-05-25T00:00:00",
            "fechaAlta": "2019-04-17T17:26:16.417",
            "fechaModificacion": "2019-04-22T12:14:38.293",
            "provincia": "Córdoba",
            "habilitado": "S",
            "email": "apozada@gmail.com",
            "cp": "5000",
            "perfilesGenerales":[
                {
                    "idPerfilGeneral":1306, "nombre":"P - Formas de Pago","tipoPerfil": "Múltiple",
                    "perfilGeneralValores": [
                        {"idPerfilGeneralValor": 30870,"nombre": "MASTERCARD"},
                        {"idPerfilGeneralValor": 30871,"nombre": "VISA CREDITO"}
                    ]
                }
            ],
            "camposPersonales":[
            	{
                    "idCampoPersonal": 1542,
                    "nombre": "CUIL-CUIT",
                    "valor": "27-4451211-3",
                    "segmentos": [
                    	{"idSegmento": "NTM4OA","nombre": "Clientes"},
                      	{"idSegmento": "Mzc4Mg","nombre": "Fidelity"}
                    ]
                }  
            ]
        }
    ]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Petición inválida***
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Parámetros idPersona e idExterno vacios",
            "estado": false
        }
    ]
}
```

##### HTTP STATUS CODE: 400 (BadRequest)
