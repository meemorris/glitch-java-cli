## Overview
To run a Java command-line program as a project on [Glitch](https://glitch.com):
1. Fork this repository.
1. Replace `my_app.jar` with your own jar (named `my_app.jar`, or update `start.sh` with your jar name).
1. On Glitch, select New Project > Clone from Git Repo, and select your fork of this repository.

## How to create my_app.jar (using Maven and the Spring Boot Maven plugin)

* Add this section to your pom.xml file within project/build/plugins, replacing `com.example.main` with the class that contains the main method you want to execute:
```
<plugin>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-maven-plugin</artifactId>
  <version>2.4.1</version>
  <configuration>
    <mainClass>
      com.example.main
    </mainClass>
  </configuration>
</plugin>
```
* Build the jar by running `mvn clean package spring-boot:repackage`
* Find the resulting jar in the target directory, rename it to `my_app.jar` and confirm it runs with `java -jar my_app.jar`

## IMPORTANT NOTE
Glitch currently only supports Java 8, so your jar file needs to be compatible with Java 8.
