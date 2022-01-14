# Configuring Spring Boot Project: Starting from CLI vs IntelliJ
Since Spring Boot 2.3.0.RELEASE, documentation indicates that the default
behavior for the server sending back the stack trace on bad requests is:
```
server.error.include-stacktrace=never
```
While this is important for security (we don't want bad actors to intentionally
send bad requests to expose information about our system), it can be a pain 
during development. Sometimes, developers wan't to see the stack trace when
testing positive and negative cases for their API endpoints. 

The pom.xml dependency ***spring-boot-devtools*** sets the default behavior to:
```
server.error.include-stacktrace=always
```
When you include this, you will not need to modify your application.properties
to include the stack trace; however, this behavior holds only in the IntelliJ
environment. When you attempt to run your project outside of IntelliJ, and you
still want the stack trace to appear, you must add the setting to
application.properties:
```
server.error.include-stacktrace=always
```
Somehow, the mentioned pom.xml dependency
does not get picked up when you start the server from the terminal, so unless
you manually configure the application.properties to override the default
behavior, you will not recieve the stack trace.

## Related
[202112130115](../202112130115) - Java: Popular Maven Commands \
[Spring GitHub Issue](https://github.com/spring-projects/spring-boot/issues/21497)

## Tags
#java #maven #spring
