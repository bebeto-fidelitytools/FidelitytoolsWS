### Descripcion
Obtiene un archivo mediante su id
___

### URL
` https://ws.fidelitytools.net/v2/api/archivos/archivo/getArchivo?idArchivo= `
___

### Método
GET
___
### Parámetros

##### URL

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| idArchivo | Si | Id del archivo que se quiere obtener |

___
### Ejemplo
```bash
curl -XGET 
"https://ws.fidelitytools.net/v2/api/archivos/archivo/getarchivo?idArchivo=VWtiM1BoNU4wO1VV1jJWSERkUktTd509"
```
___
### Respuestas
***Petición exitosa: Con el link se puede visibilizar el archivo deseado***

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas: [bad_request]()***
