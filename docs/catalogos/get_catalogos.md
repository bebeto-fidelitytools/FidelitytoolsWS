### Descripcion
Permite obtener todos los catálogos asociados a una llave de acceso. Por cada catálogo se obtienen las siguientes propiedades:

* idCatalogo: Identificador único de catálogo.
* nombre: Nombre del catálogo.
* cantidadProductos: La cantidad de productos asociados.

___

### URL
` https://ws.fidelitytools.net/v2/api/catalogos/catalogo/getcatalogos `
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
https://ws.fidelitytools.net/v2/api/catalogos/catalogo/getcatalogos
```
___
### Respuestas
***Petición exitosa***
```json
{
  "catalogos": [
    {
      "idCatalogo": "NzkzNQ", "nombre": "Catálogo 1", "cantidadProductos": 12345      
    },
    {
      "idCatalogo": "ODA3MA", "nombre": "Catálogo 2", "cantidadProductos": 5432
    },
    {
      "idCatalogo": "ODA3MQ", "nombre": "Catálogo 3", "cantidadProductos": 312      
    }
  ],
  "paginador": { "total": 3 }
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/bad_request.md)
