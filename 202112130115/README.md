# Java: Popular Maven Commands

|   Command                                         |   Use
|   -                                               |   -
|   mvn clean compile                               |   Compiles code
|   mvn clean test -Dtest=xxxTest                   |   Runs the tests (-Dtest to run a specific test)
|   mvn clean install                               |   Compiles, tests, and packages the Java project
|   mvn -DskipTests=true package                    |   Builds the executable jar (make sure you have pom dependencies)
|   mvn exec:java -Dexec.mainClass=package.name.App |   A way to excecute the main method from command line

* The ```clean``` option on all of the above commands functions to remove all
previously compiled ```*.class``` files that were a part of your project. It does this
by removing the ```target``` directory.


## Related


## Tags
#java #maven
