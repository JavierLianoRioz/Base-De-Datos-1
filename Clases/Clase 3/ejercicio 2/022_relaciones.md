# Relaciones y Verbos

Usuario —< Es un >— Cliente:
 - Un Usuario puede ser un Cliente (1:1).
 - Un Cliente es un Usuario (1:1).

Usuario —< Es un >— Vendedor:
 - Un Usuario puede ser un Vendedor (1:1).
 - Un Vendedor es un Usuario (1:1).

Vendedor —< Pone a la venta >— Producto:
 - Un Vendedor pone a la venta muchos Productos (1:N).
 - Un Producto es puesto a la venta por un Vendedor (N:1).

Producto —< Tiene >— Variante de Producto:
 - Un Producto tiene muchas Variantes (1:N).
 - Una Variante pertenece a un solo Producto (N:1).

Producto —< Pertenece a >— Categoría:
 - Un Producto pertenece a una Categoría (N:1).
 - Una Categoría agrupa muchos Productos (1:N).

Categoría —< Es subcategoría de >— Categoría:
 - Una Categoría puede ser subcategoría de otra Categoría (N:1).
 - Una Categoría puede tener muchas subcategorías (1:N).

Variante de Producto —< Mantiene >— Inventario:
 - Una Variante de Producto mantiene un Inventario (1:1).
 - Un Inventario corresponde a una Variante de Producto (1:1).

Inventario —< Se encuentra en >— Almacén:
 - Un Inventario se encuentra en un Almacén (N:1).
 - Un Almacén contiene muchos Inventarios (1:N).

Vendedor —< Posee >— Almacén:
 - Un Vendedor puede poseer múltiples Almacenes (1:N).
 - Un Almacén pertenece a un Vendedor (N:1).

Cliente —< Crea >— Pedido:
 - Un Cliente crea muchos Pedidos (1:N).
 - Un Pedido es creado por un solo Cliente (N:1).

Pedido —< Contiene >— Línea de Pedido:
 - Un Pedido contiene muchas Líneas de Pedido (1:N).
 - Una Línea de Pedido pertenece a un solo Pedido (N:1).

Línea de Pedido —< Apunta a >— Variante de Producto:
 - Una Línea de Pedido apunta a una Variante de Producto (N:1).
 - Una Variante de Producto puede estar en muchas Líneas de Pedido (1:N).

Pedido —< Se divide en >— Envío:
 - Un Pedido puede dividirse en varios Envíos (1:N).
 - Un Envío agrupa items de un solo Pedido (N:1).

Pedido —< Registra >— Pago:
 - Un Pedido registra muchos Pagos (1:N).
 - Un Pago corresponde a un solo Pedido (N:1).

Pago —< Utiliza >— Método de Pago:
 - Un Pago utiliza un Método de Pago (N:1).
 - Un Método de Pago puede ser utilizado en muchos Pagos (1:N).

Línea de Pedido —< Genera >— Devolución:
 - Una Línea de Pedido puede generar una Devolución (1:1).
 - Una Devolución es generada por una Línea de Pedido (1:1).

Devolución —< Emite >— Nota de Crédito:
 - Una Devolución puede emitir una Nota de Crédito (1:1).
 - Una Nota de Crédito es emitida por una Devolución (1:1).

Promoción —< Se aplica a >— Producto:
 - Una Promoción se aplica a muchos Productos (N:M).
 - Un Producto puede tener muchas Promociones aplicadas (N:M).

Promoción —< Se aplica a >— Categoría:
 - Una Promoción se aplica a muchas Categorías (N:M).
 - Una Categoría puede tener muchas Promociones (N:M).

Promoción —< Se aplica a >— Vendedor:
 - Una Promoción se aplica a muchos Vendedores (N:M).
 - Un Vendedor puede tener muchas Promociones (N:M).

Promoción —< Se aplica a >— Pedido:
 - Una Promoción se aplica a muchos Pedidos (N:M).
 - Un Pedido puede tener muchas Promociones (N:M).

Cliente —< Escribe >— Reseña:
 - Un Cliente escribe muchas Reseñas (1:N).
 - Una Reseña es escrita por un Cliente (N:1).

Reseña —< Valora >— Producto:
 - Una Reseña valora un Producto (N:1).
 - Un Producto puede ser valorado en muchas Reseñas (1:N).

Variante de Producto —< Tiene >— Historial de Precios:
 - Una Variante de Producto tiene un Historial de Precios (1:N).
 - Un Historial de Precios pertenece a una Variante de Producto (N:1).