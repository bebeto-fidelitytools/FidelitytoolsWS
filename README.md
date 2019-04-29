# Servicios Web de Fidelitytools - V2

Este documento detalla los servicios web que permiten comunicarse con Fidelitytools bajo el protocolo de comunicación REST y el formato de los mensajes JSON.

Fidelitytools es un software web de fidelización de personas y gestión de acciones de las mismas,
permitiendo asociarles diversos tipos de datos que luego servirán para obtener información relevante y
detallada sobre el entorno gestionado.

## Requisitos

Para utilizar los servicios web de Fidelitytools es necesario contar con:

* Credenciales de autenticación y generación de tokens de acceso provista por los Administradores de Fidelitytools.
* Llave de acceso a los servicios web provista por los Administradores de Fidelitytools.

## Reglas de uso

La cantidad de solicitudes permitidas por cliente es de 40 cada 5 segundos, es decir 8 solicitudes cada 1
segundo. Si este límite es superado, el cliente será bloqueado temporalmente y recibirá una respuesta
de tipo HTTP 401 (Unauthorized) cada vez que quiera realizar una petición al servicio web. El bloqueo
temporal dura 1 minuto desde el momento que fue bloqueado.

## Servicios Web Disponibles

Los servicios web de Fidelitytools están divididos por módulos, donde por cada módulo se pueden
realizar varias acciones.

#### Autenticación
+ [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/autenticaci%C3%B3n.md)

#### Módulo Segmentación

##### Personas
* [Registrar / Actualizar Personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/set_personas.md)
* [Obtener Persona](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_persona.md)
* [Obtener Personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_personas.md)
* [Obtener Cantidad de Personas](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_cant_personas.md)
##### Perfiles Generales
* [Obtener Perfiles Generales](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_perfil_general.md)
##### Campos Personales
* [Obtener Campos Personales](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/segmentacion/get_campo_personal.md)

#### Módulo Ecommerce

##### Pedidos
* [Obtener Pedidos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/get_pedidos.md)
* [Obtener Estados](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/get_estados.md)
* [Obtener Tipos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/get_tipos.md)
* [Actualizar Estados de Pedidos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/set_estados.md)

#### Módulo Catalogos

##### Catalogos
* [Registrar/ Actualizar Catalogos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/set.md)
* [Eliminar Catalogo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/delete.md)
* [Obtener Catalogos](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/get_catalogos.md)
* [Obtener Catalogo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/get_catalogo.md)
* [Actualizar Catalogo(Precio y Stock)](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/set_precio_stock_x_productos.md)

#### Módulo Actividades

##### Actividades
* [Registrar/ Actualizar Actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/set.md)
* [Eliminar Actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/tree/master/docs/actividades/delete.md)
* [Obtener Configuracion de un Tipo de Actividad](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/get_configuracion_tipo.md)
* [Obtener Tipos de Actividades](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/actividades/get_tipos.md)
