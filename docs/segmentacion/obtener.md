### Descripcion
Esta consulta permite obtener un listado de hasta 100 personas a partir del resultado obtenido de aplicar un grupo de filtros.
Los filtros se envián dentro del cuerpo de la consulta, para entender como se construyen estos filtros y personalizar tus conultas, ingresá al siguiente link ["Estructura de filtros"](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/consultas/consulta.md)
___

### URL
` https://ws.fidelitytools.net/v2/api/segmentacion/persona/Obtener `
___

### Método
POST
___
### Parámetros

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | Token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/usuario/autenticaci%C3%B3n.md). |
| Content-Type         | Si		 | Es la propiedad de cabecera (header) usada para indicar el  media type del recurso. Se debe enviar el valor "application/json". |

##### Body

Dentro del body o cuerpo de la consulta se debe proporcionar los filtros, los filtros permiten ser más precisos con la información que se desea obtener. Para entender más de cómo se crean los filtros ingresa al siguiente link ["Estructura de filtros"](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/consultas/consulta.md).

Es importante que tengas en cuenta que estos filtros deben basase en las ["Propiedades del modelo persona."](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/set_personas.md#propiedades-de-la-clase-persona)

___
### Ejemplo
```bash
curl -X POST 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6InVzZXJBY2Nlc3NDb25maWciLCJuYmYiOjE1NTYxMjI1NzYsImV4cCI6MTU1NjIwODk3NiwiaWF0IjoxNTU2MTIyNTc2LCJpc3MiOiJodHRwczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHR0cHM6Ly93cy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9.lIY6hvvs8kjzAblEQzxkRcj-tVQOJ5Jmkh_ynmeLAe4" 
-H "key: 5c2e343fdad07d2b94e184d4" 
-d "{\"filtros\":[{\"propertyName\":\"segmento.idSegmento\",\"value\":"Mzc4Mg\",\"comparator\":\"Equal\"}],\"select\":[\"apellido\",\"nombre\",\"email\"],\"limit\":1}"
https://ws.fidelitytools.net/v2/api/segmentacion/persona/set
```
___
### Respuestas
***Petición exitosa***
```json
{
    "data": [
        {
            "nombre": "Desarrollo",
            "apellido": "Fidelitytools",
            "email": "desarrollo@fidelitytools.com"
        }
    ],
    "estado": true
}
```
##### HTTP STATUS CODE: 200 (Ok)
