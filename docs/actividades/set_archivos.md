### Descripcion
Permite registrarle una lista de archivos a una actividad. La forma que se utiliza para el envio de archivos en el request es a través de un [form-data](https://developer.mozilla.org/en-US/docs/Web/API/FormData/Using_FormData_Objects).
___

### URL
` https://ws.fidelitytools.net/v2/api/actividades/actividad/setArchivos/{idTipoActividad}/{idActividad} `
___

### Método
POST
___
### Parámetros obligatorios

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/autenticaci%C3%B3n.md). |
| Content-Type | Si | El content-type de la peticion debe ser **'multipart/form-data'** |

##### Body
El body debe ser un form data, Compuesto de registros <clave, valor> En donde el valor será el archivo a registrar de la actividad. 
___
### Ejemplo
```bash
curl -XPOST 
-H "Content-Type: multipart/form-data" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
-F "file=@D:\Files\FacturaN22154.txt" 
-F "file=@D:\Files\FacturaN22155.txt" 
https://ws.fidelitytools.net/v2/api/actividades/actividad/setarchivos/FTWS/10124
```
___
### Respuestas
***Petición exitosa***
```json
{
	"mensajes":[
    	{
            "respuesta":"Archivo creado correctamente",
            "estado":true,
            "clase":"archivo",
            "id":"1012154"
        },
        {
            "respuesta":"Archivo creado correctamente",
            "estado":true,
            "clase":"archivo",
            "id":"1012155"
        }
	]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/bad_request.md)***
