## 以下代码执行时，三次打印分别输出什么？为什么？
```js
function add1(i){
  console.log("函数声明："+(i+1));
}
add1(1);
 
var add1 = function(i){
  console.log("函数表达式："+(i+10));
}
add1(1);
 
function add1(i) {
    console.log("函数声明："+(i+100));
}
add1(1);
```
输出：
```
101
11
11
```
说明：
浏览器会对代码进行预解析，把 `变量` 、 `变量声明` 、 `函数声明` 提取到代码的最上方，js解析会优先考虑函数，对于重名的声明式函数和变量，函数会忽略变量，重名的声明式函数，会取最后一次定义。  
开始的时候，存在三个 `add1` js会选择第一和第三个函数声明，因为第二个是函数表达式，当存在多个函数声明的时候，取最后一个，也就是输出 `101` 。但是当执行到第二个函数表达式的时候，`add1` 的指针指向 `11` 。代码继续向下执行的时候，`add1` 不会再被改变了，再次调用输出 `11`。

## js_1
验证实例化的对象的
```js
var obj = new Object();
console.dir(obj);
var Person = function () {};
console.dir(Person);
var p = new Person();
console.dir(p);
console.log(p.__proto__ === Person.prototype);
```
> 非常有用  
> [关于__proto__和prototype的一些理解](http://www.cnblogs.com/zzcflying/archive/2012/07/20/2601112.html)



## end