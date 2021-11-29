## Introduction of JavaDoc

Hello World !!

Almost all developers have a better practices to write good comments and understandable variable/method/class name according to code style in order to write clean source code.

For each and every source code developer needs to write documentation so any other developer can understand and use/manage that source code further.

What if I told you that, there is one tool which is generating documentation for source code using comments present in the source code !! - Sounds great right ?

We can use  [JavaDoc](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/javadoc.html) tool to generate documentation from comments present in Java source code. Fortunately, all modern version of the Java JDK provide the JavaDoc tool. So, we don't have to install manually.

# Java Comments 

Let's start with comments in Java.

- Single Line Comment in Java

![carbon.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638167565493/hfBZW2BaT.png)

- Multi-Line Comment in Java

![carbon (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638167646488/bgMjlpsLY.png)

- JavaDoc Comments in Java

![carbon (2).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638167874581/_Bo_31E76.png)


Keep in mind, JavaDoc comments looks very similar to normal multi-line comment, but main difference is extra asterisk (*) at the starting of comment. Also, JavaDoc comments may contain HTML tags as well.


# JavaDoc Comment Format

JavaDoc comment can be placed above any class, field or method which we want to document.

These comments are made up of two section,
1. Description of comment
2. Specific meta-data using standalone block tags marked with `@` symbol 

Standalone tags can be added after the description with the help of `@` at starting of line. Inline tags can be added anywhere and it's surrounded with `{}` `curly brackets`.

We are going to see some of the common block tags for JavaDoc. For more details please visit this  [link](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/javadoc.html).

# JavaDoc Comments at Class Level

To write/understand JavaDoc comments on Class level, please consider below mention example.


![carbon (4).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638172445399/e_HnRBTs_e.png)

As you can see in example, we have given short description first. After description we have used some block tags to add documentation meta-data.

- `{@link}` - Provides an inline link to a particular part of our source code

- `@author` - Name of the author who created particular class, method or field that is commented

- `@version` - Indicated the source code version number

- `@since` - Indicated the version number with which particular class, method or field was added


# JavaDoc Comments at Field Level

We can use a short description without any block tags as shown in below example for any field.

![carbon (5).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638174285672/0jRQo_eY5.png)


# JavaDoc Comments at Method Level

Any method can contain multiple type of JavaDoc block tags. To understand JavaDoc comments at method level please consider below mention example.

![carbon (6).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638175434804/MJirsJYVb.png)

The greetingsJarvis method contains both a description and more then one standalone block tags. Also we have used some HTML tags to write comments.

As you can see in above example, we have used some common block tags describe below

- `@param` - Provides useful description about method's parameter

- `@see` - Provides generated link reference

- `@return` - Provides a description of what a method is going to return 

- `@author` - Name of the author who created particular class, method or field that is commented

- `@version` - Indicated the source code version number

- `@since` - Indicated the version number with which particular class, method or field was added


# JavaDoc Generation using CLI

JavaDoc command line tool is very easy to use. We need to use below mention command to generate documentation using JavaDoc.


> javadoc -version -author -d doc *.java

This command is used when you have more then one separate java file. Here, `-d` flag is going to generate new folder named `doc` if doc folder is not there. Our generated HTML document is going to store in that particular folder. Also, we have used `-version` and `-author` flag respectively to add version and author related information in our documentation. 


> javadoc -d doc src\\*

This command is used when we need to specify particular package to generate JavaDoc documentation.


# JavaDoc Complete Example

In this section we are going to see complete example of using JavaDoc.

Have created one folder called JavaDocEx. In that folder I have created two files named *JavaDocExample.java* and *User.java*.

## JavaDocExample.java 

![carbon (7).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638182594635/nr_l7inKj.png)

## User.java

![carbon (8).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638182670005/IR3_XFhMA.png)

As you can see in above both files, we have added particular JavaDoc comments on particular class, methods and fields.

Now, we are going to generate documentation using JavaDoc command. Please consider below mention image for JavaDoc command execution.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1638182967444/VOyQ1x77Y.png)

As you can see, after running command particular documentation related files is generated in doc folder which we have mentioned in command for saving document related HTML files.

## Source code Output View as HTML

If you open HTML files in browser, you can see source code documentation.

#### All Classes 

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1638183350782/w4woYq0K-.png)

#### JavaDocExample.java Documentation

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1638183426723/C6zaOnc9d.png)

#### User.java Documentation

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1638183520531/nNCYY58K3.png)

#### Hierarchy for all Package

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1638183632471/xPyfLk2OG.png)


# Conclusion

Thank you for reading, I hope you found this article useful.

If you enjoyed reading, please consider following me here on Hashnode and also on  [Twitter](https://twitter.com/Its_SR__)  /  [Github](https://github.com/sahilrajput2223)  /  [LinkedIn](https://www.linkedin.com/in/rajputsahil/).
