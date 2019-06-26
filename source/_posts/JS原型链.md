---
title: JS原型链
date: 2018-07-26 14:19:46
categories: JS
tags: JS基础知识
cover: /img/JSyuanxinglian.jpg
---

### 什么是原型对象(prototype)

只要创建了一个新函数，就会根据一组特定的规则为该函数创建一个prototype属性，这个属性指向函数的原型对象.原型对象,不管你实例化多少次,都只生成一次. 所以,为了避免内存浪费,出现了原型帮助我们解决了这个问题.

原型对象的属性查找机制

首先会先在实例上面搜索属性，如果找到了直接返回，否则就继续去原型上面寻找。

### 什么是_proto_

举个例子:你的父亲给你买了一部手机,那是你父亲自己买的手机.相当于自己创建对象iphone时候用的构造方法, 这个方法就是prototype。那作为儿子的你不可能是别人的儿子,你得指向你自己的父亲,所以你需要通过_proto_指向你父亲创造你时所用的构造方法.

```javascript
       function Father() {
           this.iphone = "iphone";
       }
       var son = new Father();
       console.log(son.__proto__ === Father.prototype);
       //true
```
### 原型链的提及

JS语言里,万物皆对象.我们平时所使用的基本数据类型、函数、等等皆为对象.例如:写下一段代码
```javascript
   var a = '字符串';
   //相当于
   var a = new String('字符串')
```
那么既然JS里皆为对象,每一个对象就会有自己的父亲也就是原型.那么每一个对象想指向自己父亲的prototype是不是又需要
名为_proto_的属性去指向原型对象.这样,在JS内部就形成了一个很长很长的链子,这条指向过程线,就称之为原型链.

```javascript
        /*object的__proto__指向Function对象的原型*/
       //Object对象是Function对象的一个实例
       console.log(Object.__proto__ === Function.prototype)
   
   
   
       /*Function.prototype对象的原型的__proto__属性指向Object.prototype*/
       console.log(Function.prototype.__proto__ === Object.prototype)
   
       /*object的原型的__proto__属性为null*/
       console.log(Object.prototype.__proto__ )
   
       /*一个自定义对象可以访问到Function对象的所有属性和方法，也可以访问到Object对象的所有属性和方法*/
```


```javascript
       console.log(Number.__proto__ === Function.prototype)  // true
       console.log(Boolean.__proto__ === Function.prototype) // true
       console.log(String.__proto__ === Function.prototype)  // true
       console.log(Object.__proto__ === Function.prototype)  // true
       console.log(Function.__proto__ === Function.prototype) // true
       console.log(Array.__proto__ === Function.prototype)   // true
       console.log(RegExp.__proto__ === Function.prototype)  // true
       console.log(Error.__proto__ === Function.prototype)   // true
       console.log(Date.__proto__ === Function.prototype)    // true
```
如果想看图解,可以参考[这里](https://www.cnblogs.com/libin-1/p/5820550.html)