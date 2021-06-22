# AJAX

```javascript
    let xhr = new XMLHttpRequest();
    
```

# Data Structures

## Maps

- One advantages of maps over objects is that the key can be of any type, not just a string.

- If order matters, maps often trump objects.

- On the other hand, no literal syntax

- Cannot have methods on maps

# Events

## Event Targets

- An event target is the element that the even is being called on, for example, the button that's being clicked

- The first argument passed to a callback function by an event will always be that event, regardless of what it's called.

- `event.target`: what got clicked, `event.currentTarget`: what fired the even listener

- Propagation or 'event bubbling' is when an event 'bubbles' up and is "heard" by parent event listeners

- Propagation is stopped by `event.stopPropagation()`

- Setting `capture: true` on the options object on `addEventListener` allows you to capture other events

# DOM

- The `document` encompasses everything between the opening and closing `html` tags.

- When single `querySelector` is used and there are multiple instances of that element, it will grab only the first one.

## Nodes vs Elements




# Functions

- When there is a standalone function ala:

```javascript
function sodaMachine() {
    console.log("here's your soda");
}
```
- That is a function statement. 

- Functions assigned to variables are function expressions.

# The Hard Parts

## JS Principles

- JavaScript does two things at it's most basic level:
    1) Goes through written code line by line, and executes those lines, the *thread of execution*
    2) Saves data (primitives an data structures) in memory

- The execution context of code is comprised of it's: a) Thread of execution and b) memory

- JavaScript utilizes the call stack to keep track of it's thread of execution.

- The global execution context is always at the bottom of the call stack


- Because functions in JavaScript are first-class "citizens" (Objects), we can utilize the sort of flexible behavior seen in techniques like higher-order functions, that include:

    - They can be assigned to variables and as properties of other objects

    - They can be passed as arguments into other functions

    - They can be returned as values from other functions

- Parameter = label, argument = what's being labelled

## Closures

- The most esoteric of JavaScript concepts?

- Enables powerful pro-level functions like 'once' or 'memoize'

- Many JS patterns (such as the module pattern) utilize closures

- It enables you to build iterators, handle partial application, and maintain state in an async world.

- When functions are declared, they get a hidden property that refers to the lexical scope of where they were declared.

- Think about the 'backpack of data' that passes throughout scopes

- That backpack is the C.O.V.E: Closed Over Variable Environment

- JavaScript is lexically (aka static) scoped

- Kyle Simpson defines a closure as:

> "Closure is observed when a function uses variable(s) from outer scope(s) even while running in a scope where those variable(s) wouldn't be accessible."

- Closure can improve efficiency by allowing a function instance to remember previously determined information instead of having to compute it each time.

- Closure can improve code readability, bounding scope-exposure by encapsulating variable(s) inside function instances, while still making sure the information in those variables is accessible for future use. The resultant narrower, more specialized function instances are cleaner to interact with, since the preserved information doesn't need to be passed in every invocation.

## Errors

- A TypeError indicates an illegal operation with a value.

- A ReferenceError indicates a value that can't be found or doesn't exist.

## Hoisting

- Variables declared with the `var` keyword are hoisted, that is, their declaration is moved to the top of the scope it's declared in

- This happens with functions as well, but NOT function expressions: `var doink = () => console.log('doink');`

## Asynchronous JavaScript

JavaScript is:

-Single-threaded, meaning that one command runs at a time

-Synchronously executed (each line is run in order that the code appears)

-The simplest explanation of the event loop is this: if there is any synchronous code on the call stack waiting to be run, 
asynchronous code such as a function wrapped in setTimeout will not run until the sync code (including that in the global context) is cleared

ES5 Web Browser APIs with callbacks are: 

-Very explicit once you understand how they work under the hood!

-.....But the response data is only available in callback form, and it's odd to think about a function to run much faster once it's passed into another function

-Not the cleanest for error handling

## Promises

-Promises utilize a two-pronged approach: 1) Sets up a network request to browser features, 2) returns a placeholder object (the actual Promise)

-The Promise object contains two properties: a value, and an onFulfillment field.
    -Value contains the value that the promise is fetching (like JSON data from an API endpoint)
    -the onFulfillment properties executes code passed to it by the `.then()` method.

-Old school async browser code is queued in the callback queue (called the task queue in the specs). Async code returned by Promises is queued in
the microtask queue

-Items in the microtask queue are prioritized over the microtask queue

### Advantages

-Nice error-handling process

-Cleaner, more readable style with psuedo-synchronous code

### Disadvantages

-Vast majority of developers have no idea how they work under the hood, and bomb technical interviews & have a tough time debugging code as a result.

## Classes and Prototypes

-One of the beautiful things about objects is that they can store data and functionality in one place

-

# The Hard Parts of OOP

# The Hard Parts of Servers & Node.js

# Hard Parts: Functional JS Foundations

# The New Hard Parts

# YDKJSY

## Scope and Closures

## Chapter 1

- When it comes to target (aka LHS) and source (aka RHS), how do we distinguish between them? If a variable has a 
  value that has been (or is being) assigned to it, it's a `target`. Otherwise, it's a `source`.







