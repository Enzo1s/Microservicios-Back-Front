Proyecto desarrollado con el objetivo de aprender sobre microservicios, consumo de APIs para el Back-end y desarrollo del Front-end de una aplicación web por medio Angular.

El proyecto consta de la administración de cursos teniendo en cuenta, cursos cons sus alumnos, asignaturas, examenes y respuestas por medio de una aplicacion web desarrollada con Angular, Angular Material y Bootstrap para consumir una API desarrollada por medio de microservicios. Esta API es la parte principal del proyecto, la cual está dividida en varios proyectos menores los cuales representan cada microservicio.

Cada uno de esos proyectos menores se encarga de manejar los datos de los cursos, alumnos y demas explicados anteriormente, persistiendo los datos en una base de datos de mySQL (curso,examenes, asignaturas) e postgreSQL (Alumnos) y en mongoDB (respuestas). Todos ellos siendo clientes (Eureka Client) del microservicio Eureka (Servidor Eureka), a medida que se levanta cada microservicio es registrado en eureka. Finalmente el acceso a cada microservicio se realiza a travez de Zuul o Gateway utlizando balanceador de carga para obtener la mejor instancia disponible.

Para esto es necesario tener conocimientos en:

	-Java (Se utiliza en todo el desarrollo del Back-End).
	-TypeScript (Utilizado para el Front-End, lenguaje implementado en 		Angular).
	-SQL (Manejo de base de datos estructuradas).
	-MongoDB (Base de datos documental, almacena los datos en archivos 		JSON y las consultas tambien se realizan por medio de JSON ).
	-HTML y CSS (Encargados de la estructura y la vista de la 		aplicación web).

Se implementan las siguientes tecnologías
Backend:
    • Spring Boot: Para desarrollar con microservicios, están implementados en Spring Boot
    • Spring IoC: Inversion de control es el contexto y contenedor de spring
    • Spring Data JPA e Hibernate:nos permite un manejo de base de datos transaccional través de anotaciones
    • API REST: La comunicación de microservicios es a través de API REST 
    • Spring Cloud: proporciona herramientas para un desarrollo rápido de algunos de los patrones comunes en sistemas distribuidos
    • Servidor Eureka Netflix: Es el servidor de registro. Se encarga de registrar a los microservicios a su vez son Eureka Client
    • Eureka Client:
    • Feign: Cliente http que se utiliza para comunicar entre microservicios mediante API REST. Utiliza anotaciones, interfaces y también es declarativo
    • Gateway Zuul: Centraliza el acceso a nuestros microservicios. Enruta de forma dińámica cada uno de los servicios. 
    • Spring Cloud Gateway:En las ultimas versiones de Spring no es posible utilizar zuul por lo que debemos utilizar Gateway
    • Ribbon: También de Netflix es un balanceador de carga
    • Spring Cloud LoadBalancer: Propio del desarrollo de Spring frameworks
    • Patrón de base de datos compartida: varios microservicios interactúan con una base de datos y la relación es por medio de claves foraneas, relación entre tablas
    • Patrón de base de datos por servidor: Cada microservicios posee su propia base de datos y las relaciones son distribuidas. La relación es a nivel de microservicios.

Frontend:
    • Angular CLI: Nos permite crear proyectos, componentes, clases service, modulos de un proyecto por medio de comandos.
    • Angular: Frameworks para el diseño de aplicaciones de una sola página
    • Service y HttpClient: Utilizado para comunicarnos con nuestra api
    • Angular material: Nos permite brindar estilos predefinidos a nuestra aplicación web
    • Bootstrap: al igual que angular material no brinda las herramientas para mejorar la experiencia del usuario de nuestra aplicación
    • Observable y API RxJs:Clase y librería reactiva que nos permite mejorar la respuesta de nuestra aplicación
