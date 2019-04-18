### Descripción:

Permite agregar y/o actualizar una o más personas.

##### Cuando es agregada una persona
---
Si la persona tiene los campos idPersona, idExterno, dni o email vacíos, el servicio web por defecto
intentará registrar la persona sin realizar comprobación de su existencia previa ya que dichos campos se
encuentran sin valor alguno de búsqueda.

##### Cuando es actualizada una persona
---
Si la persona tiene los campos idPersona, idExterno, dni y/o email con valores, el servicio web por
defecto intentará actualizar la persona realizando la comprobación de su existencia previa mediante alguno
de los valores de los campos mencionados. Estos campos son llamados __*campos de comprobación de existencia*__ y se dividen en dos tipos: __*Por Defecto*__ y __*Requeridos*__.

A su vez, los __*campos de comprobación requeridos*__ pueden ser complementados por los __*campos de comprobacion complementarios*__ que permiten una comprobacion de existencia más rigurosa sobre una persona a registrar o a actualizar.

##### Campo de comprobación de existencia por defecto
---
El campo idPersona es el campo de búsqueda por defecto. Es decir que el servicio web por defecto,
si este campo se tiene valor, utiliza dicho campo para la búsqueda de una persona previamente a decidir si
debe ser registrada o actualizada. El orden y prioridad de búsqueda es idPersona y luego los campos de
comprobación por configuración. Por lo que primero el servicio web intentara obtener la persona mediante
el valor del campo idPersona y, si el resultado obtenido es nulo, intentará obtenerla mediante los campos de
comprobación por configuración.

##### Campos de comprobación de existencia requeridos
---

Los campos de comprobación requeridos son:
1. idExterno
2. dni + email
3. dni
4. email

En ese orden se realiza la búsqueda de la persona siempre y cuando los campos contengan valores.
Es decir que el servicio web, luego de no obtener la persona mediante el campo idPersona (porque este se
encontraba vacío o porque no encontró dicha persona con el valor proporcionado), primero intentará
obtener la persona mediante el campo idExterno (si este contiene un valor), luego intentará obtenerlo
mediante el campo dni + email (si ambos contienen valores), luego por dni y por último mediante el campo
email (si contiene un valor).

##### Campos de comprobación de existencia complementarios
---

Los campos de comprobación complementarios se acoplan a los campos de comprobación
requeridos de orden 2,3 y 4, permitiendo agregar condiciones de búsqueda más específicas para la
comprobación de la existencia de una persona.

Estos campos complementarios son propiedades de la clase Persona que por sí solas no pueden
determinar la unicidad de la misma, pero al complementarse con los campos de comprobación
requeridos generan una cualidad de verificación más rigurosa a diferencia de utilizar los campos de
comprobación requeridos solamente.

Los campos de comprobación complementarios son: nombre, apellido, cp, fechaNac, localidad,
provincia, país, barrio, empresa, nomFantasia y usuario.

A diferencia de los campos de comprobación requeridos, los complementarios no tienen un orden
de prioridad y mientras más campos complementarios existan más rigurosa será la condición de búsqueda
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

#### Propiedades de la clase persona
---

|Propiedad    |Tipo      |Descripción                                   |Requerido |Formato      |
|-------------|----------|----------------------------------------------|----------|-------------|
|idPersona    | int      | Código identificador único					| No       | Nro. Entero |
|idExterno    | string   | Código identificador único externo			| No       | -			 |
|nombre       | string   | Nombre de la persona							| No       | -			 |
|apellido     | string   | Apellido de la persona						| No       | -			 |
|dni	      | int      | Código identificador único					| No       | Nro. Entero |
|apellido     | string   | Apellido de la persona						| No       | -			 |
|habilitado   | string   | Determina si se encuentra habilitada			| No       | -			 |
|email	      | string   | Email de la persona							| No       | -			 |
|email2	      | string   | Email alternativo de la persona				| No       | -			 |
|fechaNac     | Datetime | Fecha de nacimiento							| No       | DD/MM/YYYY HH:MM:SS			 |
|fechaAlta    | Datetime | Fecha de alta de la persona					| No       | DD/MM/YYYY HH:MM:SS			 |
|fechaModificacion | Datetime | Fecha de modificación de la persona		| No       | DD/MM/YYYY HH:MM:SS			 |
|codigoPais   | string   | Código teléfonico del país					| No       | -			 |
|telefono     | int      | Telefono										| No       | Nro. Entero |
|telefono2    | int      | Telefono alternativo							| No       | Nro. Entero |
|telefono3    | string   | Teléfono alternativo con caracteres			| No       | -           |
|movil        | int      | Teléfono móvil								| No       | Nro. Entero |
|pref1		  | int      | Prefijo del campo telefono					| No       | Nro. Entero |
|pref2		  | int      | Prefijo del campo telefono2					| No       | Nro. Entero |
|pref3		  | int      | Prefijo del campo movil						| No       | Nro. Entero |
|direccion    | string   | Dirección de la persona						| No       | -			 |
|numero	      | string   | Número de calle de dirección de la persona	| No       | -			 |
|barrio       | string   | Barrio de la persona							| No       | -			 |
|pais	      | string   | País de la persona							| No       | -			 |
|provincia    | string   | Provincia de la persona						| No       | -			 |
|localidad    | string   | Localidad de la persona						| No       | -			 |
|nomFantasia  | string   | Nombre de fantasía de la persona				| No       | -			 |
|dpto	      | string   | Apellido de la persona						| No       | -			 |
|piso	      | string   | Apellido de la persona						| No       | -			 |
|cp		      | string   | Apellido de la persona						| No       | -			 |
|apellido     | string   | Apellido de la persona						| No       | -			 |
|apellido     | string   | Apellido de la persona						| No       | -			 |
|apellido     | string   | Apellido de la persona						| No       | -			 |
|apellido     | string   | Apellido de la persona						| No       | -			 |
|apellido     | string   | Apellido de la persona						| No       | -			 |
|apellido     | string   | Apellido de la persona						| No       | -			 |
|apellido     | string   | Apellido de la persona						| No       | -			 |
