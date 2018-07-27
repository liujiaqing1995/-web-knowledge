

## PHP

#### 1 服务器

- 通俗说,就是提供某种服务的机器(计算机)称为服务器

#### 2 软件架构

- C/S架构  Client/Server架构
  + 客户端/服务端架构
  + 客户端向服务器请求服务,服务器向客户端响应服务
  + 特点:
    + 安装对应的客户端软件
    + 性能较好,体验比较好
    + 需要不时的更新
- B/S架构   Broswer/Server架构
  + 浏览器向服务器请求服务,服务器向浏览器响应服务
  + 特点:
    + 浏览器向服务器索取服务
    + 性能相对较差
    + 默认计算机会自带

#### 3 动态网站与静态网站

- 静态网站:  使用浏览器端语言进行编译,由静态代码(HTML,CSS,JS)组成
- 动态网站:  网页通过服务器的程序(php等)动态生成的,用户可以和服务器进行交互(可以根据用户输入的不同信息,返回不同的运行结果)

#### 4 ip地址

- 所谓IP地址就是给每个连接在互联网上的主机分配的一个32位地址。(就像每个人的身份证号码一样)
- 通过ip地址可以找到具体的某一台计算机

#### 5 域名

- 由于IP地址基于数字，不方便记忆，于是便用域名来代替IP地址，域名是一个IP地址的“好记的名字”

- 可以查看到域名对应的ip地址

- 特效域名:  localhost 本地主机;

- 这是一个保留域名,主要用于本地测试,对应的ip地址为 127.0.0.1


#### 6 DNS服务器

- 作用:  记录ip地址和域名之间的对应关系;会将域名解析成对应的ip地址
- 查找优先级:  本地hosts文件 > DNS服务器

#### 7 端口

- 端口号是计算机与外界通讯交流的出入口，每个端口对应不同的服务。
- 默认端口是80;
- 不同的客户端软件对应的端口不同

## PHP基础

#### 1 PHP简介

- 开源（open source）软件，跨平台，常用操作系统稳定执行。Windows / Linux。做WEB开发的经典组合 WAMP,LAMP基本都是开源软件。

- 入门简单,用户只需要关注应用，开发成本低。

- 支持的大多数主流数据库。MySQL，oracle,Redis等

#### 2 php初体验

- ```
  <?php
  //php代码块
  ?>
  ```

- php的语法中,每行代码末尾必须加分号;不然就报错

- 第一行设置字符集

- 必须通过访问服务器的方式,访问php文件

#### 2 输出

```
1)  echo: 输出简单数据类型
2)  print_r: 输出复杂数据类型
3)  var_dump: 输出数据的同时,输出详细信息(类型+长度)
```

#### 3 变量

变量: 存储数据的容器

```
1) 在程序运行中, 可以变化的量 
2) 在php中使用 $ 符号声明变量
3) $ 后面的命名规则与js的变量命名规则一致
4) 在php中变量没有声明,变量会在进行第一次赋值的时候创建
```

#### 4 变量相关方法

```
1) isset($var)=>判断变量是否进行了赋值
   如果未赋值或为null,都返回false;否则返回true
2) empty($var)=>判断变量是否为空 
   只要未赋值/0/''/[]/null/false 都认为为空,返回true;否则返回false
3) unset($var)=>删除变量
```

## 数据类型

####       1 整数和浮点数

```
eg: $a=123;
	$PI=3.1415926;
```

#### 2 boolean类型

```
echo在进行输出boolean类型,true输出1,false输出空字符串
```

#### 3 字符串类型

```
1) 单双引号都可以使用
2) 进行字符串拼接不是+,而是.
3) 双引号会对变量进行解析,而单引号不会
4) 单引号的效率高, 但是双引号功能更强大
```

#### 4 数组类型

