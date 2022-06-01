## React Component

Hello World !!

In this blog, we are going to talk about React Components, component types and how can we create one.  


# Overview

To develop any application, any developer spend so much time and write so many lines of code. Earlier, this type of application follows traditional DOM structure and to make any kind of change in this kind of application will take more time as we need to make changes on multiple places.

To overcome this issue, `component-based development` was introduced.

# Component-based development

In component-based development, entire application is divided into logical parts. This logical parts also knows as component and it can be used in whole application many times as per requirement. Every component have their own structure, API calls, methods, design etc.

We can say that - Components are like functions that return React element and describe what and how it's going to render on UI.

# Types of Component

In React, We have two types of component.

1. Class Based Component
2. Functional Component



# Class Based Component

Class based component are nothing but a simple class which are made of multiple/single functions, which are going to add functionality to the application.

To create class based component we need to **`extends  React.Component`**, with the help of this statement we can inherit component methods form React.Component to our component.

Also, this class is going to have **render()** function, which is going to return React element to describe UI part.

Class based component must contain render() method returning JSX.

Class based component also known as Stateful components because they implement logic and state.

### Class Based Component Example

In below image, have mentioned basic example


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654011641792/9xoDHPuEp.png align="left")
 

As you can see, we have extended React.Component from React and added render() function which is going to return H1 tag to show on display.



# Functional Component

Functional component is more common component, simple JavaScript function and will see many times while working in React.

This functions may or may not receive parameter values and return elements to describe UI.

Functional Component is not going to contain render() method.

Functional component is also known as Stateless Component as they just receive data and display them in some form, they are mainly responsible for rendering UI. To make this component Stateful, hooks can be easily used. 

### Functional Component Example

In below image, have mentioned basic example


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654013129864/FevRaIMmZ.png align="left")

As you can see, with this logic we can create Functional Component, which is going to return H1 tag to show on display.

# Conclusion

In today's blog, we talked about React Components, component types and how can we create one. 

Thank you for reading, I hope you found this article useful.

If you enjoyed reading, please consider following me here on [Hashnode](https://sahilrajput.hashnode.dev/) and also you can reach me at [Twitter](https://twitter.com/Its_SR__) / [GitHub](https://github.com/sahilrajput2223) / [LinkedIn](https://www.linkedin.com/in/rajputsahil/).