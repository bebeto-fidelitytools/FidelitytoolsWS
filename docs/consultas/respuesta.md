### Descripcion
Estructura de respuesta ante una consulta. 

#### Estados HTTP
|Estado		     |Descripción      |
|--------------------|----------|
|200    		 | La solicitud se proceso correctamente     | 
|400    		 | Ocurrio un error     | 
|401    		 | Error en la autenticacion     | 

#### Modelo
|Propiedad		     |Tipo      |Descripción                                     |
|--------------------|----------|-----------------------------------------------|
|data    		 | object      | Contiene el resultado de la solicitud. En caso de una insercion contendra el registro que se inserto y en caso de una busqueda contendra la lista resultante			|	      
|estado    		 | bool      | Indica si se pudo resolver correctamente la solicitud. En caso de venir en false se debe revisar la propiedad message	       |
|message    		 | object      | En caso de ser necesario se utiliza para comunicar informacion sobre la solicitud. Ejemplo: errores, mensaje de registro insertado/actualizado			|	      
