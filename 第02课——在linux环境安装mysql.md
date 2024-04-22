#### 第二课——在linux环境安装mysql

接下来我们在 Centos7 系统下使用 yum 命令安装 MySQL，需要注意的是 CentOS 7 版本中 MySQL数据库已从默认的程序列表中移除，所以在安装前我们需要先去官网下载 Yum 资源包，下载地址为：https://dev.mysql.com/downloads/repo/yum/

1.使用wget命令，下载mysql的安装包（rpm包）

wget http://repo.mysql.com/mysql57-community-release-el7-8.noarch.rpm

2. 正式使用rpm包下载mysql组件

rpm -ivh mysql57-community-release-el7-8.noarch.rpm

（rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2022）

3.安装mysql

yum install -y mysql-server（--nogpgcheck）

※两个括号内的代码作用相同，都是关于GPG密钥的，输入其一即可

---

安装完成后

启动 MySQL：

systemctl start mysqld

查看 MySQL 运行状态：

systemctl status mysqld

注意：如果我们是第一次启动 mysql 服务，mysql 服务器首先会进行初始化的配置。

正常情况下需要使用如下命令获取初始密码，再使用登录命令:

grep “password” /var/log/mysqld.log

mysql -uroot -pxxxxxxx

登录成功如下图所示

<img src="https://raw.githubusercontent.com/arkfork/MySQL-Tutorial/main/image/mysql2.1.png"> 

