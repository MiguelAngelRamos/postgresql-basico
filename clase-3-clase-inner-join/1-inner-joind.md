```sql
create table instructores(
  id serial primary key,
  nombre varchar(100) not null,
  email varchar(100) unique not null
);

create table cursos(
  id serial primary key,
  titulo varchar(100) not null,
  descripcion text,
  instructor_id int,
  constraint fk_instructor
    foreign key (instructor_id)
    references instructores(id)
);

insert into instructores (nombre, email) values 
('juan perez', 'juan.perez@example.com'),
('maria lopez', 'maria.lopez@example.com');

select * from instructores;

insert into cursos(titulo, descripcion, instructor_id) values
('curso de python', 'arpende python desde cero', 1),
('curso de postgresql', 'base de datos con postgresql', 2),
('curso de javascript', 'desarrollo web con javascript', 1);

select * from cursos;

select cursos.titulo, cursos.descripcion, instructores.nombre
from cursos
join instructores on cursos.instructor_id = instructores.id;

```