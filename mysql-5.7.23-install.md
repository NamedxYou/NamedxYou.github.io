## MySQL 5.7 以上解压缩版本安装

1. 安装包的链接 https://dev.mysql.com/downloads/file/?id=478884

   ![image](/1.png "Package")


点进这个页面点击最下边的“No thank，just start my download” 即可

下载压缩包.zip，解压到指定路径，我这里是D:\mysql-5.7.23-winx64

2. 配置环境变量

新建 变量名：MYSQL_HOME

变量值：D:\mysql-5.7.23-winx64

修改环境变量PATH

在PATH后面加入%MYSQL_HOME%\bin   注：如果前面有值，要用;隔开

3. 自己创建一个文本文档my.ini，放在mysql根目录下，内容如下（其中的dir路径按自己的来）

   ```
   [mysql]
   # 设置mysql客户端默认字符集
   default-character-set=utf8
   [mysqld]
   explicit_defaults_for_timestamp=true
   #设置3306端口
   port = 3306 
   # 设置mysql的安装目录
   basedir=D:\mysql-5.7.23-winx64
   # 设置mysql数据库的数据的存放目录
   datadir=D:\mysql-5.7.23-winx64\data
   # 允许最大连接数
   max_connections=200
   # 服务端使用的字符集默认为8比特编码的latin1字符集
   character-set-server=utf8
   # 创建新表时将使用的默认存储引擎
   default-storage-engine=INNODB 
   ```

   4. 管理员权限打开cmd，cd到mysql安装目录\bin路径下，执行安装命令mysqld -install  (安装成功后，这时候是无法启动mysql服务的，因为没有data文件夹)
   5. 执行mysqld --initialize-insecure 自动生成无密码的root用户，如果使用mysql --initialize 则生成随机密码的root用户

   ps: 这里如果报以下错误，说明该data目录里已经有文件，如果之前安装过/安装失败过就会出现这种情况，将data文件的内容全部删除，重新执行命令即可。

   ![image](/2.png "Error")

   6. net start mysql 启动mysql服务(启动服务：net start mysql，停止服务：net stop mysql)
   7. 这时再执行mysql -u root -p ，登陆mysql服务器即可。

如果需要修改密码

mysqladmin -u root -p password 新密码 Enter password: 旧密码 

顺带附一个使用了mysql --initialize产生了随机密码的root用户，登陆不上去的解决办法，文章地址：

<http://blog.csdn.net/u014520039/article/details/50949672>




