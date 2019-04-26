### Descripcion
La posibilidad de eliminar un catálogo de productos de Fidelitytools está restringida solamente al
catálogo de pruebas que los administradores de Fidelitytools proporcionan para que se realicen las acciones
descriptas en los puntos anteriores.

Esta función permite vaciar completamente un catalogo para cargar uno nuevamente,
y así poder realizar diversas pruebas sobre el mismo, ya que, una vez completada las etapas de pruebas,
cuando se trabaje sobre el catálogo real de productos, esta función está prohibida por razones de seguridad
para nuestros clientes.
___

### URL
` https://ws.fidelitytools.net/v2/api/catalogos/catalogo/delete/{idCatalogo} `
___

### Método
DELETE
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
curl -XDELETE 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff"
https://ws.fidelitytools.net/v2/api/catalogos/catalogo/delete/8Io9Zz
```
___
### Respuestas
***Petición exitosa***
```json
{
    "mensajes": [
        {
            "respuesta": "Catálogo eliminado exitosamente",
            "estado": true
        }
    ]
}
```
Si desea comprobar que realmente el catalogo fue eliminado por completo debe utilizar el metodo [get_catalogo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/get_catalogo.md) de Fidelitytools.

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
 
 
 
