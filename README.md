# ExamenDataBase

erDiagram
    vehiculos {
        int VIN PK
        int marca_id FK
        int modelo_id FK
        date year
        int numero_serie
        decimal precio
        varchar color
        varchar tipo_combustile
        varchar tipo_transmision
        varchar estado
        varchar disponibilidad
    }
    marcas {
        int id PK
        varchar marca
    }
    modelo {
        int id PK 
        int id_marca FK
        varchar marca 
    }
    clientes {
        int id PK
        varchar nombre
        varchar telefono
        varchar correo
        varchar direccion
        
    }
    vendedores {
        int id PK
        varchar nombre
        varchar telefono
        varchar correo
        varchar direccion
    }
    ventas {
        int id
        int vehiculo_id FK
        int vendedor_id FK
        int metodo_pago_id FK
    }
    
    mantenimiento {
        int id PK
        int tipo_servicio_id FK   
        decimal Costo              
        date fecha_servicio  
        int id_cliente FK    
        int VIN FK   
    }
    tipo_servicios{
        int id PK
        varchar tipo_servicio
    }
    detalle_mantenimiento {

    }
    kardex{
        int id
        date fecha
        int cantidad
        id tipo_mov_id
    }
    mov_kardex{
        int id
        int kardex_id
        int vehiculo_id
    }
    tipo_movimiento{
        int id
        varchar tipo_movimiento
    }
    factura{
        int id
        int cliente_id
        date fecha
        decimal total
    }
    pago_factura{
        int id
        int factura_id
        decimal monto
        date fecha_pago
    }
    tipo_pago{

    }
    transaccion{

    }
    detalle_factura{
        
    }


    Cliente ||--o| Pedido : Realiza
    Pedido ||--|{ Producto : Contiene
