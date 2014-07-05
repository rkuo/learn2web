---

title: learn to write web page with AngularJS and Bootstrap
tags:
 
- AngularJS
- Bootstrap

---

As the first step to learn how to write a webpage with AngularJS and Bootstrap.

[TOC]

## References

## Basic

- create an index.html with notepad or textpad.
    - add `<h1>hello</h1>` to file and use Chrome to view the file
- add body of html5
    - use Sublime Text, set file type to html, then use Tools > Snipets > html, save.
    - add title of page, and view in browser, no change on display. 
    
```
<!DOCTYPE html>
<html>
<head>
	<title>hello world</title>
</head>
<body>
	<h1>hello</h1>
</body>
</html>
```
    
## Add AngularJS

- add `ng-app` to `<body>` or `<html>` tag to indicate this will be AngularJS application.

```
<body ng-app>
```

- refresh the browser, there is no change.
- add `{{1+1}}` in `<h1>` tag like `<h1>hello {{1+1}}</h1>`, if you review it in brawser, nothing really happen, you will see `hello {{1+1}}`. This is because the browser does not know how to evaluate `{{1+1}}`, which has been treated as a string.
- We need to supply AngularJS library to help the browser to perform additional functions. We can add the following code in `<head>` section; this tell the browser to load library, `angular.min.js`, from Content Delivery Network. 

```
 <script
 	src="http://ajax.googleapis.com/ajax/libs/angularjs/1.2.17/angular.min.js">
 </script>
```
 
- When we refresh the browser, we will see `hello 2`. 
- ng-app is one of many **directives** in AngularJS; each directive has its own semantics and functions. You can design your own directives too. 
- You can put a expression in `{{}}`; AngularJS evaluate the expression, then put the results in there.

## Data 
There are various way to get data into webpage.

### get from user input
We cab add an input tag to get input from user. `ng-model ` will hold the text value, which may be used in the page.

`
<input type="text" ng-model="name" placeholder="your name">`

`<p>hello, {{ name }}!</p>`	

placeholder will act as part of prompt.

### from ng-init
refer to: http://www.c-sharpcorner.com/UploadFile/cd7c2e/using-ng-init-and-ng-repeat-directive-of-angularjs-in-asp-ne/

- add a initial value by adding `<div ng-init> ... </div>` in the app,

```

```

### from API


## ToDo

embed image ![alt text](https://drive.google.com/uc?id=FILE-ID)