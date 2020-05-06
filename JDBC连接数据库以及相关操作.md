# JDBC连接数据库

1. 准备驱动，下载必要文件

   MySQL驱动文件：[mysql-connector-java-8.0.15.jar](https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-8.0.19.tar.gz)

2. 初始化连接，获取Driver文件

```java
            //加载驱动
            Class.forName("com.mysql.cj.jdbc.Driver");
```



3. 链接数据库，获取数据库连接对象

   连接方法为`DriverManager.getConnection`

```java
try {
            //加载驱动
            Class.forName("com.mysql.cj.jdbc.Driver");
            //getConnecting（）方法，用来连接mysql的数据库
    		//参数
            conn = DriverManager.getConnection("jdbc:mysql://" + dbUrl + "?useUnicode=true&characterEncoding=utf8&serverTimezone=GMT%2B8&useSSL=false&allowPublicKeyRetrieval=true  ", dbUser, dbPW);
            if (!conn.isClosed()) {
                System.out.println("Succeeded connecting to the Database" + dbUrl);
            }
        } catch (ClassNotFoundException e) {
            //数据库驱动类异常处理
            System.out.println("can't find the Driver!");
            e.printStackTrace();
        } catch (SQLException e) {
            //数据库连接失败异常处理
            e.printStackTrace();
        } 
```

4. 使用statement执行SQL语句：

   + 从连接对象获取statement对象。
   + 设置SQL语句
   + 执行 SQL语句（查询/更新）

   ```java
   //获取连接对象
   Statement stmt=conn.createStatement();
   //执行查询语句，返回ResultSet对象
   ResultSet rs=stmt.executeQuery("SELECT * FROM book");
   //执行SQL语句，结果为ResultSet返回True,否则（结果为更新行数或无结果）返回False
   stmt.execute("SELECT * FROM book WHERE id=1");
   //执行更新，返回更新的行数
   stmt.executeUpdate("DELETE * FROM  book");
   ```

   

5. 使用PreparedStatement执行SQL语句

   ```java
   //获取对象，设置语句模式
   PreparedStatement psmt=conn.prepareStatement("SELECT * FROM book Where id=?,name=?,price=?");
   //设置参数
   psmt.setInt(1,0);
   psmt.setString(2,"MATH");
   psmt.setDouble(3,9.99);
   //执行语句，执行方式有三种，与Statement对象相同
   ResultSet rs=psmt.executeQuery("");
   
   //以上语句等价于以下语句
   ResultSet rs=psmt.executeQuery("SELECT * FROM book Where id=0,name=\"MATH\",price=9.99");
   ```

   

