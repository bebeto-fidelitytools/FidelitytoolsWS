### Descripcion
Estrutura de un body para consultar a la api.
___

### Modelos

#### Paginador
|Propiedad		     |Tipo      |Descripción                                    |Requerido |Formato      						 |
|--------------------|----------|-----------------------------------------------|----------|-------------------------------------|
|filtros    		 | Filtro[]      | Aca se deberan colocar los filtros que se deseen aplicar a la consulta. 					| No       | Array de la clase Filtro|
|select    		 | string[]      | Representa lo que se va a seleccionar, no es necesario consultar el modelo entero, esto permite limitar la informacion que se consulta y disminuir el tiempo de respuesta.					| No       | Array de strings |
|offset    		 | int      | La posición desde donde arranca el rango de registros a obtener.					| No       | Nro. Entero |
|limit    		 | int      | Limite de registros a obtener. El limite permitido por el sistema es de 100.					| No       | Nro. Entero |

#### Filtro
|Propiedad		     |Tipo      |Descripción                                    |Requerido |Formato      						 |
|--------------------|----------|-----------------------------------------------|----------|-------------------------------------|
|propertyName    		 | object      | Dentro de esta propiedad debe ir el nombre de la propiedad a la que se le desea aplicar el filtro.  					| Si       | Texto |
|value    		 | object      | Representa el valor que se va a comparar en la propiedad	que se indique en propertyName				| Si       | Texto |
|comparator   		 | string      | Representa la comparacion que se quiere realizar entre la propiedad propertyName y value					| Si       | Nombre de un Comparador |

#### Comparadores
|Nombre		     |Descripción      |
|--------------------|----------|
|Equal    		 | Igual     | 
|GreaterThanOrEqual    		 | Mayor o igual que      | 
|GreaterThan    		 | Mayor que      | 
|LessThanOrEqual    		 | Menor o igual que      | 
|LessThan    		 | Menor que      | 

[Referencia](https://docs.microsoft.com/en-us/dotnet/api/system.linq.expressions.expressiontype?view=netframework-4.8)
___

### Ejemplos
Caso: Consultar el nombre, apellido e email de las personas que correspondan a un segmento.

```json
{
    "filtros": [
        {
            "propertyName":"segmento.idSegmento",
            "value":"Mzc4Mg",
            "comparator":"Equal"
        }
    ],
    "select": ["apellido","nombre","email"]
}
```


Caso: Buscar a una persona por su dni e email

```json
{
    "filtros": [
        {
            "propertyName":"email",
            "value":"desarrollo@fidelitytools.com",
            "comparator":"Equal"
        },
        {
            "propertyName":"dni",
            "value":"12345678",
            "comparator":"Equal"
        }
    ],
    "limit": 1
}
```

Caso: Buscar personas con fecha de alta posterior o igual al 8/7/2020 a las 10:15 hs

```json
{
    "filtros": [
        {
            "propertyName": "fechaAlta",
            "value": "2020-07-08 10:15:00",
            "comparator": "GreaterThanOrEqual"
        }
    ],
    "select": [
        "apellido",
        "nombre",
        "email",
        "fechaAlta"
    ]
}
```
