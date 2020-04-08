## APUNTES DDL ##

### INDICE ###
1. [Definición DDL](#id1)
2. [Create](#id2)
	- [Create Database](#id2.1)
	- [Create Domain](#id2.2) 
	- [Create table](#id2.3)
3. [Alter](#id3)
4. [Drop](#id4)
5. [Constraints](#id5)
	- [Constraint primary key](#id5.1)
	- [Constraint foreign key](#id5.2) 
	- [Constraint not null](#id5.3)
	- [Constraint unique](#id5.4)
	- [Constraint check](#id5.5)
6. [Ejemplo creación de una base de datos](#id6)

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

#### CONSTRAINT <a name="id5"></a> ####
Sirve para limitar los tipos de datos que podemos meter en una tabla. Estas restricciones podemos añadirlas cuando la creamos con `CREATE TABLE` o después con `ALTER TABLE`. Los tipos de `CONSTRAINT` que veremos serán:

- `PRIMARY KEY`
- `FOREIGN KEY`
- `NOT NULL`
- `UNIQUE`
- `CHECK`

##### CONSTRAINT PRIMARY KEY <a name="id5.1"></a> #####
Asegura que los valores sean únicos para cada registro, cada tabla tiene que tener una obligatoriamente. La sintaxis será:
	
	[CONSTRAINT <nombreCONSTRAINT>]
		PRIMARY KEY (nombreAtributo)
Otra manera de poder usarlo sería:

	CREATE TABLE nombreTABLE(
		nombreAtributo CHAR(*) PRIMARY KEY,
		...
	);
Esto solo lo podemos hacer si la clave principal es un atributo y no varios.

##### CONSTRAINT FOREIGN KEY <a name="id5.2"></a> #####
Sirve para relacionar 2 tablas, cuando la usamos tenemos que indicar a tabla hace referencia esa clave foránea. La sintaxis será:

	FOREIGN KEY (nombreAtributo)
	REFERENCES <nombreTABLE> (nombreAtributoReferenciado)
	[ON DELETE CASCADE / NO ACTION / SET NULL / SET DEFAULT]
	[ON UPDATE CASCADE / NO ACTION / SET NULL / SET DEFAULT];
No es obligatorio poner el nombre del atributo referenciado, si no lo indicamos cogerá la clave principal de la tabla o el atributo que se llame igual que el otro. También podemos ver que tenemos diferentes criterios:

- `ON DELETE`: Sirve para decir que hacer cuando los datos son borrados
- `ON UPDATE`: Sirve para decir que hacer cuando se actualizan los datos.
- `CASCADE`: Sirve para poder eliminar o actualizar los datos que provenga de otra tabla y esten modificados.
- `No ACTION`: Sirve para dejar los datos como estaban, no elimina ni actualiza. Es el valor por defecto si no se indica nada.
- `SET NULL`: Si los datos son modificados o eliminados el valor es nulo.
- `SET DEFAULT`: Si los datos son modificados o eliminados el valor es el predeterminado. Poco usado ya que puede dar problemas.


##### CONSTRAINT NOT NULL <a name="id5.3"></a> #####
Sirve para no aceptar valores nulos. La sintaxis será:
	
	CREATE TABLE nombreTable (
	nombreAtributo1 CHAR(*) PRIMARY KEY
	nombreAtributo2 CHAR(*) NOT NULL,
	...
	);
Esto hace que el atributo 2 no pueda ir vacío, tendremos que darle un valor.