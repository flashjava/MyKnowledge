>当一个function被调用的时候是有主语的时候，它是一个**方法**；
>
>当一个function被调用的时候是没有主语的时候，它是一个**函数**。

当一个函数运行的时候，它虽然没有主语，但是它的this的值会是全局对象。在浏览器里，那就是window。当然了，前提是函数没有被bind过，也不是被apply或call所调用。

---
那么function作为函数的情景有哪些呢？

首先，全局函数的调用就是最简单的一种。

```js
function bar() {
  console.log(this === window); // 输出：true
}
bar();
```

立即调用的函数表达式（IIFE，Immediately-Invoked Function Expression）也是没有主语的，所以它被调用的时候this也是全局对象。

```js
(function() {
  console.log(this === window); // 输出：true
})();
```

但是，当函数被执行在严格模式（strict-mode）下的时候，函数的调用时的this就是undefined了。这是很值得注意的一点。

```js
function bar() {
  'use strict';
  console.log('Case 2 ' + String(this === undefined)); // 输出：undefined
}
bar();
```
