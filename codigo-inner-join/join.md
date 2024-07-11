### Creación de Tablas

```sql
-- Crear tabla de Libros
CREATE TABLE Libros (
    IDLibro SERIAL PRIMARY KEY,
    Titulo VARCHAR(255) NOT NULL,
    Autor VARCHAR(255) NOT NULL
);

-- Insertar datos en la tabla de Libros
INSERT INTO Libros (Titulo, Autor) VALUES
('Cien Años de Soledad', 'Gabriel García Márquez'),
('El Señor de los Anillos', 'J.R.R. Tolkien'),
('1984', 'George Orwell'),
('El Principito', 'Antoine de Saint-Exupéry');

-- Crear tabla de Prestamos
CREATE TABLE Prestamos (
    IDPrestamo SERIAL PRIMARY KEY,
    IDLibro INT NOT NULL,
    IDUsuario INT NOT NULL,
    FechaPrestamo DATE NOT NULL,
    FOREIGN KEY (IDLibro) REFERENCES Libros (IDLibro)
);

-- Insertar datos en la tabla de Prestamos
INSERT INTO Prestamos (IDLibro, IDUsuario, FechaPrestamo) VALUES
(1, 100, '2024-03-01'),
(3, 101, '2024-03-05'),
(2, 102, '2024-03-10');

-- Crear tabla de Usuarios
CREATE TABLE Usuarios (
    IDUsuario SERIAL PRIMARY KEY,
    Nombre VARCHAR(255) NOT NULL
);

-- Insertar datos en la tabla de Usuarios
INSERT INTO Usuarios (Nombre) VALUES
('Ana Pérez'),
('Juan López'),
('María Gómez');
```

### Consulta 1: Libros Prestados

```sql
SELECT Libros.Titulo, Libros.Autor, Prestamos.FechaPrestamo
FROM Libros
INNER JOIN Prestamos ON Libros.IDLibro = Prestamos.IDLibro;
```

### Consulta 2: Libros Prestados por un Usuario Específico (Ana Pérez)

```sql

SELECT Usuarios.Nombre, Libros.Titulo, Libros.Autor, Prestamos.FechaPrestamo
FROM Usuarios
INNER JOIN Prestamos ON Usuarios.IDUsuario = Prestamos.IDUsuario
INNER JOIN Libros ON Prestamos.IDLibro = Libros.IDLibro
WHERE Usuarios.Nombre = 'Ana Pérez';

```

