[参考网址](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
```js
if (!Array.prototype.indexOf) {
        Array.prototype.indexOf = function(searchElement, fromIndex) {

// 由于数组的indexOf是ecmaScript5的新方法，不能被IE8(包括IE8)以下浏览器支持，
// 因此本方法的作用是：为不支持indexOf方法的低级浏览器，添加同样的indexOf功能
// 
// 功能：
// 返回根据给定元素找到的第一个索引值，否则返回-1。
// 
// 语法：
// arr.indexOf(searchElement[, fromIndex = 0])
// 
// 参数：
// searchElement:位于数组中的元素。
// fromIndex:默认值: 0 (即在整个数组中查找指定元素)
            
            var i = 0,
                O = null,
                len = 0,
                n = +fromIndex || 0;

            if (this === "undefined") {
                throw new TypeError("'this' not defined");
            }

// 调用ToObject方法，并将this作为参数传入，把结果保存在O中

            O = Object(this);   

// 使用参数length,调用O的内部方法,获取O的长度lenValue(注意lenValue可以不为number类型),
// 如果lenValue不能转换为数值,使用ToUnit32()方法,返回0

            len = O.length >>> 0;   

// 如果对象的长度为0,则返回-1

            if (len === 0) {
                return -1;
            }

// 如果查询索引在数值有效范围之外,则设置n为0

            if (Math.abs(n) === Infinity) {
                n = 0;
            }

// 如果索引越界,则返回-1

            if (n >= len) {
                return -1;
            }

// 如果n大于等于0,则设置i的值为n
// 否则,小于0的话,设置i的值为len与n的绝对值的差
// 最终,如果i小于0,则设置i的值为0

            i = Math.max(n >=0 ? n : len - Math.abs(n), 0);

            while (i < len) {
                if (i in O && O[i] === searchElement) {
                    return i;
                }
                
                i += 1;
            }

            return -1;
        };
        console.log("我是低等级IE!!!");
    }
```
