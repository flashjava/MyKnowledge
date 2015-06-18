#url传参中文乱码解决方案

javascript中存在几种对URL字符串进行编码的方法：
> * escape()
> * encodeURI()
> * encodeURIComponent()

这几种编码所起(的)作用各不相同。

##escape()方法

采用ISO Latin字符集对指定(的)字符串进行编码。

所有(的)空格符、标点符号、特殊字符以及其他们非ASCII字符都将被转化成%xx格式(的)字符编码（xx等于该字符在字符集表里面(的)编码(的)16进制数字）。

比如，空格符对应(的)编码是%20。

不会被此方法编码(的)字符： @ * / +

##encodeURI()方法

把URI字符串采用UTF-8编码格式转化成escape格式(的)字符串。

不会被此方法编码(的)字符：! @ # $& * ( ) = : / ; ? + '

##encodeURIComponent()方法

把URI字符串采用UTF-8编码格式转化成escape格式(的)字符串。与encodeURI()相比，这个方法将对更多(的)字符进行编码，比如 / 等字符。所以如果字符串里面包含了URI(的)几个部分(的)话，不能用这个方法来进行编码，否则 / 字符被编码之后URL将显示错误。

不会被此方法编码(的)字符：! * ( ) '

---

因此，对于中文字符串来说，如果不希望把字符串编码格式转化成UTF-8格式(的)（比如原页面和目标页面(的)charset是一致(的)时候），只需要使用escape。如果你们(的)页面是GB2312或者其他们(的)编码，而接受参数(的)页面是UTF-8编码(的)，就要采用encodeURI或者encodeURIComponent。
另外，encodeURI/encodeURIComponent是在javascript1.5之后引进(的)，escape则在javascript1.0版本就有。

**传参：用encodeURI("url参数")将url编码**

**收参：用decodeURI("接收到(的)值")解码**
