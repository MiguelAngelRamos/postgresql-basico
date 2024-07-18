```sql
-- Having

-- Cuantas personas(users) hay por pais(country)

select count(*) as users, country from users group by country order by country asc;

-- Queremos saber donde hay mas personas en nuestra red social, campaña de marketing 

-- Having 
-- Queremos que exporte aquellos que tengan arriba de 5 personas (paises importante para nuestra campaña de marketing)
/*
 * Orden recomendado
 * 1. Group by - Agrupador
 * 2. Having - Condicion
 * 3. Order By -- Expresion asc, desc
 * */
select 
	count(*) as total,
	country
from
	users
group by
	country
having
	count(*) > 5
order by
	count(*) desc;

-- Paises que no tenemos tantos usuarios(personas)

select 
	count(*) as total,
	country
from 
	users
group by
	country
having
	count(*) between 1 and 5
order by
	count(*) desc;

-- Obtener los paises de forma unica sin duplicados.
select distinct country from users;

-- Saber cuantos dominios tienen mas de un correo electronico en nuestra red social

select count(*), substring(email, position('@' in email) + 1) as domain
from users
group by substring(email, position('@' in email) + 1)
having count(*) > 1
order by substring(email, position('@' in email) + 1) asc;
```
