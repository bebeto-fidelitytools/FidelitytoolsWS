### Descripción:

Permite agregar y/o actualizar una o más personas.

---
##### Cuando es agregada una persona
Si la persona tiene los campos idPersona, idExterno, dni o email vacíos, el servicio web por defecto
intentará registrar la persona sin realizar comprobación de su existencia previa ya que dichos campos se
encuentran sin valor alguno de búsqueda.

---
##### Cuando es actualizada una persona
Si la persona tiene los campos idPersona, idExterno, dni y/o email con valores, el servicio web intentará actualizar la persona realizando la comprobación de su existencia previa mediante alguno
de los valores de los campos mencionados. Estos campos son llamados __*campos de comprobación de existencia*__ y se dividen en dos tipos: __*Por Defecto*__ y __*Requeridos*__.

A su vez, los __*campos de comprobación requeridos*__ pueden ser complementados por los __*campos de comprobacion complementarios*__ que permiten una comprobacion de existencia más rigurosa sobre una persona a registrar o a actualizar.

---
##### Campo de comprobación de existencia por defecto

El campo idPersona es el campo de búsqueda por defecto. Es decir que el servicio web por defecto,
si este campo tiene valor, lo utiliza para la búsqueda de una persona previamente a decidir si
debe ser registrada o actualizada. 

El orden y prioridad de búsqueda es idPersona y luego los campos de
comprobación por configuración. Por lo que primero el servicio web intentara obtener la persona mediante
el valor del campo idPersona y, si el resultado obtenido es nulo, intentará obtenerla mediante los __*campos de
comprobación de existencia requeridos*__.

---
##### Campos de comprobación de existencia requeridos

Los campos de comprobación requeridos son:
1. idExterno
2. dni + email
3. dni
4. email

En ese orden se realiza la búsqueda de la persona siempre y cuando los campos contengan valores.
Es decir que el servicio web, luego de no obtener la persona mediante el campo idPersona (porque este se
encontraba vacío o porque no encontró dicha persona con el valor proporcionado), primero intentará
obtener la persona mediante el campo idExterno (si este contiene un valor), luego intentará obtenerlo
mediante la combinación de valores de los campos dni + email (si ambos contienen valores), luego por dni (si contiene un valor) y por último mediante el campo email (si contiene un valor).

---
##### Campos de comprobación de existencia complementarios

Los campos de comprobación de existencia complementarios se acoplan a los campos de comprobación de existencia 
requeridos de orden 2, 3 y 4, permitiendo agregar condiciones de búsqueda más rigurosas para la
comprobación de la existencia de una persona.

Estos campos complementarios son propiedades de la clase Persona que por sí solas no pueden
determinar la unicidad de la misma, pero al complementarse con los campos de comprobación de existencia
requeridos generan una cualidad de verificación más rigurosa.

Los campos de comprobación de existencia complementarios son: nombre, apellido, cp, fechaNac, localidad,
provincia, país, barrio, empresa, nomFantasia y usuario.

A diferencia de los campos de comprobación de existencia requeridos, los complementarios no tienen un orden
de prioridad y mientras más campos complementarios existan más rigurosa será la verificación de existencia
de una persona.

Por ejemplo, en base a la siguiente configuración preestablecida:

* Campos de comprobación requeridos: dni + email
* Campos de comprobación complementarios: cp - fechaNac.

El servicio web intentará identificar una persona mediante la combinación de los valores: dni + email - cp - fechaNac. 

Esto siempre y cuando la persona cuente con valores en dichos campos requeridos y complementarios, ya que, si
la persona cuenta con al menos una de estas propiedades sin valor la comprobación será nula y la persona
será tenida en cuenta como nueva. 

Por ejemplo si la persona solo cuenta con valores en los campos dni - cp
y no cuenta con valores en los campos email - fechaNac, la persona será dada de alta.

Tanto los campos de comprobación requeridos como los complementarios deben estar previamente
configurados por parte de los administradores del sistema Fidelitytools ya que por defecto solo se encuentra
activo el campo de comprobación por defecto idPersona.

---
#### Propiedades de la clase persona

