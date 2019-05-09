### Descripcion
Permite obtener tanto los estados de entrega como los estados de pago relacionados a los pedidos.
___

### URL
` https://ws.fidelitytools.net/v2/api/ecommerce/pedido/getestados `
___

### Método
GET
___
### Parámetros

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/usuario/autenticaci%C3%B3n.md). |

___
### Ejemplo
```bash
curl -XGET 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff"
https://ws.fidelitytools.net/v2/api/ecommerce/pedido/getestados
```
___
### Respuestas
***Petición exitosa***
```json
{
    "estadosPago": [
        {
            "idEstado": 1,
            "nombre": "El pago fue aprobado y acreditado."
        },
        {
            "idEstado": 4,
            "nombre": "El pago fue rechazado. El usuario puede intentar nuevamente."
        },
        {
            "idEstado": 5,
            "nombre": "El pago fue devuelto al usuario."
        },
        {
            "idEstado": 21,
            "nombre": "Presupuesto"
        }
    ],
    "estadosEntrega": [
        {
            "idEstado": 8,
            "nombre": "En Local comercial"
        },
        {
            "idEstado": 9,
            "nombre": "En Transporte"
        },
        {
            "idEstado": 10,
            "nombre": "En Espera de Retiro por Sucursal Transporte"
        }
    ]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/ecommerce/bad_request.md)
