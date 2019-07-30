# JS-Essential-Interview ★
Essential JS Interview Questions, that will come handy durning JS Interviews. 👋

> Here JS BIN Comprises of code snippets, of the following Questions, along with explanation as comments. 📖

Question 1 - 
What is a potential pitfall with using typeof bar === "object" to determine if bar is an object? How can this pitfall be avoided?

[JS BIN](https://jsbin.com/qeyenuh/edit?js,console).


Question 2 -
What will the code below output to the console and why?

```js (function(){
var a = b = 3;
})();

console.log("a defined? " + (typeof a !== 'undefined'));
console.log("b defined? " + (typeof b !== 'undefined'));
```
[JS BIN](https://jsbin.com/qacaruh/edit?js,console).

Question 3 - 

What will the code below output to the console and why?

```js

var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();

```

[JS BIN](https://jsbin.com/xaxefud/1/edit?js,console)

What is the significance of, and reason for, wrapping the entire content of a JavaScript source file in a function block?

```js
  /*
    This is an increasingly common practice, employed by many popular JavaScript libraries (jQuery, Node.js, etc.). This  
    technique creates a closure around the entire contents of the file which, perhaps most importantly, creates a private 
    namespace and thereby helps avoid potential name clashes between different JavaScript modules and libraries.


    Another feature of this technique is to allow for an easily referenceable (presumably shorter) alias for a global 
    variable. This is often used, for example, in jQuery plugins. jQuery allows you to disable the $ reference to the jQuery 
    namespace, using jQuery.noConflict(). If this has been done, your code can still use $ employing this closure technique, 
    as follows:

(function($) { jQuery plugin code referencing $ } )(jQuery);
  
  */

```
