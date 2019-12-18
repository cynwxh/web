# JS（五）简要介绍数组或对象 typeof、类型转换

## 初始引用值

- 数组
- 对象

### 数组

> 数组对象用来在单独的变量名中存储一系列的值。形式是一个中括号,里面可以写很多东西,中间用逗号隔开,每个逗号类似可以隔开两个仓库,每个仓库可以放东西,比如 Number、String 、undefined，放什么类型的值都可以。

```js
var arr = [1, 2, undefined, "abc", ["a", 1, 5], null];
// 数组的增加
document.write(arr.push("吴彦祖"));
// 打印arr-->[1,2,undefined,"abc",["a",1,5],null,"吴彦祖"]
// 数组的删除(还有多种方法)
arr.splice(0, 1);
// 打印出来是[2,undefined,"abc",["a",1,5],null]
// 数组的修改
arr[0];
//打印出来是0
arr[0] = 100; //在打印出来就是100;
// 数组的查看
for (var i = 0; i < arr.length; i++) {
  console.log(arr[i]);
}
// 打印出对应于的值
```

### 关于数组的其他方法

- For...In 声明

使用 for...in 声明来循环输出数组中的元素。

- 合并两个数组 - concat()

如何使用 concat() 方法来合并两个数组。

- 用数组的元素组成字符串 - join()

如何使用 join() 方法将数组的所有元素组成一个字符串。

- 文字数组 - sort()

如何使用 sort() 方法从字面上对数组进行排序。

- 数字数组 - sort()

如何使用 sort() 方法从数值上对数组进行排序。

### 对象

> JavaScript 对象是拥有属性和方法的数据。JavaScript 中的所有事物都是对象：字符串、数字、数组、日期，等等。在 JavaScript 中，对象是拥有属性和方法的数据。

```js
    var obj= {
    key : value,
    建 : 值,
    属性: 属性值;
    }
    var car= {
    type:"Fiat",
    model:500,
    color:"white"
    money:undefined,
    newCar:false,
    }
    // 增加对象属性car.width="1.6m";
    // 删除对象属性delete.car.width;
    // 修改对象属性car.width="1.5m";
```

### typeof

- 六种数据类型

- Number
- string
- boolean
- undefined
- object
- null

```js
// 语法 typeof("里面放数据")
// 例子
var num = 123;
var str = "123";
var a = true;
var b = null;
var c = undefined;
console.log(typeof num); //打印-->number
console.log(typeof str); //打印-->string
console.log(typeof a); //打印-->boolean
console.log(typeof b); //打印-->object
console.log(typeof c); //打印-->undefined
//第二种方法
console.log(typeofc); //打印-->undefined 空格也可以
```

---

### 类型转换

#### 显示类型转换

- Number(mix) 转换成数
- parseInt(string,radix) 转换成整数
- parseFloat(string) 把数字转换为浮点数
- toString(radix) 转换成为字符串
- String(mix) 把内容换成字符串
- Boolean() 转换成布尔值

```js
//Number 转换成数
var num = Number("123"); // 打印 123
var num = Number(true); // 打印 1
var num = Number(false); // 打印 0
var num = Number(null); // 打印 0
var num = Number(undefined); // 打印 NaN
var num = Number("a"); // 打印 NaN
var num = Number("123abc"); // 打印 NaN
// parseInt 转换成整数
// parseInt(String,radix)
// radix 是调整进制取值范围是 2-36
// parseInt 是用数字从前往后截，截取到最后一个字符，如果出现非数字，把之前的数字返回（如例子一）
var num = parseInt("123.9"); // 打印 123 不是四舍五入
var num = parseInt(true); // 打印 NaN
var num = parseInt(false); // 打印 NaN
var num = parseInt(null); // 打印 NaN
var num = parseInt(undefined); // 打印 NaN
var num = parseInt("a"); // 打印 NaN
var num = parseInt("123abc"); // 打印 123
// parseFloat 把数字转换为浮点数
var num = parseFloat("123.9"); // 打印 123.9
var num = parseFloat(true); // 打印 NaN
var num = parseFloat(false); // 打印 NaN
var num = parseFloat(null); // 打印 NaN
var num = parseFloat(undefined); // 打印 NaN
var num = parseFloat("a"); // 打印 NaN
var num = parseFloat("123.2abc"); // 打印 123.2
// String 把内容换成字符串
var num = String(123.9); //打印"123.9"
var num = String(undefined); //打印"undefined"
// Boolean 转换成布尔值
// 除了 undefined、null、NaN、""、0、false 打印出来的是 false 以外, 其他的全是 true
var num = Boolean(123.9); // 打印 true
var num = Boolean(undefined); // 打印 false
// toString(radix) 转换成为字符串
// 两个不能用一个 undefined 一个 null，会报错 undefined 和 unll 没有这个 toString 属性
// radix 是以 10 进制为基底转换为别的进制
// 用法:要转的数据.toStringvardemo=123;
varstr = demo.toString();
console.log(str); // 打印出"123"
```

#### 隐式内容转换

- isNaN()
- ++/-- +/-(一元正负)
-

-

- -，\*，/，%
- &&，||，!
- <，>，<=，>=
- == !=
```js
  //isNaN()当你把数放在括号里面的时候他能判断这个是是不是 NaN,然后给你返回回来
  console.log(isNaN(NaN));// 打印 true
  console.log(isNaN(123));// 打印 false
  console.log(isNaN("123")); // 打印 false
  console.log(isNaN("adc")); // 打印 true
  console.log(isNaN(null); // 打印 false
  console.log(isNaN(undefined); // 打印 true
  // isNaN 在内部 执行了一个 Number 方法
  // 比如 isNaN("abc")
  // 首先执行了 Number("abc") 看是不是 NaN 如果是就返回 NaN
  // 所以这个 Number 它没有显示的去调用，是隐式的去调用

  // ++，先调用 Number
  var a="123";
  a++; // 打印出 a-->124;
  var a="abc";
  a++; // 打印出 a-->NaN;
  // +/- 先调用 Number
  var a=+"abc";
  console.log(typeof(a)) // 打印出 Number
  // + 隐式类型转换调用的是 string
  var a="1"+1;
  console.log(typeof(a)) //打印出 string

  //-、\*、/、% 隐式类型转换调用的是 Number

  // <、>、<=、>= 如果有数字就调用 Number
  var a="1"<2;
  console.log(typeof(a)) // 打印出 boolean

  // == 、!=vara="1"==1;
  console.log(typeof(a)) // 打印出 boolean true

  //特殊的
  undefined>0 //打印 false
  undefined<0//打印 false
  undefined==0//打印 false
  null>0//打印 false
  null<0//打印 false
  null==0//打印 false
  undefined==null//打印 true
  NaN==NaN//不等于任何东西
```
**不发生类型转换**

- === !==(绝对的等于 绝对不等于)
```js
  1!=="1"// true
  1!==1// false
  NaN===NaN// false
```
**还有一种特殊的**
```js
    // a 在没有定义的情况下
    typeof(a);
    // 用console.log 打印出 undefined
    // typeof返回的值类型 都是 string 类型
    typeof(typeof(a))
    // 用 console.log 打印出 string
```