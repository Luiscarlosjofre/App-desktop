##  **APLICACIÓN DE ESCRITORIO G&C v2.0**

Esta aplicación de escritorio está diseñada para la ***gestión y control de equipos tecnológicos***. 

Es un **CRUD** (***Create, Read, Update and Delete***), es decir, que puede ***crear, buscar, editar y eliminar*** registros de la base de datos.

La principal ventaja de esta aplicación con una base de datos conectada de manera local ***-aparte de la rapidez para ejecutar los procesos dado que sus controles y eventos ocurren en el mismo equipo-***, es ofrecer capacidad de uso sin conexión a internet, siendo funcional en cualquier momento brindando un beneficio por sobre las aplicaciones web.

La desventaja que tiene esta aplicación de escritorio es el mantenimiento de sus actualizaciones, ya que ***habrá que recorrer cada una 
de las estaciones de trabajo para ejecutar la actualización cada vez que lo requiera*** :)

Este proyecto está siendo desarrollado con ***Tecnología Python***, ***Tkinter***, ***MySQL Community Server para la Base de Datos y mucho, mucho*** ❤️

[G&C](https://github.com/luisjofre/Aplicaciones/commit/bfb31584cfbf26680bf5ae060c8a66bc70f1d9dd "G&C")

***

Si quiere descargar y modificar el código considere lo siguiente:

**Requisitos:**

	- Sistema operativo Windows 10 o superior.
	- Python 3.0 o superior instalado
	- MySQL Workbench instalado y
	- Un editor de código.

Descarga de **MySQL Community Server** desde su sitio oficial:

	https://www.mysql.com/


**Instalación**

**PASO 1**

Una vez descargado e instalado ***MySQL Workbench,*** deberá actualizar las credenciales de acceso a la base de datos:

	Host: '127.0.0.1',
	User: 'root',
	Password: '***********'

**PASO 2**

Crear lo siguiente en el gestor de bases de datos ***MySQL Workbench:***


**Nombre de la Base de Datos:**

	"comodatos"
	
	
**Nombre de la Tabla:**

	"contratos"
	
**Ejemplo:**

id	| nombre	|apellidos	|run		|dispositivo|marca	|modelo	|serie	     |fepre	|fedevo    |estado  |date      |time    |
--------|---------------|---------------|---------------|-----------|-----------|-------|------------|----------|----------|--------|----------|--------|
1	|	Nombre  |      Apellidos|   00.000.000-0|dispositivo|      marca| modelo|000000000000|00-00-0000|00-00-0000|  estado|00-00-0000|00:00:00|


**Información para la creación de las columnas**

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


**PASO 3**


	Una vez creada la base de datos comodatos y la tabla contratos, podrá importar sus registros en un archivo CSV o JSON
	teniendo en cuenta el nombre y la cantidad de columnas creadas.


**PASO 4**

Ir al **Zip con el código en:**

	https://github.com/luisjofre/Aplicaciones.git
	
	Hacer clic en Code, luego clic en Download Zip para descargar el archivo comprimido.
	Posteiormente, descomprima el archivo en el escritorio y ejecute el archivo con el nombre sistema.py desde su editor 
	de cógido preferido.


**PASO 5**
	
	Luego de modificar el código y lo tenga listo, puede compilar y convertir en ejecutable el código, para ello existen
	algunas alternativas como pyinstaller o Auto-Py-To-Exe

***
	
	Vista de la pantalla inicio o interfaz principal sin conexión a la base datos (indicador visual luz roja).
![](https://i.postimg.cc/8cKC0ccp/Captura1.png)

***

	Conectado ya con la base de datos MySQL Workbench (indicador visual luz verde), permite realizar las operaciones de agregar, 
	buscar un nuevo contrato, editar o eliminar los registros de la base de datos. 
	En la siguiente imagen vemos el resultaso (en color gris) de la acción del botón "Mostrar todo".
![](https://i.postimg.cc/Wp6YJrqL/Captura2.png)

***

	En cuanto a la búsqueda de contratos de comodato, usted puede buscar por id, nombre de usuario, apellidos, run, dispositivo,
	marca, modelo, n°serie, etc.
![](https://i.postimg.cc/D0yrGSRn/Captura3.png)

***

	No está demás recordar de realizar los respaldos periódicamente de la base de datos. 
	Esta aplicación te permite exportar a tu computador un archivo CSV, con todos los registros de la base de datos.
![](https://i.postimg.cc/t4HgvKCV/Captura4.png)

***
	Por último, una imagen de la Base de Datos MySQL Workbench con sus columnas y registros.
![](https://i.postimg.cc/CxQwT9wN/Captura5.png)

***

**Licencia**

	Open Source Software (OSS) o sofftware de código abierto para su uso y modificación, 
	con el objetivo seguir fortaleciendo esta hermosa comunidad.

**¿Qué es Open Source Software?**

	El open source software es un código diseñado de manera que sea accesible al público: 
	todos pueden ver, modificar y distribuir el código de la forma que consideren conveniente.

	El software open source se desarrolla de manera descentralizada y colaborativa, así que depende de la revisión
	entre compañeros y la producción de la comunidad. Además, suele ser más económico, flexible y duradero que sus
	alternativas propietarias, ya que las encargadas de su desarrollo son las comunidades y no un solo autor o una
	sola empresa.

	El open source se convirtió en un movimiento y una forma de trabajo que trasciende la producción del software.
	Adopta los valores y el modelo de producción descentralizada del software open source para hallar nuevas 
	maneras	de solucionar los problemas en las comunidades.

	fuente: https://www.redhat.com/es/topics/open-source/what-is-open-source

***

![](https://i.postimg.cc/25j6WsS4/Gmail.png)		luisjofreperez@gmail.com

![](https://i.postimg.cc/2SD3kbp9/Twitter.png)		@Luiscarlosjofre

![](https://i.postimg.cc/sg4xvjsj/LinkedIn.png)		linkedin.com/in/luis-jofré-pérez-508b2755


***Copiapó, julio 2022***

