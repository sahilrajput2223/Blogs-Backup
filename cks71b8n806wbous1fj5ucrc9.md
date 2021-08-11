## Digital Clock Using JavaScript

Hello World,

In this article, we will see how we can develop Digital Clock using JavaScript. We are going to see how can we set Hours, Minutes and Seconds with AM/PM logic in html page using JavaScript.

Let's get started,


## Prerequisite

- Basic knowledge of HTML
- Basic knowledge of CSS
- Basic knowledge of JavaScript 

## Time to code!

To create digital clock, we need to create three files. One is **HTML**(DigitalClock.html), second is **CSS**(DigitalClock.css) and third one is **JavaScript**(DigitalClock.js) file.

## HTML code

DigitalClock.html


```
<!DOCTYPE html> 
<html>
    <head>
        <meta  charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=ed">
        <title>Digital Clock</title>
	    <!--to link external css file-->
        <link rel="stylesheet" href="DigitalClock.css">
    </head>
    <body>
        <!--to show time -->
        <div id="DigitalClock">
        </div>
	    <!--to link external JavaScript file-->
        <script src="DigitalClock.js"></script>
    </body>
</html>

``` 

## CSS code

DigitalClock.css


```
body{
    font-family:  sans-serif;
    background-image: linear-gradient(45deg, #5a6168, #345264);
    padding: 0;
    min-height: 100vh;
    margin: 0;
    position: relative;
}

#DigitalClock{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    color: #00f5f5;
    font-size: 7em;
    background-color: transparent;
    font-family: Arial;
    word-break: none;
    padding: 20px auto;
    text-shadow: 0px 0px 50px;
}
``` 

## JavaScript code

This is the main section for our digital clock. 

For, JavaScript file code we will step by step.

**Step 1**:- Create one function `showTime()`.


```
function showTime()
{
  /*code to update time*/
}

``` 

**Step 2**:- Inside `showTime()` function, create a object of Date class. With the help of ate class object we can get current time data like Hour, Minutes, Second etc.


```

function showTime(){

    /*creating object of Date class*/
    var date = new Date();

    /*to fetch current hours*/
    var hour = date.getHours();

    /*to fetch current minutes*/
    var minute = date.getMinutes();

    /*to fetch current seconds*/
    var secound = date.getSeconds();
}

``` 

**Step 3**:- The Date object works on `24-Hours` format, so we have to convert it in `12-Hours` format and also according to that AM/PM is going to change.


```
    var AM_PM = "AM";

    if(hour == 12){
        AM_PM = "PM";
    }

    if(hour == 0){
        hour  = 12;
        AM_PM = "AM";
    }
   
    if(hour > 12){
        hour  -= 12;
        AM_PM = "PM";
    }

``` 

**Step 4**:- Retrieved Hours, Minutes and  Seconds is in 2-Digit. But, it will display as 1-Digit in case of less then 10. We need to add 0 before data so it will show as 2-Digit format.


```
    hour = hour  < 10 ? "0" + hour : hour;
    minute = minute < 10 ? "0" + minute : minute;
    secound = secound < 10 ? "0" + secound : secound;

``` 

**Step 5**:- Now, our time created with 2-Digit format, we need to create time string which is going to display. To do that we need to use `string concatenation`. Also, at last we are adding AM/PM accordingly. 


```
    var time = hour + ":" + minute  + ":" + secound + " " + AM_PM;

``` 

**Step 6**:- Now our time string is ready. We need to show this in `div` which is we made in `html` file. For that, we need to obtain the `div` using `document.getElementById` method and add our time string as a content of div using `innerHTML` property.


```
    document.getElementById("DigitalClock").innerHTML = time;

``` 

**Step 7**:- We have created showTime(), but we have to call this function after every one second. For that we are going to us `setTimeout()`.



```
    setTimeout(showTime, 1000);

``` 

After every 1 second setTimeOut() is going to call showTime() and it will update time on our html page.

**Step 8**:- We need to call showTime() at the end of showTime function, so it will call while reloading page and it will initiate the digital clock.

```
    showTime();

```

## Complete JavaScript Code

DigitalClock.js

```
function showTime(){
    /*creating object of Date class*/
    var date = new Date();
    /*to fetch current hours*/
    var hour = date.getHours();
    /*to fetch current minutes*/
    var minute = date.getMinutes();
    /*to fetch current seconds*/
    var seconds= date.getSeconds();
    var AM_PM = "AM";
    if(hour  == 12){
        AM_PM = "PM";
    } 
    if(hour  == 0){
        hour  = 12;
        AM_PM = "AM";
    } 
    if(hour  > 12){
        hour  -= 12;
        AM_PM = "PM";
    }  
    hour = hour  < 10 ? "0" + hour : hour;
    minute = minute < 10 ? "0" + minute : minute;
    secound = secound < 10 ? "0" + secound : secound;
    var time = hour + ":" + minute  + ":" + secound + " " + AM_PM;

    document.getElementById("DigitalClock").innerHTML = time;
    setTimeout(showTime, 1000);
}   

showTime();

```
 Great, we have created Digital Clock using JavaScript. It will look something like this!.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628601675300/Hoe850oZK.png)



Thank you for reading, You can connect me on  [Twitter ](https://twitter.com/Its_SR__) /  [LinkedIn](https://www.linkedin.com/in/rajputsahil/)  /  [Github ](https://github.com/sahilrajput2223) .