- 索引数组

  ```
  // 数组的赋值
    // $arr = array(0,1,2,3,4);
    // $arr = [0,1,2,3,4];
    // echo $arr;
    // print_r($arr);
    // var_dump( $arr );

    // echo $arr[2];  // 取值
    // echo count( $arr ); //在php中数组没有length,通过count()方法计数
    // $arr[5] = 5;
    // $arr[] = 6;  // 跟数组的push作用一样
    // print_r( $arr );
  ```


  - 关联数组(和js中的对象很像,但语法不一样)

    ```
    $info = [
      //   'name' => "伟哥",
      //   'age' => 18,
      //   'sex' => '未知',
      //   'desc' => '小胖子'
      // ];

      // // print_r( $info );
      // echo $info['name'];
      // echo $info['age'];
    ```

  - 二维数组

    + 关联数组可以存储一个人的信息 
    + 二维数组就可以存储多人的信息 

    ```
    $arr = [
      //   [0,1,2,3,4],
      //   [5,6,7,8,9]
      // ];
      // echo $arr[0][2];  // 2 
    ```



- 遍历索引数组

  ```
  $arr = array("张三", "李四", "王五", "赵六", "田七", "王八");
  //获取数组的长度： count($arr)
  for($i = 0; $i < count($arr); $i++) {
    echo $arr[$i];
    echo "<br>";
  }
  ```


- 遍历关联数组

  - foreach( 数组 as 键 => 值 ) {  } 

  ```
  //遍历关联数组
  $arr = array(
    "name"=>"zs",
    "age"=>18,
    "sex"=>20
  );
  foreach($arr as $key => $value) {
    echo $key . "=" . $value . "<br>";
  }
  ```


#### 5 函数

- php中的函数语法和js中函数语法基本一致
- 不同点:函数名大小写不敏感
- 函数的参数可以设置默认值

```
function sayHello ($name="周杰伦") {
        echo "大家好，我是$name";
        echo "<br>";
    }
    sayHello();//不传参数，会使用默认值
    sayHello("鹏鹏");//传参数，默认值不生效
?>
```

#### 6 常量

- 在程序运行中, 不可以变化的量 

- 定义常量

    // 语法: define( 常量名, 常量值 );

    // 命名规范: 常量所有字符名都要大写 

  ```
  define('PI', '3.1415926');
  
    // PI = 123456; // 常量不能修改
    // unset(PI); // 常量不能删除
    // define('PI', '666');  // 常量不能重复定义
  
    echo PI;
  ```

  

## PHP内置函数

#### 1 数学函数

```
1) max(),min()   分别返回一组数的最大值及最小值；
2) abs() 返回绝对值。
3) floor() 向下取整。
4) ceil()  向上取整。
5) round() 四舍五入。
6) rand()  返回随机数，可以取到两端的值。
```

#### 2 设置时区       

```
1) time()  返回当前的 时间戳(1970到现在的时间的秒数)
2) date(format,time) 格式化一个本地时间或日期
  
格式：Y(年) m(月)  d(日)   H(时)  i(分)  s秒
  
$time=time();//获取时间戳
echo date('Y-m-d H:i:s',$time); //格式化时间戳
```
#### 3 字符串

```
1) str_replace(查找的值，替换的值，执行替换操作的字符)       字符串替换
2) trim(字符串);     去除字符串首尾处的空白字符
3) explode(分割符，执行分割的字符串);        使用一个字符串分割另一个字符串
4) implode(连接符，执行连接的数组);           将一个一维数组的值拼接为字符串
5) substr( 字符串，起始索引，截取长度  );    返回字符串的子串
6) strchr(字符串，标识字符);          从左向右查找指定的字符，并返回该字符后全部字符
7) strrchr(字符串，标识字符);                 从右向左查找指定的字符，并返回该字符后全部字符串
```

#### 4 pre标签

```
希望换行和空格,不进行合并,进行原文格式输出,pre标签,一般用于输出代码段
利用pre标签,进行代码原文输出
```

## php的代码执行过程

```
1) php代码需要放到服务器才会执行
2) php代码需放到php标签内才能执行
3) 服务只会解析php标签内部的代码,php标签外部的所有内容直接原文输出
4) 解析完php代码后,将解析结果和其他内容,全部返回给浏览器解析执行
```

#### 1 include  和include_once  文件引入

作用:  不同的页面中有相同的代码部分,可以将其分离为单个文件;需要调用时,include  和include_once 引入对应的文件即可调用,提高代码复用率.

语法:   include / include_once   "文件的路径"