|Propiedad		     |Tipo      |Descripción                                    |Requerido |Formato      						 |
|--------------------|----------|-----------------------------------------------|----------|-------------------------------------|
|idPersona    		 | int      | Código identificador único					| No       | Nro. Entero 						 |
|idExterno    		 | string   | Código identificador único externo			| No       | -			 						 |
|segmento     		 | Object   | Segmento al cúal la persona pertenece			| Si       | Clase segmento						 |
|nombre       		 | string   | Nombre de la persona							| No       | -			 						 |
|apellido     		 | string   | Apellido de la persona						| No       | -			 						 |
|dni	      		 | int      | Código identificador único					| No       | Nro. Entero 						 |
|apellido     		 | string   | Apellido de la persona						| No       | -			 						 |
|habilitado   		 | string   | Determina si se encuentra habilitada			| No       | -			 						 |
|email	      		 | string   | Email de la persona							| No       | email		 						 |
|email2	      		 | string   | Email alternativo de la persona				| No       | email		 						 |
|fechaNac     		 | Datetime | Fecha de nacimiento							| No       | YYYY-MM-DDThh:mm:ss		 		 |
|fechaAlta    		 | Datetime | Fecha de alta de la persona					| No       | YYYY-MM-DDThh:mm:ss		 		 |
|fechaModificacion 	 | Datetime | Fecha de modificación de la persona			| No       | YYYY-MM-DDThh:mm:ss		 		 |
|codigoPais   		 | string   | Código teléfonico del país					| No       | -			 						 |
|telefono     		 | int      | Telefono										| No       | Nro. Entero 						 |
|telefono2    		 | int      | Telefono alternativo							| No       | Nro. Entero 						 |
|telefono3    		 | string   | Teléfono alternativo con caracteres			| No       | -           						 |
|movil        		 | int      | Teléfono móvil								| No       | Nro. Entero 						 |
|pref1		  		 | int      | Prefijo del campo telefono					| No       | Nro. Entero 						 |
|pref2		  		 | int      | Prefijo del campo telefono2					| No       | Nro. Entero 						 |
|pref3		  		 | int      | Prefijo del campo movil						| No       | Nro. Entero 						 |
|direccion    		 | string   | Dirección de la persona						| No       | -			 						 |
|numero	      		 | string   | Número de calle de dirección de la persona	| No       | -			 						 |
|barrio       		 | string   | Barrio de la persona							| No       | -			 						 |
|pais	      		 | string   | País de la persona							| No       | -			 						 |
|provincia    		 | string   | Provincia de la persona						| No       | -			 						 |
|localidad    		 | string   | Localidad de la persona						| No       | -			 						 |
|nomFantasia  		 | string   | Nombre de fantasía de la persona				| No       | -			 						 |
|dpto	      		 | string   | Departamento de la persona					| No       | -			 						 |
|piso	      		 | string   | Piso de la persona							| No       | -			 						 |
|cp		      		 | string   | Código postal de la persona					| No       | -			 						 |
|observaciones		 | string   | Observaciones sobre la persona				| No       | -			 						 |
|sexo	      		 | string   | Identidad de género de la persona				| No       | M (masc) - F (fem) - I	(indefinido) |
|empresa      		 | string   | Empresa de la persona							| No       | -			 						 |
|tipoPers     		 | string   | tipo de persona								| No       | persona - empresa					 |
|usuario      		 | string   | Cuenta de usuario de la persona				| No       | -			 						 |
|clave        		 | string   | Clave de cuenta de usuario de la persona		| No       | -			 						 |
|personaDep   		 | string   | Persona dependiente							| No       | -			 						 |
|perfilesGenerales   | Array    | Perfiles generales de la persona				| No       | -			 						 |
|camposPersonales	 | Array    | Campos personales de la persona				| No       | -			 						 |


El campo ***tipoPers*** determina el tipo de persona a registrar, el tipo de persona puede ser persona o
empresa. Si la persona a registrar tiene este campo vacío, por defecto, será cargada como una persona de
tipo Persona.

El campo ***personaDep*** sirve para determinar la dependencia de la persona a registrar sobre otra
persona previamente registrada. La propiedad personaDep esta deshabilitada para asociar mediante el
servicio web de Fidelitytools, es decir que las asociaciones entre personas se realizan desde el Sistema
Fidelitytools. Esta propiedad es utilizada en la función de Obtener Personas (detallada posteriormente)
cuando la persona está asociada a otra persona.

Los campos de tipo fecha por defecto utilizan el formato UTC: YYYY-MM-DDThh:mm:ss

---
### URL

`https://ws.fidelitytools.net/v2/api/segmentacion/persona/set`

---
### Método

POST

---
### Parámetros

##### Headers

|Parámetro    	       |Requerido |Descripción                                   		       |
|----------------------|----------|--------------------------------------------------------------------|
| key      	       | Si	  | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authentication       | Si	  | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/usuario/autenticaci%C3%B3n.md). |

##### Body

```json
[
	{
		"segmento": { "idSegmento": "ABC123" },
		"nombre": "Nombre de persona",
		"apellido": "Apellido de persona",
		"dni": 12345678,
		"email": "email_1@email.com.ar",
		"tipoPers": "persona",
		"pref3": 351,
		"movil": 6987654,
		"observaciones": "Observaciones sobre la persona",
        "fechaNac": "1987-12-15T14:15:44",
		"perfilesGenerales": 
		[
			{ "idPerfilGeneral": 123, "perfilGeneralValores": [ {"nombre": "pgv1"}, {"nombre": "pgv2"} ] }
		],
		"camposPersonales":
		[
			{ "idCampoPersonal": 456, "valor": "21-33536253-3" }
		]
	}    
]
```

---
### Ejemplo

```bash
curl -X POST 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6InVzZXJBY2Nlc3NDb25maWciLCJuYmYiOjE1NTYxMjI1NzYsImV4cCI6MTU1NjIwODk3NiwiaWF0IjoxNTU2MTIyNTc2LCJpc3MiOiJodHRwczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHR0cHM6Ly93cy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9.lIY6hvvs8kjzAblEQzxkRcj-tVQOJ5Jmkh_ynmeLAe4" 
-H "key: 5c2e343fdad07d2b94e184d4" 
-d "[{ \"segmento\": { \"idSegmento\": \"NjA2NA\" }, \"dni\": \"33437253\", \"email\":\"bebeto@fidelitytools.com\", \"habilitado\":\"S\", \"nombre\":\"Bebeto\", \"provincia\": \"Cordoba\", \"tipoPers\":\"persona\" }]" 
https://ws.fidelitytools.net/v2/api/segmentacion/persona/set
```

---
### Respuestas
***Respuesta exitosa***
```json
{
  "mensajes": [
    {
      "estado": true,
      "respuesta": "Persona: idPersona: 7288047 - Segmento: idSegmento: NjA2NA - Nombre: Bebeto - D.N.I: 33437253 - Agregada exitosamente",
      "clase": "persona",
      "id": "7288047"
      "idExterno": "AA-BB-00-11"
    }
  ]
}

```

##### HTTP STATUS CODE: 200 (Ok)


***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/bad_request.md)
