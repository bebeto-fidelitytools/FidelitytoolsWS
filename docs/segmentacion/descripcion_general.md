## Modulo Segmentación 

El módulo de segmentación de Fidelitytools aloja parte de la estructura relacionada a las personas.
Dentro de este módulo se encuentran las siguientes herramientas que conjuntamente ponen en valor a
cada persona de la base de datos de Fidelitytools:
- Segmentos.
- Personas.
- Perfiles Generales.
- Campos Personales.

### 1. Descripción

En Fidelitytools la segmentación sirve para agrupar personas que tengan características, propiedades
y atributos similares, y permite diferenciar estos grupos entre sí.
Por ejemplo un segmento puede ser Clientes, otro segmento puede ser Proveedores, otro Recursos
Humanos, etc. Donde cada segmento puede tener una cantidad ilimitada de personas.

#### 1.1 Perfiles Generales

Uno o más perfiles generales están asociados a uno o más segmentos y la función que cumplen es
nutrir de información útil y valorable a cada persona del segmento asociado.
Por ejemplo el perfil general Rubro, que contiene muchos rubros, puede asociarse al segmento
Proveedores, y cada proveedor del segmento Proveedores puede tener (o no) uno o varios rubros a los que
se dedica el proveedor.
Lo mismo puede suceder con el segmento Clientes y el perfil general Rubros, ya que cada cliente del
segmento Clientes puede tener asociado (o no) uno o varios perfiles generales del tipo Rubro detallando el
tipo de rubro al que el cliente es asociado.
Los perfiles generales pueden ser de tipo simple o múltiple valor, la diferencia entre estos tipos de
perfiles generales es que, por ejemplo, el perfil general Rubro (establecido por el usuario de Fidelitytools
como un tipo de perfil general Múltiple) permite asociar varios de sus valores a una (o más personas) de un
segmento (o varios segmentos). En cambio si el perfil general Rubro fuese un perfil general de tipo Simple, y
aunque tenga muchos valores disponibles, permitiría asociar solo uno de sus valores a una persona (o más)
de un segmento (o varios segmentos).

#### 1.2 Campos Personales
Los campos personales, están asociados a uno o más segmentos y la función que cumplen es similar
a la de los perfiles generales, con la diferencia de que estos son variables con respecto a su valor. Por
ejemplo el campo personal CUIT puede ser utilizado para todos las personas del segmento Proveedores con
la diferencia de que el valor del campo personal va a ser distinto para cada persona del segmento
Proveedores, ya que el CUIT es un valor único e irrepetible para cada persona del segmento. En cambio los
perfiles generales pueden ser iguales para varias personas del segmento, porque, por ejemplo, pueden
existir varios Proveedores que tengan asociado varios de los valores del perfil general Rubros pero cada uno
con su valor único del campo personal CUIT.

#### 1.3 Personas
Una persona en la base de datos de Fidelitytools se compone por:
- Segmentación.
- Campos generales.
- Campos personales.
- Perfiles generales.

**Es decir que cada persona:**
- Pertenece a un segmento determinado.
- Posee campos generales (Código de Persona, Nombre, Apellido, DNI, Email, Dirección, Teléfono,
etc.).
- Posee, o no, campos personales relacionados al segmento al cuál la persona pertenece.
- Posee, o no, perfiles generales relacionados al segmento al cuál la persona pertenece.
- Posee, o no, perfiles y/o preferencias pertenecientes al segmento al cuál la persona pertenece.

### 2. Diagrama de clases
El siguiente diagrama de clases detalla solo las clases intervinientes en el módulo de segmentación,
existen otras clases, como [productos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/descripcion_general.md), [pedidos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/descripcion_general.md) o [actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/descripcion_general.md), que intervienen en otros módulos y en este
caso quedan descartadas de descripción.

![Diagrama de clases segmentacion.](https://drive.google.com/uc?export=view&id=10u_YWX-Q4sR0IdNXIAS2ZH4G-UthVaMl)

#### 2.1 Descripcion 

##### 2.1.1 Clase Raíz

Esta clase contiene todas las otras clases y es la utilizada para responder a las solicitudes recibidas
por las funciones de los servicios web de Fidelitytools. Por cada solicitud que procese el servicio web
responderá con la clase Raíz con alguna de estas clases que contiene cargada de datos correspondientes.
Como lo detalla el diagrama de clases, la clase Raiz tiene asociada:

* Matrices o arrays de:
	- Personas.
	- Segmentos.
	- Perfiles Generales.
	- Campos Personales.
	- Mensajes.
* Clase Paginador.

##### 2.1.2 Clase Paginador

Sirve para paginar los registros a obtener de algunas peticiones recibidas y así agrupar entre rangos
el resultado de registros. Es decir que si se quiere obtener personas de un segmento determinado, la clase
raiz responderá con una matriz de personas y con un objeto paginador configurado con las propiedades:
- total (cantidad total de personas del segmento determinado).
- offSet (la posición actual desde donde arranca el rango de registros a obtener).
- limit (determina la cantidad de registros a obtener establecido por el valor del offset).

Por ejemplo si el segmento Proveedores contiene 20 registros y la petición recibida por el servicio
web de Fidelitytools dice que se requieren los 10 primeros registros del segmento, la configuración de la
petición es:
- offset = 0 (arranca desde 0 porque son los 10 primeros).
- limit = 10 (10 registros desde el valor offset).
- total = 20 (valor configurado internamente por el servicio que determina la cantidad total de
registros que contiene dicho segmento).

Para obtener los 10 registros restantes, la configuración de la petición es:
- offset = 10 (arranca desde 10 porque los 10 anteriores ya se obtuvieron).
- limit = 10 (10 registros desde el valor del offset).
- total = 20 (valor configurado internamente por el servicio web que determina la cantidad total de
registros que contiene dicho segmento).

##### 2.1.3 Clase Mensaje

Esta clase sirve para comunicar al usuario que consume el servicio web de Fidelitytools el resultado
de una petición solicitada. La clase raiz tiene asociada una matriz de esta clase, debido a que puede haber
más de un mensaje por petición realizada, porque según la petición realizada puede existir (o no) uno o más
mensajes.
En caso de error en la petición, esta clase incluye el mensaje correspondiente al error producido y
estableciendo el valor false en la propiedad estado. En caso de éxito la propiedad estado se encuentra con el
valor true.

##### 2.1.4 Clase Perfil General
La clase PerfilGeneral tiene como propiedad la matriz perfilGeneralValores, donde se alojan todos los
valores del perfil general, por ejemplo el perfil general Rubro tiene una matriz de perfilGeneralValores con
los valores Gastronomía, Limpieza, Electricidad, Indumentaria y así la cantidad de valores que sea necesario
por perfilGeneral.

##### 2.1.5 Clase Perfil General Valor
La clase Perfil General Valor contiene uno o más valores asociados a un perfil general. Detallada en el
punto anterior

### [Funciones del modulo Segmentacion](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/tree/master/docs/segmentacion) 
