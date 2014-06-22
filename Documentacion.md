<style>
h1 {text-align: center;font-size:55px;margin-bottom:120%}
body{font-size:}

</style>
#Zona de Clientes y Administración

Miguel García Bajo  
2ª Desarrollo de Aplicaciones Web
<div style="page-break-after: always;"></div>

##Índice
1. Descripción en ingles **Página 3**
2. Lista de requisitos **Página 4**
3. Presupuesto **Página 4**
4. Planificación temporal con hitos **Página 4**
5. Pliego de condiciones **Página 5**
6. Documento de análisis y diseño **Página 5**
7. Documentación de instalación, configuración y desarrollo software **Página 6**
8. Documentación de usuario **Página 6**
9. Diario de bitácora **Página 7**
10. Bibliografía **Página 8**
11. Anexo 1: Contrato del proyecto


<div style="page-break-after: always;"></div>

### Descripción en ingles del objetivo del proyecto

The project is about an Administration Panel for the customer and a personalized area for their clients where they manage and check their data and revise their novelties and keep up to date.
The target of the project is to create an easy and simple network between my client and his clients, which offers a fast access to the information and particularities of each work that my client can get.  
The project has been developed using the framework Symfony and all its components.   
I have designed the application to be able to be used by anyone without knowledges in computers and internet.  
The main purpose has been to find uncomplicated possibilities to use this application in favour of the clients and his business.
All the components have been tested and troubleshoot and all everything works according to what has been agreed with the customer.
___
<div style="page-break-after: always;"></div>

### Lista de Requisitos
* Creación de un panel de administración para que la empresa pueda organizar sus actividades.
* Creación de una Zona de Cliente, donde el cliente pueda acceder a sus datos y modificarlos.
* Buen nivel de Seguridad
* Diseño con el Framework Symfony basado en php y twig.
* Diseño corporativo
___
### Presupuesto

Desglose del Trabajo:  

* Diseño de la aplicación personalizada, incluyendo Base de Datos [60 horas]  
* Mantenimiento de la aplicación durante 3 meses [100 €]
* Coste aproximado de la hora de trabajo: 15€
* Libro de Symfony: 10€
* No ha hecho falta la adquisición de nuevo material, ni para el diseño ni para su ejecución.
___
### Planificación Temporal
| Fecha        | Hito           | Tiempo Aprox.  |
| ------------- |:-------------:| -----:|
| 1 Mayo     | Estudiar Framework Symfony | 5 días |
| 6 Mayo      | Bocetos y planteamiento bbdd y estructura del proyecto   |   4 días |
| 10 Mayo | Aprender a usar y adquirir destreza con Symfony      | 5 días |
| 15 Mayo | Inserción de datos en la bbdd mediante fixtures      | 2 días |
| 17 Mayo | Desarrollar panel de administracion con SonataAdminBundle      | 5 días |
| 23 Mayo | Crear Zona de Clientes en base al UserBundle      | 3 días |
| 25 Mayo | Diseño y Css      | 3 días |
| 28 Mayo | Corrección de fallos y tests      | 2 días |
  ___
<div style="page-break-after: always;"></div>
### Pliego de Condiciones  

* Deberá estar operativa antes del 1 de Julio.
* Responsivo.
* Desarrollado según los estándares de Symfony(dentro de lo posible).
* No autorizada la re-utilización del código en otros proyectos ajenos a la empresa.
* Garantizar, según la ley de Protección de Datos de Carácter Personal, la confidencialidad de los datos personales aportados por el Cliente, la no aplicación o utilización de dichos datos
para un fin distinto al del ámbito de la actividad suscrita en este contrato, y la no cesión de
los datos a personas ajenas al cumplimiento de los acuerdos derivados de la prestación
del servicio.
___
###  Análisis y diseño
He utilizado **Bootstrap** tanto por su diseño de los elementos, su sistema de celdas y por su facilidad de aplicar el diseño responsivo  
El proyecto esta desarrollado bajo **Symfony** totalmente, usando bundles disponibles como Sonta admin para la parte de administracion de la aplicación, user bundle para manejar todo el funcionamiento de usuarios y creando mis propios bundles para organizar, manejar y modificar el proyecto.    
Los Bundles creados por mi son: Clientes, Trabajos, Servicios, Frontend, Backend y Presupuestos. El más importante es ClientesBundle, que es donde gestiono todo desde el **MVC** que Symfony nos ofrece.  
Symfony incluye la librería **Doctrine** como ORM (Object Relational Mapper) por defecto., que proporciona herramientas para simplificar el acceso y manejo de la información de la base de datos. Una característica importante de Doctrine es la posibilidad de escribir consultas de base de datos utilizando un dialecto de SQL denominado **DQL**, que facilita el use de joins.  
Doctrine trabaja con entidades, que son la representación “orientada a objetos” de nuestras tablas.  
Symfony provee un generador de Entidades para mapear la informacion de nuestras entidades he optado por usar anotaciones en vez de **YAML** o php directamente.  
El driver que utiliza la bbdd es **pdo_mysql** y voy manejando una importación de ella a través de **phpMyAdmin** durante el procesa de creación.  
**SonataAdminBundle** crea la parte de administración de la aplicación. A partir de su diseño permite modificar y adaptar a lo que el cliente necesitaba.  
El motor de Plantillas que emplea Symfony por defecto es **Twig**. Twig añade múltiples funcionalidades(de php) sobre el mismo html.  
Symfony utiliza archivos YAML de configuración sencillos para trabajar.  
He utilizado **git** como **CVS**, subiendo el código y mis commits con mi cuenta de github(**mikeobama**) a través del repositorio privado creado por mi cliente.  
He seguido la línea de diseño que la empresa emplea en su página web, utilizando el verde ```#9ABF1A ``` de su logo para decorar varios elementos html del codigo(botones, hovers...).
<div style="page-break-after: always;"></div>
###Instalación, Configuración y Desarrollo de Software  

