#### 变量声明：
const 可以使简单类型数据不变(string)，复杂类型数据不能保证内部数据结构不变(object)。const使指针不变。

es6声明6中声明变量的方式:var,function,let,const,import,class

提案global为全局对象。

#### 解构赋值：
数组，对象，字符串，数值和布尔值，函数参数

* 解构可以设置默认值。默认值只有赋的值严格等于undefined时，才会附默认值。
* 解构字符串时，会先把字符串转换成数组。
#### 函数扩展
* 函数参数可以设默认值
* 函数的额length返回的是函数没有默认值参数的个数。(设置默认值参数后面的参数都不计入length里)
* 函数参数设置默认值时，会暂时性形成一个作用域
```javascript
let x = 1;

function f(y = x) {
  let x = 2;
  console.log(y);
}

f() // 1
```
##### rest 参数
* rest参数后不可以再跟其他参数
```javascript
function add(...values) {
  let sum = 0;

  for (var val of values) {
    sum += val;
  }

  return sum;
}

add(2, 5, 3) // 10
```
##### 函数的严格模式
```javascript
'use strict';
```
##### 函数的name
```javascript
var f = function () {};

// ES5
f.name // ""

// ES6
f.name // "f"
```
##### 箭头函数
1. 函数体内的this对象，就是定义时所在的对象，而不是使用时所在的对象。
2. 不可以当作构造函数，也就是说，不可以使用new命令，否则会抛出一个错误。
3. 不可以使用arguments对象，该对象在函数体内不存在。如果要用，可以用 rest 参数代替。
4. 不可以使用yield命令，因此箭头函数不能用作 Generator 函数。


#### Symbol
es6的第七种数据类型，其他六种为;undefined,null,String,Number,Boolean,Object
```javascript
let s = Symbol();  
typeof s 
// "symbol"
```
Symbol函数前不能添加new，会报错。因为生成的Symbol是一个原始类型的值。
```javascript
var s1 = Symbol('foo');
var s2 = Symbol('bar');

s1 // Symbol(foo)
s2 // Symbol(bar)

s1.toString() // "Symbol(foo)"
s2.toString() // "Symbol(bar)"
```
加上参数方便辨认