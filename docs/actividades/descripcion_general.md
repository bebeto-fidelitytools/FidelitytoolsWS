## Modulo Actividades

El módulo de actividades de Fidelitytools aloja parte de la estructura relacionada a las personas.
Dentro de este módulo se encuentran las siguientes herramientas que conjuntamente ponen en valor a
cada persona de la base de datos de Fidelitytools:
- Tipos de Actividades.
- Perfiles Generales de Actividad.
- Campos Personales de Actividad.
- Etapas de Actividad.

### 1. Descripcion 

#### 1.1 Tipos de Actividades
En Fidelitytools los tipos de actividades sirven para agrupar actividades que tengan características,
propiedades y atributos similares. Cada tipo de actividad puede asociarse a uno o más:
- Perfiles generales de actividad.
- Campos personales de actividad.
- Etapas de actividad.
Los tipos de actividades se asocian a personas sin distinción del segmento al cuál pertenezca la
persona. Es decir, un tipo de actividad puede estar a asociado a personas de distintos segmentos que, por
pertenecer a distintos segmentos, pueden contener (o no) distintos perfiles generales y campos personales
de segmentación pero comparten la misma estructura de información relacionada a un tipo de actividad.
Tanto los perfiles generales de actividad, como los campos personales de actividad y las etapas de
actividad, cumplen con la función de nutrir de información útil y valorable a cada actividad personas en
Fidelitytools.

#### 1.2 Perfiles Generales de Actividad
Por ejemplo, en un tipo de actividad Turno Médico, un perfil general de actividad sería Especialidad,
ya que existen muchas especialidades. Donde cada actividad de este tipo asociada a una persona, de
cualquier segmento, puede establecer la especialidad en que se llevó a cabo el turno.
A diferencia de los perfiles generales de segmentación, los perfiles generales de actividad pueden ser
de selección de tipo simple o múltiple valor según al tipo de actividad que estén asociados. Es decir que el
mismo perfil general de actividad para un tipo de actividad puede ser de tipo selección simple (permite
asociar un solo valor del perfil general de actividad en la actividad asociada a la persona) y para otro tipo de
actividad puede ser de tipo selección múltiple (permite asociar más de un valor del perfil general de
actividad en la actividad asociada a la persona). Esto permite una mayor dinámica del manejo de la
información ajustándose con mayor eficacia a las necesidades de los distintos tipos de actividades.

#### 1.3 Campos Personales de Actividad
Un ejemplo de campo personal de actividad, en un tipo de actividad Turno Médico, sería Código de
Turno, el cual tendrá un determinado valor en una actividad determinada y otro valor en otra actividad del
mismo tipo, ya que, se supone, que el código que identifica un turno es único. Es decir que el valor de un
campo personal de actividad puede variar de una actividad a otra, pero siempre es un solo valor.
A diferencia de los campos personales de segmentación, los campos personales de actividad pueden
tener diferente formato de valor por cada tipo de actividad al que se asocia. Es decir que un campo personal
de actividad que en un tipo de actividad está asociado en un formato determinado, en otro tipo de actividad
puede estar asociado con otro formato. Los tipos de tipos de formatos de los campos personales de
actividad pueden ser:
- Texto: contiene cualquier tipo de carácter.
- Número: contiene solo números positivos con hasta 2 decimales.
- Fecha: contiene solo valores de tipo fecha con los formatos: dd/MM/aaaa, dd/MM/aaaa HH:MM y
dd/MM/aaaa HH:MM:SS.
- Texto HTML: contiene texto en formato HTML.
- Código: contiene texto de cualquier tipo de carácter. A diferencia del campo de tipo Texto, este
campo se usa para visualizar un valor que no pueda ser modificado desde la interfaz de Fidelitytools.

#### 1.4 Etapas de Actividad
Las etapas de actividad son idénticas a los perfiles generales de actividad. Su funcionamiento es
igual, su diferencia se basa en que tiene un tratamiento distinto a la hora de programar alertas automáticas
en Fidelitytools.
Un ejemplo de etapa de actividad sería Estado de Turno Médico, ya que pueden existir varios
estadios en el transcurso de un turno médico, por ejemplo: Pendiente, En Curso, Finalizado o Cancelado.
Las etapas de actividad pueden ser de tipo selección simple o múltiple valor según al tipo de
actividad que estén asociadas. Es decir que la etapa de actividad para un tipo de actividad puede ser de tipo
selección simple (permite asociar un solo valor de la etapa de actividad en la actividad asociada a la persona)
y para otro tipo de actividad puede ser de tipo selección múltiple (permite asociar más de un valor de la
etapa de actividad en la actividad asociada a la persona). Esto permite una mayor dinámica del manejo de la
información ajustándose con mayor eficacia a las necesidades de los distintos tipos de actividades.

### 2. Diagrama de clases
El siguiente diagrama de clases detalla solo las clases intervinientes en el módulo de actividades.
Existen otras clases, que intervienen en otros módulos y para este caso quedan descartadas de descripción.

