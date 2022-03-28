## Java --> Spring Boot + MongoDB API With Pagination

Hello World !!

In my last blog, we have seen how to develop REST CRUD APIs using Spring Boot and MongoDB. [BLOG LINK](https://sahilrajput.hashnode.dev/java-spring-boot-mongodb-crud-apis)

In that blog, we have created some APIs like create, update, delete and get data from database.

# Overview

Now consider one scenario, if we have low amount of data then we can fetch all data at the same time we can display that data on UI part. But, if we have large amount of data and if we try to show all that data at same time in UI then it will create mess on UI part. Also, at the same time APIs and database is also going to take little more time to process that data and give response.

To solve this issue, we can use `pagination` concept in API.

# What Is Pagination ?

Pagination is a concept of dividing the results into discrete batches and return a single page at a time as an API response.

# Technology

- Java 8
- Spring Boot
- MongoDB
- Maven

# Project Structure

![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648490209638/j0lpdrpzq.png)

Till now, we have created project and some basic APIs developed. If you need to re-visit that topics please follow [this link.](https://sahilrajput.hashnode.dev/java-spring-boot-mongodb-crud-apis)

Now, we are going to modify our code and going to add new API endpoint with pagination logic.

# Controller Modification

Now, we need to create new API endpoint named `/api/user/get`.

**controller/UserController.java**


![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648487979289/JkdTx0cGj.png)

Here, we have created new `GET` method endpoint named `/api/user/get` to handle pagination request.

# Service Modification

Now, we have created controller endpoint, we need to add respected service layer modification for pagination which is mentioned in below service class code snippet.  

**service/UserService.java**


![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648488204313/JbjbmD96G.png)

Here, we are calling `findAll()` with from JPA Repository with `pageable` request.

With the help of pageable we are going to get user data from database with pagination and if we pass different pages and sizes then this pageable request is going to manage and generating response with the help of dynamic page and size.

To generate user response and add `totalCount`, `totalPage`, `page`, `size` and list of user we have generated new response class named `UserPaginationResponse`.

# User Response Class

In this class, we are going to set user response with page details and generating API response for consumer.

**model/UserPaginationResponse.java**


![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648488900220/goszgs2sL.png)

# Let's Test

Now, run SpringBoot application using with Maven command: `mvn spring-boot:run`.

#### Get All User (With Pagination)


![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648489089022/8YncaJl3l.png)
 
As you can see in above postman image, we can pass page and size details (highlighted in yellow) as per our need to get API response accordingly.

**API Response,**

![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648489293764/9h2H0hqwt.png)

here in API response, you can see that we have added `totalPage` and `totalCount` related details with some other page related details (`page - current page`, `size - current page size`). 

So, we can identify that how many times we need to call particular pagination API.

# Conclusion

In today's blog, we have seen how to develop RESTful API using SpringBoot and MongoDB with the help of Pagination Concept.

Thank you for reading, I hope you found this article useful.

If you enjoyed reading, please consider following me here on Hashnode and also on [Twitter](https://twitter.com/Its_SR__) / [GitHub](https://github.com/sahilrajput2223) / [LinkedIn](https://www.linkedin.com/in/rajputsahil/) .
 