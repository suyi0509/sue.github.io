### 数据结构

---

#### Question 1: typeof 和 instanceof 检测数据类型的异同

###### Step 1： JS的数据类型

```js
- 原始数据类型（基本类型）
  Undefined、Null、Boolean、Number、String
  
- 引用类型（复杂类型）
  object => []数组、{}对象、new Date()实例化、function函数
  
- es6新增两个基本数据类型 symbol（独一无二）、bigInt（大整性）
```

###### Step 2:  typeof的特点(少null多function)

```js
- typeof 检测 返回的是对应的数据类型(无 null)
  Undefined、Boolean、Number、String、symbol、bigint、Object、funtion
  
- 特殊：typeof(null) //object
  原因：在计算机二进制中，typeof检测机器码后三位
  - 当机器码后三位为 000 ，则返回 object
  - null在设计时机器码为 0000....000
  
- 特殊：1.typeof(function(){}) // function  2.typeof(Array) // function 
  原因：typeof在判断引用类型时，在ECMA定义包含[[call]], 有=> function, 无 => object
```

###### Step 3： instanceof的特点(返回值是Boolean，只有ture、fasle)

```js
- A instanceof B 去检测，A对象是否是由B对象实例化出来的

- 特殊：1 instanceof Number // fasle
  原因：instanceof检测是在原型链上完成的，而基本数据类型是没有原型链，所以不能用instanceof去检测基本数据类型

- 特殊：[] instanceof Object // true   new Date() instanceof Object // true
  原因：instanceof检测是在原型链上完成的，
        []是由Array实例化出来的，[].__proto__===Array.prototype
        Array.__proto__===Obejct.prototype,因此[] instanceof Object // true
        
- 思考：原型链的顶端是什么
  原型链的顶端是object.prototype。所有对象的原型链最终都会指向 object.prototype
```