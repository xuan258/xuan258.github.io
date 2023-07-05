---
title: Dart简单语言
tags:
categories:
cover: https://sunny-blog.oss-cn-beijing.aliyuncs.com/%E5%8D%9A%E5%AE%A2%E5%B0%81%E9%9D%A2%E5%9B%BE%E6%96%87%E4%BB%B6/cover5.jpg
---

# Dart介绍

Flutter不是语言，是UI框架，用Dart语言书写简单。以下会大致列出在日常开发当中涉及到的语法，当然带着例子更容易理解一些啦。
更多Dart信息推荐查看官网[dart.dev](https://dart.dev/language)

## Hello World
每一个app都有一个main函数
void main() { print('Hello, World'); }

## 变量（Variables）
即便是在类型安全（type-safe）的Dart语言当中，大多数的变量都不需要显示类型声明，会根据声明的变量值去推断该变量的类型
var name = 'Voyager I';
var year = 2023;
var antennaDiameter = 3.7;
var flybyObjects = ['Jupiter', 'Saturn', 'Uranus', 'Neptune'];
var image = { 'tags': ['saturn'], 'url': '//path/to.saturn.jpg' };

## 循环语句
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 循环语句：</span><br><span class="line">if (year >= 2001) {</span><br><span class="line">   print('21st century');</span><br><span class="line">} else if (year >= 1901) {</span><br><span class="line">   print('20st century');</span><br><span class="line">}</span><br><span class="line">for (var object in flyObjects) {</span><br><span class="line">   print(object);</span><br><span class="line">}</span><br><span class="line">for (int month = 1; month <= 12; month++) {</span><br><span class="line">   print(month);</span><br><span class="line">}</span><br><span class="line">while (year < 2016) {</span><br><span class="line">   year += 1;</span><br><span class="line">}</span><br></pre></td></tr></tbody></table></figure>

## 函数
函数的声明，函数的参数要携带参数类型，如果有返回值，也要声明返回值类型，如果为空，则为void
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 函数的声明格式：</span><br><span class="line">int fibonacci(int n) {</span><br><span class="line">   if (n == 0 || n == 1)</span><br><span class="line">   return n;</span><br><span class="line">   return fibonacci(n - 1) + fibonacci(n - 2);</span><br><span class="line">}</span><br><span class="line">var result = fibonacci(20);</span><br></pre></td></tr></tbody></table></figure>
Dart也有箭头函数，箭头函数适应于函数体只有一行语句

## 注释
Dart语言的注释通常以'//开头'，也支持/* xxx */，以下是官方的说明
// This is a normal, one-line comment.
/// This is a documentation comment, used to document libraries.
/// classes, and their members. Tools like IDEs and dartdoc treat.
/// doc comments specially.
/* Comments like these are also supported. */

## import
同大多数语言一样，Dart语言引入依赖的方式也是Import
例如：import 'dart.math'; // 引入核心依赖，来源dart的SDK
     import 'package:test/test.dart'; // 引入pub市场的依赖包
     import 'path/to/my_other_file.dart'; // 引入本项目内部的依赖

## 类（Class）
先引入一个class的样板，然后我们剖析一下
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// class：</span><br><span class="line">class Spacecraft {</span><br><span class="line">   String name;</span><br><span class="line">   DateTime launchDate;</span><br><span class="line">   // Constructor, with suntactic sugar for assignment to membeers.</span><br><span class="line">   Spacecraft(this.name, this.launchDate) {</span><br><span class="line">      // Initialization code goes here.</span><br><span class="line">   }</span><br><span class="line">   // Named constructor that forwards to the default one.</span><br><span class="line">   Spacecraft.unlaunched(String name) : this(name, null);</span><br><span class="line">   int get launchYear => launchDate?.year; // read-only non-final property</span><br><span class="line">   // Method.</span><br><span class="line">   void describe() {</span><br><span class="line">      print('Spacecraft: $name');</span><br><span class="line">      if (launchDate != null) {</span><br><span class="line">         int years=DateTime.now().difference(launchDate).inDays ~/365;</span><br><span class="line">         print('Launched: $launchYear ($years years ago)');</span><br><span class="line">      } else {</span><br><span class="line">         print('Unlaunched');</span><br><span class="line">      }</span><br><span class="line">   }</span><br><span class="line">}</span><br></pre></td></tr></tbody></table></figure>
然后这里声明的Class我们可以这样使用：

var voyager = Spacecraft('Voyager I', DateTime(2023, 07, 05));
voyager.describe();
var voyager2 = Spacecraft.unlaunched('Voyager III');
voyager2.describe();
说明：函数的构造器是一个为成员赋值的语法糖，省去我们使用this.name = value;
该Class里面有两个构造函数，其中Spacecraft.unlaunched(String name):this(name, null);这个构造函数的定义基于他之前的构造函数（冒号（:）的作用在于此，等同于Spacecraft(String name)）
name和launchDate这两个属性我们可以直接读取和修改，而get包装的属性只能读取，需要通过set包装的方法才可以修改

## 继承
Dart是单继承的，不像某些语言可以多继承
class Orbiter extends Spacecraft {
    num altitude;
    Orbiter(String name, DateTime launchDate, this.altitude) : super(name, launchDate);
}
 
 ## 混合（Mixins），继承+实现
 class MockSpaceship implements Spacecraft { // ...}

 ## Interfaces and abstract classes
 Dart没有interface的关键词，所有的类都会隐式的定义一个接口，因此你可以书写下面的语句来实现任何类
 class MockSpaceship implements Spacecraft { // ...}
 抽象类一般用作基类

 ## 异步Async
 我们在书写代码的时候为了保证可读性和避免地狱回调，因此使用 async/await。
 const oneSecond = Duration(seconds: 1); // ... Future<<void>void> printWithDelay(String message) async { await Future.delayed(oneSecond); print(message);}
 这段代码等价于
 Future<<void>void> printWithDelay(String message) { return Future.delayed(oneSecond).then((_) { print(message);});}
 以下这段代码就是
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// async/await可读性：</span><br><span class="line">Future<<void>void> createDescriptions(Iterable<<String>String>objects) async {</span><br><span class="line">   for (var object in objects) {</span><br><span class="line">      try {</span><br><span class="line">         var file = File('$object.txt');</span><br><span class="line">         if (await file.exists()) {</span><br><span class="line">            var modified = await file.lastModified();</span><br><span class="line">            print('File for $object already exists. It was modified on $modified.');</span><br><span class="line">            continue;</span><br><span class="line">         }</span><br><span class="line">         await file.create();</span><br><span class="line">         await file.writeAsString('Start describing $object in this file.');</span><br><span class="line">      } on IOException catch (e) {</span><br><span class="line">         print('Cannot create description for $object: $e');</span><br><span class="line">      }</span><br><span class="line">   }</span><br><span class="line">}</span><br></pre></td></tr></tbody></table></figure>

## 异常处理 Exceptions
同其他语言，Dart语言的异常抛出也为throw，如果先捕获，则try ...on或者catch或者on+catch
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 异常处理：</span><br><span class="line">try {</span><br><span class="line">   for (var object in flybyObjects) {</span><br><span class="line">      var description = await File('$object.txt').readAsString();</span><br><span class="line">      print(description);</span><br><span class="line">   }</span><br><span class="line">} on IOException catch (e) {</span><br><span class="line">   print('Could not desctibe object: $e');</span><br><span class="line">} finally {</span><br><span class="line">   flybyObjects.clear();</span><br><span class="line">}</span><br></pre></td></tr></tbody></table></figure>