### Descripcion
Permite obtener todos los catálogos asociados a una llave de acceso.
___

### URL
` https://ws.fidelitytools.net/v2/api/catalogos/catalogo/getcatalogo/{idCatalogo/{offset}/{limit} `
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
https://ws.fidelitytools.net/v2/api/catalogos/catalogo/getcatalogo/Zz8Xx9A/10/10
```
___
### Respuestas
***Petición exitosa***
```json
{
    "productos": [
          {
            "idProducto": 156687,
            "titulo": "CAROLINA HERRERA FOR MEN",
            "categoria": {
                "nombre": "Fragancias Masculinas",
                "codigoInterno": ""
              },
            "precio": 30000,
            "stock": 20,
            "codigoInterno": "3"
          },
          {
            "idProducto": 156688,
            "titulo": "212 NYC MEN",
            "categoria": {
                "nombre": "Fragancias Masculinas",
                "codigoInterno": ""
              },
            "precio": 30000,
            "stock": 20,
            "codigoInterno": "4"
          }
    ],
    "paginador": {
        "total": 2,
        "offset": 10,
        "limit": 10
    }
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/bad_request.md)
