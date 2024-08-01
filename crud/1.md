### Crear la Tabla `usuarios`

Primero, crea la tabla `usuarios`:

```sql
CREATE TABLE usuarios (
    id SERIAL PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    correo VARCHAR(100) UNIQUE NOT NULL,
    fecha_registro TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Crear (Insertar Datos)

Para insertar datos en la tabla `usuarios`:

```sql
INSERT INTO usuarios (nombre, correo)
VALUES ('Juan Perez', 'juan.perez@example.com');

INSERT INTO usuarios (nombre, correo)
VALUES ('Maria Gomez', 'maria.gomez@example.com');
```

### Leer (Consultar Datos)

Para leer todos los datos de la tabla `usuarios`:

```sql
SELECT * FROM usuarios;
```

Para leer datos específicos con una condición:

```sql
SELECT * FROM usuarios
WHERE nombre = 'Juan Perez';
```

### Actualizar (Modificar Datos)

Para actualizar el correo de un usuario específico:

```sql
UPDATE usuarios
SET correo = 'juan.p.new@example.com'
WHERE id = 1;
```

### Borrar (Eliminar Datos)

Para eliminar un usuario específico:

```sql
DELETE FROM usuarios
WHERE id = 2;
```

### Consultas Completas del CRUD

#### Insertar

```sql
INSERT INTO usuarios (nombre, correo)
VALUES ('Carlos Ruiz', 'carlos.ruiz@example.com');
```

#### Leer

```sql
SELECT * FROM usuarios;
```

#### Actualizar

```sql
UPDATE usuarios
SET correo = 'carlos.ruiz.new@example.com'
WHERE nombre = 'Carlos Ruiz';
```

#### Eliminar

```sql
DELETE FROM usuarios
WHERE nombre = 'Carlos Ruiz';
```