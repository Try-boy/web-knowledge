# ES6

> ECMAScript 6.0（简称ES6）是JS的新一代标准，在2015年6月正式发布
>
> 可能我们觉得ES6太麻烦,就不去使用,但是15年发布的ES6,现在19年了
>
> 很多新的技术文档和官方demo都会使用ES6语法,要是我们再不用就真的OUT了
>
> 个人认为,ES6看上去没有多少东西很简单的样子,但是用心去看,还是值得深究的



### let与const命令

##### let

ES6新增了`let`命令，用来声明变量

###### 代码块内有效 

用法类似于`var`，但所声明的变量，只在`let`命令所在的代码块内有效

```js
{
    var a = 1
    let b = 2
}

console.log(a) // 1
console.log(b) // ReferenceError : b is not defined
```



###### 不允许重复声明

let 只能声明一次 var 可以声明多次

```js
var a = 1
var a = 2
let b = 3
let b = 4
a  // 2
b  // Identifier 'b' has already been declared
```



###### 不存在变量提升

let 不存在变量提升，var 会变量提升 ,let变量一定要在声明后使用，否则报错 

```js
console.log(a); // 输出undefined
console.log(b); // 报错ReferenceError : b is not defined

var a = 2;
let b = 2;
```



###### 暂时性死区

只要块级作用域内存在`let`命令，它所声明的变量就绑定了这个区域，不再受外部的影响

```js
var a = 1
{
    a = 2 // ReferenceError: a is not defined
    let a
}
```









未完成。。。













