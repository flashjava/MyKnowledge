#express-获取ajax请求的数据

在使用以Node.js(版本：0.12.0)平台为基础，以express(版本：4.12.1)为框架的项目中，不

可避免地会碰到后台接收前台ajax请求的场景，其中接收ajax请求的数据是处理此类场景的关

键环节。

ajax最常见的请求方式有两种：GET和POST。

##GET方式

当ajax以GET方式发送请求时，后台可以使用`req.query.数据名称`的方式获得请求的数据。

示例代码：

>前台代码：
>```js
>window.location = "/pic/singlePic?picName=张三"
>```
>
>后台代码：
>```js
>router.get("/singlePic", function (req, res) {
    var imageName = req.query.picName;  // 此时imageName的值为“张三”
    ......
})
>```

##POST方式

当ajax以POST方式发送请求时，处理起来要稍微麻烦一点，要在项目中引入body-parser包，并

使用`req.body.数据名称`的方式获得请求的数据。

示例代码：
>前台代码：
>```js
>$.ajax({
    url: "/singlePic",
    type: "POST",
    data: {
        picName: "李四"
    }
});
>```
>
>后台代码：
>```js
>var bodyParser = require('body-parser');

>...

>// 定义数据解析器

>app.use(bodyParser.json());
>app.use(bodyParser.urlencoded({ extended: false }));

>...

>router.post("/singlePic", function (req, res) {
    var imageName = req.body.picName;  // 此时imageName的值为“李四”
    ......
})
>```
