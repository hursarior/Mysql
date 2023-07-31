## Mysql
?Como esta organizada una base de datos?

* en toda base de datos hay una entidad
* esta entidad es un repositorio que almacena datos
* puede ser una ssd o un espacio de memoria para guardar datos
* y esta tambien esta constituida por otras entidades una de ella es (La tabla)
  

### la tabla
* esta esta constituida por varios elementos
* campos = columnas o tipo de dato, registros = filas o datos
  
![Tabla](C:\Users\user\Desktop\MarkDown\Tabla.png)
1. es necesario que al momento de crear la tabla es necesario definir campos y el tipo de dato que estara depositado en cada campo.


* cada tabla tiene un indice, que digamos que solo es un numero que nos ayuda a buscar de forma secuencial algun elemento en la tabla.

### Clave primaria 
* una clave primaria es un campo en el cual ninguno de sus registros se pueden repetir.
* No es obligatorio el uso de claves primarias.


### Esquemas
* las tablas las organizamos en esquemas, que serian la siguiente entidad que conforma una base de datos.
* los esquemas solo es una forma de agrupar tablas.


# Comandos
* el * es para referirse a todo, es como decir all.
* para empezar a utilizar una tabla, usamos el comando Use + NombreDelaTabla.
* select * from = evidentemente es para hacer una consulta de todo lo contenido en una tabla.

### Palabras y comandos comunes en MySQL:

Base de datos (Database): Es un conjunto organizado de datos que se almacenan y gestionan en el servidor de MySQL.

Tabla (Table): Es una estructura que contiene datos organizados en filas y columnas.

Columna (Column): Es un campo individual en una tabla que define el tipo de datos que se puede almacenar en ella.

Fila (Row): Es un conjunto de datos que corresponde a una entidad en la tabla.

Clave primaria (Primary Key): Es una columna única en una tabla que identifica de manera única cada fila y garantiza la integridad de los datos.

Consulta (Query): Es una instrucción SQL que se utiliza para interactuar con la base de datos, ya sea para recuperar, insertar, actualizar o eliminar datos.

* SELECT: Se utiliza para recuperar datos de una tabla o vistas.

* INSERT: Permite agregar nuevos registros a una tabla.

* UPDATE: Actualiza los valores de uno o más registros existentes en una tabla.

* DELETE: Elimina registros de una tabla.

* CREATE: Se utiliza para crear nuevas tablas, bases de datos o vistas.

* ALTER: Modifica la estructura de una tabla existente.

* DROP: Elimina una tabla, base de datos o vista.

* JOIN: Combina filas de dos o más tablas en función de una relación entre ellas.

* GROUP BY: Agrupa filas que comparten el mismo valor en una o más columnas.

* HAVING: Filtra los resultados de una consulta con condiciones basadas en los resultados de agregación.

Ejemplo de creación de una tabla y agrupación de datos:

Supongamos que deseamos crear una tabla para almacenar información de clientes y luego agruparlos por su país y contar cuántos clientes hay en cada país.

```sql

-- Creación de la tabla "clientes"
CREATE TABLE clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50),
    pais VARCHAR(30),
    edad INT
);


-- Inserción de datos en la tabla
INSERT INTO clientes (nombre, pais, edad) VALUES
    ('Juan', 'España', 30),
    ('María', 'España', 25),
    ('Carlos', 'México', 28),
    ('Luisa', 'México', 22),
    ('Ana', 'Argentina', 35);

-- Agrupación de clientes por país y conteo de clientes en cada país
SELECT pais, COUNT(*) AS total_clientes
FROM clientes
GROUP BY pais;

```


### Explicación:

Primero, creamos una tabla llamada "clientes" con cuatro columnas: id (clave primaria), nombre, país y edad.
Luego, insertamos cinco registros de clientes en la tabla.
Finalmente, realizamos una consulta para agrupar los clientes por país y contar cuántos clientes hay en cada país. Utilizamos la función de agregación COUNT(*) para contar el número de filas en cada grupo.
El resultado de la consulta será:





| pais      | total_clientes |
|-----------|----------------|
| España    | 2              |
| México    | 2              |
| Argentina | 1              |



En este ejemplo, hemos utilizado la cláusula GROUP BY para agrupar los clientes por país y la función de agregación COUNT(*) para contar el número de clientes en cada grupo de país. Así, podemos obtener una visión resumida de cuántos clientes hay en cada país.

## Uso
insert into (orden en el que se insertara, con las variable) values (los valores, en el mismo orden de las variable entre parentesis).

