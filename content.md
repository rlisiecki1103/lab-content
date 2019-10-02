# Getting Started with NodeJs


![NodeJs](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/1200px-Node.js_logo.svg.png)
## What is NodeJs?

NodeJs is a lightweight framework for executing JavaScript. JavaScript is commonly used for front end browser applications but can also be used as a backend service!

## Why Node.Js?
Because its awesome!! And because why not? 

>[!knowledge] NodeJs is a nice lightweight approach to programming, with the power of JavaScript.

====

## Getting Started

To your left, you will notice visual studio code with several code files. This is a fully functional NodeJS application. VSCode is easy to use and light weight. From here you can run and debug your program! Debugging can help you find problems and even inspect the value of a variable. In this section, you will learn how to use a debugger and run a NodeJS application

Setting a breakpoint is easy.

!IMAGE[Breakpoint1.gif](Breakpoint1.gif)

This allows you to stop a program while its running to check values. This is very useful to inspect a variable or see what logic path your application has taken.

## Debugging

Next you will get started with debugging. You will see how to set a break point and run the program in debug mode! 

!IMAGE[debug1.gif](debug1.gif)

>[!knowledge] You can add  breakpoint to any line of code

## Running The Application

The application in front of you is a fully functional application. It serves a web page that you can access from your browser. Follow the steps below to run the program past the breakpoints.

!IMAGE[d2.gif](d2.gif)

Now click [Here to launch the site](@lab.Container(code-server).ExposedPort(3000).Address). This is running from your code.

If the page does not load, make sure your application is running. If it is not, then you can click the green play button again. 
Now press the stop button on the debug toolbar in the top middle of the screen.

====
# Writing Code

Now that you know how to debug your application, we will add in some code. This application is setup as a basic web service, to provide data to other applications over the internet. 

NodeJS starts from the app.js file, since it is listed as our launch.json file under "Program"

!IMAGE[60b2mqg6.jpg](60b2mqg6.jpg)

If the app.js code file is renamed, the value in the launch.json should be modified as well, to ensure that the application starts at the correct entry point when debugging starts.

## Routes
This node.js application uses routes to ensure that a specific function is run when any user navigates to a url relative to the applications root (@lab.Container(code-server).ExposedPort(3000).Address). There are already several routes available to see as an example. For this section, a new route will be added to display text. 

1. Right click on the routes folder and select "New File"
2. Name the file "learning-route.js"
3. Paste the following code into the new file:
```Javascript
var express = require('express');
var router = express.Router();

router.get('/', function(req, res, next) {
    res.send('');
    res.end;
});

module.exports = router;
```
4. Open app.js and type the following code to line 4:
```Javascript-nocode
var learningRouter = require('./routes/learning-route');
```
5. On line 16 add the following to register your route:
```Javascript-nocode
app.use('/learn', learningRouter);
```
>[!hint] This will register the router on a sub path "learn"

6. Now go back to learning-route.js and notice the empty path in line 4.
!IMAGE[u0x2iehp.jpg](u0x2iehp.jpg)

The empty string with nothing but the slash is the next part of the path that we will use to access our web page. In the App.Js file, we registered our router with a path of "learn" so navigating to the site and "/learn will run the code in our new function. Now we will add some code to see when we run the application.

## Adding Route Code
1. Open learning-route.js
1. Add the word "Hello World" to the string on line 4 !IMAGE[izzjs0hm.jpg](izzjs0hm.jpg)
1. Now go to the debug panel and press Play
1. Navigate to [@lab.Container(code-server).ExposedPort(3000).Address/learn](http://@lab.Container(code-server).ExposedPort(3000).Address/learn)

Congrats! You have added your first route!

====
# Going Further
You can change the route in the app.js file to match whatever you like. This allows you to make a custom URL and manage endpoints! Try sending object data, strings, and even HTML. 

Make a new endpoint and send data to the client. You can send HTML the same way the hello world message was sent to the browser. Try an Img html tag, or bold tag!

You now know the basics, but it is important to experiment. Experimentation will help explore possibilities and where change can be made. If you break the lab, simply relaunch. 

====
# Save your work!

Want to save your work to a github repository?

Repository: @lab.TextBox(Repo)

Username: @lab.TextBox(User)

Password: @lab.TextBox(Pass)


@lab.Activity(SaveWork)
====

# Test Time!

Open LabCode.js
Modify the user endpoint to respond with a generated email address. The email address will be, the first name, the users age, and the domain name. Run application debugging and test your work below.

@lab.Activity(Automated2)

====
# notes



