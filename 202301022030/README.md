# SSL Issues with Spring Boot Applications

I recently added a self signed certificate to my `zettels-service` application;
the changes that allowed me to do this were:

Generate Self-Signed Cert
```
keytool -genkey -alias <ALIAS> -storetype PKCS12 -keyalg RSA -keysize 2048 -validity 365 -keystore <CERT>.p12
```

Spring Boot `application.properties`
```
# The format used for the keystore. for JKS, set it as JKS
server.ssl.key-store-type=PKCS12

# The path to the keystore containing the certificate
server.ssl.key-store=classpath:keystore/<CERT>.p12

# The password used to generate the certificate
server.ssl.key-store-password=<>

# The alias mapped to the certificate
server.ssl.key-alias=<ALIAS>

# Run Spring Boot on HTTPS only
server.port=8443

#HTTP port
http.port=8080
```

Spring Boot `App.java` to allow both `http` and `https` requests to be processed
(port 8080 and port 8443)
```java
@SpringBootApplication
public class App {

    // This will be the port for the http traffic
    @Value("${http.port}")
    private int httpPort;

    public static void main(String[] args) {
        SpringApplication.run(App.class, args);
    }

    // Added this bean to allow http traffic on httpPort
    @Bean
    public ServletWebServerFactory servletContainer() {
        TomcatServletWebServerFactory tomcat = new TomcatServletWebServerFactory();
        tomcat.addAdditionalTomcatConnectors(createStandardConnector());
        return tomcat;
    }

    // Creates the connector for the above @Bean
    private Connector createStandardConnector() {
        Connector connector = new Connector("org.apache.coyote.http11.Http11NioProtocol");
        connector.setPort(httpPort);
        return connector;
    }
}
```

FYI: the `keystore/<CERT>.p12` file was placed under the `src/main/resources/`
directory to work with the `server.ssl.key-store=classpath:keystore/<CERT>.p12`
in `application.properties`...

Now, when I am running my application, there appears to be a new error which is
associated with the self-signed cert that I generated. When I run the following
command:
```
curl -X GET https://ec2-54-176-135-148.us-west-1.compute.amazonaws.com:8443/previews
```

I get the error from cURL:
```
curl: (60) SSL certificate problem: self signed certificate
More details here: https://curl.haxx.se/docs/sslcerts.html

curl failed to verify the legitimacy of the server and therefore could not
establish a secure connection to it. To learn more about this situation and
how to fix it, please visit the web page mentioned above.
```

Note: if you want to ignore the SSL validity issues with curl, you could simply
change the `curl -X [...ARGS]` to `curl -kX [...ARGS]`.

I think I will need to use a legit cert instead. I'll create another zettel to
see if this is the case.

## Tags
#java #spring
