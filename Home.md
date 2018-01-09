Welcome to the Angular-JS-Basics wiki!

* ->directives

* ->expression

* ->filters

* ->modules

* ->controllers

 

* angularjs:

* events

* dom

* form

* input

* validation

* http

*  

* ng-app

* ng-model

* ng-bind

* ng-init

 

* ->ng-app="";

* ->"ng-init='firstname'='john'";

* angular expression: {{ }}

 

## angularjs applications:

* ->modules

* ->controllers

 

## function using controller:

 

`<div ng-app="myapp" mg-controller="myctrl">`

`<script>`

`var app=angular.module('myapp',[]);            //app -name`

`app.controller('myctrl',function($scope)){     //function-name`

`$.scope.firstname="John";`

`$.scope.lastname="doe";`

`});`

`</script>`

 

 

## creating module:

 

`var app=angular.module('myapp',[]); `

 

## controller:

 

`app.controller('myctrl',function($scope)){  `

 

## Directives:

 

`<div ng-app="Myapp" w3-test-directive></div>`

 

`app.directive("w3TestDirective",function()){`

`return{`

`template:"I was made in directive!"`

`};`

`});`

 

 

## moduels and controller in  a file:

 

`<script src="myApp.js"></script> ` //contains an application module

`<script src="myCtrl.js"></script>` // contains the controller

 

## myapp.js

 

* var app=angular.module("myapp",[]);

 

## myctrl:

 

`app.controller("myctrl",function($scope){`

`$scope.firstname="sandy",`

`$scope.lastname="Doe";`

`});`

 

 

## 4)Directives:

* ->built-in directives which offers functionality

* ng-app   -initializes an Angularjs

* ng-init  -application data

* ng-model -binds the value of HTML controls(input,select,textarea)

 

* ng-app=====start

* ng-init====itital var|value

* ng-model===id

* ng-repeat===foreach

 

## 5)ng-model:

 

* ->binds the value of the HTML(input,select,textarea)

* ->type validation->number,email,required

* ->status of application -> invalid,dirty,touched,error

* ->css classes for html

* ->bind html to html forms

*  

## ng-repeat:

 

* <div ng-app="" ng-init="names=['sand','hehe','kai']">

* <ul>

* <li ng-repeat=" x in names">

* {{ x }}

* </li>

* </ul>

* </div>

*  

## ng-repeat act as array of object:

 

->cloens html element

 

`<div ng-app="" ng-init="names=[`

`{names:'javi',country:'norway'},`

`{names:'hege',country:'swedem'}]">`

 

`<ul>`

`<li ng-repeat="x in names">`

`{{ x.name + ',' + x.country }}`

`</li>`

`</ul>`

 

## 5.5)creating an new directive:

 

`<w3-test-directive></w3-test-directive>`

 

`var app=angular.module("myapp",[]);`

 

`app.directives("w3TestDirective",function()){`

`return:`

`template:"<h1>Made by a directive!</h1>"`

`};`

`});`

 

## ->creating a new directive camelcase

## ->accessing directive use sepereated name: w3-test-directive

 

## legal directives:

 

## EACM:

* ELEMENT NAME,ATTRIBUTE,CLASS,COMMENT

 

## ng-model:

 

->bind the value of an input field to a variable

 

 

->TWO way binding:

 

`<div ng-app="myapp" ng-controllet="myctrl">`

`Name:<input ng-model="name">`

`<h1> YOU Entered : {{ name }} </h1>`

`</div>`

 

## `validate user INput:`

 

`<form ng-app="" name="myForm">`

## Email:

`<input type="email" name="myAddress" ng-model="text">`

`<span ng-show="myForm.myAddress.$error.email">not a valid</email>`

`</form>`

 

## number validate:

 

`<input type="number" name="myAddress" ng-model="text">`

`<span ng-show="myForm.myAddress.$error.number">`

 

ng-model in css:

 

<style>

input.hg-invalid{

backgorund-color:lightblue;

}

</style>

 

`<form ng-app="" name="myform">`

` Enter your name:`

`<input name="myName" ng-model="myText" required>`

 `</form>`

 

