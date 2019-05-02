## Modulo Ecommerce
El módulo de ecommerce de Fidelitytools aloja la estructura relacionada a los pedidos generados a
través de ventas realizadas vía Ecommerce y/o mediante la herramienta Gestor Comercial. El módulo
pedidos está relacionado tanto con el módulo segmentación como con el módulo catálogo, ya que cada
pedido generado tiene asociado un cliente (persona alojada en el módulo segmentación) y uno o más
productos (alojados en el módulo catálogo)

### 1. Descripcion 

#### 1.1 Clase Pedido
Esta clase contiene todas las propiedades necesarias para soportar datos de pedidos. La clase raíz
contiene una matriz de pedidos que, por cada elemento de la matriz existe un objeto Pedido.
Cada objeto pedido existente en la matriz contiene la propiedad Persona utilizada para asociar el
pedido con un cliente determinado.
Cada objeto pedido contiene la matriz productosxPedido utilizada para asociar el pedido con uno o
más productos de un catálogo determinado.

***Propiedades de pedido***

| Propiedad | Tipo | Descripcion | Requerido | Formato |
|-----------|------|-------------|-----------|---------|
| idPedido | Int | Codigo identificador unico de pedido | No | Numero entero | 
| tipoPedido | Object | Tipo de pedido | No | Object | 
| persona | Object | Datos del cliente | No | Object |
| fecha | Date | Fecha del pedido | No | dd/mm/yyyy | 
| estadoEntrega | Object | Estado de entrega del pedido | No | Object |
| estadoPago | Object | Estado de pago del pedido | No | Object |
| total | Decimal | Precio total de pedido | No | Numero Decimal(10,2) | 
| observaciones | String | Observaciones de pedido | No | - |
| destino | String | Provincia, Localidad y Barrio de destino | No | - |
| formaPago | String | Forma de pago de pedido | No | - | 
| validezOferta | String | Plazo de validez de la oferta de pedido | No | - | 
| plazoEntrega | String | Plazo de entrega de pedido | No | - |
| descuento | Decimal | Monto de descuento de pedido | No | - | 
| codigoDescuento | String | Codigo identificador de descuento | No | - | 
| entrega | String | Direccion de entrega de pedido | No | - | 
| transporteNombre | String | Nombre de el transportista del pedido | No | - | 
| productosxPedido | Array | Matriz de productos asociados al pedido | No | Matriz | 
| logPedido | Array | Matriz de strings asociadas a las acciones del pedido | No | Matriz |

#### 1.2 Clase Producto por Pedido
Un pedido tiene uno o más productos asociados, mediante la matriz productosxPedido se realiza
dicha asociación, que por cada elemento de la matriz productosxPedido existe un objeto de tipo
ProductoxPedido el cual tiene las siguientes propiedades:

***Propiedades de producto por pedido***

| Propiedad | Tipo | Descripcion | Formato |
|-----------|------|-------------|---------|
| cantidad | Decimal | Cantidades de unidades de producto | Numero Decimal(10,2) |
| producto | Object | Producto | Object |
| precio | Decimal | Precio por unidad de producto | Numero Decimal(10, 2) |
| subtotal | Decimal | Subtotal de unidades por precio de producto | Numero Decimal(10,2) |


### 2. Diagrama de clases

El siguiente diagrama de clases detalla solo las clases intervinientes en el módulo ecommerce. Existen
otras clases, como persona o pedidos, que intervienen en otros módulos y en este caso quedan descartadas
de descripción.

![Diagrama de clases Ecommerce.](https://drive.google.com/uc?export=view&id=1oLhNumIn0Iqj1-LfhnC07vYoAiM-7SMh)

### [Funciones del modulo Ecommerce](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/tree/master/docs/ecommerce) 
