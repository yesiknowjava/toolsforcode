+++
title = "Javascript interview questions with answers"
description = "Growing list of python questions with simple answers"
# image = "images/post/post-2.png"
featuredImage = "/img/javascript-interview-questions.jpg"
tags = ["code"]
categories = ["code"]
date = 2022-08-02T09:46:44.431Z
draft = false
type = "featured"
+++
  
<p></p>
<p></p>

###### What are the advantages of using JSON rather than using xml

JSON is a lightweight format for storing and transferring data. When compared to xml, json files are of lesser size for the same amount of data as it doesnt need the extra tags as required by xml. Also, json is widely used in various languages.
<p></p>

###### Difference between Javascript Object and JSON format
There are 3 fundamental differences between Javascript Object and JSON format. They are

1. Keys should be enclosed in double quotes in JSON, but its not mandatory in javascript objects.
2. Javascript objects can have functions as value, whereas JSON may not contain functions.
3. The last value in a javascript object can have a trailing comma ',', but in JSON its not the case (this is a structural difference only)

<p></p>

###### Difference between var and let

```var``` can be redeclared within {}, but ```let``` cannot be redeclared. 

{{< highlight javascript "hl_lines=2" >}}
var a = "my string";
var a = 5;// Does not throw error

let a = "my string";
let a = 5;// Uncaught SyntaxError: Identifier 'a' has already been declared
{{< / highlight >}}

While ```var``` has function scope, ```let``` has block scope.

{{< highlight javascript "hl_lines=4-6" >}}
for(var i=10; i<20; i++) {
    //do something
}

console.log(i) // prints i as 20

for(let j=10; j<20; j++) {
    //do something
}
console.log(j) //j is not defined error
{{< / highlight >}}

