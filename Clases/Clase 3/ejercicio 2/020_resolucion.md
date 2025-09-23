# Resolución

## Desarrollo escrito
1. [Identificación de Entidades](/021_entidades.md)
2. [Relaciones y Verbos](/022_relaciones.md)
3. [Atributos](/023_atributos.md)
4. [Identificadores](/024_identificadores.md)
5. [Jerarquías de Generalización](/025_jerarquias.md)

## Diagrama

```mermaid
erDiagram
    USUARIO {
        int id_usuario PK
        string email
        string contrasena
        date fecha_registro
    }
    CLIENTE {
        int id_usuario FK
    }
    VENDEDOR {
        int id_usuario FK
        string reputacion
    }
    PRODUCTO {
        int id_producto PK
        string nombre
        string descripcion
        int id_vendedor FK
        int id_categoria FK
    }
    VARIANTE_PRODUCTO {
        int id_variante PK
        string talla
        string color
        decimal precio_actual
        int id_producto FK
    }
    CATEGORIA {
        int id_categoria PK
        string nombre
        string descripcion
        int id_categoria_padre FK
    }
    INVENTARIO {
        int id_inventario PK
        int cantidad_stock
        int id_variante FK
        int id_almacen FK
    }
    ALMACEN {
        int id_almacen PK
        string nombre
        string ubicacion
        int id_vendedor FK
    }
    PEDIDO {
        int id_pedido PK
        date fecha_creacion
        string estado
        string direccion_envio
        int id_cliente FK
    }
    LINEA_PEDIDO {
        int id_linea PK
        int cantidad
        decimal precio_unitario
        int id_pedido FK
        int id_variante FK
    }
    ENVIO {
        int id_envio PK
        date fecha_envio
        string estado_envio
        string empresa_transporte
        int id_pedido FK
    }
    PAGO {
        int id_pago PK
        decimal monto
        date fecha_pago
        string estado_pago
        int id_pedido FK
        int id_metodo_pago FK
    }
    METODO_PAGO {
        int id_metodo_pago PK
        string nombre
    }
    DEVOLUCION {
        int id_devolucion PK
        string motivo
        string estado_devolucion
        date fecha_devolucion
        int id_linea_pedido FK
    }
    NOTA_CREDITO {
        int id_nota PK
        decimal monto
        date fecha_emision
        int id_devolucion FK
    }
    PROMOCION {
        int id_promocion PK
        string codigo
        string descripcion
        date fecha_validez_inicio
        date fecha_validez_fin
    }
    RESENA {
        int id_resena PK
        int calificacion
        string comentario
        date fecha_resena
        int id_cliente FK
        int id_producto FK
    }
    HISTORIAL_PRECIOS {
        int id_historial PK
        decimal precio_anterior
        date fecha_cambio
        int id_variante FK
    }

    USUARIO ||--|{ CLIENTE : "es un"
    USUARIO ||--|{ VENDEDOR : "es un"
    VENDEDOR ||--|{ PRODUCTO : "vende"
    VENDEDOR ||--o{ ALMACEN : "posee"
    CLIENTE ||--o{ PEDIDO : "crea"
    CLIENTE ||--o{ RESENA : "escribe"
    PRODUCTO ||--o{ VARIANTE_PRODUCTO : "tiene"
    PRODUCTO }o--|| CATEGORIA : "pertenece a"
    PRODUCTO ||--o{ RESENA : "recibe"
    CATEGORIA }o--o{ CATEGORIA : "es subcategoria de"
    VARIANTE_PRODUCTO ||--o{ HISTORIAL_PRECIOS : "tiene"
    VARIANTE_PRODUCTO ||--o{ INVENTARIO : "mantiene"
    VARIANTE_PRODUCTO }o--o{ LINEA_PEDIDO : "incluida en"
    ALMACEN ||--o{ INVENTARIO : "contiene"
    PEDIDO ||--o{ LINEA_PEDIDO : "contiene"
    PEDIDO ||--o{ ENVIO : "se divide en"
    PEDIDO ||--o{ PAGO : "registra"
    PEDIDO }o--o{ PROMOCION : "aplica"
    LINEA_PEDIDO ||--|| DEVOLUCION : "genera"
    DEVOLUCION ||--|| NOTA_CREDITO : "emite"
    PAGO }o--|| METODO_PAGO : "usa"
    PROMOCION }o--o{ PRODUCTO : "aplica a"
    PROMOCION }o--o{ CATEGORIA : "aplica a"
    PROMOCION }o--o{ VENDEDOR : "aplica a"
```
[source](/026_diagrama.mermaid)