# Spring Boot 'Hello World' application

## Introduction
This guide aims to instruct the beginners on how to create, build and run a Simple Java Web App based on Spring Boot framework.
Before we begin, I'd like to appreciate Mr. Marcin Wojtysiak's effort in creating [this amazing tutorial](https://github.com/martinwojtus/tutorials/tree/master/spring-boot/hello-world). Also, [here](https://frontbackend.com/spring-boot/your-first-spring-boot-application-hello-world) here you can find detailed instructions on how to use it.

## Requirements

* Java Runtime Environment 8 to 11
* maven 3.3+

## Creating the Application
First, start a Maven project using your favorite IDE or just creating an empty folder, like `spring-boot-helloworld-example`, and put `pom.xml` file containing this:

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.springboot</groupId>
    <artifactId>hello-world</artifactId>
    <version>0.0.1-SNAPSHOT</version>

    <!-- Inherit defaults from Spring Boot -->
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.1.5.RELEASE</version>
    </parent>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>

</project>
```

Also, create the following folders:

* `src/main/java/com/springboot/` - source directory, you'll need to put here the `Application.java` file containg single Java class with public static void main method that starts Spring Boot application
* `src/main/resources/`- you can put `application.properties` file here

Change directory to `src/main/java/com/springboot/` and create `Application.java` file containing this:
```
package com.springboot;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.EnableAutoConfiguration;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@EnableAutoConfiguration
public class Application {

    @RequestMapping("/")
    String index() {
        return "Hello World!";
    }

    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
```

Finally, navigate to the project's root folder (the one containing `pom.xml` file) and type:

```
mvn spring-boot:run
```

Maven will build the Application and start Spring Boot:
```

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.1.5.RELEASE)

2021-05-29 19:18:57.855  INFO 69 --- [           main] com.springboot.Application               : Starting Application on 325181b77bfe with PID 69 (/opt/spring-boot-helloworld-example/target/classes started by root in /opt/spring-boot-helloworld-example)
2021-05-29 19:18:57.860  INFO 69 --- [           main] com.springboot.Application               : No active profile set, falling back to default profiles: default
2021-05-29 19:18:59.528  INFO 69 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2021-05-29 19:18:59.606  INFO 69 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2021-05-29 19:18:59.606  INFO 69 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.19]
2021-05-29 19:18:59.737  INFO 69 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2021-05-29 19:18:59.738  INFO 69 --- [           main] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1805 ms
2021-05-29 19:19:00.046  INFO 69 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2021-05-29 19:19:00.329  INFO 69 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2021-05-29 19:19:00.338  INFO 69 --- [           main] com.springboot.Application               : Started Application in 3.224 seconds (JVM running for 27.806)
^C2021-05-29 19:19:07.073  INFO 69 --- [       Thread-4] o.s.s.concurrent.ThreadPoolTaskExecutor  : Shutting down ExecutorService 'applicationTaskExecutor'

```

## Building JAR archive
In the project's root folder run this:
```
mvn clean install
```
If it succeeds, you should be able to find `target/hello-world-0.0.1-SNAPSHOT.jar` in the `target` directory.

## Containerizing the Application
Install `Docker Engine` if it is not installed yet.
In the project's root directory, create `Dockerfile` with the following content:
```
TBD
```


## Using CI to build and containerize the Application
### GitHub Actions
TBD

### Jenkins
TBD

### GitLab CI
TBD

## Running the Application in a Kubernetes cluster
TBD