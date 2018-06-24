## Implement an efficient sort Algorithm . What is it’s complexity ?
Quick-sort has O(n^2) worst-case runtime and O(n log n) average case runtime and it is also in-place . 

Quick sort is widely considered as the de-facto algorithm for sort.

## What is event Bubbling and capturing in JavaScript.
Event bubbling and capturing are two ways of event propagation in the HTML DOM API. When an event occurs in an element inside another element, and both elements have registered a handle for that event, the event propagation mode determines in which order the elements receive the event.

With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.

With capturing, the event is first captured by the outermost element and propagated to the inner elements.
Using addEventListener with last argument true is only the way to catch the event at capturing .

## Explain Promise. What purpose it’s solving and how it’s different from callback ?
Promise helps us avoid nested call back functions (resulting in incomprehensible code) when there are multiple async function calls are dependent of each other’s returned value .

It has 3 states: pending, fulfilled and rejected

## Difference between Function Call and Apply in javaScript.
Apply lets you invoke the function with arguments as an array; call requires the parameters be listed explicitly. 
A useful mnemonic is “A for array and C for comma.”

## What is the low level difference between Slice and Splice methods.
Splice is a mutating function , it modifies the array itself, and slice is non-mutating it creates a new array and returns that.

## How will you sort an array containing just [1.11, 0.2, 3, 11] in ascending order.
JavaScript `sort` does lexical sorting , so it’s converting the numbers to string before sorting . We need to pass a custom method to sort.

```
[1.11, 0.2, 3, 11].sort(function(a, b){
 return (a — b);
});
```

## What's the difference between a variable that is: null, undefined or undeclared?

A variable is undeclared when it does not use the var keyword. It gets created on the global object (that is, the window), thus it operates in a different space as the declared variables.

### undefined

Something is undefined when it hasn’t been defined yet. If you call a variable or function without having actually created it yet the parser will give you an not defined error.

Example:
```
1
2
3
4
5
var undefinedVariable; // undefined
typeof undefinedVariable; // "undefined"

undefinedFunction(); // undefined
typeof undefinedFunction; // "undefined"
```
Note that the typeof returns "undefined", therefore undefined is a primitive type.

The fix for an undefined variable or function is easy, simply define it:
```
1
2
3
4
5
6
7
var definedVariable = 'test';
typeof definedVariable; // "string"

function definedFunction(){
  return "I'm defined!"
}
typeof definedFunction // "function"
```
You can know if a variable is undefined with the following:
```
1
2
3
4
5
if (typeof(variable) !== "undefined") {
  console.log('variable is not undefined');
} else {
  console.log('variable is undefined');
}

```
Finally we'll finish up with null.

null is a variable that is defined to have a null value.
```
1
2
var nullVariable = null; // null
typeof nullVariable // "object"
```
You probably don’t often purposefully define a variable to null, but it may be the return value of a function. Often you'll need to gaurd against null values in your code.

You can know if a variable is null with the following:
```
1
2
3
4
5
if( variable === null ) {
  console.log('variable is null');
} else {
  console.log('variable is not null');
}
```

I think the order “undeclared, undefined, and null” makes sense since it’s increasing order of certainty.

undeclared variables don’t even exist
undefined variables exist, but don’t have anything assigned to them
null variables exist and have null assigned to them

## Can you describe the main difference between a forEach loop and a .map() loop and why you would pick one versus the other?

*map* : map transforms each item in the array and returns a new array of transformed items with same size as that of old array.

e.g. Say you have an array of integers and want to construct an array that contains the square value of the items. You will use map in this case.
```
var squared = [1,2,3,4].map(function(num){
  return Math.pow(num,2);
});

console.log(squared); // 1,4, 9, 16
```

*forEach*h : If you just want to iterate over the items in an array and do something with the items you need to use forEach . A

## What's a typical use case for anonymous functions?

Whenever you need a function that would get executed when a specific action is triggered.

Anonymous functions are just that simple, nameless functions that don't mean anything to you without the action they are bound to.

In a typical situation you wouldn't call an anonymous function yourself, other code would have to execute it. Take the example of a click event handler. If you bind an anonymous function to the click event of a button, and that button submits a form, you wouldn't normally want to call the function unless the button has been clicked. This is when you would use an anonymous function instead of a named function.

##  Difference between: function Person(){}, var person = Person(), and var person = new Person()?

There are different ways (not to be exact) we can use functions in JavaScript, but with the given code below highlights important differences on how functions work.

```function Person() {}```
### Function Declaration
Code above declares a function statement (statements perform an action) but does not execute, however, it does get registered into the global namespace.

```var person = Person()```
$$$ Function Expression
A variable ‘var person’ has been defined and contains a value reference to a Person function. Any JavaScript Expressions (including Function Expressions) always returns a value. This may also be an Anonymous function if no name has been assign to a function but wrapped in parenthesis to be interpreted as an expression.

