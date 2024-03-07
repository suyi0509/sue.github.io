## TS基础知识

> Typescript是JS的类型的超集，支持ES6语法，支持面向对象编程的概念，比如：类、接口、继承、泛型等。JS是TS的子集，TS是JS的超集（包含关系）

ts是一种静态类型检查语言，提供类型注解，在代码编译阶段就可以检查出数据类型的错误，同时扩展JS的语法，兼容JS在TS下工作，这需要TS在编译阶段需要编译器编译成**纯JS**，来运行


```js
const hello:string = "Hello World"
console.log(hello)
```
编译后

```js
const hello = "Hello World"
console.log(hello)
```

### 函数区别
函数在js中的作用是：实现抽象层、模拟类、信息隐藏和模块
函数在TS中的作用是：支持类、命名空间、模块

### 特性
- **类型批注和编译时类型检查**：在编译时批注变量类型
- **类型推断**：ts没有批注变量类型会自动推断变量的类型
- **类型擦除**：在编译过程中批注的内容和接口会在运行时利用工具擦除
- **接口**:ts中用接口来定义对象类型
- **枚举**：用于取值被限定在一定范围内的场景
- **Mixin**：可以接受任意类型的值
- **泛型编程**：写代码时使用后再指定的类型
- **名字空间**：名字只在该区域内有效，其他区域可重复使用该名字而不冲突
- **元组**：元组合并了不同类型的对象，相当于一个可以装不同类型数据的数组

### 类型批注
通过类型批注提供在编译时启动类型检查的静态类型，是可选的，可以忽略使用JS常规的动态类型，弱/动态类型的结构是any类型

### 类型推断
当我们没有明确声明类型时，TS会进行类型推断

```js
let str = "string" // 推断为字符串类型
```
通过初始变量值和成员，设置默认参数值和决定函数返回值时，如果缺乏声明不能推断类型，则会默认为动态any类型

### 接口
用来描述对象类型

```js
interface Person{
    name：string;
    age: number;
    sex?: '男' | '女'
}

let Zhangsan:Person = {
    name:'Zhangsan',
    age:18,
}
```




## TS和JS的区别
1. TS是JS的超集，扩展JS的语法
2. 编写TS文件会被自动编译成JS文件
3. TS文件后缀名 .ts/.tsx , JS文件后缀名是  .js/jsx
4. TS为面向对象编程语言，而JS为脚本语言
5. TS支持静态类型，JS无静态类型的概念
6. ts新增 模块、接口、原型特性等功能