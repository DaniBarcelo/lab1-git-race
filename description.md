# Web Engineering 2020-2021 / Lab1 Git Race

Simple Spring web application which can perform several actions:
* Get current date & welcome message
  * The actual date (*Thu Sep 17 16:26:04 CEST 2020*, for example)
  * A welcome (*Hola alumno*)
* Add two integer numbers
* Show a link to a youtube video
* Show current browser and version
* Roll the dice to resolve disputes

## Table of Contents

1. [How to build the code](#how-to-build-the-code)
1. [How to test the code](#how-to-test-the-code)
1. [How to run the code](#how-to-run-the-code)
1. [How to deploy the code in a server](#how-to-deploy-the-code-in-a-server)
1. [Setting up Redis](#setting-up-redis)
1. [Using Redis in your application](#using-redis-in-your-application)
1. [Which are the technologies used in the code](#which-are-the-technologies-used-in-the-code)
1. [How these technologies work](#how-these-technologies-work)
1. [What means each a specific piece or code](#what-means-each-a-specific-piece-or-code)
1. [Which is the purpose of a specific Java annotation](#which-is-the-purpose-of-a-specific-java-annotation)
1. [How to implement code following TDD best practices](#how-to-implement-code-following-tdd-best-practices)
1. [Copyright issues](#copyright-issues)

## How to build the code

This App's code is built using [Gradle](http://gradle.org), for its installation please refer to the [Gradle installation guide](https://docs.gradle.org/current/userguide/installation.html). To then build the code follow the following steps:

```bash
git clone https://github.com/UNIZAR-30246-WebEngineering/lab1-git-race
cd lab1-git-race
./gradlew build
```

After the build is completed, the generated WAR file will be located inside the _libs_ folder under the _build_ directory.

## How to test the code

Gradle can perform all tests automatically.

```bash
./gradlew check
```

## How to run the code

This program runs an application server (embedded into Spring library).
In order to build and execute the project you have to do:

```bash
./gradlew bootRun
```

## How to deploy the code in a server

Web's deployment using Heroku and GitHub:

	-Install Git Bash and Heroku CLI locally
	-Log in Git and Heroku
	-Create a new app in Heroku's web with the desired name (deployp1iw)
	-Add dependencies in build.gradle
	-Create a Procfile file that executes app's .war
	-While on app's root directory (locally), create a link between GitHub and Heroku: heroku git:remote -a deployp1iw
	-Push to Heroku: git push heroku master

Once the previous steps have been followed, the web is deployed, the following link shows the web (it may take time to load the web due to Heroku's restrictions on free apps): https://deployp1iw.herokuapp.com/
These guides have been followed to deploy the web: https://devcenter.heroku.com/articles/git (deploy using Git) and https://devcenter.heroku.com/articles/deploying-gradle-apps-on-heroku (deploy using Gradle).


This web has been documented using Swagger, which allows you to describe the generated API (Controllers) and its functions. The next guide has been followed to document the web: https://www.baeldung.com/swagger-2-documentation-for-spring-rest-api
A new class has been added to the application, SpringSwaggerConf.java, which defines Swagger's configuration. The class HelloController.java has been modified, adding the API's description and its only function's description (welcome).
Swagger documentation: https://deployp1iw.herokuapp.com/swagger-ui/#/


## Which are the technologies used in the code

* Spring ~ Controller side
* HTML/CSS ~ View side
* Tomcat ~ Server side
* Java ~ Controller engine

This project's code is documented following Javadoc standards.

## How to deploy the code in a server

Despliegue de la Web utilizando Heroku y GitHub:

	-El primer paso es tener instalados Git Bash y Heroku CLI
	-Estar logueado en ambas plataformas
	-Se crea una nueva app en Heroku con el nombre que se desee (deployp1iw)
	-Añadir al build.gradle las líneas necesarias para el despliegue de la web.
	-Crear un fichero Procfile sin extensión con la ejecución del .war de la aplicación.
	-En el directorio raíz de la aplicación, donde también se ha declarado un repositorio git con un commit hecho, se crea una conexión GitHub-Heroku con el siguiente comando: heroku git:remote -a nombre_app (nombre_app es deployp1iw en este caso), y pushear el contenido del repositorio: git push heroku master.

Una vez seguidos los pasos anteriores la web se encuentra desplegada, en el siguiente link se muestra la web (es posible que tarde en cargar la página, dadas las restricciones de Heroku a aplicaciones gratuitas): https://deployp1iw.herokuapp.com/
Se han seguido las siguientes guías para desplegar la aplicación: https://devcenter.heroku.com/articles/git (para desplegar con Git) y https://devcenter.heroku.com/articles/deploying-gradle-apps-on-heroku (para desplegar con Gradle).

Para la documentación de la aplicación se ha utilizado Swagger que permite describir la API generada por la web (Controllers) y sus funciones. Para esta tarea se ha seguido la siguiente guía: https://www.baeldung.com/swagger-2-documentation-for-spring-rest-api
Las inyecciones de dependencias hechas en Maven en la guía se han transcrito a dependencias en build.gradle, se ha creado una nueva clase SpringSwaggerConf.java que define la configuración de Swagger y en la clase HelloController.java se han definido las descripciones para la API y para su única función (welcome).
Dicha documentación se puede consultar en el siguiente link: https://deployp1iw.herokuapp.com/swagger-ui.html#/

## Which is the purpose of a specific java annotation

### @SpringBootApplication

This annotation is used on top of most Spring Boot main class programs, as it enables the developer an to configure and scan for components automatically.

This annotation has teh same function as @ComponentScan, @EnableAutoConfiguration, and @Configuration with their default attributes, allowing the developer to reduce this three annotations into only one.

Here's a brief description of each annotation's function:

* @Configuration: allows us define the class which possesses it as a configuration class. It also allows us to inject additional dependencies(beans).
* @EnableAutoConfiguration: it's Spring Boot's automatic configuration, which changes in function of the beans aggregated.
* @ComponentScan: works alongside @Configuration in order to tell Spring where to find other @Component, always on the package where the application is located.

If the developer wants to replace one of these three annotations for a different one, it would be necessary to substitute the unwanted annotation.

## Copyright issues

Added an image with creative commons license to the web.The source of the image chosen is the following: https://commons.wikimedia.org/wiki/File:Zaragoza_-_Bas%C3%ADlica_del_Pilar_y_r%C3%ADo_Ebro.jpg attributed to [Turol Jones, un artista de cojones from Villanueva del Cascajal, República Independiente de Mi Casa](https://commons.wikimedia.org/wiki/File:Zaragoza_-_Bas%C3%ADlica_del_Pilar_y_r%C3%ADo_Ebro.jpg) / [CC BY](https://creativecommons.org/licenses/by/2.0)
