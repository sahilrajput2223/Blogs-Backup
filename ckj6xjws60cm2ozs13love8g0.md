## APIs & Different types of HTTP Status Codes

Hello world !

During this time almost everyone is connected using APIs. Some of them are developing it, some consuming it in any way and some are developing and consuming both.

APIs give response using HTTP status codes and response body. With the help of this status codes we can understand status of API output and get information about it.

In this Blog, What is **APIs and Different types of HTTP Status Codes**.

**Things covered in this blog,**

```
1. Whats is APIs?
2. Different types of HTTP Status Codes.
``` 

**Let's get started with details,**

What is APIs ?

As per Definition, 

> API is the acronym for Application Programming Interface, which is a software intermediary that allows two applications to talk to each other.


There are two types of APIs.
1. REST APIs
2. SOAP APIs

 [REST API](https://en.wikipedia.org/wiki/Representational_state_transfer)  (also known as RESTful API) is an application programming interface (API or web API) that conforms to the constraints of REST architectural style and allows for interaction with RESTful web services. REST stands for `representational state transfer`. It returns data to receiver in `json format`.

 [SOAP](https://en.wikipedia.org/wiki/SOAP)  stands for `Simple Object Access Protocol`. It's a messaging protocol for interchanging data in a decentralized and distributed environment. SOAP can work with any application layer protocol, such as HTTP, SMTP, TCP, or UDP. It returns data to the receiver in `XML format`.

### Different types of HTTP Status Codes

Status codes are issued by a server in response to a client's request made to the server. It includes codes from  [IETF](https://www.ietf.org/) [Request for Comments](https://en.wikipedia.org/wiki/Request_for_Comments)  (RFCs), other specifications, and some additional codes used in some common applications of the HTTP.

All HTTP response status codes are separated into five classes or categories. 
The first digit of the status code defines the class of response, while the last two digits do not have any classifying or categorization role. 

-  [1xx - Informational response](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#1xx_informational_response)  
-  [2xx - Successful](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#2xx_success)  
-  [3xx - Redirection](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#3xx_redirection) 
-  [4xx - Client error](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_client_errors) 
-  [5xx - Server error](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#5xx_server_errors) 

### In detail for 1xx (Information response),

1xx means request received and continuing process.

- **100 (continue)** - This response means everything is OK so far and client should continue the request, or ignore if the request already made.


- ** 101 (Switching Protocol)** - This code is sent in response to an Upgrade request header from the client, and indicates the protocol the server is switching to.

- **102 (Processing)** - This response indicates that server received request and processing this request, but no response is made to client or sender.

- **103 (Early Hints)** - This status code mostly used with  link headers, which can capable to let user preload resource while the server preparing the response.

### In detail for 2xx (Successful),

2xx means request  was received by server, understood, and accepted.

- **200 (OK)** - The request has succeeded. The meaning of the success depends on the HTTP method.


1. `GET` - The requested resource fetched successfully and transmitted in response body.
2. `POST` or `PUT` - The given resource in request is modified or added at server side.
3.  `HEAD`  - The header resource fetched successfully and transmitted to client or receiver. 
4. `TRACE` - The message body contains the request message as received by the server. 


- **201 (Created)** - The request has succeeded and new resource is created according to request. This response is sent to client after POST request, or sometime in PUT request.

- **202 (Accepted)** - The request is received but not yet acted upon. It is intended for cases where another process or server handling the request, or in case of batch processing.

- **203 (Non-Authoritative Information)** - This response code means the returned meta-information is not exactly same as available on origin server, but it's collected from a local or a third-party copy. Mostly used in mirrors and backup resources.

- **204 (No Content)** - This response code means, there is no content to send for any particular request, but header can be useful.

- **205 (Reset Content)** - This response code,  tells the user-agent(client) to reset the document which sent this request.

- **206 (Partial Content)** - This response code is used when the `Range` header is sent from user-agent to request only some part of a particular resource.   

- **207 (Multi-Status)** - This response code used when we need to convey information about multiple resources, where multiple status codes can be appropriate to use.

- **208 (Already Reported)** - Used inside a `<dav:propstat>` response element to avoid repeatedly enumerating the internal members of multiple bindings to the same collection

- **226 (IM Used)** - This response  code  means, the server has fulfilled a `GET` request for resource and the response is a collection or combination of the result of one or more instatus/manipulations applied to the current instance.

### In detail for 3xx (Redirection),

3xx means further action needs to be taken in order to complete the request.

- **300 (Multiple Choice)** - This response code means, the request has more than one possible response and user-agent (client) needs to choose any one of them.

- **301 (Moved Permanently)** - This response code means, requested URL or resource is moved permanently on new location and new URL or resource location is given in response.

- **302 (Found)** - This response code means, the requested URL of resource has been moved temporarily. 

- **303 (See Other)** - This  response code means, the server direct the client to get requested resource at another URI with GET request.

- **304 (Not Modified)** - This is used for catching purpose. This tells the client that response has not been modified, so the client can continues to use same cached version of response.  

- **307 (Temporary Redirect)** - The server sends this response to direct the user-agent to get the requested resource from some other URL without changing it's method.

- **308 (Permanent Redirect)** - This response code means, resource permanently located at new URL, which specified by `Location:` HTTP response header and same method used as used in previous request.  

### In detail for 4xx (Client error),

4xx means the request contains bad syntax or cannot be fulfilled.

- **400 (Bad Request)** - The server could not understand the request due to invalid syntax.

- **401 (Unauthorized)** - This response code means, user needs to authenticate  itself to get/access requested information or response.

- **402 (Payment Required)** - This response code is reserved for future use. Initial aim for creating this code was using it in digital payment system, but this status  code is used very rarely and have no standard conventions exists.

- **403 (Forbidden)** - When client does not have rights to access to particular response or content, then server gives 403 status code as response. Unlike 401, the client's identity is known to server.

- **404 (Not Found)** - This response code means, server unable to find requested resource. Or in case of browser, this means the URL is not recognized or not correct.

- **405 (Method Not Allowed)** - The request method is known by server but it has been disabled for that endpoint/API and cannot be used. We can only use specified methods for particular endpoint/API. 

- **406 (Not Acceptable)** - This response code means, web server unable to find any content that conforms to the criteria given by the user agent, after performing  [server-driven content negotiation](https://en.wikipedia.org/wiki/Content_negotiation#Server-driven) . 

- **407 (Proxy Authentication Required)** - This response code is similar to 401, but authentication is needed to be done by a PROXY.

- **408 (Request Timeout)** - This response code is sent on idle connection by some servers, even without any previous request by client. It means that server would like to shut down this unused connection. Also note that some servers shut down the connection without sending this message.

- **409 (Conflict)** - This response is sent to client when request conflicts with the current stats of the server.

- **410 (Gone)** - This response code means, requested resource is permanently deleted from server.

- **411 (Length Required)** - This response code means, server required `Content-Length` header and it's not present is client request.

- **412 (Precondition Failed)** - This response code means, client has indicated some preconditions in its headers which the server does not meet.

- **413 (Payload Too Large)** - This response code means, request entity is larger than limits defined by server. The server might close the connection or return an `Retry-After` header field.

- **414 (URI Too Long)** - This response code means, the URI requested by client is longer then server willing to interpret.

- **415 (Unsupported Media Type)** - The media format of the requested data is not supported by server, so the server rejected the request and give 415 response code.

- **416 (Range Not Satisfiable)** - When the range specified by the `Range` header field in the request can't be fulfilled.

- **417 (Expectation Failed)** - This response code means, the expectation made by the `Expect` request header field can't meet by the server.

- **418 (I'm a teapot)** - The server refuses the attempt to brew coffee with a teapot.  

- **421 (Misdirected Request)** - This response code means, request was directed at a server but the server is not able to produce a response because the server is not configured to produces response for that particular combination specified in requested URI. 

- **422 (Unprocessable Entity)** - This response code means, the request was well-formed but it was unable to be followed due to semantic errors.

- **423 (Locked)** - This response code means, the requested resource is being being accessed is locked.

- **424 (Failed Dependency)** - This response code means, the request failed due to failure of a previous request.

- **425 (Too Early)** - This response code means, the server is unwilling to risk processing a request that might be replayed.

- **426 (Upgrade Required)** - When the server refuses the request with the current given protocol, but might willing to do so after the user-agent upgrades to different protocol. In this case server sends an `Upgrade` header in a 426 response to indicate required protocols.

- **428 (Precondition Required)** - When the origin server requires the request to be conditional.

- **429 (Too Many Request)** - When the user has sent too many requests in a given amount of time ( [`rate limiting`](https://en.wikipedia.org/wiki/Rate_limiting)), then server sends 429 response code.

- **431  (Request Header Fields Too Large)** - When the server is unwilling to process the request because its header fields are too large for server. That time server send 431 response status code.

- **451 (Unavailable For Legal Reasons)** - This response code means, the requested resource cannot legally be provided, such as a web page censored by a government.  

### In detail for 5xx (Server error), 

5xx means  the server failed to fulfil an apparently valid request.

- **500 (Internal Server Error)** - This response code means, server has encountered a situation it doesn't know how to handle.

- **501 (Not Implemented)** - This response code means, the request method is not supported by the server and cannot be handled.

- **502 (Bad Gateway)** - This error response means, server while working as gateway to get a response needed to handle the request, got an invalid response.

- **503 (Service Unavailable)** - This response means, server is not ready to handle the request. Common cause are a server that is down for maintenance or server is overloaded.

- **504 (Gateway Timeout)** - This error response is given when the server is acting as a gateway and cannot get a response in time.

- **505 (HTTP Version Not Supported)** - This response code means, HTTP version defined in request is not supported by the server.

- **506 (Variant Also Negotiates)** - This response code indicates an internal server configuration error in which the chosen  variant is itself configured to engage in content negotiation, so is not a proper negotiation endpoint.

- **507 (Insufficient Storages)** - This response code means, the server unable to perform specified method on resource because server is unable to store the needed details to successfully complete the request.

- **508 (Loop Detected)** - When the server detected an infinite loop while processing the request, then server sends 508 response code to client.

- **510 (Not Extended)** - Further extensions to the request are required for the server to fulfil it.

- **511 (Network Authentication Required)** - This response code means, user-agent (client) needs to authenticate to gain network access.



Thank you for reading, You can connect me on  [Twitter](https://twitter.com/sahil__2223)  /  [LinkedIn ](https://www.linkedin.com/in/rajputsahil/) /  [Github](https://github.com/sahilrajput2223)  .