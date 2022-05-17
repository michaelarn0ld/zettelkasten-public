# Configuring IntelliJ: Autoreload + Lombok Enabling

## Autoreload

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
