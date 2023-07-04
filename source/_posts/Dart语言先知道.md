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
