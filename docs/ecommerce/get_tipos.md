### Descripcion
Permite obtener todos los tipos de pedidos.
___

### URL
` https://ws.fidelitytools.net/v2/api/pedido/gettipospedido `
___

### Método
GET
___
### Parámetros obligatorios

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/autenticaci%C3%B3n.md). |

___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
https://ws.fidelitytools.net/v2/ecommerce/pedido/gettipos
```
___
### Respuestas
***Petición exitosa***
```json
{
    "tiposPedido": [
        {
            "idTipoPedido": 1,
            "nombre": "General"
        },
        {
            "idTipoPedido": 17,
            "nombre": "Sucursal"
        },
        {
            "idTipoPedido": 22,
            "nombre": "Administracion"
        },
        {
            "idTipoPedido": 25,
            "nombre": "Ventas"
        }
    ],
    "paginador": {
        "total": 4
    }
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Petición inválida***
```json
{
    "mensajes": [
        {
            "respuesta": "Error: Acceso denegado",
            "estado": false
        }
    ]
}
```

##### HTTP STATUS CODE: 400 (BadRequest)
 