```
1) 引入php文件,相当于js的script标签引入
2) 引入html文件,将html的全部内容,复制到指定位置
3) 多次引入同一个文件,会对文件重复引入,使用include_once

- 区别: include  可以重复引入文件

- include_once  只引入一次，防止多次引入文件
- php中的函数不可以多次复用
```

#### 2 数据持久化

含义:  将数据存储到硬盘文件中,可以让数据持久保存

```
1) file_get_contents('文件路径') ; 获取文件内容,返回文件内容字符串

2) file_put_contents('文件路径','数据'); 将数据写入文件

3) 如果对复杂数据类型直接进行 写入,会导致数据格式丢失,数据丢失
	● 写入一种有格式的字符串,在字符串中就有数据格式
	● json字符串(有特定格式的字符串),方便转换成数组

  ▲ 存的时候,只能存储字符串;存有格式的字符串(json字符串)
  ▲ json字符串(有特定格式的字符串)
  ▲ json_encode($arr);可以将复杂数据类型编码成json 字符串
  ▲ 要求所有的键,必须用双引号引起来
  ▲ json_decode(json字符串,是否转换成数组)
```

#### 3 表单提交

- 前端页面：
  - action :  提交地址
  - method : 提交方式
  - name：  name属性必写
  - enctype:   上传文件必写


- 后面处理表单常用的超全局变量
  - $_GET
  - $_POST 
  - $_FILES
  - $_SESSION
  - $_COOKIE  可以获取cookie中数据 

#### form 表单

作用:收集用户信息,将来提交给后台

```
表单的三大属性: 
1) action:  指定表单提交的地址,如果不设置提交到当前页面
2) method:  指定表单的提交方式;  get / post  
3) name:  给表单元素设置,将来便于后台获取数据
```

#### 4 超全局变量

```
1) $_GET  超全局变量  获取到是用户通过get提交的数据,是一个关联数组

2) $_POST 超全局变量  获取到是用户通过post提交的数据, 是一个关联数组

3) $_FILES 超全局变量 通过前端提交时设置的 name ,可以从$_FILES中获取到提交的文件信息  是二维数组
```

#### 5 文件的上传的要求

```
1) 提交方式必须为post
2) 指定name属性
3) 给form指定 enctype="multipart/form-data"属性
4) action属性
```

#### 6 单选框

```
1) name属性用来分组,还可以用于给后台提交数据
2) 必须设置 value;用于将来提交到后台
3) checked 默认选中

```

#### 7 复选框

```
1) 必须指定name
2) checked可以多选,需要指定name名格式为name[],最终后台才能以数组的方式接收
3) checked 默认选中

```

#### 8 下拉框

```
1) name值要给select 设
2) value 值给option设
3) selected 默认选中

```

## http协议

含义: 是超文本传输协议,就是一套标准,规定浏览器端和服务器端请求(request)和响应(response)的标准规定了请求和响应的格式

常用请求方法: GET  ,POST

#### 1 请求报文: 响应报文分析

```
1) 请求行  (包括请求方式  请求地址  协议 )
2) 请求头  (作用:告诉服务器端一些浏览器端的信息)
3) 请求体  (post请求传输给后台的数据)

```

#### 2 响应报文

```
1) 状态行  (包括协议  状态码  状态文本)
2) 响应头  (作用:告诉浏览器端一些服务器端的信息)
3) 响应体  (后台传输给前端的内容)

```

#### 3 get和post的区别

```
1) get用于服务器查询数据,post用于向服务器提交数据
2) get通过url传递数据,post通过http请求体传输数据
3) get传输数据不超过4k,post传输数据较大
4) get安全性低,在url中容易暴露,post安全性较高
```

#### 4 状态码

```
1) 200 响应的状态
2) 200表示成功
3) 302页面重定向
4) 304表示文档未修改
5) 404表示找不到资源
6) 500表示服务端错误
```

## mysql数据库

专门用来存储 管理数据的仓库(空间),按照数据结构来组织 存储和管理,可以实现高效存取数据.英文:Database,DB

#### 1 分类

