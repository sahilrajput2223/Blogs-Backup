## Java -> Spring Boot + MongoDB CRUD APIs


Hello World !!

During this time, so many peoples creating APIs and at the same time so many peoples using that APIs on daily basic.

## Overview 

Today, in this blog we are going to see how to develop REST CRUD APIs using Spring Boot and MongoDB.

We are going to create below mention APIs (methods, urls and action defined in below table)

<table border=2> 
<tr>
<th>Method</th>
<th>Urls</th>
<th>Action</th>
</tr>

<tr>
<td>POST</td>
<td>/api/user/create</td>
<td>Create New User</td>
</tr>

<tr>
<td>GET</td>
<td>/api/user/getAllUser</td>
<td>Get All Users</td>
</tr>

<tr>
<td>GET</td>
<td>/api/user/getUser?id=</td>
<td>Get User By ID</td>
</tr>

<tr>
<td>PUT</td>
<td>/api/user/update</td>
<td>Update User By ID</td>
</tr>

<tr>
<td>DELETE</td>
<td>/api/user/deleteUser?id=</td>
<td>Delete User By ID</td>
</tr>

<tr>
<td>DELETE</td>
<td>/api/user/deleteAllUser</td>
<td>Delete All Users</td>
</tr>
</table>

## Technology
- Java 8
- Spring Boot 
- MongoDB
- Maven 


## Project Structure


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640526914065/WUeA8lOZM.png)

- `User` data model class is same as Entity and table User.
- `UserResponse` class is we are using to create API json response format.
- `UserRepository` is an interface that extends MongoRepository for CRUD methods of MongoDB database. This interface is autowired in Service class, according to CRUD methods.
- `UserService` is a class in which `UserRepository` CRUD methods is used to interact with database and this service class is autowired in `UserController` class.
- `UserController` class is a RestController, which has all the required RESTful method mapping.
- Configuration related to MongoDB is in `application.properties`.


## Create & Setup Spring Boot project

To create spring boot project we can use [Spring Online Tool](https://start.spring.io/) or we can use IDE development tools.

Now, add below mentioned dependency in `pom.xml` file

![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639902778073/nGpHAgNdr.png)

Now, using this dependency we are able to interact with MongoDB. But, First we need to define user/database and port number to connect with MongoDB.

## Configure MongoDB with Spring Boot

To configure, we need to add/define user/database and port in `application.properties` file under `src/main/resource` folder.

![carbon (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639903348518/K-qkS-00T.png)

## Define Data Model

We are going to use Id, userName, userEmail, userPhone fields in our data model named User.

**model/User.java**


![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640527816093/EmtHJlmbaxk.png)


here, `@Document` annotation helps us to define collection name as `user` and `@id` annotation helps use to generate id column as unique.

## Create Repository to interact with MongoDB

In repository package, create UserRepository interface that extends MongoRepository.

**repository/UserRepository.java**



![carbon (3).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640532240653/Rhr7YOa_v.png)


Now, using this interface we can use MongoRepository's methods like save(), findById(), findAll(), deleteById(), deleteAll() etc.

Also, we can define our own methods in this interface to interact with database.


## Create Service to interact with Repository interface

In service package, create UserService class. In that class we are going to auto-wire UserRepository to use methods from that interface.

**service/UserService.java**

![carbon (4).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640534187209/A-iuVdbFd.png)

In this service class we have created some methods to interact with `UserRepository`.

Now, we are going to auto-wire this class in controller so we can use this methods as per our need in REST services.

## Create Spring REST APIs controller

Now, we need to create basic API controller, after that we are going to add logic in each and every API endpoint.

**controller/UserController.java**


![carbon (5).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640534532183/Zp_pY8K5H.png)


Here, we have created some RESTful APIs to work with MongoDB.

### Create User

To handle `POST` `HTTP` request we are using `@PostMapping`.

To create new user we need to call API (`/api/user/create`) using `POST` method with required json data. Internally, we are calling `MongoRepository.save()` method to create new user.


![carbon (6).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640534839125/vpwlX6QhR.png)


### Update User

To handle `PUT` `HTTP` request we are using `@PutMapping`.

To update user we need to call API (`/api/user/update`) using `PUT` method with required json data including id. Here also, internally we are calling `MongoRepository.save()` method to update user information.


![carbon (8).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640535198569/lAkG8JGFW.png)


### Get User Details


To handle `GET` `HTTP` request we are using `@GetMapping`.

To get user details we are going to follow to methods. 


#### Get All User

To get all user details, we need to call API (`/api/user/getAllUser`) using `GET` method.
Internally, we are calling `MongoRepository.findAll()` method.

![carbon (9).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640535684497/MjAJn6nRr.png)

#### Get User By Id 

To get user details by id, we need to call API (`/api/user/getUser`) using `GET` method with `id` as a query parameter.
Internally, we are calling `MongoRepository.findById()` method.

![carbon (10).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640535888090/Toi2_hWpK.png)


### Delete User Details

To handle `DELETE` `HTTP` request we are using `@DeleteMapping`.

To delete user details we are going to follow to methods. 

#### Delete All User

To delete all user details, we need to call API (`/api/user/deleteAllUser`) using `DELETE` method.
Internally, we are calling `MongoRepository.deleteAll()` method.

![carbon (11).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640536047764/hfG5EP9J4.png)

#### Delete User By Id 

To delete user details by id, we need to call API (`/api/user/deleteUser`) using `DELETE` method with `id` as a query parameter.
Internally, we are calling `MongoRepository.deleteById()` method.

![carbon (12).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640536148173/s8E8jEe5M.png)


## Let's Test

Now, run SpringBoot application using with Maven command: `mvn spring-boot:run`.

#### Create Users

Let's Create Some Users:

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640537392478/6KS6ZNFUV.png)

Now, Check MongoDB Database:

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640537551308/SeEgc1Gk0.png)


#### Update User

Let's update user having id: 61c89d6e193b73734f7cec9d

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640537714471/vuG2TeV_q.png)

Now, Check MongoDB Database:

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640537770771/wOCxFj7DT.png)


#### Get All Users 

Let's get all user data:

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640537910419/vjnR6mY2A.png)

#### Get User Details By Id

Let's get user data having id: 61c89d84193b73734f7cec9e

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640538005346/VIDvjMxXd.png)

#### Delete User Details By Id

Let's delete user data having id: 61c89cf0193b73734f7cec9c

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640538092073/872jh8BIZ.png)

Now, Check MongoDB Database:

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640538150531/4k2j4rxKB.png)

#### Delete All Users 

Let's delete all user data:

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640538247390/OiJf886vO.png)

Now, Check MongoDB Database:

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640538316034/kjNoWeuVU.png)

## Conclusion

In today's blog, we have seen how to develop RESTful APIs using SpringBoot and MongoDB.

Thank you for reading, I hope you found this article useful.

If you enjoyed reading, please consider following me here on Hashnode and also on  [Twitter](https://twitter.com/Its_SR__)  /  [GitHub ](https://github.com/sahilrajput2223) /  [LinkedIn](https://www.linkedin.com/in/rajputsahil/) .

