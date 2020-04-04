# Instalación MariaDB

Para empezar descargaremos MariaDB para la versión de equipo que estemos usando, en mi caso la versión de 64 bits MSI para Windows.

Despues abrimos el archivo y dejamos la primeras opciones por defecto.
![](img/instalacionMariaDB-1.png)

Pondremos la contraseña para el usuario root
![](img/instalacionMariaDB-2.png)

Dejamos las características por defecto.
![](img/instalacionMariaDB-3.png)

Y instalamos el programa.
![](img/instalacionMariaDB-4.png)

Ahora abrimos las variables del entorno y añadimos la ruta de la carpeta bin del MariaDB en PATH
![](img/instalacionMariaDB-5.png)

Abrimos el CMD y ponemos el comando para ejecutar MariaDB ``mysql -u root -p``, despues de esto ponemos la contraseña del root, que ya establecimos antes.
![](img/instalacionMariaDB-6.png)

Con esto ya estaría instalado MariDB, ahora haremos una prueba creando una base de datos a ver si funciona bien. 
![](img/instalacionMariaDB-7.png)