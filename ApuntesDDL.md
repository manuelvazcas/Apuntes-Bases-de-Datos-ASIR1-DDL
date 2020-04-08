## APUNTES DDL ##

### INDICE ###
1. [Definición DDL](#id1)
2. [Create](#id2)
	- [Create Database](#id2.1)
	- [Create Domain](#id2.2) 
	- [Create table](#id2.3)
3. [Alter](#id4)
4. [Drop](#id5)
5. [Constraint primary key](#id7)
6. [Constraint foreign key](#id8)
7. [Constraint unique](#id9)
8. [Constraint check](#id10)

### DEFINICIÓN DDL<a name="id1"></a> ###

DDL, lenguaje de definición de datos, es un sublenguaje de SQL que permite llevar a cabo las tareas de definición de las estructuras que almacenarán los datos así como de los procedimientos o funciones que permitan consultarlos. Dentro de DDL existen varias sentencias que iremos viendo a continuación.

#### CREATE<a name="id2"></a> ####

La sentencia Create sirve para crear una nueva base de datos ```CREATE DATABASE``` o ```CREATE SCHEMA```, tabla ```CRREATE TABLE```, dominio ```CREATE DOMAIN```, usarios ```CREATE USER```. Create crea un objeto dentro de un sistema de gestión de bases de datos relacionales, podiendo llegar a crear todos los objetos anteriormente puestos. Ahora especificaremos un poco más cada una de estas sentencias.

#####```CREATE DATABASE ```<a name="id2.1"></a>
Sirve para dar una orden para crear una nueva base de datos, tambien podriamos utilizar la palabra ***SCHEMA*** en vez de ***DATABASE*** para crear una base de datos. La sintaxis que usamos para crear una base de datos es:

	CREATE DATABASE/SCHEMA
	(Si no existe) nombreDATABASE
	(CHARACTER SET nombreCHARSET);

#####`CREATE DOMAIN`<a name ="id2.2"></a>
Sirve para no tener que repetir siempre el mismo dato en una base de datos, así cuando aparezcan diferentes atributos con el mismo tipo de datos usaremos un `CREATE DOMAIN`. La sintaxis que usaremos será:

    CREATE DOMAIN [nombreDATABASE] (nombreDOMINIO) <tipoDato>;
	
#####`CREATE TABLE`<a name ="id2.3"></a>
Sirve para crear una tabla dentro de una base de datos, el contenido que queramos meter dentro de ella tendrá que ir entre paréntesis. Dentro de los paréntesis pueden ir los atributos, los cuales tenemos que especificar los tipos de datos que queremos que vayan con cada atributo, también tendremos que indicar si hay Primary Keys, Foreign o si es NOT NULL , aunque en el segundo y tercer caso no siempre tiene que existir. La sintaxis que se usará será:

	CREATE TABLE [nombreDATABASE] <nombreTABLE> (
		<nombreATRIB1> <tipoDato> {ClavePrimaria}
		<nombreATRIB2> <nombreDOMINIO>...
	);

#### ALTER<a name="id3"></a> ####
Sirve para poder modificar todo tipo de cosas en una base de datos, pero nos centraremos en las tablas `ALTER TABLE`, con el que podemos añadir 
`ADD` o eliminar `DROP` columnas y restricciones. Usando `CASCADE` hacemos que se elimine todo de lo que tenga dependencia una columna o una restricción, usando `RESTRICT` no se eliminará una columna si otras tienen dependencia de ella. La sintaxis que utilizaremos será: 
	
	ALTER TABLE <nombreTABLE>
	ADD <nombreColumna> ...
	DROP <nombreColumna> (CASCADE/RESTRICT);
Otra cosa que podemos utilizar con `ALTER` sería modificar una columna, usaríamos `ALTER COLUMN`

#### DROP<a name="id4"></a> ####
Como ya vimos en la explicación anterior DROP se utiliza para eliminar elementos de una base de datos. La sintaxis que utilizaremos será:

	DROP SCHEMA [NombreDATABASE]
	(CASCADE/RESTRICT);
Podemos usar `CASCADE` si queremos borrar la base de datos aunque tenga datos en ella o podemos usar `RESTRICT` si queremos que no la borre si tiene datos en ella.

Para borrar una tabla seria igual.
	
	DROP TABLE [nombreTABLE]
	(CASCADE/RESTRICT);
	 