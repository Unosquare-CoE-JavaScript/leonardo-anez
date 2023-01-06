# Chapter 1: What _Is_ Javascript?

This first part was a little bit tricky because there are some things needed to specify in order to understand what _Javascript_ is.

First, is not related to _Java_. Actually the name is more an artifact of marketing because it was intended to apppeal to Java programmers, plus, the word **script** was very popular back then, so:  

Java + script = _Javascript_ was born

Nowadays the official name of the language is _ECMAScript_. This was specified by the TC39[^1] (_Technical Committee number 39_: TC39 is a group of JavaScript developers, implementers, academics, and more, collaborating with the community to maintain and evolve the definition of JavaScript.) and formalized by the [ECMA](https://www.ecma-international.org/) Standards. Having it's own revision every year, so for example  your browser can be running something like _ECMAScript 2019_ or _ES2019_ for short. 😱

That's why there is some kind of implicit agreement between programmers to call the language _ES20`XX`_ or just _JS_ in order to avoid confusion. 😵

## The Web Rules Everything About (JS)

Javascript is present in many places, from browsers, to servers (_NodeJS_), to robots, IOT, etc... But the one that rules JS is the web.


## Not All (Web) JS…

Not all the features we use in our regular basis are part of the ECMAScript Standard, lets take the following piece of code:

```javascript
alert("Hello, this is an Alert 😺")
```
This line of code displays the following:

![](../assets/images/alert.png)

The `alert(..)` function is not included in the JS specification, but is something present in all web JS environments. That's why diferent environments like browsers or _NodeJS_ add APIs to provide JS programs with environment-specific capabilities. Lets see some examples of these API capabilities:

* [`fetch(..)`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) provides a JavaScript interface for accessing and manipulating parts of the protocol, such as requests and responses.
* [`getCurrentLocation(..)`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition) is used to get the current position of the device.
* [`getUserMedia(..)`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia) prompts the user for permission to use a media input.
* [`fs.write(..)`](https://nodejs.dev/en/learn/writing-files-with-nodejs/) easiest way to write to files in Node.js.

Even the well-known `console.log(..)` and all the `console.*` methods are not specified in JS, but due to it's universal utility is defined in most of the JS environments.

## Paradigms 

This section treats the paradigms within JS. But "What is a paradigm?" Basically is an approach to solve problem using some programming language or also we can say it is a method to solve a problem using tools and techniques that are available to us following some approach. Within a paradigm, there are myriad variations of style and form that distinguish programs, this can include libraries, frameworks, etc... 

Some important categories[^2] are:

* **Procedural**: organizes code in a top-down, linear progression through a pre-determined set of operations, usually collected together in related units called procedures. Examples: _C, Algol_
* **Object-Oriented (OO/classes)**: organizes code by collecting logic and data together into units called classes.  Examples: _Java, C#_
* **Functional (FP)**: organizes code into functions. Examples: _Haskell, Lisp_

Of course there are languages that support more than one code patterns, these are called _«multi-paradigm languages»_. In our case Javascript is on of them.

## Backwards & Forwards

First, we need to keep clear some definitions, those are: _backwards compatibility_ and _forward compatibility_.

* **Backwards compatibility** means that once something is accepted as valid JS, there will not be a future change to the language that causes that code to become invalid JS. This means that code written two or ten years ago should still work today, even code from the 90's should still run today with some issues maybe. All this is made in order to JS developers write code with confidence that it won't stop working out of the blue due to a browser update. 😎

That's why the TC39 is extremely cautious in doing so. They study the impact of those possible changes and browsers ultimately decide to adopt those changes with the cost of breaking a very small amount of sites or comparing if the benefits of the new features improve somehow for many more sites.

* **Forward compatibility** means that including a new addition to the language in a program would not cause that program to break if it were run in an older JS engine.

> **JS is not forwards-compatible** 😳

## Jumping the Gaps

Since JS is not forwards-compatible, it means that there is always the potential for a gap between code that you can write that’s valid JS, and the oldest engine that your site or application needs to support. Let's see an example:

For this example I took the `fromEntries` function which is an _ES2019_ feature the simply converts a list of key-value pairs into an object.​                

```javascript
const fruits = [
    ["apples", 300],
    ["pears", 900],
    ["bananas", 500]
    ];
    
const myObj = Object.fromEntries(fruits);
```
Running this piece of code in _NodeJS 11.0.0_ give us an error whereas running this in the latest version I have on my computer (_18.12.1_) runs without any problem.

```
const myObj = Object.fromEntries(fruits);
                         ^
TypeError: Object.fromEntries is not a function
```

So in order to overcome this the solution is *transpiling*. It's a term to describe using a tool to convert the source code of a program from one form to another (but still as textual source code). Typically, forwards-compatibility problems related to syntax are solved by using a transpiler like _Babel_ to convert from that newer JS syntax version to an equivalent older syntax.

## Filling the Gaps

## Deep Dive Javascript

## Web Assembly (WASM)

## Strict Mode 🤨


[^1]: Ecma International's TC39, [https://tc39.es](https://tc39.es/#:~:text=Ecma%20International's%20TC39%20is%20a,evolve%20the%20definition%20of%20JavaScript.)

[^2]: [OOP vs Functional vs Procedural](https://www.scaler.com/topics/java/oop-vs-functional-vs-procedural/)