# Spring Annotation: @{Qualifier} vs @{Profile} (Unresolved Question)
Was browsing through the Spring docs. Started thinking about @{Qualifier} and
@{Profile}. Is it fair to say that both of these help resolve DI when there are
multiple options, but in slightly different ways? In example 1:
```java
@Component
@Profile("student")
public class Student implements Person {
 // foo bar
}

@Component
@Profile("teacher")
public class Teacher implements Person {
    // foo bar
}

@Component
@Autowired
public class Office {
    private Person person
  // foo bar
}
```
Let's say for some reason in one environment, we wanted to use Student, in 
another we wanted to use Teacher; here, we only have one instance of the Office
so we add @Profile and will resolve the actual dependency at runtime via the
config files.


In example 2:
```java
@Component
@Qualfier("student")
public class Student implements Person {
 // foo bar
}

@Component
@Qualifier("teacher")
public class Teacher implements Person {
    // foo bar
}

@Component
public class Office {
    private Person person
  // foo bar
}

@Autowired
@Qualifier("student")
Office officeOne = new Office()

@Autowired
@Qualifier("teacher")
Office officeTwo = new Office()
```
We have two instances of the Office class, each with a dependency on Person.
These dependencies are consistent across environments so we do not care for 
configuration after compile time. We use qualifiers to configure in this manner.


## Related
[202112130115](../202112130115) - Java: Popular Maven Commands \
[202201142108](../202201142108) - Configuring Spring Boot Project: Starting from CLI vs IntelliJ


## Tags
#java #spring
