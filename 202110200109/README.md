# Clients, Servers, and the Web
Understanding the basic concepts of how clients and servers interact will serve
as a benefit in designing, implementing, and troubleshooting your applications.


## Clients and Servers
* When two machines interact to exchange information, one acts as the client and
the other acts as the server
* On the web, the client sends a request to the server which answers with a
response
* When you open a browser and look for a URL (uniform resource locator) such as
google.com, your browser, acting as the client, issues a request to the Google
server. In return, the Google server sends a response containing the HTML, CSS,
and JS that your browser uses to render the web page

Interestingly, in modern applications, clients and servers can be any number of 
devices or computers and sometimes a specific machine may take the role of
client and server simutaneously. For example, if you use an application on your
phone to set the temperature on your smart thermostat, then your phone acts as
the client and the thermostat acts as the server. If your thermostat is also
connected to the internet to retrieve weather information, then the thermostat
is also acting as a client and the computer that has the weather information is
the server.


## HTTP
* HTTP (HyperText Transfer Protocol) is the default protocol by which
information is exchanged (sent and recieved) over the internet.
* the *http://* in front of a web address tells the browser application that you
want to use HTTP protocol to request a given web page.


## TCP/IP, IP Addresses, Ports, and DNS
* Most networks transmit data with the TCP/IP (Transmission Control Protocol / 
Internet Protocol) standard
* TCP/IP is the pathway between clients and servers while HTTP refers to the
format that they use to communicate

When a computer attaches to a network, it needs an identifier so that other
computers may find it; this is often referred to as an IP Address and it comes
as either ***IPV4*** or ***IPV6***.

* IPV4 is the older version of IP Addresses and is a 32-bit number that has 4
segments. One of the public-facing server address for Google is 172.217.4.196
* IPV6 is the newer version of IP Addresses and came about due to the increasing
scarcity of addresses. These addresses are 128 bit which means that there are
2^128 available addresses versus only 2^32 addresses for IPV4
* One of the jobs of the ***router*** is to assign IP Addresses to every device
connected to it so that it can manage sending and recieving (routing) data
between those devices and the outside world
* Ports are like channels for IP Addresses so that they can seperate different
types of traffic for various services. For example, port 80 is one of the
standard ports for unsecured internet traffic, and port 443 is used for secured
(SSL, secured socket layer). If you were to send a request to the Google public
server for a web page, the IP and port could look something like 
**172.217.4.196:443**
* DNS (domain name servers) allow us to alias IP Addresses to friendlier, more
memorable names. When you type Google.com into the browser, a DNS lookup occurs
which routes your request to the proper machine via its IP Address (which is
bound to the domain name, Google.com)


## How a Web Request Works
1. A user types in a URL (uniform resource locator) into their browser; A DNS
lookup occurs and finds the IP Address that is associated with that URL
1. An HTTP GET request message is routed to the server, asking it to send the
data/files associated with that specific URL. The request is ***formatted*** as
HTTP, but is using the TCP/IP protocol.
1. The server recieves the request and forms an HTTP formatted response; there
are many types of responses, but a common one is "200 OK". This response
signifies that the request was successful and all of the HTML, CSS, JS required
to load the webpage are returned to the user.
1. The browser take all the HTML, CSS, and JS files recieved from the server and
assembles it into a visual view for the user to interact with. While the page
is being assembled, the broweser may also perform additional requests for other
page resources (images, music, videos, etc...). Any time your broswer sees
a link to another resource, it will automatically issue an additional GET
request for that resource.
1. At this point, the client and the server close their connection and are no
longer communicating; they do this to save resources.


## Related
[202110200316](../202110200316) - Types in JavaScript


## Tags
#webdev
