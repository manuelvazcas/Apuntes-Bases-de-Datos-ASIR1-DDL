## Apuntes DML ##

### Indice ###
- [Definición DML](#DML)
	- [INSERT](#INSERT)
	- [UPDATE](#UPDATE)
	- [DELETE](#DELETE) 

### Definición DML <a name="DML"></a>###
DML (Data Manipulation Language) es un sublenguaje de SQL que permite llevar a cabo las tareas de consulta o manipulación de los datos, organizados por el modelo de datos adecuado. 

#### INSERT <a name="INSERT"></a> ####
Sirve para insertar los valores en una base de datos. La sintaxis será:

	INSERT INTO <nombreTABLE>
	[nombreAtributo1, nombreAtributo2,...]
	VALUES
		(valorAtributo1A, valorAtributo2A,...)
		(valorAtributo1B, valorAtributo2B,...);
	
También podemos insertar valores haciendo una consulta DQL:
		
	INSERT INTO <nombreTABLE>
	[nombreAtributo1, nombreAtributo2,...]
		SELECT nombreAtributo3, nombreAtributo4
		FROM nombreTABLE
		WHERE ...
	;
Los atributos 1-3 y 2-4 tienen que ser equivalentes entre ellos.
Un ejemplo:
	
	INSERT INTO Alumnos
	(DNI, Nombre, edad)
	VALUE
		('12345678A', 'Manuel', 18)
		('87654321B', 'Luis', 23);
Ejemplo con consulta:

	INSERT INTO Alumnos
	(DNI, Nombre, edad)
		SELECT ID, name, age
		FROM Alumno
		WHERE age = 18 ;

#### UPDATE <a name="UPDATE"></a> ####
Sirve para modificar o actualizar los datos de una base de datos.