---
title: ES6: Top features you should know
date: 2019-01-23T00:00:00.000Z
layout: post
tags:
  - javascript
categories:
  - code
published: false
---

## Const & Let

For example:

```javascript
const name = "Ben"
let age = 24

for(let i = 0; i < 10; i++){

}
```

## Template literals

Before:

```javascript
function tag(str1, str2, name, age){
  console.log(str1 + ' ' + name + '\n' + str2 + ' ' + age + '\n');
}
tag("My name is", "I am", "Ben", "24")
```

After:

```javascript
const name = "Ben"
let age = 24

function tag(str, name, age){
  return '${str[0]} ${name} ${str[1]} ${age}'
}
```

## Native Modules

Before:

```javascript
var myModule = require("myModule");
var foo = myModule.foo;
```

After:

```javascript
import { myModule as module, foo} from "myModule";
```

## Spread (...)

```javascript
const arr = [1, 2];
const arr2 = [5, 6];
const arr3 = [...arr, ..arr2];
console.log(arr3)
// [1, 2, 5, 6]
```

## Classes

```javascript
class Person {
  constructor (name){
    this.name = name;
  }

  sayHello(){
    console.log("some thing");
  }
}

class Child extends Person{
  constructor (name){
    super(name);
  }
}
```

## Arrow Functions

Before:

```javascript
var addNumbers = function(a, b){
  return a + b;
}
```

After:

```javascript
const addNumbers = （a,b) => {
  return a+b;
}
```

or

```javascript
const addNumbers = ((a,b) => a+b)
```
