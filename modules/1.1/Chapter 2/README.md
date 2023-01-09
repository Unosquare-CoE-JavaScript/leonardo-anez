# Chapter 2: Surveying JS 

## Each File is a Program

Technically speaking in JS, each file is its own separate program. The main reason for this is error handling, one file may fail and that will not necessarily prevent the next file from being processed.

## Values

Values come in two forms in JS: **primitive** and **object**.

### Strings
---

Let's begin with ways to print strings 😱, we can use `""`, `''` and finally ``. We're going to asume the is a variable called `firstName='Leo'`:

```javascript
console.log("My name is ${ firstName }."); // My name is ${ firstName }.
console.log('My name is ${ firstName }.'); // My name is ${ firstName }.
console.log(`My name is ${ firstName }.`); // My name is Leo.
```

The last example is called **interpolation**.

### Booleans and Numbers
---
Well..., what can I say, the only thing interesting about this section is that JS has a _bigint_. LoL



### `null` and `undefined`
---

Both values serve the purpose of indicating emptiness (or absence) of a value. It’s safest and best to use only undefined as the single empty value, even though null seems attractive in that it’s shorter to type.

### Symbol
---

Special-purpose value that behaves as a hidden unguessable value. Symbols are almost exclusively used as special keys on objects.

```javascript
Symbol("Gordon Freeman")
```

They’re mostly used in low-level code such as in libraries and frameworks.

## Arrays And Objects

This is an array:

```javascript
names = [ "Frank", "Kyle", "Peter", "Susan" ];
```
Thanks for you attention.

<details>
  <summary>Nah, there is more</summary>
    JS arrays can hold any value type, either primitive or object (including other arrays).
</details>

And this is an `object`:

```javascript
name = {
    first: "Gordon", 
    last: "Freeman", 
    age: 27, 
    specialties: ["JS", "Scientist"]
}; 
console.log(`My name is ${name.first}.`);
```

## Value Type Determination

There is an operator called `typeof` that tells you its built-in type, if primitive, or "object" otherwise:

```javascript
typeof 42;                  // "number"
typeof "abc";               // "string"
typeof true;                // "boolean"
typeof undefined;           // "undefined"
typeof null;                // "object"
typeof { "a": 1 };          // "object"
typeof [1,2,3];             // "object"
typeof function hello(){};  // "function"
```

Intersting to highlight:

> `typeof null` unfortunately returns `"object"` instead of the expected `"null"`. Also, `typeof` returns the specific `"function"` for functions, but not the expected `"array"` for arrays. 🤯

Converting from one value type to another, such as from string to number, is referred to in JS as **“coercion.”**

## Declaring and Using Variables

`var` and `let` statement: 

```javascript
var name = "Gordon";
let lastname = "Freeman"
```
But, what is the difference between them?

## Functions

## Comparisons

### Coercive Comparisons