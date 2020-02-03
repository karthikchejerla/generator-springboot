# generator-springboot
A Yeoman generator for generating Microservice with SpringBoot

## How to use?

```
> npm install -g yo
> npm install -g generator-springboot
> yo springboot
```

## Features

1. Microservice

    * SpringBoot REST API with jar type packaging
    * CORS configuration
    * Swagger UI Integration
    * Spring Data JPA integration with option to select databases like MySQL, Postgresql, MariaDB etc
    * Flyway or Liquibase data migration support
    * SpringBoot Actuator configuration
    * Integration with Config Server, Service Registry, Sleuth, Zipkin
    * TestContainers integration
    * JUnit 5 
    * Docker configuration for Application, ELK, Prometheus, Grafana
    * Jenkinsfile

2. Spring Cloud Config Server

    * Config Server with Git and native backend configuration

3. Service Registry

    * Service Registry based on Netflix Eureka

### Generate SpringBoot Microservice

![Microservice Generation](docs/microservice-generation.png)

### Generate REST API with CRUD operations
You can generate REST API with CRUD operation using the following command:

:high_brightness: You should run the following command from within the generated project folder. 

`myservice> yo springboot:controller Customer --base-path /api/customers`

This will generate:
* JPA entity
* Spring Data JPA Repository
* Service
* Spring MVC REST Controller with CRUD operations
* Unit and Integration Tests for REST Controller
* Flyway or Liquibase migration to create table

![Microservice Generation](docs/crud-generation.png)

### Generate SpringCloud Config Server

![Microservice Generation](docs/configserver-generation.png)

### Generate SpringCloud Service Registry

![Microservice Generation](docs/serviceregistry-generation.png)

## Why another generator when you have JHipster?
JHipster is an amazing SpringBoot application generator with lots and lots of cool features.
However, there are certain JHipster features that does not fit for my preferences such as:

1. I like *jar* packaging
2. I like to use spring-boot-starter-* than configuring individual libraries
3. I like to have an option to generate application without spring-security
4. I prefer Flyway over Liquibase
5. I like to have only minimum and required configuration ie no AsyncConfiguration, LocaleConfiguration, CacheConfiguration, Logstash Logging etc.
6. I like .properties over .yml

## Local Development Setup

```
> git clone https://github.com/sivaprasadreddy/generator-springboot.git
> cd generator-springboot
> npm install 
> npm link
> yo springboot
```

## Changelog

### Version 0.0.5
* Added support for generating docker-compose yml files for application, ELK, Prometheus, Grafana

### Version 0.0.6
* Updated to use testcontainers-spring-boot https://github.com/testcontainers/testcontainers-spring-boot
* Generate Zipkin docker-compose file when Distributed Tracing is selected
* Fixed Flyway/Liquibase db migration script generation issue
* Added tests for sanity check
