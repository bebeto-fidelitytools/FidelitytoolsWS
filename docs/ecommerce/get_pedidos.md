### Descripción

Permite obtener todos los pedidos registrados entre fechas determinadas.

---
### URL

`https://ws.fidelitytools.net/v2/api/ecommerce/pedido/getPedidos/{idEcommerce}/{fechaInicio}/{fechaFin}/{estadoPago}/{estadoEntrega}/{tipoPedido}`

---
### Método

GET

---
### Parámetros obligatorios

##### Headers

|Parámetro    	       |Requerido |Descripción                                   		       |
|----------------------|----------|--------------------------------------------------------------------|
| key      	       	   | Si	  	  | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authentication       | Si	  	  | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/autenticaci%C3%B3n.md). |

##### URL

|Parámetro    	       |Requerido |Descripción                                   		       		|
|----------------------|----------|-----------------------------------------------------------------|
| idEcommerce		   | SI		  | Clave identificadora del módulo de ecommerce			   		|
| fechaInicio		   | SI		  | Fecha de inicio de alta de pedido. **Formato DD-MM-YYYY**  		|
| fechaFin			   | SI		  | Fecha de fin de alta de pedido. **Formato DD-MM-YYYY** 	   		|
| estadoPago		   | NO		  | Identificador asociado al estado de pago de uno o más pedidos   |
| estadoEntrega		   | NO		  | Identificador asociado al estado de entrega de uno o más pedidos|
| tipoPedido		   | NO		  | Indentificador asociado al tipo de pedido de uno o más pedidos  |

---
### Ejemplo

```bash

```

---
### Respuesta

```json


```
