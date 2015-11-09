# JS获取IE浏览器版本
> 一段非常好用的代码，JS判断浏览器是IE6/IE7/IE8/IE9/IE10/IE11或不是IE浏览器，如果是IE浏览器则返回IE浏览器的版本号，否则返回0。

> 原文出处：[JS获取IE浏览器版本](http://www.51-n.com/t-4193-1-1.html)

代码如下：
---
```js
/*
* JS 获取IE版本信息
* @author 吴先成 QQ:229256237 www.51-n.com
* @return integer 返回IE版本，具体的值可能为 0/6/7/8/9/10/11, 其中0表示浏览器不是IE内核
*/
function getIEVersion(){
      var ua = navigator.userAgent;
      var ver = 0;
      if(ua){
              if(ua.match(/MSIE\s+([\d]+)\./i)){
                      ver = RegExp.$1;
              }else if(ua.match(/Trident.*rv\s*:\s*([\d]+)\./i)){
                      ver = RegExp.$1;
              }
      }
      return parseInt(ver);
}
```
