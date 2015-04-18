以root用户进行JDK环境变量的配置

配置classpath，修改所有用户的环境变量
'$ sudo gedit /etc/profile'


在文件最后添加

>#set java environment

>JAVA_HOME=/usr/java/jdk1.7.0_71

>export JRE_HOME=/usr/java/jdk1.7.0_71/jre

>export CLASSPATH=.:$JAVA_HOME/lib:$JRE_HOME/lib:$CLASSPATH

>export PATH=$JAVA_HOME/bin:$JRE_HOME/bin:$PATH


---
说明:/usr/java/jdk1.7.0_71是JDK所在的目录