```
1) 关系型数据库:
    - 当前使用范围最广的数据库,基于表,按照关系模型(数据之间表与表存在联系)组织的数据库
    - 基于表与表之间可以存在关系进行多表查询的存储方式,适合较为复杂的存储 mysql ,SQL Server ,Oracle
    
2) 非关系型数据库:
	- 基于键值对的存储方式,数据之间没有耦合性,执行效率高,  mongodb

```

#### 2 数据库的组织架构

```
1) 数据表(table)	
  - 一个数据库中可以有很多个表
  - 表是以行和列的形式组织起来的数据的集合;项目一般需要不同的数据表,将数据分布存储在不同的数据表中
  - 如:订单表  用户信息表 商品表 .....

2) 记录 (row record)	
  - 表中的每一行叫做一条"记录"
  - 通俗理解就是 行

3) 字段(column field)
  - 字段比记录更小的单位,多个字段集合组成记录,即数据项
  - 通过理解就是  一格数据  , 多个就组成列
  
4) 字段的约束
  - not null:不能为空
  - default: 设置默认值
  - primary key: 主键,不能重复,不能为空
  - auto_increment 自动增长,必须是Int类型
  - unique key: 唯一
  
```

#### 3 sql语句对数据库的增删改查

注:  注释用--          语句结束加分号

```
1) 添加数据  insert
  - 语法:  insert into 表名 （字段。。。） values (值， 值)
		  insert into 表名 (字符1,字段2...) values (值1,值2);
  
2) 修改数据  update 
  - update  表名  set  字段名称1=值1,字段名称2=值2... where 条件
  
3) 删除数据  delete
  - delete from 表名   where 条件
  - delete  from  默认清空表格
  
4) 查询数据  select 
  - selete *from 表格 //查询所有数据
  - selete  字段列表 from 表格  where 条件
  - 条件可以是 and并且/ or或者/ =等于/ != 不等于
```

```
and  or  !  与或非 
id  in (3,5,9)  一对多匹配
模糊匹配
where  name  like  '%春%';

select count(*) as total  from 表名；
```

####  4 查询语句的其他语法

like  %:  模糊度

```
select *from stu where name like '张%' //以..开头
select *from stu where name like '%张' //以..结尾
select *from stu where name like '%张%' //包含
```

in 语法:  一次查询多个符合条件的数据

```
select 字段列表 from 表格名 where 字段 in (value1,value2);
select * from 表名 where id in (5,7,8);
```

count() :  获取返回数据的总条数

```
select count(*) as "总条数" from 表名
```

排序

```
select * from 表名 order by (字段名称) age   //默认升序排序
select * from 表名 order by (字段名称) age  desc  //降序排序
```

limit 对查询的 结果集 进行截取:  截取索引(从0开始)  , 截取几个

```
select * from 表名 limit 0 ,3
```

联合查询(多个表联合查询)

- 主键:当前表中的唯一标识,不能为空,不能重复
- 外键:别的表中的主键,通过外键可以建立和其他表的关系,可以进行多个表联合查询

```
select 字段列表 from 表A join 表B on A.字段=B.字段 where 条件

eg: select teacher.*, class.classname, class.total from teacher join class   -- 查询语句
on teacher.classid = class.id   -- 联合条件s
where teacher.id = 1;   -- 查询条件
```

## php操作数据库思路

```
1) 连接数据库
   $link=@mysqli_connect(ip地址,用户名,密码,数据库名,端口(默认3306))   连接数据库 ; 
   连接成功返回一个连接对象 , 连接失败返回false
   @错误抑制符,可以抑制错误的输出
   mysqli_error($link) ,返回错误信息
   
2) 准备sql语句
  eg: $id = 10 ;
      $sql = 'delete from stu where id = $id';
	
3) 执行sql语句
   mysqli_query(连接对象,sql语句) ;
   执行非查询语句,返回true或者false 
   执行查询语句返回的是查询结果
4) 获取执行的结果并分析
   - mysqli_fetch_assoc(返回查询结果集);  取结果集的数据,每次只拿取一条数据信息,返回一个关联数组,如果没取到就返回null
   - mysqli_num_rows(返回查询结果集) , 返回结果集的行数

5) 关闭数据库连接
   mysqli_close($link) 
```

#### 1 sql操作注意事项

