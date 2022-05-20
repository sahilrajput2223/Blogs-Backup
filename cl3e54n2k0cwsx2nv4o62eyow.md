## Java -> Spring Boot - Interceptor

Hello World !!

In my previous blogs, we have seen how to implement APIs using Java Spring boot with MongoDB. Also, we have added pagination for that data too.

Blog details is as mentioned below,

1. [Java -> Spring Boot + MongoDB CRUD APIs](https://sahilrajput.hashnode.dev/java-spring-boot-mongodb-crud-apis)
2. [Java -> Spring Boot + MongoDB API With Pagination](https://sahilrajput.hashnode.dev/java-greater-spring-boot-mongodb-api-with-pagination)


# Overview

Now, we are going to see the concept of [Spring Boot - Interceptor](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/servlet/HandlerInterceptor.html) and how we can use it with our code.


# What is Spring Boot - Interceptor ?

We can say that, spring boot Interceptor concept is similar to Servlet Filter, Spring Boot  Interceptor is only applied to requests which are sending to controller.

We can use to do such things as writing logs, adding request/response details in database, modifying/updating/adding request or response headers, modifying configuration and much more as per our requirement.   


In this Blog, we are going to use Spring Boot Interceptor for log writing.


# Technology

- Java 8
- Spring Boot
- MongoDB
- Maven

# Project Structure


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652985809320/qqtnbay7x.png align="left")

# Create & Setup Spring Boot project

To create spring boot project we can use [Spring Online Tool](https://start.spring.io/) or we can use IDE development tools.




# Basic Configuration for Spring Boot Interceptor

To work with interceptor, we need to create one `@Component` class (for us, named: `UserInterceptor.java`) which is going to implements `HandlerInterceptor` interface from `org.springframework.web.servlet.HandlerInterceptor`.

**interceptor/UserInterceptor.java**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652976181104/BaE35vCn5.png align="left")


Now, we are going to override three methods from `HandlerInterceptor` interceptor as shown in below code,

**interceptor/UserInterceptor.java**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652976211080/EAcHM_N-E.png align="left")


Now, we have created our interceptor. But, in order to use this interceptor, firstly we need to register this interceptor in `InterceptorRegistry` by using `WebMvcConfigurer`. 

To register interceptor, we have created new `Config.java` class, which is going to implements `WebMvcConfigurer`.

Now, we need to  override `addInterceptors()` method and register our interceptor as shown in below code,

**config/Config.java**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652977959665/bblVUjOzp.png align="left")

Till now, we have created User Interceptor, override some methods from `HandlerInterceptor` interceptor and register that interceptor in `InterceptorRegistry`.

So, now one question is what is this specific three overridden methods and how that methods can be useful for us ?

# HandlerInterceptor Methods 

As we can see, there are total three overridden methods and details as mentioned below.

1. **preHandle()** method - This This is used to perform operations `before sending the request to the controller`. This method should return true to return the response to the client.

2. **preHandle()** method - This is used to perform operations `before sending the response to the client`.

3. **afterCompletion()** method - This is used to perform operations `after completing the request and response`.

#  HandlerInterceptor Methods Modification for Log Generation

First, we need to create `logger variable to log data`, as mentioned below,  

**interceptor/UserInterceptor.java**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652984600692/jMWQcBfNd.png align="left")

Now, we are going to modify our specific methods to generate logs at specific time.

## preHandle() Modification

First, we are going to modify `preHandle()` method to write logs before sending request to the controller.

**interceptor/UserInterceptor.java**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652978824062/WBIublYWS.png align="left")

We have added, `logger.info()`  to log Request URL and Request Method details.


Now, we have created some APIs before ([in this blog](https://sahilrajput.hashnode.dev/java-spring-boot-mongodb-crud-apis)). From that APIs, we are going to use some APIs to check our interceptor logic.

let's say, we have called `/api/user/getAllUser` API with `GET` method, at that time out log will be, 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652986063218/RiExJ6pSh.png align="left")


as we can see, we are getting logs with request url and request methods before sending request to the controller.


## postHandle() Modification

Now, we are going to modify `postHandle()` method to write logs before sending response to the client.

**interceptor/UserInterceptor.java**



![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652981276356/eLmMP71zJ.png align="left")

We have added, `logger.info()`  to log Request URL and Response status code related details.

Now, again we are going to call `/api/user/getAllUser` API with `GET` method, at that time out log will be, 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652986002020/L3XGnXklt.png align="left")

as we can see, we are getting logs with request url and response status code before sending response to the client.


## afterCompletion() Modification

Now, we are going to modify `afterCompletion()` method to write logs after completing the request and response.

**interceptor/UserInterceptor.java**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652982125938/Z9OVyjkCe.png align="left")

We have added, `logger.info()`  to log Request Object and Response Object details.

Now, again we are going to call `/api/user/getAllUser` API with `GET` method, at that time out log will be, 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652982275703/sctHVYdSp.png align="left")

as we can see, we are getting logs with request object and response object before sending response to the client.


# Calculate API Response Time

Now, let's say we want to log our API response time using interceptor, then 

First, we need to set current time attribute in `preHandle` with current time value as a `startTime`.

Now, we need to get  `startTime` attribute in `afterCompletion()` method and need to subtract it from current time (`endTime`). With this we are able to get API response time.

Modified `UserInterceptor.java` file as mentioned below,

**interceptor/UserInterceptor.java**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652983715112/GdGBOC6z-.png align="left")
  
Now, again we are going to call `/api/user/getAllUser` API with `GET` method, at that time out log will be, 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652983503334/2FH63j_bj.png align="left")

as we can see, we are getting logs with request object and response object before sending response to the client at that time we are also getting execution/response time in log.

# Conclusion

In today's blog, we have seen what is Spring Boot - Interceptor and how it can be useful for us.

We have seen, how we can log data with the help of Spring Boot - Interceptor and also we have seen How can we calculate API response/execution time using it.

Thank you for reading, I hope you found this article useful.

If you enjoyed reading, please consider following me here on [Hashnode](https://sahilrajput.hashnode.dev/) and also you can reach me at [Twitter](https://twitter.com/Its_SR__) / [GitHub](https://github.com/sahilrajput2223) / [LinkedIn](https://www.linkedin.com/in/rajputsahil/).





 





 