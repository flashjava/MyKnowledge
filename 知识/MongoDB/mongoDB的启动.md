#mongoDB的启动
*(以windows为例)*

1. 下载

	**下载地址为：https://www.mongodb.org/downloads**

	我下载的是：mongodb-win32-i386-3.0.4.zip

2. 解压

	**把压缩包mongodb-win32-i386-3.0.4.zip解压至某一目录。**

	我解压的目录位置是：D:\MyDatabase\mongodb\3.0.4

3. 启动

	在Shell环境界面，执行`mongod.exe --dbpath D:\MyDatabase\mongodb\3.0.4\data`命令。

	说明：
	>--dbpath 参数是设定数据库文件的存放路径。

	MongoDB默认的数据目录为：C:\data\db。如果不用默认目录，则需要在在mongod.exe命令

	后加--dbpath参数。

	我这里设置的数据目录为：D:\MyDatabase\mongodb\3.0.4\data

	启动命令，如图所示：

	![启动的Shell界面](/resources/forKnowledge/mongoDB/mongoDB的启动/启动的Shell界面.png "启动的Shell界面")

	访问`http://localhost:27017/`地址，页面如图所示：

	![浏览器访问27017端口](/resources/forKnowledge/mongoDB/mongoDB的启动/浏览器访问27017端口.png "浏览器访问27017端口")

至此，mongoDB已正常启动了。