```
1) 使用php发生sql语句前,可以先打印sql语句,检查语句的正确性
2) 使用变量拼接sql语句时,字段为字符串类型的,需要使用双/单引号
3) 外双内单原则

```

#### 2 隐藏域

```
含义: 有些时候需要传递参数给后台,但是这个参数又不希望被用户看到,不希望被修改,可以用隐藏域
eg: <input type='hidden' name='id' value = '<?php echo $id ?>'>
```

## cookie和session

- 会话:浏览器和服务器的数据交流
- http协议特点:无状态的,多次请求之间没有相关性
- 例如:同一用户请求同一网站的不同页面,服务器无法识别是否是同一用户发起的请求

#### 1 区别

```
1) cookie:在浏览器端的存储数据的容器
2) session:在服务器端的存储数据的容器
```

#### 2 cookie

特点: 在cookie中数据设置后,浏览器再次请求服务器指定页面时,会自动携带cookie中的数据到服务器,在服务器中可以获取cookie中的数据

js操作cookie

```
//设置
document.cookie = "name=zs";
//获取
document.cookie;
```

 jquery.cookie.js插件操作cookie

```
//设置cookie
$.cookie(键,值,{expires:过期天数});

//获取
$.cookie(键)

//删除
$.removeCookie(key)
```

php操作cookie

```
// 设置setcookie(key,value,过期的时间戳(1970开始))

// 设置七天后失效,需要加上7*24*3600  (秒为单位)
setcookie('myname','keke',time()+7*24*3600);

// 如果设置成过去的时间,会将已设置的cookie销毁
setcookie('nyname',''.'time()-1')

//获取,可以通过超全局变量$cookie
echo $_COOKIE['myname'];
```

注意点:

```
1) cookie中的数据可以被同一个网站的页面共享
2) 不同浏览器的cookie不能共享
3) cookie的数据存储在浏览器中,每次请求 服务器,在请求报文中携带cookie的数据,发送给服务器
4) 服务器端无法直接操作cookie,是通过在服务器端设置响应头的方式,通知浏览器对cookie进行设置
5) cookie中的数据有效期限,不设置是会话级别的,浏览器关闭,会话结束,数据销毁.
6) cookie存储容量小,约4kb

```

特点:

```
cookie特点：
	1- 同一个网站中的多个页面的cookie可以共享
	2- 内存小,大概4kb左右
 	3- cookie中的数据会自动添加到请求报文中,传递给服务器,供服务器使用
 	4- 服务器可以设置响应报文,在设置响应报文中进行设置,浏览器获取响应报文,获取响应报文后会根据要求设置cookie中添加数据
```

#### 3 session

+ session容器是一个数组的形式,通过超全局变量$_SESSION进行取值和设置

+ session在使用前,必须先session_start开启session机制

+ session中的数据可以被当前网站所共享

  注:  在每个页面中,需要访问session之前,必须先开启session=>session_start();

```
php操作session
1)设置session
$_SESSION['name']= 'hehe';

2) 获取session
echo $_SESSION['name'];

3)删除
unset($_SESSION['name']);

4)清空
$_SESSION=[]

5)销毁session 销毁的是存储session的文件

```

cookie 和 session 配合 实现登录状态保持 的过程

```
1-用户登陆成功,开启session记录用户登陆标记;
session_start();
$_SESSION['user_id'] = id;
2-用户下次登陆个人中心
 1 请求时先判断用户是否携带sessionId;
 2 判断sessionId是否和后台一致
 if(!empty($_COOKIE['PHPSESSID'])){
     //判断是否和后台对应一致
   if(empty($_SESSION['user_id'])){
       //去登陆
   }
 }else{
     //去登陆
 }
```

####  4 开启session_start()做了三件事

```
1) 创建一个sessionID,就是随机字符串
2) 会根据sessionID创建一个文件,用来存储session数据
3) 会进行设置响应头的set-cookie内容就是sessionID将来浏览器接收到响应头,会根据set-cookie来设置cookie,将sessionID存在cookie中
```

#### 5 php页面跳转

```
header('refresh: 时间(秒);url=地址')
```

## AJAX

不是一门新的语言,而是对现有技术的综合利用,本质上是在HTTP协议的基础上以异步的方式与服务器进行通信.