![Diagrama de clases Actividades.](https://drive.google.com/uc?export=view&id=1B0fav9MGYAVEu8nHcFqcFnVBjuyigXKS)

#### 2.1 Descripcion del diagrama

##### 2.1.1 Clase Raíz

Esta clase es utilizada para responder a las solicitudes recibidas por las funciones de los servicios web
de Fidelitytools. Por cada solicitud que procese el servicio web, este responderá con la Raiz con alguna de las
clases que contiene.
De las clases que contiene, en este módulo son utilizadas las clases Personas y Mensaje. Para mayor
información de la clase Raíz dirigirse al documento que detalla el módulo [Segmentación](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/descripcion_general.md).

##### 2.1.2 Clase Persona
Contiene todas las propiedades que una persona en Fidelitytools puede poseer. En este módulo solo
se detalla la propiedad actividades, correspondiente a la clase Actividad. Para mayor información de la clase
Persona dirigirse al documento que detalla el módulo [Segmentación](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/descripcion_general.md).

##### 2.1.3 Clase Actividad
Permite registrar o actualizar una o más actividades por persona. Las propiedades que contiene son:
- id: Identificador único de actividad generado por Fidelitytools al dar de alta una actividad. Este
identificador puede ser utilizado para actualizar una actividad previamente registrada.
- idExterno: Identificador único de actividad provisto por el sistema externo que quiere dar de alta una
actividad. Este identificador puede ser utilizado para actualizar una actividad previamente registrada.
- nombre: Nombre de la actividad.
- descripción: Descripción de la actividad.
- fechaAlta: Fecha de alta de la actividad. Esta es autogenerada por el servicio web si no se especifica
el valor de la misma al darla de alta.
- fechaModificación: Fecha de modificación de actividad. Esta es autogenerada por el servicio web
cada vez que se actualiza una actividad.
- estado: Estado de la actividad.
- actividadTipo: Tipo de actividad.
- perfilesGenerales: Perfiles generales de actividad. Referenciados en la clase ActividadPG.
- camposPersonales: Campos personales de actividad. Referenciados en la clase ActividadCP.
- etapas: Etapas de la actividad. Referenciadas en la clase Etapa.

##### 2.1.4 Clase Estado
Clase que es utilizada por otras clases al establecer un estado determinado para sí mismas. La clase Estado
contiene los estados:
1. Habilitado.
2. Deshabilitado.

(*) En el diagrama de clases la clase estado se repite para una mayor claridad de diseño.

##### 2.1.5 Clase ActividadTipo
Contiene los tipos de actividades. Esta clase es utilizada tanto para obtener la estructura de datos de
un determinado tipo de actividad como para dar de alta una nueva actividad.
Al obtener la estructura de datos de un determinado tipo de actividad esta clase contiene las
propiedades:
- id: Identificador único del tipo de actividad generado por Fidelitytools. Este identificador debe ser
utilizado tanto para obtener la configuración de la estructura de datos del tipo de actividad como
para dar de alta o actualizar una determinada actividad.
- nombre: Nombre del tipo de actividad.
- fechaAlta: Fecha de alta del tipo de actividad.
- estado: Estado del tipo de actividad.
- actividadesTipoPG: Contiene todos los perfiles generales de actividad asociados al tipo de actividad.
Referenciados en la clase ActividadTipoPG.
- actividadesTipoCP: Contiene todos los campos personales de actividad asociados al tipo de actividad.
Referenciados en la clase ActividadTipoCP.
- actividadTipoEtapa: Contiene todas las etapas de actividad asociadas al tipo de actividad. Referenciadas
en la clase ActividadTipoEtapa.

##### 2.1.6 Clase ActividadTipoPG
Esta clase contiene todos los perfiles generales de actividad que están asociados a un tipo de
actividad. La misma es utilizada cuando se obtiene toda la configuración de un tipo de actividad
determinado. Las propiedades de esta clase son:
- id: Identificador único generado por Fidelitytools.
- pgActividad: Contiene un perfil general de actividad. Referenciada en la clase PGActividad.
- tipoSeleccion: Contiene el tipo de selección asociado al perfil general de actividad. Referenciado en
la clase TipoSeleccion.

##### 2.1.7 Clase PGActividad
Cada objeto de esta clase contiene un perfil general de actividad junto con sus valores asociados. Las
propiedades de esta clase son:
- id: Identificador único de perfil general de actividad generado por Fidelitytools. Este identificador es
utilizado para dar de alta uno o más valores de un perfil general de actividad cuando es dada de alta
o actualizada una actividad.
- nombre: Nombre del perfil general de actividad.
- estado: Estado del perfil general de actividad.
- pgActividadValores: Contiene todos los valores asociados al perfil general de actividad. Referenciados
en la clase PGActividadValor.

##### 2.1.8 Clase ActividadPG
Esta clase contiene todos los perfiles generales de actividad que están asociados a una actividad
mediante su tipo de actividad. Al dar de alta o al actualizar una actividad solo pueden darse de alta o
actualizar perfiles generales de actividad del tipo de actividad a la cual la actividad pertenece. Las
propiedades de esta clase son:
- Id: Identificador único de perfil general de actividad generado por Fidelitytools. Este identificador
debe ser utilizado al dar de alta o actualizar valores asociados al perfil general de actividad.
- nombre: Nombre del perfil general de actividad.
- estado: Estado del perfil general de actividad.
- pgActividadValores: Contiene todos los valores asociados al perfil general de actividad. Referenciados
en la clase PGActividadValor.

##### 2.1.9 Clase PGActividadValor
Contiene todos los valores asociados a un perfil general de actividad. Las propiedades de esta clase
son:
- Id: Identificador único del valor del perfil general de actividad generado por Fidelitytools. Este
identificador puede ser utilizado para asociar el valor del perfil general de actividad a una actividad.
- nombre: Nombre del valor del perfil general de actividad. Este campo puede ser utilizado para
asociar el valor del perfil general de la actividad a una actividad.
- estado: Estado del perfil general de actividad.

##### 2.1.10 Clase TipoSeleccion
Contiene los tipos de selección válidos utilizados tanto para los perfiles generales de actividad como
para las etapas de actividad. Las propiedades de esta clase son:
- id: Identificador único del tipo de selección.
- nombre: Nombre del tipo de selección.
Los valores del tipo de selección son:
- 1: Selección simple.
- 2: Selección múltiple.

##### 2.1.11 Clase ActividadTipoCP
Esta clase contiene todos los campos personales de actividad que están asociados a un tipo de
actividad. La misma es utilizada cuando se obtiene toda la configuración de un tipo de actividad
determinado. Las propiedades de esta clase son:
- id: Identificador único generado por Fidelitytools.
- cpActividad: Contiene un campo personal de actividad. Referenciado en la clase CPActividad.
- tipoCampo: Contiene el tipo de campo asociado al campo personal de actividad. Referenciado en la
clase TipoCampo.

##### 2.1.12 Clase CPActividad
Cada objeto de esta clase contiene un campo personal de actividad. Las propiedades de esta clase
son:
- id: Identificador único de campo personal de actividad generado por Fidelitytools. Este identificador
es utilizado para asociar el campo personal con una actividad.
- nombre: Nombre del campo personal de actividad.
- estado: Estado del campo personal de actividad.

##### 2.1.13 Clase ActividadCP
Esta clase contiene todos los campos personales de actividad que están asociados a una actividad
mediante su tipo de actividad. Al dar de alta o al actualizar una actividad solo pueden darse de alta o
actualizar campos personales de actividad del tipo de actividad a la cual la actividad pertenece. Las
propiedades de esta clase son:
- id: Identificador único del valor asociado a la actividad del campo personal de actividad generado por
Fidelitytools.
- cpActividad: Se asocia a esta clase para utilizar el campo id como identificador único del campo
personal de actividad. Esta propiedad es utilizada para de alta o actualizar un valor de campo
personal de actividad asociado a una actividad.
- valor: Valor del campo personal de actividad asociado a una actividad.

##### 2.1.14 Clase TipoCampo
Contiene los tipos de campos válidos para los campos personales de actividad. Las propiedades de
esta clase son:
- id: Identificador único del tipo de campo.
- nombre: Nombre del tipo de campo.
Los valores del tipo de selección son:
- 1: Texto.
- 2: Numérico.
- 3: Fecha
- 4: Texto HTML.
- 5: Código Único.

##### 2.1.15 Clase ActividadTipoEtapa
Esta clase es utilizada para asociar un determinado tipo de actividad a etapas de actividad. Las
propiedades de esta clase son:
- id: Identificador único del tipo de actividad de etapa generado por Fidelitytools.
- tipoSeleccion: Establece si el tipo de selección de las etapas de actividad es de tipo simple o múltiple.
- etapas: Contiene una o más etapas asociadas al tipo de actividad. Referenciada en la clase
EtapaActividadTipo.

##### 2.1.16 Clase EtapaActividadTipo
Esta clase asocia el tipo de actividad con una etapa permitiéndole asignar un orden de
aparición/importancia a la etapa en ese tipo de actividad. Las propiedades de esta clase son:
- id: Identificador único de la etapa actividad tipo generado por Fidelitytools.
- Etapa: Contiene una etapa de actividad. Referenciada en la clase Etapa.
- orden: Establece el orden de aparición/importancia de la etapa de actividad con respecto a las otras
etapas de actividad asociadas al tipo de actividad.

##### 2.1.17 Clase Etapa
Esta clase contiene todas las etapas de actividad que están asociadas a una actividad mediante su
tipo de actividad. Al dar de alta o al actualizar una actividad solo pueden darse de alta o actualizar etapas de
actividad del tipo de actividad a la cual la actividad pertenece. Las propiedades de esta clase son:
- id: Identificador único de etapa de actividad generado por Fidelitytools. Este identificador debe ser
utilizado para dar de alta o actualizar una etapa asociada a una actividad.
- nombre: nombre de la etapa de actividad.
- estado: Estado de la etapa de actividad.
- fecha: Fecha de la etapa de actividad

### [Funciones del modulo Actividad](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/tree/master/docs/actividades) 
