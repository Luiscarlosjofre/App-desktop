##  **APLICACIÓN DE ESCRITORIO G&C**

Esta aplicación de escritorio está diseñada para la gestión y control de equipos tecnológicos. Es un **CRUD** (Create, Read, Update y Delete), es decir, que puede crear, buscar, editar y eliminar un registro de la base de datos.

La principal ventaja de esta aplicación, aparte de la rapidez para ejecutar los procesos -dado que sus controles y eventos ocurren en el mismo equipo- es ofrecer capacidad de uso sin conexión a internet, siendo funcional en cualquier momento brindando un beneficio por sobre las aplicaciones web.

La desventaja que tienen la mayoría de las aplicaciones de escritorio es el mantenimiento de sus actualizaciones, ya que se deberá recorrer cada una de las estaciones de trabajo para ejecutar la actualización.

Este proyecto está desarrollado con **Tecnología Python**, la **Librería Tkinter**, **MySQL** para la Base de Datos y mucho ❤️ ;) [G&C](https://github.com/luisjofre/Aplicaciones/commit/bfb31584cfbf26680bf5ae060c8a66bc70f1d9dd "G&C")

**Requisitos:**

	- Sistema operativo Windows 10 o superior.
	- Intalación de MySQL Workbench en su sistema operativo, y
	- Un editor de código.

Descargar **MySQL** desde su sitio oficial:

	https://www.mysql.com/

**Instalación**

**Paso 1**

Una vez instalado MySQL Workbench, deberá actualizar las credenciales en el código para dar acceso a la base de datos:

	Host: '127.0.0.1',

	User: 'root',

	Password: '***********'

**Paso 2**

Descargar las líneas de código:

	https://github.com/luisjofre/Aplicaciones.git


**Paso 3**

Crear lo siguiente en el gestor de bases de datos MySQL:


Nombre de la Base de Datos:

	"comodatos".
	
	
Nombre de la Tabla:

	"contratos".
	

id	| nombre	|apellidos	|run		|dispositivo|marca	|modelo	|serie	     |fepre	|fedevo    |estado  |date      |time    |
--------|---------------|---------------|---------------|-----------|-----------|-------|------------|----------|----------|--------|----------|--------|
1	|	Nombre  |      Apellidos|   00.000.000-0|dispositivo|      marca| modelo|000000000000|00-00-0000|00-00-0000|  estado|00-00-0000|00:00:00|

		- id int AI PK
		- nombre varchar(100)
		- apellidos varchar(100)
		- run varchar(30)
		- dispositivo varchar(45)
		- marca varchar(45)
		- modelo varchar(45)
		- serie varchar(45)
		- fepre varchar(45) (fecha préstamo)
		- fedevo varchar(45) (fecha devolución)
		- estado varchar(45)
		- date varchar(45)
		- time varchar(45)

**Paso 3**
	Una vez creada la base de datos comodatos y la tabla contratos, puede importar sus registros desde un archivo CSV o JSON teniendo en cuenta
	las columnas de la tabla creada.
****

	Vista previa de la pantalla de inicio o interfaz principal sin conectar a la base datos.
![](https://i.postimg.cc/8cKC0ccp/Captura1.png)

	Conectado ya con la base de datos MySQL Workbench, permite realizar todas las operaciones de agregar o buscar un nuevo contrato, 
	editar o eliminar los registros de la base de datos. Aquí en la imagen vemos la acción del botón "**Mostrar todo**".
![](https://i.postimg.cc/Wp6YJrqL/Captura2.png)

	En cuanto a la búsqueda de contratos de comodato, se puede hacer por Id, nombre de usuario, apellidos, run o por dispositivo, 
	marca, modelo, n°serie, etc.
![](https://i.postimg.cc/D0yrGSRn/Captura3.png)

	Por último, recordad realizar los respaldos de la base de datos cada cierto tiempo. En esta aplicación puedes exportar un archivo
	de tipo CSV de Excel, con todos los registros de la base de datos.
![](https://i.postimg.cc/t4HgvKCV/Captura4.png)

	La Base de Datos del proyecto en MySQL Workbench con sus columnas y registros.
![](https://i.postimg.cc/CxQwT9wN/Captura5.png)

**Licencia**
	Se pone a disposición de las escuelas públicas y su comunidad escolar este software con licencia open source (OSS).

**¿Qué es Open  Source?**

	El software open source es un código diseñado de manera que sea accesible al público: todos pueden ver, modificar y distribuir el código
	de la forma que consideren conveniente.

	El software open source se desarrolla de manera descentralizada y colaborativa, así que depende de la revisión entre compañeros y la 
	producción de la comunidad. Además, suele ser más económico, flexible y duradero que sus alternativas propietarias, ya que las encargadas de su 		desarrollo son las comunidades y no un solo autor o una sola empresa.

	El open source se convirtió en un movimiento y una forma de trabajo que trasciende la producción del software. Adopta los valores y el modelo de 		producción descentralizada del software open source para hallar nuevas maneras de solucionar los problemas en las comunidades y los sectores.

	fuente: https://www.redhat.com/es/topics/open-source/what-is-open-source


![](https://i.postimg.cc/25j6WsS4/Gmail.png)  luisjofreperez@gmail.com

![](https://i.postimg.cc/2SD3kbp9/Twitter.png)  @Luiscarlosjofre

![](https://i.postimg.cc/sg4xvjsj/LinkedIn.png)  linkedin.com/in/luis-jofré-pérez-508b2755

	Copiapo, julio 2022

