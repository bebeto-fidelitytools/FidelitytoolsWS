# Servicios Web de Fidelitytools - V2

Este documento detalla los servicios web que permiten comunicarse con Fidelitytools bajo el protocolo de comunicación REST y el formato de los mensajes JSON.

Fidelitytools es un software web de fidelización de personas y gestión de acciones de las mismas,
permitiendo asociarles diversos tipos de datos que luego servirán para obtener información relevante y
detallada sobre el entorno gestionado.

## Requisitos

Para utilizar los servicios web de Fidelitytools es necesario contar con:

* Contar con las credenciales de autenticación y generación de tokens de acceso provista por los Administradores de Fidelitytools.
* Contar con la llave de acceso a los servicios web provista por los Administradores de Fidelitytools.

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
