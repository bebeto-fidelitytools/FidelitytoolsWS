### Descripción

Permite obtener todos los pedidos registrados entre fechas determinadas.

---
### URL

`https://ws.fidelitytools.net/v2/api/ecommerce/pedido/getPedidos/{idEcommerce}/{fechaInicio}/{fechaFin}/{estadoPago}/{estadoEntrega}/{tipoPedido}`

---
### Método

GET

---
### Parámetros

##### Headers

|Parámetro    	       |Requerido |Descripción                                   		       |
|----------------------|----------|--------------------------------------------------------------------|
| key      	       	   | Si	  	  | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authentication       | Si	  	  | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/usuario/autenticaci%C3%B3n.md). |

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
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
https://ws.fidelitytools.net/v2/api/ecommerce/pedido/getPedidos/fGu8yU/01-12-2018/01-01-2019/1/8/10
```
___
### Respuestas
***Petición exitosa***
```json
{
	"pedidos":
	[
		{
			"estadosEntrega": {"idEstado":12, "nombre":"Sin Definir"},
			"estadoPago":{"idEstado":21, "nombre":"Sin Definir"},
			"fecha": "2018-02-01T09:23.007", "formaPago":"Contado, ConIva, PesoAR", "idPedido":21412,
			"persona":
			{
				"apellido":"Flexes","nombre":"agustin", "dni":"45615845", "email":"flexesagustin@gmail.com", 
				"fechaAlta":"2018-02-01T09:23.007", "habilitado":"S", "idPersona":2234432,
				"sexo": "M", "tipoPers":"persona"
			},
			"plazoEntrega":"10 dias",
			"productosxPedido":
			[
				{"cantidad":21.00, "precio":50.99, "producto":{"codigoInterno":"1", "idProducto":3255554, 
				"titulo":"CH FOR MEN"}, "subtotal":21000.00},
				{"cantidad":5.00, "precio":100.00, "producto":{"codigoInterno":"1", "idProducto":3255884, 
				"titulo":"INVICTUS"}, "subtotal":500.00},
				{"cantidad":1.00, "precio":1000.00, "producto":{"codigoInterno":"1", "idProducto":3255774, 
				"titulo":"CAROLINA HERRERA FOR WOMAN"}, "subtotal":1000.00}
			],
			"tipoPedido":{"idTipoPedido":17, "nombre":"Sucursal 2"},
			"total":22500.00,
			"validezOferta":"2018-02-02"
		}
	],
	"paginador": {"total":1}
}
```
Por cada elemento de la matriz pedidos hay un objeto pedido que, junto con sus propiedades, contiene el objeto persona (datos del cliente asociado al pedido) y la matriz productosxPedido que contiene uno o más productos asociados al pedido.
##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/bad_request.md)
