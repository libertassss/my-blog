+++
title='数据类型&判断'
date='2024-08-29'
+++

## 1、js基础数据类型有哪些
    1、 boolean
    2、 string
    3、 number
    4、 undefined
    5、 null
    6、 symbol
    7、 object
  
## 2、数据类型判断
### typeof
    console.log(typeof "hello"); // "string"
    console.log(typeof 42); // "number"
    console.log(typeof true); // "boolean"
    console.log(typeof undefined); // "undefined"
    console.log(typeof null); // "object" (这是一个特殊情况)
    console.log(typeof {a: 1}); // "object"
    console.log(typeof [1, 2, 3]); // "object" (数组也是对象)
    console.log(typeof function(){}); // "function"

### instanceof
    console.log([] instanceof Array); // true
    console.log({} instanceof Object); // true
    console.log(function(){} instanceof Function); // true
    console.log(new Date() instanceof Date); // true
    console.log([] instanceof Object); // true (因为数组是对象)

### Array.isArray()
    // Array.isArray() 用来判断一个变量是否为数组。
    console.log(Array.isArray([])); // true
    console.log(Array.isArray({})); // false

### Object.prototype.toString.call()
    //这是一个更为通用的判断方式，适用于所有类型。
    console.log(Object.prototype.toString.call("hello")); // "[object String]"
    console.log(Object.prototype.toString.call(42)); // "[object Number]"
    console.log(Object.prototype.toString.call(true)); // "[object Boolean]"
    console.log(Object.prototype.toString.call([])); // "[object Array]"
    console.log(Object.prototype.toString.call({})); // "[object Object]"
    console.log(Object.prototype.toString.call(null)); // "[object Null]"
    console.log(Object.prototype.toString.call(undefined)); // "[object Undefined]"
    console.log(Object.prototype.toString.call(function(){})); // "[object Function]"
    console.log(Object.prototype.toString.call(new Date())); // "[object Date]"

### constructor
    // constructor 属性可以用来判断对象是由哪个构造函数创建的。
    console.log([].constructor === Array); // true
    console.log({}.constructor === Object); // true
    console.log((function(){}).constructor === Function); // true
    console.log((new Date()).constructor === Date); // true

### isNaN()
    //isNaN() 用来判断一个值是否为 NaN（Not-a-Number）。
    console.log(isNaN(NaN)); // true
    console.log(isNaN(123)); // false
    console.log(isNaN("123")); // false (字符串可以被转换为数字)
    console.log(isNaN("hello")); // true

### isFinite()
    //isFinite() 用来判断一个值是否是一个有限数值。
    console.log(isFinite(123)); // true
    console.log(isFinite(Infinity)); // false
    console.log(isFinite(-Infinity)); // false
    console.log(isFinite(NaN)); // false
    console.log(isFinite("123")); // true (字符串可以被转换为数字)



