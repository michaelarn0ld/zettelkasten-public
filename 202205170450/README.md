# Configuring IntelliJ: Autoreload + Lombok Enabling

## Autoreload (Spring Boot)
* Make sure you have the following dependency
  ```
  <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
    <scope>runtime</scope>
    <optional>true</optional>
  </dependency>
  ```
* Make sure auto-build is enabled: Build -> Compiler

## Lombok
* Make sure Lombok IntelliJ plugin is installed!
* Make sure annotations processing is enabled in settings:
  Build -> Compiler -> Annotation Processors
* Add the following to your `pom.xml`:
  ```
  <dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>1.18.24</version>
    <scope>provided</scope>
  </dependency>
  ```

## Tags
#java
