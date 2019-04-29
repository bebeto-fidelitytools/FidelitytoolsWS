### Descripcion
Obtiene un rango de personas registradas de un segmento específico. El rango de personas a
obtener está determinado por los parámetros offset y limit.
Se pueden aplicar dos filtros más al rango de registros que son la fecha de alta y/o la fecha de
modificación del rango de personas a obtener.
___

### URL
` https://ws.fidelitytools.net/v2/api/segmentacion/persona/getpersonas/{idSegmento}/{offset}/{limit}?fechaAltaDesde=&fechaAltaHasta=&fechaModificacionDesde=&fechaModificacionHasta= `
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
| idSegmento | Si | Id del segmento en donde se va a buscar las personas. |
| offset | Si | la posición desde donde arranca el rango de registros a obtener. |
| limit | Si | Limite de registros a obtener. El limite permitido por el sistema es de 100.| 
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
-H "Authorization: Bearer eeyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHR0cHM6Ly93cy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
"https://ws.fidelitytools.net/v2/api/segmentacion/persona/getPersonas/Mzc4Mg/0/100?fechaAltaDesde=01/01/2018&fechaAltaHasta=01/01/2019&fechaModificacionDesde=01/01/2018&fechaModificacionHasta=01/01/2020"
```
___
### Respuestas
***Petición exitosa***
```json
{
    "personas": [
        {
            "idPersona": 70100001,
            "nombre": "Agustin",
            "apellido": "Flexes",
            "dni": "1231231",
            "fechaNac": "1999-05-25T00:00:00",
            "fechaAlta": "2019-04-22T12:15:42.633",
            "fechaModificacion": "2019-04-22T14:25:18.593",
            "provincia": "Córdoba",
            "habilitado": "S",
            "email": "agustivazquez453@gmail.com",
            "cp": "5000"
        },
        {
            "idPersona": 70010002,
            "nombre": "Ramon",
            "apellido": "Alvarez",
            "dni": "12144114",
            "fechaNac": "1999-05-25T00:00:00",
            "fechaAlta": "2019-04-22T14:26:20.97",
            "fechaModificacion": "2019-04-22T14:28:23.867",
            "provincia": "Córdoba",
            "habilitado": "S",
            "email": "Alvarez.Ramon@gmail.com",
            "cp": "5000"
        },
        {
            "idPersona": 7001003,
            "nombre": "Ricardo",
            "apellido": "Juarez",
            "dni": "41777314",
            "fechaNac": "1999-05-25T00:00:00",
            "fechaAlta": "2019-04-22T14:31:36.22",
            "fechaModificacion": "2019-04-22T14:31:36.22",
             "habilitado": "S",
            "email": "RJuarez@gmail.com",
            "cp": "5000"
        },
    ],
    "paginador": {
        "total": 3,
        "limit": 100
    }
}
```

##### HTTP STATUS CODE: 200 (Ok)
Como se ve en la respuesta, el servicio web responde en formato JSON, mediante la estructura
de la clase raiz, con la matriz personas cargada con uno o más objetos de tipo Persona. Destacándose el
valor idPersona como identificador único de la persona. El valor del campo idPersona puede ser utilizado en
varias funciones como por ejemplo:
- La función [set_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/set_personas.md), donde cada persona a actualizar tiene su valor en el campo idPersona.
- La función [get_persona](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_persona.md) (más adelante descripta) que sirve para obtener las matrices perfiles,
preferencias, perfilesGenerales y camposPersonales de la persona, ya que en esta función
([get_personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md)) estas matrices están exeptuadas de carga para que la comunicación sea más ágil.
Es decir, que para obtener estas matrices se debe consultar la función wsGetPersona.
Otro punto importante de esta función es el objeto Paginador que, como detalla la imagen, retorna
el total de personas del segmento consultado (total = 1), el offset y limit. Cabe destacar que el valor máximo
permitido del campo limit es 100, esto significa que se pueden obtener hasta 100 personas por consulta.

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/bad_request.md)
