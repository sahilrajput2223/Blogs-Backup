## Find IP Address of any URL using Java

Hello World !

In this virtual world,  [IP address ](https://en.wikipedia.org/wiki/IP_address) helps in connecting our computer to other devices on our network in whole world and even in outer space.

In this blog article, we will learn about what is ip address and how to **Find IP Address of any URL using Java**.


**Things covered in this Blog**
```
1. What is IP Address ?
2. How to find IP Address of any URL using Java ?
``` 

Let' get started with details,

**What Is IP Address ?**

As per definition, 


> An Internet Protocol address (IP address) is a numerical label assigned to each device connected to a  [computer network](https://en.wikipedia.org/wiki/Computer_network)  that uses the  [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol)  for communication.

**There is two type of IP Address,**

1.  IPV4
2. IPV6

In Internet Protocol version 4( [IPV4](https://en.wikipedia.org/wiki/IPv4) ) protocol IP address define as a 32-bit number. But in case of IPV4 there is constrain on available IP addresses. So, new version of IP( [IPV6](https://en.wikipedia.org/wiki/IPv6) ) was standardized in 1998. In case of IPV6 protocol IP address define as a 128-bit number. 

Example of IPV4 IP: `192.168.43.31`

Example of IPV6 IP: `2402:8100:39ae:5352:acba:7dba:6e8b:4d43`

**Time to do some Coding !**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1608378237974/Rz2MGmame.png)

To fetch Hostname and IP address of URl we need to use two Java classes.

```
import java.net.InetAddress;
``` 
The InetAddress class represents an IP address, both IPv4 and IPv6. This class doesn’t have public constructors, so you create a new instance by using one of its factory methods and get your things done.

```
import java.net.URL;
``` 
The URL class is works as a gateway to any of the resource available on the internet. A Class URL represents a Uniform Resource Locator, which is a pointer to a `resource` in this virtual world.

we can import both this class using java `import` keyword.

after that, in line 9

```
String url = "https://sahilrajput.hashnode.dev/";	
``` 
we have to mention for which URL we want to find Hostname and IP address.

then, in line 13

```
InetAddress ip = InetAddress.getByName(new URL(url).getHost());
``` 
using URL class, url instance from the String representation generated and with the help of factory method of InetAddress we can find hostname and ip of that url.

for that we need to use `InetAddress.getByName()` factory method.

then, in line 15
```
 System.out.println("Hostname/IP address : " + ip);
``` 
Hostname and IP address is displayed on screen.

**output is,**

```
Hostname/IP address : sahilrajput.hashnode.dev/139.59.77.163
``` 
using this steps you can find hostname and IP address of any url using Java.

Thank you for reading, You can connect me on  [Twitter](https://twitter.com/sahil__2223)  /  [LinkedIn](https://www.linkedin.com/in/rajputsahil/)  /  [Github](https://github.com/sahilrajput2223) .


























