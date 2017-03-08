---
title: HTML5---localStorage本地存储
date: 2017-01-05 00:33:03
tags:
categories: 性能优化
---
### 概述
HTML5 提供了两种在客户端存储数据的新方法：
`localStorage` - 没有时间限制的数据存储
`sessionStorage` - 针对一个 session 的数据存储
<!-- more -->
之前，这些都是由 `cookie` 完成的。但是 cookie 不适合大量数据的存储，因为它们由每个对服务器的请求来传递，这使得 cookie 速度很慢而且效率也不高。
在 HTML5 中，数据不是由每个服务器请求传递的，而是只有在请求时使用数据。它使在不影响网站性能的情况下存储大量数据成为可能。
对于不同的网站，数据存储于不同的区域，并且一个网站只能访问其自身的数据。
HTML5 使用 `JavaScript` 来存储和访问数据。
### 用法小结
（一）设置值
```javascript
1.localStorage.setItem(key,value) //如果key的value存在时，更新key的值,例：localStorage.setItem("name","moomoo");【推荐写法】
2.localStorage.name = "moomoo";
3.localStorage["name"] = "moomoo";
```
（二）获取值
```javascript
1.localStorage.getItem(key,value):如果key的value不存在时，返回null，例：localStorage.getItem("name");【推荐写法】
2.var name = localStorage.name;
3.var name = localStorage["name"];
```
（三）清除值
```javascript
1.localStorage.remove(key);// 表示清除单项key的值，例:localStorage.remove("name");执行这句话就会清除name的值
2.localStorage.clear();  // 表示清除localStorage存储的所有数据
```
（四）遍历存储的数据
当你不清楚本地localStorage存储了多少数据的时候，用`key(index)`方法绝对是一个不错的选择，key(index)方法可以遍历localStorage存储的key。写个简单的例子：
```javascript
for(i=0;i<localStorage.length;i++){
　　document.write(localStorage.key(i)+":"+localStorage.getItem(localStorage.key(i))+"<br/>");
}
localStorage.length表示本地存储数据的总量；
localStorage.key(i),表示获取第i个数据的key；
localStorage.getItem(localStorage.key(i));表示获取第i个数据的value。
```
（五）JSON存储
当需要存储的数据很多时，可以将数据存储到数组中并转换成JSON格式的数据。
1.SON.stringify(data) 将对象转换成JSON格式的数据串。
2.JSON.parse(data)将数据解析成对象并返回解析后的对象。
这样说或许不太好懂，直接上例子：
```javascript
var arr = {"name":"moomoo","age":2,"eat":"apple"};
localStorage.setItem("arr",JSON.stringify(arr));
arr = JSON.parse(localStorage.getItem("arr"));
```
不过需要注意的是：localStorage存储的数据是不能跨浏览器共用的，也就是说存储在浏览器的数据只能在这个浏览器中访问，现在各个浏览器的存储空间是5M。
（六）sessionStorage
`sessionStorage`是个全局对象，它维护着在页面会话(page session)期间有效的存储空间。只要浏览器开着，页面会话周期就会一直持续。当页面重新载入(reload)或者被恢复(restores)时，页面会话也是一直存在的。每在新标签或者新窗口中打开一个新页面，都会初始化一个新的会话，也就是说sessionStorage针对一个 session 进行数据存储。当用户关闭浏览器窗口后，数据会被删除。
当浏览器被意外刷新的时候，一些临时数据应当被保存和恢复。sessionStorage 对象在处理这种情况的时候是最有用的。sessionStorage自动保存一个文本域中的内容，如果浏览器被意外刷新，则恢复该文本域中的内容，所以不会丢失任何输入的数据。
sessionStorage 方法与localStorage的方法相似，这里就不过多赘述。
（七）兼容性
   [点击这里查看兼容性^_^](http://caniuse.com/#search=localStorage)
作者 [@eyea](mailto:deyeseau@gmail.com)
### END
