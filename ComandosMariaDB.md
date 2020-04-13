## Comandos de MariaDB ##
En esta tarea se mostrarán comandos de MariaDB que permiten ver la estructura y los datos de una base de datos simulando una GUI en la ventana de comandos, mostrando la sintaxis de estos comandos y capturas para ver el resultado.

### Indice ###
- [Logearse en MariaDB](#LOGIN)
- [Mostrar base de datos.](#SHOWBDD)
- [Usar una base de datos](#USE)
- [Mostrar tablas](#SHOWT)
- [Describir una tabla](#DESC)
- [mostrar Index tabla](#INDEX)
- [Exportar una base de datos](#EXPORT)

### Logearse en MariaDB <a name="LOGIN"></a>
Este comando sirve para poder entrar en MariaDB desde la ventana de comandos. La sintaxis del comando sería:
	
	mysql -u [nombreUsuario] -p [contraseña]
![](Img/Comandos-1.PNG)

### Mostrar una base de datos <a name="SHOWBDD"></a> ###
Este comando sirve para mostrar las bases de datos que tenemos creadas. La sintaxis del comando sería:

	SHOW DATABASES;
![](Img/Comandos-2.PNG)

### Usar una base de datos <a name="USE"></a> ###
Este comando sirve para especificar la base de datos que queremos usar en concreto. La sintaxis del comando sería:

	USE <nombreDATABASE>;
![](Img/Comandos-3.PNG)

### Mostrar tablas <a name="SHOWT"></a> ###
Una vez ya selecciona la base de datos que queremos usar y creadas las tablas podemos ver si las tablas estan creadas usando este comando. La sintaxis sería:

	SHOW tables;
![](Img/Comandos-4.PNG)

### Describir una tabla <a name="DESC"></a> ###
Este comando nos sirve para poder ver la estructura interna de una tabla, sus atributos, de que tipo son, cual es la clave primaria, si hay claves foraneas... La sintaxis sería:

	Describe <nombreTable>;
![](Img/Comandos-5.PNG)

### Mostrar Index tabla <a name="INDEX"></a> ###
Este comando sirve para poder ver la información de los indices de la tabla que seleccionemos. La sintaxis sería:

	SHOW INDEX FROM <nombreTable>;
![](Img/Comandos-6.PNG)

### Exportar una base de dato <a name="EXPORT"></a> ###
Este comando nos servirá para exportar una base de datos a un fichero .sql. La sintaxis será