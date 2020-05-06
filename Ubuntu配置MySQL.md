# Ubuntu配置MySQL

1. 使用apt-get安装MySQL服务端和客户端

   ```
   sudo apt-get install mysql-server mysql-client
   ```

   执行命令后输入y，确认安装。在弹出的界面按照指引设置MySQL  **root用户密码**

2. 确认安装

   ```
   mysql -V
   ```

   输出一下信息说明安装成功。

   mysql  Ver 14.14 Distrib 5.7.29, for Linux (x86_64) using  EditLine wrapper

3. 启动、停止MySQL服务以及查看服务状态 service mysql (start/stop/status)

   + 停止

     ```
     service mysql stop
     ```

     

   + 开始

     ```
     service mysql start
     ```

     

   + 查看服务运行状态

     ![image-20200304215751991](https://raw.githubusercontent.com/ChCh1999/md_img/master/md_img/image-20200304215751991.png)

4. 进入mysql:

   ```my
   mysql -u root -p
   your password
   ```

   