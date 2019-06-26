---
title: JS函数预编译
date: 2018-5-7 13:20:15
categories: JS
tags: JS基础知识
cover: /img/JSyubianyi.jpg
---
### 初步理解预编译：

1.函数定义整体提升

2.变量声明提升

预编译目的 ：将变量或函数提升到指定作用域中，当程序执行时，到预编译作用域中查找内容。

### 函数体内预编译四部曲

**预编译发生在函数执行前一刻**

1.创建AO对象(活动对象，也叫执行期上下文，可以理解为作用域或存储空间)

2.找形参和变量声明，进行参和变量名作为AO属性名，值为undefined

3.将实参和形参统一(实参带入AO对象中的形参变量)

4.在函数体内找函数声明，将名做为AO属性名，值赋予函数体(提升子函数)

**四部不能跳，同名只提升一次**

{% asset_img a.jpg a %}

---
可以从此图看出,先创建AO对象.在AO对象内部找形参和变量声明,a:undefined b:undefined实参和形参统一,a:1 b:undefined. 在函数体内找函数声明. a:function a(){} b:undefined最后依次负值输出,结果为上图控制台打印出为例.

### 全局预编译

与函数体内预编译类似,不同点为全局预编译创建GO对象,在GO内部进行变量赋值.全局预编译内部若AO对象寻找不到未出现变量名,则会在全局内部部进行寻找.也就是说,预编译的方向是由里向外的.举个简单的例子

```javascript
     a = 1
     function fn(){
         console.log(a)
         //a:1
     } 
     fn()
```
 
```javascript
     a=1
     function fn(){
         var a;
         console.log(a)
         //a:undefined
     }
     fn()
```
 
