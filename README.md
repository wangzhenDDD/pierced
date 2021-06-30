# pierced
钉钉内网穿透

TCP 穿透需要在数据库里面执行：
GRANT ALL PRIVILEGES ON *.* TO root@'%' IDENTIFIED BY '123456';
FLUSH PRIVILEGES;
数据库连接命令：
mysql -h vaiwan.com -u root -p -P 1234 //端口号地址



![image](https://user-images.githubusercontent.com/85866843/123894777-571dfb00-d991-11eb-8b2f-406bb764ec2b.png)

配置内网穿透
如果你还没有公网域名，在本部分，你可以使用钉钉内网穿透工具，映射一个本地的公网域名使用。

打开命令行工具，执行以下命令，下载内网穿透工具。

git clone https://github.com/open-dingtalk/pierced.git
执行以下命令，启动内网穿透。

Windows执行以下命令：

说明 Windows需使用cmd工具打开命令行。
cd windows_64
ding -config=ding.cfg -subdomain=abcde 8080
MAC执行以下命令：

cd mac_64
chmod 777 ./ding
./ding -config=./ding.cfg -subdomain=abcde 8080
注意 启动内网穿透时，请不要直接使用abcde字符串，如果需要使用默认端口8080，需确保在同一内网环境下该字符串唯一且未重复使用，如果重复，启动后可能会出现访问端口不一致问题。
启动完客户端后，你访问http://abcde.vaiwan.com/xxxxx都会映射到http://127.0.0.1:8080/xxxxx。

重启后端服务。
