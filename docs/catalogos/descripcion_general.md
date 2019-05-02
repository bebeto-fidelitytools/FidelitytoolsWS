## Modulo Catálogo
El módulo catálogo de Fidelitytools aloja la estructura relacionada a productos y categorías de
productos. Tanto los productos como las categorías de los mismos forman un catálogo de productos; Y
mediante este módulo se puedan realizar diferentes acciones posteriores, como por ejemplo visualizar el
catálogo de productos en sitios web y realizar ventas por Ecommerce.

### 1. Descripcion 

#### 1.1 Producto

Esta clase contiene todas las propiedades necesarias para soportar datos de productos. La clase raíz
contiene una matriz de productos que, por cada elemento de la matriz existe un objeto Producto.
Cada objeto producto existente en la matriz contiene la propiedad Categoria utilizada para asociar el
producto con una categoría.
Cada objeto producto puede tener (o no) una matriz de productosDep, que son productos
previamente registrados dependientes del producto asociado.

***Propiedades de producto***

| Propiedad | Descripción | Tipo de Dato | Requerido | 
|-----------|-------------|--------------|-----------|
| titulo | Nombre de producto | Cadena de caracteres | No | 
| descripcion | Descripcion de producto | Cadena de caracteres | No |
| detalle | Detalle de producto | Cadena de caracteres | No |
| codigoInterno | Codigo identificador unico de producto | Cadena de caracteres | Si |
| precio | Precio primario de producto | Numero Decimal(10,2) | No |
| precio2 | Precio secundario de producto | Numero Decimal(10,2) | No |
| precio3 | Precio terciario de producto | Numero Decimal(10,2) | No |
| stock | Stock primario de producto | Numero Entero(10) | No |
| stock2 | Stock secundario de producto | Numero Entero(10) | No |
| etiquetas | Tags identificadores de producto | Cadena de caracteres | No | 
| categoria | Categoria de producto | Objeto tipo Categoria | Si | 
| productosDep | Productos dependientes del producto principal | Matriz de tipo Producto | No | 




#### 1.2 Categoría

***Propiedades de categoria***

| Propiedad | Descripción | Tipo de Dato | Requerido | 
|-----------|-------------|--------------|-----------|
| nombre | Nombre de la categoria del producto | Cadena de caracteres | No | 
| codigoInterno | Codigo identificador unico de  la categoria | Cadena de caracteres | Si | 
| categoriaDep | Categoria padre de la categoria del producto | Cadena de caracteres | No |

### 2. Diagrama de clases

El siguiente diagrama de clases detalla solo las clases intervinientes en el módulo catálogo. Existen
otras clases, como persona o pedidos, que intervienen en otros módulos y en este caso quedan descartadas
de descripción.

![Diagrama de clases Catalogos.](https://drive.google.com/uc?export=view&id=1ha3bXL4OnAipkctJ8IAHzMGG5ODb85w0)

| Reglas de uso para que la carga sea valida | 
|--------------------------------------------|
| Cada producto a agregar debe tener un codigoInterno único e irrepetible (sucede lo mismo para los productosDep). | 
| Cada producto principal a agregar debe tener al menos una categoría y a su vez dicha categoría puede tener hasta 2 categorías asociadas. Es decir que un producto principal tiene una categoría y puede depender de hasta 2 categorías más. |
| Cada categoría debe tener un codigoInterno único e irrepetible. |
| Cada producto principal puede tener infinitos productosDep. La matriz productosDep es una matriz de subproductos, que poseen las mismas propiedades que el producto principal con la salvedad de que cada subproducto dentro de la matriz productosDep no posee categoria, ni productosDep. |
| Un subproducto dentro de la matriz productosDep depende únicamente del producto principal que aloja dicha matriz, es decir el mismo subproducto no puede ser producto principal ni subproducto de otro producto principal. |
| La propiedad etiquetas permite que el producto posea Tags identificadores. Estos Tags deben estar separados por una coma entre sí. |

### [Funciones del modulo Catalogo](https://github.com/bebeto-fidelitytools/FidelitytoolsWS/tree/master/docs/catalogos) 
