# JavaScript Primitive Data Types and Objects

## Objectives
+ Explain what a primitive data type is
+ Explain what an object is
+ Create a primitive data type
+ Create an object
+ Explain why to use the literal constructor over the new constructor

While JavaScript shares a lot of the same data types with Ruby, it does handle them a little bit differently.

In Ruby, every data type is an object. A string (whether it's made with the literal constructor or `String.new`) is considered an instance of the String class. Also in Ruby, every object is mutable, which means you can change the object with methods like `upcase` and `swapcase`.

In JavaScript, data types fall into two categories: **primitive data types** and **objects** and they behave very differently.

All primitive types are immutable (values incapable of being changed), while objects are mutable. Primitive values are important for application performance. They are way faster for an application to process than objects.

## Primitive Data Types

JavaScript has six primitive data types: 

+ Number
+ String
+ Boolean
+ Undefined
+ Null
+ Symbol

Primitive values are created using the literal constructor for each data type. 

```js
var name = "joe";
typeof name;
// returns "string"

var cents = 99;
typeof cents;
// returns "number"

var truth = true;
typeof truth;
// returns "boolean"
```

## Objects

In JavaScript, objects can be seen as a collection of properties. You can think of them as most similar to Ruby hashes but with the superpower of storing functions as values in addition to the standard strings, numbers, etc.

Objects are created using the New constructor:

```js
var word = new String("hello");
typeof word;
//returns "object"

word;
//returns String {0: "h", 1: "e", 2: "l", 3: "l", 4: "o", length: 5, [[PrimitiveValue]]: "hello"}

var num = new Number(10);
typeof num;
//returns "object"
num;
//returns Number {[[PrimitiveValue]]: 10}
```
Because objects are mutable, you can use convenience methods to mutate these values. We'll get more into String convenience methods later, but just know they exist and can be done to any string object.

## Mutating Numbers and Strings

So we know we can modify objects but not primitive data types. But that's not entirely true. Let's take a string created with the literal constructor as an example:

```js
var word = "hello";
typeof word;
//returns "string"


word.toUpperCase();
// returns "HELLO"
```

But wait, I thought primitive values, like the one we just created, were immutable? That's because JavaScript gives you the ability to treat primitive values like objects. In the example above, behind the scenes, JavaScript turns the primitive value into an object, mutates the object, and turns it back into a primitive value.

Given the following code:

```js
  var greeting = "hello";
  var word = new String("hello");
  word === greeting; 
  // returns false
```

The `===` is a type comparison operator. This means that it checks not just value, but data type. If the value and the data type don't match, it returns false. Using the type comparison operator, `greeting` and `word` are not the same type (one is a primitive value and the other an object) so we wouldn't expect them to be equal. But you can use convenience methods to manipulate both in the same way.

Because of this, you want to use the literal constructor as much as possible. For all intents and purposes, you can use the literal constructor and the new constructor in same way, but your code will process much more quickly with the literal constructor.

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/js-primitive-data-types-and-objects' title='JavaScript Primitive Data Types and Objects'>JavaScript Primitive Data Types and Objects</a> on Learn.co and start learning to code for free.</p>
