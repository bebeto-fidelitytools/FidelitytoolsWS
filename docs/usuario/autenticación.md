### Descripción
Este endpoint permite renovar el token de acceso, que luego debe utilizarse en los demás endpoints del servicio.

El flujo de renovación del token es el siguiente:

1. El token inicial ya se encuentra en la ficha de acceso compartida.
2. Cuando necesite renovar el acceso, envía ese mismo token al endpoint de refresh y recibe uno nuevo.
3. Con el token generado puede consumir los demás servicios.

### Vigencia del token
El token de acceso tiene una vigencia de 24 horas.
Si el token ya venció, también puede enviarlo en este endpoint para obtener un nuevo token y continuar operando.

### Sistema de autenticación utilizado
Este servicio trabaja con JWT (JSON Web Token).

JWT es un token firmado digitalmente que permite validar la identidad del cliente en cada solicitud.

Características principales para cliente:

1. No requiere sesión activa en el servidor para cada llamada.
2. El token se envía en cada petición a servicios protegidos.
3. Si el token vence, puede renovarse mediante este endpoint de refresh.

___

### URL
https://ws.fidelitytools.net/v2/api/user/gettokenrefresh

___

### Método
GET

___

### Parámetros

##### Headers

| Parámetro | Requerido | Descripción |
|----------|----------|-------------|
| token | Si | Token actual del cliente. Puede enviarse como `Bearer <token>` o solo el token. |

___

### Ejemplo
```bash
curl -X GET \
    -H "Content-Type: application/json" \
    -H "token: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..." \
    "https://ws.fidelitytools.net/v2/api/user/gettokenrefresh"
```

___

### Respuestas

***Petición exitosa***
```json
{
    "mensajes": [
        {
            "respuesta": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
            "estado": true
        }
    ]
}
```

##### HTTP STATUS CODE: 200 (Ok)

***Peticiones inválidas:*** [bad_request](bad_request.md)

 

