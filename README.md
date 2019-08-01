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


Question 4 - 

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

Question 5 -

What is the significance, and what are the benefits, of including 'use strict' at the beginning of a JavaScript source file?

```js
    /*
    
    Makes debugging easier - Code errors that would otherwise have been ignored or would have failed silently will now generate errors or throw exceptions,
    
    Prevents accidental globals - Without strict mode, assigning a value to an undeclared variable automatically creates a global variable with that name. This is one of the most common errors in JavaScript. In strict mode, attempting to do so throws an error.
    
    Eliminates this coercion - Without strict mode, a reference to a this value of null or undefined is automatically coerced to the global. This can cause many headfakes and pull-out-your-hair kind of bugs. In strict mode, referencing a a this value of null or undefined throws an error.
    
    Disallows duplicate parameter values - Strict mode throws an error when it detects a duplicate named argument for a function (e.g., function foo(val1, val2, val1){}), thereby catching what is almost certainly a bug in your code that you might otherwise have wasted lots of time tracking down.
    
    Throws error on invalid usage of delete - The delete operator (used to remove properties from objects) cannot be used on non-configurable properties of the object. Non-strict code will fail silently when an attempt is made to delete a non-configurable property, whereas strict mode will throw an error in such a case.
    
    
    */

```

Question 6 - 

Consider the two functions below. Will they both return the same thing? Why or why not?

```js
    
function foo1()
{
  return {
      bar: "hello"
  };
}

function foo2()
{
  return
  {
      bar: "hello"
  };
}

```

[JS BIN](https://jsbin.com/tajimor/1/edit?js,console)


Question 7 - 

What is NaN? What is its type? How can you reliably test if a value is equal to NaN?

```js
    
/* 

The NaN property represents a value that is “not a number”. This special value results from an operation that could not be performed either because one of the operands was non-numeric (e.g., "abc" / 4), or because the result of the operation is non-numeric.

While this seems straightforward enough, there are a couple of somewhat surprising characteristics of NaN that can result in hair-pulling bugs if one is not aware of them.

For one thing, although NaN means “not a number”, its type is, believe it or not, Number:

*/

console.log(typeof NaN === "number");  // logs "true"

/*

Additionally, NaN compared to anything – even itself! – is false:

*/

console.log(NaN === NaN);  // logs "false"

/*

A semi-reliable way to test whether a number is equal to NaN is with the built-in function isNaN(), but even using isNaN() is an imperfect solution.

A better solution would either be to use value !== value, which would only produce true if the value is equal to NaN. Also, ES6 offers a new Number.isNaN() function, which is a different and more reliable than the old global isNaN() function.

*/


```

Question 8 - 

What will the code below output? Explain your answer.

```js
    
    console.log(0.1 + 0.2);
    console.log(0.1 + 0.2 == 0.3);
    
```

[JS BIN](https://jsbin.com/tepiguj/1/edit?js,console)

Question 9 -

In what order will the numbers 1-4 be logged to the console when the code below is executed? Why?

```js
    
    (function() {
        console.log(1); 
        setTimeout(function(){console.log(2)}, 1000); 
        setTimeout(function(){console.log(3)}, 0); 
        console.log(4);
    })();

```

[JS BIN](https://jsbin.com/boyuruw/1/edit?js,console)


Question 10 - 

Write a simple function (less than 160 characters) that returns a boolean indicating whether or not a string is a palindrome.

[JS BIN](https://jsbin.com/edit?js,console)

Question 11 -

Write a sum method which will work properly when invoked using either syntax below.

```js
    
    console.log(sum(2,3));   // Outputs 5
    console.log(sum(2)(3));  // Outputs 5

```

[JS BIN](https://jsbin.com/piwuvog/3/edit?js,console)


Question 12 -

Consider the following code snippet:

```js
    
for (var i = 0; i < 5; i++) {
  var btn = document.createElement('button');
  btn.appendChild(document.createTextNode('Button ' + i));
  btn.addEventListener('click', function(){ console.log(i); });
  document.body.appendChild(btn);
}

```

(a) What gets logged to the console when the user clicks on “Button 4” and why?

(b) Provide one or more alternate implementations that will work as expected.


[JS BIN](https://jsbin.com/gupecin/1/edit?js,console)


Question 13 - 

Assuming d is an “empty” object in scope, say:

```js 
    var d = {};
  
```

…what is accomplished using the following code?

```js
    [ 'zebra', 'horse' ].forEach(function(k) {
	d[k] = undefined;
});

```

```js
    /*
        The snippet of code shown above sets two properties on the object d. Ideally, any lookup performed on a JavaScript             object with an unset key evaluates to undefined. But running this code marks those properties as “own properties” of           the object.

        This is a useful strategy for ensuring that an object has a given set of properties. Passing this object to                   Object.keys will return an array with those set keys as well (even if their values are undefined).
    
    */

```

Question 14 -

What will the code below output to the console and why?

```js
	var arr1 = "john".split('');
	var arr2 = arr1.reverse();
	var arr3 = "jones".split('');
	arr2.push(arr3);
	console.log("array 1: length=" + arr1.length + " last=" + arr1.slice(-1));
	console.log("array 2: length=" + arr2.length + " last=" + arr2.slice(-1));

```
[JS BIN](https://jsbin.com/fejulit/edit?js,console)

Question 15 -

What will the code below output to the console and why ?

```js
	
	console.log(1 +  "2" + "2");
	console.log(1 +  +"2" + "2");
	console.log(1 +  -"1" + "2");
	console.log(+"1" +  "1" + "2");
	console.log( "A" - "B" + "2");
	console.log( "A" - "B" + 2);

```

[JS BIN](https://jsbin.com/cucaqay/1/edit?js,console)





