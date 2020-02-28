# git 学习笔记

## git系统架构

![git 系统架构图](https://www.runoob.com/wp-content/uploads/2015/02/1352126739_7909.jpg)

## 安装git

+ windows：下载安装包运行安装。

  ![git安装](https://www.runoob.com/wp-content/uploads/2015/02/20140127131250906)

  - 配置用户信息 （--global 将修改用户文件夹中的配置文件，对全局的项目生效）

  ```
  $ git config --global user.name test
  $ git config --global user.email xxxx@163.com
  ```

  - 查看配置信息

  ```
  git config -l
  ```

## 使用git

### 配置SSH公钥

1. 生成ssh公钥：

   进入用户根目录，执行ssh公钥生成程序。

   ```
    cd ~
   ssh-keygen -t rsa -C "github邮箱"
   ```

   回车执行，确认相关信息（存储路径、访问密码（用于访问该公钥，不是github登录密码））

   ![image-20200225174339814](E:\workspace\md_img\md_img\image-20200225174339814.png)

2. 将公钥添加到github

   复制存储路径 （一般为：`C:\Users\用户名\.ssh` ）下公钥内容：使用notepad++或其他相关工具打开 ***id_rsa.pub*** 到github->setting->SSH and GPG keys->New SSH key，输入公钥备注，粘贴公钥内容，确认即可完成

   ![image-20200225174600099](E:\workspace\md_img\md_img\image-20200225174600099.png)

3. 测试连接

   + 执行以下命令连接github

   ```
   ssh -T git@github.com
   ```

   + 首次连接可能会出现ip验证：

   ![image-20200225174859419](E:\workspace\md_img\md_img\image-20200225174859419.png)

   ​		输入**yes**回车确认，将github的ip加入到已知列表，以后便可以顺利连接github

   + 连接成功会出现如下结果

   ​	Hi XXXXXXX! You've successfully authenticated, but GitHub does not provide shell access.

### 创建与获取代码库（repo/repository）

+ 创建代码库命令：` git init  [文件夹路径] `

```
git init [文件夹路径]
Initialized empty Git repository in XXXX
```

+ 克隆代码 ` git clone (源) [目标目录]`

```
git clone git@github.com:fsliurujie/test.git         --SSH协议
git clone git://github.com/fsliurujie/test.git          --GIT协议
git clone https://github.com/fsliurujie/test.git      --HTTPS协议
```

