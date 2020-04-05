## APUNTES DDL ##

### INDICE ###
1. [Definición DDL](#id1)
2. [Create](#id2)
	- [Create Database](#id2.1)
	- [Create Domain](#2.2) 
3. [Drop](#id4)
4. [Alter](#id5)
5. [Ejemplo Create table](#id6)
6. [Constraint primary key](#id7)
7. [Constraint foreign key](#id8)
8. [Constraint unique](#id9)
9. [Constraint check](#id10)

### DEFINICIÓN DDL<a name="id1"></a> ###

DDL, lenguaje de definición de datos, es un sublenguaje de SQL que permite llevar a cabo las tareas de definición de las estructuras que almacenarán los datos así como de los procedimientos o funciones que permitan consultarlos. Dentro de DDL existen varias sentencias que iremos viendo a continuación.

### CREATE<a name="id2"></a> ###

La sentencia Create sirve para crear una nueva base de datos ```CREATE DATABASE``` o ```CREATE SCHEMA```, tabla ```CRREATE TABLE```, dominio ```CREATE DOMAIN```, usarios ```CREATE USER```. Create crea un objeto dentro de un sistema de gestión de bases de datos relacionales, podiendo llegar a crear todos los objetos anteriormente puestos. Ahora especificaremos un poco más cada una de estas sentencias.

```CREATE DATABASE <a name="id2.1"></a>``` sirve para dar una orden para crear una nueva base de datos, tambien podriamos utilizar la palabra ***SCHEMA*** en vez de ***DATABASE*** para crear una base de datos. La sintaxis que usamos para crear una base de datos es:

	CREATE DATABASE/SCHEMA
	(Si no existe) nombreDATABASE
	(CHARACTER SET nombreCHARSET)