Para su ejecución en local debes seguir los siguientes pasos:
```sh
cd /var/www/
git clone https://github.com/sclaver/nuevatobe.git nuevatobe
cd nuevatobe/
composer install
```
El  ```composer install``` se encarga de instalar todo lo necesario para el funcionamiento del proyecto.  
Existe una BBDD en los archivos, **nuevatobe.sql** con la configuración adecuada y ciertos datos para mostrar.  
Configuramos los parametros de la BBDD, si vas a importar el .sql, el nombre de la Base de Datos es nuevatobe  
Debes modificar los permisos siguientes(el último es opcional, si no cargas los datos no hace falta):
```
chmod 777 -R web/
chmod 777 -R app/cache
chmod 777 -R app/logs
```

Una vez que esta instalada la aplicación junto con la BBDD nos dirigimos a ```http://localhost/nuevatobe/web/app_dev.php/login``` y con la información suministrada puede loguearse tanto como Admin o como un Cliente, ya que hay varios perfiles de prueba.
___

### Documentación de usuario
Una vez que el sistema se encuentre en funcionamiento y se empiece a crear usuarios y clientes, estos simplemente tendrán que acceder a su Zona a través de la web principal de [ToBeSolutions] con el nombre de usuario y contraseña que le sean asignados y una vez dentro de la zona podrán ver el estado de sus proyectos, facturas, archivos interesantes para el correcto funcionamiento de su web y acceder a sus datos y modificarlos si existiese algún cambio.
___
<div style="page-break-after: always;"></div>
### Diario de bitácora

| Fecha        | Hito           |
| ------------- |:-------------:| 
| 6 Mayo     | Fase Inicial de creación de Bundles y Entidades | 
| 10 Mayo  | Fixtures      | 
| 13 Mayo | SonataAdminBundle, instalación y desarrollo   | 
| 22 Mayo | UserBundle, instalación y desarrollo      | 
| 24 Mayo | Empezando a crear Zona de Clientes   | 
| 27 Mayo | Reestructuración de entidades y creación de nuevas      | 
| 3 Junio | Sobreescribiendo Formularios  | 
| 13 Junio | Trabajando en el Diseño  |   


  
> Para datos más concretos ver Commits del [Proyecto] en GitHub .  

___
<div style="page-break-after: always;"></div>
## Bibliografía


He utilizado:

* [Desarrollo web ágil con Symfony2]
* [Symfony Esp] Documentación Symfony en Español
* [Documentación Symfony] - Documentación Online de Symfony
* [StackOverflow] - para resolver todo tipo de dudas, ya sea php puro, Symfony, Twig, YAML...
* [Twitter Bootstrap] - La Documentación de Bootstrap online
* [Circle Hover Effects] 


[Desarrollo web ágil con Symfony2]:http://symfony.es/libro
[StackOverflow]:http://stackoverflow.com
[Documentación Symfony]:http://symfony.com/doc/current/index.html
[Circle Hover Effects]:http://tympanus.net/Tutorials/CircleHoverEffects/index7.html
[Symfony Esp]:http://gitnacho.github.io/symfony-docs-es/
[Twitter Bootstrap]:http://getbootstrap.com/css
[ToBeSolutions]:http://www.tobesolutions.com
[Proyecto]:https://github.com/sclaver/nuevatobe/commits/master
