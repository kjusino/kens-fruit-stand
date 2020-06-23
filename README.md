# kens-fruit-stand
Simple shopping cart web application using Java Spring
# Spring Boot Shopping Cart Web App

## About

This is a project created in preparation for the final round of interviews for Foundation Medicine. The application uses Java 1.8 and Spring + Thymeleaf. The idea was to build some basic shopping cart web app, create a docker image from a dockerfile, and deploy it onto AWS.

It was made using **Spring Boot**, **Thymeleaf**, **Spring Data JPA**, **Spring Data REST and Docker**. 
Database is in memory **H2**.

Users can shop for products. Each user has his own shopping cart (session functionality).
Checkout is transactional.

## Configuration

### Configuration Files

Folder **src/resources/** contains config files for **Kens Fruit Stand** Spring Boot application.

* **src/resources/application.properties** - main configuration file. Here it is possible to change the port number.

## How to run

You can run it from the command line with Docker. Create the docker image and run the docker container by running the script file **run_docker.sh**.

Once the app starts, go to the web browser and visit `http://localhost:8070`


### Maven

Open a terminal and run the following commands to ensure that you have valid versions of Java and Maven installed:

```bash
$ java -version
java version "1.8.0_102"
Java(TM) SE Runtime Environment (build 1.8.0_102-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.102-b14, mixed mode)
```

```bash
$ mvn -v
Apache Maven 3.3.9 (bb52d8502b132ec0a5a3f4c09453c07478323dc5; 2015-11-10T16:41:47+00:00)
Maven home: /usr/local/Cellar/maven/3.3.9/libexec
Java version: 1.8.0_102, vendor: Oracle Corporation
```
##### Helper script

It is possible to run all of the above with helper script:

```bash
$ . ./run_docker.sh
```

## Docker 

Folder **docker** contains:

* **docker/Dockerfile** - Docker build file for executing kens-fruit-stand Docker image. 
Instructions to build artifacts, copy build artifacts to docker image and then run app on proper port with proper configuration file.

## Tests

Tests can be run by executing following command from the root of the project:

```bash
$ mvn test
```

## Helper Tools

### H2 Database web interface

Go to the web browser and visit `http://localhost:8070/h2-console`

In field **JDBC URL** put 
```
jdbc:h2:mem:kens_fruit_stand_db
```

In `/src/main/resources/application.properties` file it is possible to change both
web interface url path, as well as the datasource url.