```var person = new Person()```
### Function Constructor
By adding the keyword ‘new’. We are instantiating a new object of the Person class constructor. A function declaration is just a regular function unless it has been instantiated, it then becomes a class constructor.

## What is AJAX?

AJAX = Asynchronous JavaScript And XML.
AJAX allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

It can:
- Update a web page without reloading the page

- Request data from a server - after the page has loaded

- Receive data from a server - after the page has loaded

- Send data to a server - in the background

## What is the difference between classical inheritance and prototypal inheritance?
#### Class Inheritance: 

instances inherit from classes (like a blueprint — a description of the class), and create sub-class relationships: hierarchical class taxonomies. Instances are typically instantiated via constructor functions with the `new` keyword. Class inheritance may or may not use the `class` keyword from ES6.

#### Prototypal Inheritance: 
instances inherit directly from other objects. Instances are typically instantiated via factory functions or `Object.create()`. Instances may be composed from many different objects, allowing for easy selective inheritance.

## What does “favor object composition over class inheritance” mean?
This is a quote from “Design Patterns: Elements of Reusable Object-Oriented Software”. It means that code reuse should be achieved by assembling smaller units of functionality into new objects instead of inheriting from classes and creating object taxonomies.

In other words, use can-do, has-a, or uses-a relationships instead of is-a relationships.

## What are two-way data binding and one-way data flow, and how are they different?
Two way data binding means that UI fields are bound to model data dynamically such that when a UI field changes, the model data changes with it and vice-versa.

One way data flow means that the model is the single source of truth. Changes in the UI trigger messages that signal user intent to the model (or “store” in React). Only the model has the access to change the app’s state. The effect is that data always flows in a single direction, which makes it easier to understand.

One way data flows are deterministic, whereas two-way binding can cause side-effects which are harder to follow and understand.

## What are the pros and cons of monolithic vs microservice architectures?
A monolithic architecture means that your app is written as one cohesive unit of code whose components are designed to work together, sharing the same memory space and resources.

A microservice architecture means that your app is made up of lots of smaller, independent applications capable of running in their own memory space and scaling independently from each other across potentially many separate machines.

Monolithic Pros: The major advantage of the monolithic architecture is that most apps typically have a large number of cross-cutting concerns, such as logging, rate limiting, and security features such audit trails and DOS protection.

When everything is running through the same app, it’s easy to hook up components to those cross-cutting concerns.

There can also be performance advantages, since shared-memory access is faster than inter-process communication (IPC).

Monolithic cons: Monolithic app services tend to get tightly coupled and entangled as the application evolves, making it difficult to isolate services for purposes such as independent scaling or code maintainability.

Monolithic architectures are also much harder to understand, because there may be dependencies, side-effects, and magic which are not obvious when you’re looking at a particular service or controller.

Microservice pros: Microservice architectures are typically better organized, since each microservice has a very specific job, and is not concerned with the jobs of other components. Decoupled services are also easier to recompose and reconfigure to serve the purposes of different apps (for example, serving both the web clients and public API).

They can also have performance advantages depending on how they’re organized because it’s possible to isolate hot services and scale them independent of the rest of the app.

Microservice cons: As you’re building a new microservice architecture, you’re likely to discover lots of cross-cutting concerns that you did not anticipate at design time. A monolithic app could establish shared magic helpers or middleware to handle such cross-cutting concerns without much effort.

In a microservice architecture, you’ll either need to incur the overhead of separate modules for each cross-cutting concern, or encapsulate cross-cutting concerns in another service layer that all traffic gets routed through.

Eventually, even monolthic architectures tend to route traffic through an outer service layer for cross-cutting concerns, but with a monolithic architecture, it’s possible to delay the cost of that work until the project is much more mature.

Microservices are frequently deployed on their own virtual machines or containers, causing a proliferation of VM wrangling work. These tasks are frequently automated with container fleet management tools.

## What is asynchronous programming, and why is it important in JavaScript?
Synchronous programming means that, barring conditionals and function calls, code is executed sequentially from top-to-bottom, blocking on long-running tasks such as network requests and disk I/O.

Asynchronous programming means that the engine runs in an event loop. When a blocking operation is needed, the request is started, and the code keeps running without blocking for the result. When the response is ready, an interrupt is fired, which causes an event handler to be run, where the control flow continues. In this way, a single program thread can handle many concurrent operations.

User interfaces are asynchronous by nature, and spend most of their time waiting for user input to interrupt the event loop and trigger event handlers.

Node is asynchronous by default, meaning that the server works in much the same way, waiting in a loop for a network request, and accepting more incoming requests while the first one is being handled.

This is important in JavaScript, because it is a very natural fit for user interface code, and very beneficial to performance on the server.


