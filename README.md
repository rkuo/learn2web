---

title: learn to write web page with AngularJS and Bootstrap
tags:
 
- AngularJS
---

As the first step to learn how to write a webpage with AngularJS.

[TOC]

## References
[tool - plnkr](http://plnkr.co/)

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

- add `ng-app` to `<body>` or `<html>` tag to indicate this will be AngularJS application. From [angularJS doc]()Use this directive to auto-bootstrap an AngularJS application. The ngApp directive designates the root element of the application and is typically placed near the root element of the page - e.g. on the <body> or <html> tags.

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
refer to: 
- [ng-repeat car example](http://www.c-sharpcorner.com/UploadFile/cd7c2e/using-ng-init-and-ng-repeat-directive-of-angularjs-in-asp-ne/)

- [ng-repeat doc](https://docs.angularjs.org/api/ng/directive/ngRepeat)

- [ng-repeat friends example with filter](http://stackoverflow.com/questions/22271484/ng-class-in-ng-repeat-conditional-class-names-depending-on-the-item-parameters)

- add a initial value by adding `<div ng-init> ... </div>` and `ng-repeat` and `example-animate-container` 

```
<body>
	<div ng-init="movies = [
	{name:'Big City', date: '2012-10-10'},
	{name:'Godfather', date: '1970-1-1'}
	]">
	<h3> I saw {{movies.length}} of his movies and they are:</h3>
	<ul class="example-animate-container">
		<li class="animate-repeat" ng-repeat="movie in movies">
			[{{$index + 1}}] I saw {{movie.name}} in {{movie.date}}.
		</li>
	</ul>
</div>
</body>

```
It turns out the simple version, without container class, will work. I am sure there is role for the container class. We will use simple version for now. 

```
	<ul>
		<li ng-repeat="movie in movies">
			[{{$index + 1}}] I saw {{movie.name}} in {{movie.date}}.
		</li>
	</ul>
```
I simplified it by removing index field, works.

```
	<ul>
		<li ng-repeat="movie in movies">
			I saw {{movie.name}} in {{movie.date}}.
		</li>
	</ul>
```

In the middle of learning, I found a very well organized tutorial video and code samples. [Introduction to Angular.js in 50 Examples (part 1) - good](https://www.youtube.com/watch?v=TRrL5j3MIvo)
**I switch my learning approach to this tutorial and use plunker too.**




## ToDo