+ 原生Ajax(XMLhttpRequest对象

  ```
  var xhr = new XMLhttpRequest();
  xhr.open('get','01.php');
  //post设置请求头
  xhr.setRequestHeader()
  //get
  xhr.send(null);
  //post
  xhr.send(参数);
  //监听响应状态,处理数据
  xhr.onreadystatechange = function(){
      if(xhr.readyState === 4 && xhr.status === 200){
          var text = xhr.responseText;
      }
  }
  ```

#### 1 同步与异步

```
1) 同步:指的就是事情要一件一件做,等做完前一件才能做后一件任务
2) 异步:不受当前任务的影响,两件事情同时进行,做一件事情时,不影响另一件事情的进行.
3) 编程中:异步程序代码执行时不会阻塞其他程序代码执行,从而提升整体执行效率.

```

#### 2 ajax发送请求-----get

本质上就是发送一个http请求,肯定要遵循http协议

```
1) 创建XMLHttpRequest
   var xhr = new XMLHttpRequest();
   
2) 请求行
   open(type,url,同步/异步);       默认true异步
eg: open('get','03-get.php');
注: 如果要传参数时,get需要在地址栏中,拼接参数
eg: open('get','03-get.php?username=hehe&password=123');

3) 请求头
get请求不需要设置请求头,因为没有请求体不用设置content-type

4) 请求体
get没有请求体,因为请求参数在地址栏中
xhr.send(null);
   
```

#### 3 ajax发送请求-------post

```
1) 创建XMLHttpRequest
   var xhr = new XMLHttpRequest();
   
2) 请求行(请求方式,请求地址)
   open(type,url,同步/异步);       默认true异步
eg: open('get','03-get.php');

3) 请求头--post有请求体
需要设置请求体的编码方式,需要设置请求头中的content-type
xhr.setRequestHeader('content-type','application/X-www-form-urlencoded')

4) 请求体
xhr.send(请求体);
eg: xhr.send('username=pp&password=666');
```

#### 4 ajax发送请求的响应状态

监听响应状态:  xhr.onreadystatechange

readyState :记录了XMLHttpRequest对象的当前状态

```
readyState有五种可能的值：

1) xhr.readyState = 0时，UNSENT open尚未调用
2) xhr.readyState = 1时，OPENED open已调用
3) xhr.readyState = 2时，HEADERS_RECEIVED 接收到头信息
4) xhr.readyState = 3时，LOADING 接收到响应主体
5) xhr.readyState = 4时，DONE 响应完成
使用最多的是 4 的状态
```

#### 5 json数据格式的特点:

```3
1) 键值对的组,键值对之间用逗号隔开
2) 所有的键都必须用双引号引起来(为了通用)
3) json数据格式可以是对象或者是数组
```

#### 6 json数据格式与数组或对象的转换

```
1) json数据格式转换为js对象或者数组
JSON.stringify(obj/arr)

2) js对象或者数组转换为json数据格式
JSON.parse(jsonstr)
```

#### 7 json数据格式与php数组的转换

```
1) json数组格式转换为php数组
json_decode($jsonstr,是否转换成数组);

2) php数组转换为json数据格式
json_encode($arr);
```

#### 8 eval()----也可以解析json数据格式

```
1) eval()函数可计算某个字符串,并执行其中的js代码;
2) eval()的参数是一个字符串,这个字符串是需要执行的表达式或者语句;
3) 使用这个方法,也可以将json字符串转换成js对象

eg: console.log(eval("{}")); //undefined,因为将{}当成了代码块
	console.log(eval("({})"));obj,用引号引起来了就可以解析了
```

#### 9 js页面跳转

```
js的3秒跳转页面

setTimeout(function(){
	location.href = 'http://jsonstr';
})
```

#### 10 表单序列化

注:  使用之前,必须在外面套一个form表单而且要指定name

```
$('form').serialize()
serialize可以将一个form表单中,所有添加了name属性的input框中的值,全部进行拼接,拼接ajax所需要的参数格式

```

```
$.ajax({
  type:"ge",
  url:"...",
  data:$(from).serialize(),
  dataType:"json",
  success:function(info){
    console.log(info);
  }
})
```

#### 11 模版引擎

```
1) 是为了使用户界面与业务数据(内容)分离而产生的,它可以生成特定格式的文档,用于网站的模版引擎就会生成一个标准的HTML文档
2) 我们通过ajax获取到数据后,需要把数据渲染到页面上,在学习模版引擎前,一般都是拼接字符串,不适应复杂页面结果
3) 常见的模版引擎:
  - Baidu Template;
  - velocity.js;
  - ArtTemplate(使用最广泛)

```

#### 12 Template入门----artTemplate.js

```
1) 引入template模版引擎的js文件
<script src="artTemplate.js"></script>

2) 准备模版
- 指定type属性为text/html,这一段script标签不会被解析,也不会执行
<script type="text/html" id="myTmp">
  <p>姓名：隔壁老王</p>
  <p>年龄：18</p>
  <p>技能：查水表</p>
  <p>描述：年轻力气壮</p>
</script>

3) 获取到数据
通过ajax获取后台数据,数据是会发送变化的
$.ajax({
  type:"ge",
  url:"...",
  data:$(from).serialize(),
  dataType:"json",
  success:function(info){
    console.log(info);
  }
})

4) 将数据和模版进行绑定
- 使用template(模版id,数据对象)
- 第一个参数是模版id,
- 第二个参数是数据对象
- 返回一个根据模版生成的html形式字符串
var htmlStr = template("tpl",obj)
//第二个参数必须是数据对象,如果不是数据对象,需要转换成数据对象
var html = template("tpl",{data:info})

5) 处理模版中的数据
将数据对象中的属性名作为变量添加到数据模版中对应的数据值位置,一般使用标准语法
<script type="text/html" id="myTmp">
  <p>姓名：{{username}}</p>
  <p>年龄：{{age}}</p>
  <p>技能：{{skill}}</p>
  <p>描述：{{desc}}</p>
</script>

6)  将数据渲染到页面中
var box = document.querySelector("div");
box.innerHTML = htmlStr;
```

#### 13 template标准语法

if语句

```
{{if gender = "男"}}
 <div class="man">
 {{else}}
 <div class="woman">
 {{/if}}
```

each语句

```
//{{each data $value $index}}
//$value获取值,$index获取下标
//也可以自定义
{{each data v i}}
<li>
  <a href="{{v.url}}">
    <img src="{{v.src}}" alt="">
    <p>{{v.content}}</p>
   </a>
 </li>
 {{/each}}
```

#### 14 同源

- 同源策略:  目前所有浏览器都实行这个策略.同源策略:最初,它的含义,A网页设置的cookie,B网页不能打开,除非这两个网页"同源"

- 所谓"同源"指的是"三个相同":

  ```
  1) 协议相同
  2) 域名相同
  3) 端口相同

  ```

- 同源策略的目的:  是为了保证用户信息的安全,防止恶意的网站窃取数据

- 同源策略的限范围:

  - 随着互联网的发展,"同源策略"越来越严格,目前,如果非同源,以下三种行为都收到限制:
    - Cookie,LocalStorage 和 IndexDB 无法读取
    - DOM 无法获取
    - AJAX 请求在浏览器端有跨域限制

#### 15 跨域

- 跨域:  是浏览器对于js的同源策略的限制,所以就出现跨域
- jsonp:  全称是JSON with Padding,是为了解决跨域请求资源而产生的解决方案,是一种依靠开发人员创造出来的一种非官方跨域数据交互协议.
- jsonp原理:

```
1) 初步演化: 
  - 1 利用script标签 src属性可以跨域的特性,实现跨域请求数据
  - 2 可以动态创建script标签,利用 src 请求服务器端的js内容的字符串返回回来
  - 3 浏览器就可以解析执行 js的内容
  
2) 后来jsonp:
  - 前端工作:
    - 1 定义一个全局函数,传递形参接收后台传递的数据
    - 2 再通过script src请求后台的同时,拼接上参数:callback=函数名
  - 后台工作:
    - 1 获取到通过callback传递过来的函数名
    - 2 返回函数调用,将返回的json数据作为实参传递到调用函数中返回给前端
    - 补充:相当于前端接收到数据,调用了全局函数

```

