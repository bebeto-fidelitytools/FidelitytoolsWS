### Descripcion
Permite agregar uno o más productos a una categoria perteneciente a un catálogo determinado. Esta categoria se identifica mediante su codigo interno y si no se encuentra una categoria registrada previamente con ese codigo interno se registrara la categoria.
___

### URL
` https://ws.fidelitytools.net/v2/api/catalogos/catalogo/set/{idCatalogo} `
___

### Método
POST
___
### Parámetros

##### Headers

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| key         | Si		 | Llave de acceso otorgada por los administradores de Fidelitytools. |
| Authorization       | Si		 | token generado mediante el endpoint [Generar token de acceso](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/usuario/autenticaci%C3%B3n.md). |

##### URL

|Parámetro |Requerido |Descripción                 |
|----------|----------|----------------------------|
| idCatalogo | Si | Id del catalogo al cual se le van a agregar los productos. |

##### Body
```json
[
    {
        "idProducto": 156760,
        "titulo": "212 VIP MEN",
        "categoria": {
            "nombre": "Fragancias Masculinas",
            "codigoInterno": "554-001",
            "categoriaDep": {
                "nombre": "P/ Hombres",
                "codigoInterno": "554-002",
                "categoriaDep": {
                    "nombre": "Fragancias",
                    "codigoInterno": "554-003"
                }
            }
        },
        "descripcion": "Fragancias para hombre. VIP.",
        "etiquetas": "E4, E5, E6",
        "codigoInterno": "COD_INT_P4",
        "productosDep": [
        {
            "idProducto": 156762,
            "titulo": "212 VIP MEN. 100ml ",
            "descripcion": "212 VIP MEN. En envase de 100 ml.",
            "etiquetas": "E4, E5, E6",
            "codigoInterno": "COD_INT_P5"
        },
        {
            "idProducto": 156763,
            "titulo": "212 VIP MEN 500ml.",
            "descripcion": "212 VIP MEN. En envase de 500 ml.",
            "etiquetas": "E4, E5, E6",
            "codigoInterno": "COD_INT_P6"
        }
        ]
    }
]
```
___
### Ejemplo
```bash
curl -XPOST 
-H "Content-Type: application/json" 
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkbmlxdWVfbmFtZSI6InVzZXJb25maWciLCJuYmYiOjE1NTYxMTk0MNjIwNTgwNywiaWF0IjoxNTU2MTE5NDA3LCJpczovL3dzLmZpZGVsaXR5dG9vbHMubmV0L3YyIiwiYXVkIjoiaHa2U2asdasdy5maWRlbGl0eXRvb2xzLm5ldC92MiJ9RDDpMHEB4SsmY0j87OcS5mbxe2XxSAY" 
-H "key: 5c2e343fdaddsb94e18fff" 
-d "[{\"titulo\": \"CH FOR MEN\",\"categoria\": {\"nombre\": \"Fragancias Masculinas\",\"codigoInterno\": \"554-001\"},\"codigoInterno\": \"8471\"}]" 
https://ws.fidelitytools.net/v2/api/catalogos/catalogo/set/4sY89o
```
___
### Respuestas
***Petición exitosa***
```json
{
    "mensajes": [
        {
            "respuesta": "Producto: Cod. Interno: 8471 - Titulo: CH FOR MEN - Carga Exitosa.",
            "estado": true
        }
    ]
}
```
Como se detalla, el metodo responde mediante la estructura
de la clase raiz, con la matriz mensajes cargada con uno o más objetos de tipo Mensaje. En este caso, por 10
cada producto a registrar, será equivalente la cantidad de mensajes a obtener como respuesta. Cada
mensaje puede detallar el éxito o error del registro.

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas***: [bad_request](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/blob/master/docs/catalogos/bad_request.md)
