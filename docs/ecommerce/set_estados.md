### Descripcion
Permite actualizar el estado de pago y de entrega de uno o más pedidos.
___

### URL
` https://ws.fidelitytools.net/v2/api/ecommerce/pedido/setestados/{idEcommerce} `
___

### Método
POST
___
### Parámetros obligatorios

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/autenticaci%C3%B3n.md). |

##### URL
|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| idEcommerce | Si | Id de la ecommerce dentro de la cual se encuentran los pedidos a los que se les modificara el estado de venta y el de entrega | 
##### Body
```json
[
	{"idPedido":1532, "estadoPago":{"idEstado": 1 }, "estadoEntrega": {"idEstado": 8}},
	{"idPedido":1533, "estadoPago":{"idEstado": 3 }, "estadoEntrega": {"idEstado": 10}}
]
```
Como se detalla, el metodo recibe una matriz de pedidos a actualizar, donde por
cada elemento de la matriz hay un objeto pedido.
Son requeridos obligatoriamente los datos idPedido y al menos uno de los 2 tipos de estados
asociados: estadoPago (idEstado) o estadoEntrega (idEstado) por cada pedido a actualizar.
___
### Ejemplo
```bash
curl -XPOST 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
-d "[{\"idPedido\":777, \"EstadoPago\":{\"idEstado\": 1 }, \"estadoEntrega\": {\"idEstado\": 8}}]" 
https://ws.fidelitytools.net/v2/api/ecommerce/pedido/setestados/mZ222Q
```
___
### Respuestas
***Petición exitosa***
```json
{
    "mensajes": [
        {
            "respuesta": "Cod. Pedido: 1532 - Actualizado Exitosamente"
        }
    ]
}
```
La cantidad de pedidos a actualizar, será equivalente la cantidad de mensajes a obtener como respuesta. Cada mensaje puede detallar el éxito o error de la actualización.

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/bad_request.md)
 
