```sql
-- Creación de la tabla ventas
CREATE TABLE ventas (
    id SERIAL PRIMARY KEY,
    producto VARCHAR(50),
    cantidad INT,
    precio DECIMAL(10, 2),
    fecha_venta DATE
);

-- Inserción de datos en la tabla ventas
INSERT INTO ventas (producto, cantidad, precio, fecha_venta) VALUES
('A', 10, 100, '2023-01-01'),
('B', 5, 50, '2023-01-02'),
('A', 7, 70, '2023-01-03'),
('C', 3, 30, '2023-01-04'),
('B', 8, 80, '2023-01-05');

```