## Data-binding between model and view:

 

## ng-model:

* ->directive to bind data from the model to the view  on HTML controls

 

## 6)Controllers:

 

## controllers control the data

 

## ng-controller:

 

`<div ng-app="myApp" ng-controller="myctrl">`

`firstname:< input type="text" ng-model="firstname">`

`lastname:<input type="text" ng-model="Lastname">`

`<br>`

`full name:{{ firstname + "" + lastname }}`

 

## controller in external page:

 

`<script src="person.js"></script>`

 

## person.js:

 

`angular.module('myApp',[]).controller('personCtrl',function($scope)){`

 

`$scope.names=[`

`{ name:'sandy',country:'norway'},`

`{ name:'hege',country:'sweden'},`

`{ name: 'Kai',country: 'Denwark'}`

`];`

`});`

 

 

`<li ng-repeat="x in names">`

    `{{ x.name + ', ' + x.country }}`

  `</li>`

 

 

## 7)scopes:

 

* ->binding part between html(view) and javascript(controller)

* ->available between view and controller

 

* view->html

* model->data available for the current view

* controller->javascript->makes/changes/removes/controls

 

## RootScope:

->$rootscope

`var app=angular.module('myapp',[]);`

`app.run(function($rootScope) {`

    `$rootScope.color = 'blue';`

`});`

 

 

## -->filters:

 

* filter can be added in AngularJS to format Data.

 

## AngularJS filters:

 

## ## ## currency ->format a number to a currency format

## ## ## date     ->Format a date to a specified format

## ## ## filter   ->subset of items from an array

## ## ## json     ->format an object to a json format

## ## ## limitTo   ->limits an array/string

## ## ## lowercase->strng to lower cae

## ## ## number   ->format a number to a string

## ## ## orderBy  ->orders an array by an expression

## ## ## uppercase->Format a string to uppercase

 

 

## uppercase:

 

`{{ lastName | uppercase }}`

 

## lowercase:

 

## {{ lastName | lowercase }}

 

## currency:

 

`Price: {{ price | currency }}   ----> price:8.00`

 

## filter:

 

`ng-repeat="x in names | filter : 'i'">`

 

`<P><input type="text" ng-model="test"></p>`

`<li ng-repeat="x in names | filter : test">    //ng-model="test"`

 

* ## filter--->uupercase,lowercase,currency,orderby

 

## 8)ANGULARJS SERVICES:

 

* ->make your own service | use one of the built-in services

 

## 30 built-in services:

 

$location:

 

## 9)AngularJS $HTTP:

 

-* >$HTTP SERVICES makes a request to the server and resturns a response.

 

## method:

*  

* .delete()

* .get()

* .head()

* .jsonp()

* .patch()

* .post()

* .put()

 

## properties:

 

* ->config ->used to generate request

* data->  carrying the response

* headers ->get header information

* status  ->HTTP  status

* statusText ->string defnining the HTTP status

 

## 9)angularJS Tables:

 

`<div ng-app="myAPP" ng-controllet="customerCtrl">`

 

`<table>`

`<tr ng-repeat="x in names">`

`<td> {{ x.Name }} </td>`

`<td> {{ x.Country }} </td>`

`</tr>`

`</table>`

 

`<Script>`

 

$http.get("customer.php")

.then

 

## 11)ng-include:

 

`<div ng-include="'myFile.htm'"></div>`

 

## 12)animtaion:

##  

## ng-show

## ng-hide

## ng-class

## ng-view

## ng-include

## ng-repeat

## ng-if

## ng-switch

 

## 13)anglar API:

 

* angular.lowercase()

* angular.uppercase()

* angular.isString()

* angular.isNUmber()

 

`<script>`

`var app=angular.module('myApp',[]);`

`app.controller('myCtrl',function($scope){`

`$scope.x1="JOHN";`

`$scope.x2=angular.isString($scope.x1);    //`

`});`

`</script>`

 

* //$scope.x2=angular.uppercase($scope.x1);    //uppercase

* //$scope.x2=angular.lowercase($scope.x1);    //lowercase

* //$scope.x2=angular.isNumber($scope.x1);    //true | false
