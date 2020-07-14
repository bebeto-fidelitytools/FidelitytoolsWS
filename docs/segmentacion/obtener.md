### Descripcion
Esta consulta permite obtener un listado de hasta 100 personas a partir del resultado obtenido de aplicar un grupo de filtros.
Los filtros se envián dentro del cuerpo de la consulta, para entender como se construyen estos filtros y personalizar tus conultas
conulta el siguiente link ["Estructura de Filtros"](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/consultas/consulta.md)
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

Para consultar este endpoint se debe utilizar una [estructura de Filtros](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/consultas/consulta.md) en base a las [propiedades del modelo persona.](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/set_personas.md#propiedades-de-la-clase-persona)

___
### Ejemplo
```bash
```
___
### Respuestas
***Petición exitosa***
```json
```

##### HTTP STATUS CODE: 200 (Ok)
