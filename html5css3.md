# css5

#### 1. 私有前缀

```
	在标准还未确定时，部分浏览器已经根据最初草案实现了部分功能，为了与之后确定下来的标准进行兼容，所以每种浏览器使用了自己的私有前缀与标准进行区分，当标准确立后，各大浏览器将逐步支持不带前缀的css3新属性

	目前已有很多私有前缀可以不写了，但为了兼容老版本的浏览器，可以仍沿用私有前缀和标准方法，逐渐过渡。

	一般来说，CSS3主要是为移动端而生的，因此我们在移动端没必要写太多的前缀，因为移动端的ios和Android的浏览器都是webkit内核
谷歌，苹果浏览器：-webkit-
火狐浏览器：-moz-
IE浏览器：-ms-
欧朋浏览器：-o-
```

#### 2. 选择器

```
（1）关系选择器
```

![img](images/s1.png)

```
（2）属性选择器
```

![img](images/s2.png)

```
（3）伪类选择器------child系列语法
注：伪类选择器的语法都带有一个 冒号 :
```

![img](images/s3.png)

```
（4） 其他伪类选择器
    :of-type系列，  用法与child系列很像，但是找的是子元素中对应类型			
        区别：兄弟元素不是一种类型的情况下：
        E:nth-child(n)  获取第n个元素 并且类型必须是E
        E:nth-of-type(n)  获取第n个E元素 
    :focus    查找获取到焦点的文本框
    :checked 获得选中的checkbox
    :disabled 获得不可用的框
    :enabled 获得可用的框
    :not(selector) 选择不匹配selector的那些元素
    :target  获取当前活跃的锚链接	
    
（5）伪元素选择器
	在元素内部的最前面（before）或者最后面（after）添加一个虚拟的标签
	
 关于:before与::before的区别：
	:before是css2中伪元素的写法，但是呢，在css3中严格规定，伪类采用单冒号，伪元素需要使用双冒号。为了兼容旧的代码，当浏览器碰到了:before之后，会自动的转换成::before。
	如果需要兼容老的浏览器，比如IE678，推荐使用:before
	如果不需要兼容老的浏览器，比如移动端，推荐使用::before

（6）其他伪元素选择器
    ::first-letter  :获取元素的第一个字符
    ::first-line   :获取元素的第一行
    ::selection   ：获取选中的元素
```

#### 3. css3阴影------文字阴影text-shadow

```
text-shadow: X轴偏移 Y轴偏移 羽化大小 颜色  
注：阴影可以写多个，中间用逗号隔开
```

#### 4. css阴影------盒子阴影box-shadow

```
box-shadow: X轴偏移 Y轴偏移 羽化大小 阴影大小 颜色 内外阴影
```

#### 5. css3阴影------边框图片border-image

```
注：遵从的是九宫格式切图，上下左右分别来一刀，量取向上右下左的距离

border-image-source:url('border.png'); 图片路径
border-image-slice:26 12 14 12;图片切割，不要带单位
border-image-repeat:round没有瑕疵/stretch默认拉伸/repeat 平铺（可能有瑕疵）

简写：border-image:border-image-source border-image-slice border-image-repeat.
```

#### 6. 背景图片缩放------background-size

```
background-size：像素/百分比
background-size: contain;//保证等比例缩放,但是会出现留白
background-size: cover;//保证等比例缩放,不会留白，但是出现有一部分图片不显示

//注意：这两种设置方式会导致图片失真。
/*background-size:设置背景图片的大小*/
background-size: 600px 400px;

/* 百分比是相对于盒子自身的宽度和高度 */
background-size: 100% 100%;

```

#### 7. 背景区域大小-------background-clip

```
/*盒子的背景区域是整个盒子，包括边框和padding*/
background-clip: border-box;   //(默认值)设置背景区域包括了边框
background-clip: padding-box;  //背景区域只包含padding和content
background-clip: content-box;  //背景区域只包含content
```

#### 8. 多重背景

```
background设置背景的时候，可以设置多个背景图片，使用逗号隔开。注意颜色只能设置一次，并且通常来说，颜色都是在最后面进行设置

eg:  background: url(images/mn1.jpg) no-repeat top left, 		            url("images/mn2.jpg") no-repeat right bottom, pink;
```

#### 9. css3渐变------线性渐变和径向渐变

```
（1）inear-gradient指沿着某条直线朝一个方向产生的渐变效果。
//注意：渐变实际上相当与一张图片，因为需要加给background-image才会生效

//1. 最简单的渐变
background-image: linear-gradient(red, green);
//2. 渐变的方向to
background-image: linear-gradient(to right, red, green);
//3. 渐变的角度
background-image: linear-gradient(45deg, red, green);
//4. 渐变的范围
background-image: linear-gradient(to right, red 20%, green 80%)
//5. 渐变颜色的范围
background-image: linear-gradient(to right, red 20%, green 20%)

(2) radial-gradient指从一个中心点开始沿着四周产生渐变效果
/*1. 最简单的渐变*/
background-image: radial-gradient(red, green);
/*2. 指定圆的半径和圆心 at*/
background-image: radial-gradient(200px at center, red, green);
/*3. 指定椭圆*/
background-image: radial-gradient(200px 80px at center, red, green);
/*4. 指定范围*/
background-image: radial-gradient(200px at center, green 50%, red 50%);
```

#### 10. css3过渡------transition

```
(1) transition-property：设置过渡属性
transition-property:all;   /*也可以是width,height*/

(2) transition-duration:设置过渡时间
transition-duration:1s;

(3) transition-delay：设置过渡延时
transition-delay:2s;

(4) transition-timing-function:设置过渡的速度
transition-timing-function:linear;
/*linear，ease(默认)，ease-in，ease-out，ease-in-out， steps(10)*/

(5) 复合写法
/* 属性 时间 延时 速度 */
transition: width 1s 3s linear;
```

#### 11. 2D转换------scale缩放

```
transform: scaleX(0.5);/*让宽度变化*/
transform: scaleY(0.5);/*让高度变化，注意不能写多个transform，不然会覆盖。*/
transform: scale(0.5);/*让宽度和高度同时变化*/

注:
  - scale接收的值是倍数，因此没有单位
  - scale可以是一个值，如果是一个值，不是说仅仅缩放宽度，高度也会等比例的缩放。
  - 可以通过transform-origin:方位名词/像素 设定旋转原点

```

#### 12. 2D转换------translate平移

```
transform: translateX(100px);
transform: translateY(100px);
transform: translate(100px, 100px);
transform: translate(50%, 50%);

注:
- translate的值可以是px，也可以是百分比，如果是百分比，那么参照的是自身的宽高。
- translate移动的元素并不会影响其他盒子，类似于相对定位。

```

#### 13. 2D转换------rotate旋转

```
transform: rotate(360deg);//旋转360度
transform: rotate(-360deg);//逆时针旋转360度

注:
    - 单位是deg，角度，不是px
    - 正值顺时针转，负值逆时针转
    - 可以通过transform-origin设定旋转原点

```

#### 14. 2D转换------skew斜切(变形)

```
transform: skewX(30deg);//在水平方向倾斜30deg
transform: skewY(30deg);//在垂直方向倾斜30deg
```

#### 15. 2D转换------transform-origin转换原点

```
transform-origin: center center;
transform-origin: 40px 40px;
```

#### 16. 2D转换的复合写法------transform

```
transform: translateX(800px) scale(1.5) rotate(360deg) ;

注:
   - transform属性只能写一个，如果写了多个会覆盖
   - transform属性可以连写，但是顺序对效果影响的，因为它会在第一个效果的基础上		执行第二个效果，然后执行第三个效果
   - 如果对transform进行过渡效果的时候，初始状态和结束状态一一对应
```

#### 17. 3D转换------rotate旋转

```
transform: rotate(45deg);// 让元素在平面2D中旋转
transform: rotateX(45deg);// 让元素沿着X轴转45度
transform: rotateY(45deg);// 让元素沿着Y轴转45度
transform: rotateZ(45deg);// 让元素沿着Z轴转45度
```

#### 18. 3D转换------perspective透视

```
注:	当为元素定义 perspective 属性时，其子元素会获得透视效果，而不是元素本身。
	 perspective : 像素    //取值越大,视觉越模糊,近大远小
perspective：900px;	 //通常
```

#### 19. 3D转换------translate平移

```
transform: translateX(45px);   //沿着X轴的正方向移动45px
transform: translateY(45px);   //沿着Y轴的正方向移动45px
transform: translateZ(45px);   //沿着Z轴的正方向移动45px

```

#### 20. 3D转换------transform-style

```
flat:默认值，2d显示
preserve-3d: 3d显示
```

#### 21. transform-style与perspective的区别

```
透视：透视只是相当于设置了一个距离，辅助我们查看3D效果的工具，呈现效果为近大远小

preserve-3d:给父盒子添加，让子元素保留3D的位置，说白了，只有设置了preserve-3d，这个元素才能被称之为3d元素。

//一个3d元素可以没有perspective，但是不能没有transform-style
```

#### 22. 3D转换------animation动画

```
animation-name:动画名称，由@keyframes定义的
animation-duration：动画的持续时间
animation-timing-function：动画的过渡类型   ()
animation-delay：动画的延迟时间
animation-iteration-count：动画的循环次数  (默认一次/inifite)
animation-direction：设置动画在循环中是否反向运动(running(默认)/paused(暂停))
animation-fill-mode：设置动画时间之外的状态(forwards/backwards/none/both)
animattion-play-state:设置动画的状态。
```

#### 23. 3D转换------动画库的使用

```
(1) 引包animation.css
(2) 添加类"animation 当前效果类"
```

#### 24.  弹性布局------flex-direction调节主轴方向

```
flex-direction: row            //主轴方向为水平向右(默认)
                column         //主轴方向为竖直向下
                row-reverse    //主轴方向为水平向左
                column-reverse //主轴方向是竖直向上。
```

#### 25. 弹性布局------justify-content主轴方向的对齐方式

```
justify-content: flex-start     //弹性盒子元素将向起始位置对齐(默认)
                  flex-end   `  //弹性盒子元素将向结束位置对齐。
                  center        //弹性盒子元素将向行中间位置对齐
                  space-around  // 弹性盒子元素会平均地分布在行里
                  space-between //第一个贴左边，最后一个贴右边，其他盒子均									分,保证每个盒子之间的空隙是相等的。
```

#### 26. 弹性布局------align-items调整侧轴的对其方式

```
align-items:flex-start  // 元素在侧轴的起始位置对其。 (默认)
            flex-end   // 元素在侧轴的结束位置对其。
            center     // 元素在侧轴上居中对其。
            stretch    // 元素的高度会被拉伸到最大（不能给死高度）。			
```

#### 27. 弹性布局------flex-wrap控制flex容器是单行或者多行

```
flex-wrap: 	nowrap  //不换行（默认），会压缩子盒子的宽度。
			wrap    // 当宽度不够的时候，会换行。
```

#### 28. 弹性布局------align-content设置多行的flex容器的排列方式

```
align-content:flex-start     // 各行向侧轴的起始位置堆叠。 
              flex-end       // 各行向弹性盒容器的结束位置堆叠。
              center         // 各行向弹性盒容器的中间位置堆叠。
              space-between  // 各行在侧轴中平均分布。 
              space-around   // 第一行贴上边，最后一个行贴下边,其他行在弹性盒容器中平均分布。 
              stretch        //拉伸，不设置高度的情况下。	
```

#### 29. 弹性布局------align-items与align-content的区别

```
align-items:调整的是侧轴的对其方式，不换行一般用align-items
align-content:必须是多行才生效，如果单行，没有效果。换行了就用align-content
```

#### 30. 弹性布局------flex属性设置子盒子如何分配主轴空间

```
复合写法
flex:  flex-frow flex-shrink flex-basis
flex: 1
```

#### 31. 弹性布局------order属性定义项目的排列顺序

```
注: 数值越小，排列越靠前，默认为0。
order:1;
```

#### 32. 弹性布局-------flex-grow分剩余空间

```
注: 占分量
flex-grow:1;
```

#### 33.弹性布局-------flex-shrink控制项目缩放

```
flex-shrink:0(不缩放)/默认缩放
```

#### 34. 弹性布局------flex-basis设置项目宽度

```
flex-basis:像素
```

#### 35. 弹性布局------align-self设置在侧轴的位置

```
注: align-self也是用于设置在侧轴的位置，但是align-self给子元素设置，优先级比align-items的优先级高。

取值和align-items一样
```

# html5

#### 1. html5------语义化标签

```
header
footer
nav 导航
section 区块
aside 侧边栏
article 文章
```

#### 2. html5------兼容性处理

```
<!--[if lte IE 8]>
    <script src="js/html5shiv.min.js"></script>
<![endif]-->
//当ie浏览器的版本小于等于8的时候，才会引入html5shiv.js
```

#### 3. html5------classList操作类名

```
classList是一个集合，会存储某个元素上所有的类名，使用classList来替代className操作class类

//添加类
node.classList.add("classname");
//移除类
node.classList.remove("classname");
//切换类
node.classList.toggle("classname");
//判断类
node.classList.contains("classname");
```

#### 4. html5------data操作自定义属性

```
<div id="demo" data-name="itcast" data-age="10" data-user-name="hcc">

//var demo = document.querySelector('#demo');
//1、读取 demo.dataset['name'] 或者 demo.dataset['age']
//2、设置demo.dataset['name'] = 'web developer'
//3、demo.dataset['userName']

注:  在data-*属性中，大写字母无效，相当于是小写字母
    在data-中的中划线(-)跟小写字母会转换成更大些字母 data-abc-def === abcDef

```

#### 5. html5-------网络状态

```
navigator.onLine返回用户当前的网络状况，是一个布尔值
1. 如果浏览器连不上网(包括局域网)，就是离线状态，也就是脱机状态，会返回false
2. 否则就是在线状态，返回true

监听网络变化
//网络连接时会被调用
window.addEventListener("online", function () {
    alert("online");
});
//当网络断开时会被调用
window.addEventListener("offline", function () {
    alert("offline");
});
```

#### 6. html5------地理位置

```
HTML5规范提供了一套保护用户隐私的机制。必须先得到用户明确许可，才能获取用户的位置信息。在获取地理位置之前，会询问用户，只有在获得许可之后，才能获取到用户的位置信息。 

H5提供的获取地理位置信息并不是特别的精确，会一定的误差，如果需要非常精确的定位，还是需要使用安卓或者ios，访问基于操作系统的方法。

相关方法
//successCallback:获取成功后会调用,并返回一个position对象，里面包含了地理位置信息
//获取失败了会调用，并返回error对象，里面包含了错误信息。
//获取当前的地理位置信息
navigator.geolocation.getCurrentPosition(successCallback, errorCallback)
//重复的获取当前的地理位置信息
navigator.geolocation.watchPosition(successCallback, errorCallback)

实例:
navigator.geolocation.getCurrentPosition(function(position){
    // 定位成功会调用该方法
    // position.coords.latitude 纬度
    // position.coords.longitude 经度
    // position.coords.accuracy 精度
    // position.coords.altitude 海拔高度
}, function(error){
    // 定位失败会调用该方法
    // error 是错误信息
});
```

百度地图官网：[http://lbsyun.baidu.com/](http://lbsyun.baidu.com/)

```
1. 在开发中，找到javascript API
2. 直接查看示例demo
3. 复制相应的代码，替换掉秘钥就行，秘钥只需创建一个新的应用就可以了。
```

#### 7. html5------web存储

```
(1) cookie
	传统方式，我们以document.cookie进行存储，但是存储起来特别麻烦，并且，存储大小只有4k。每次请求都会带上cookie

cookie是以字符串形式存在的，这个字符串有固定的格式：key=value;key1=value1;
在获取cookie内容时，一般需要通过正则或者字符串的方法进行处理，转换成对象，最终得到数据。
	
使用cookie：操作太麻烦，最多只能存储4k ,每次请求都会带上cookie，一般只会有sessionID会存储在cookie中   

document.cookie = "name=zhangsan";
document.cookie = "age=18";
document.cookie = "sex=23";

//设置过期时间
document.cookie = 'sex=12;max-age=3600';

//读取cookie
var result = document.cookie;
console.log(result);

(2)sessionStorage与localStorage
HTML5规范提出了解决方案，使用sessionStorage和localStorage存储数据。设置、读取、删除操作很方便

window.sessionStorage的特点:
1. 声明周期为关闭浏览器窗口
2. 不能在多个窗口下共享数据。
3. 大小为5M

window.localStorage的特点:
1. 永久生效，除非手动删除
2. 可以多个窗口共享
3. 大小为5M

window.sessionStorage与window.localStorage的方法:
setItem(key, value) //设置存储内容
getItem(key) //读取存储内容
removeItem(key) //删除键值为key的存储内容
clear() //清空所有存储内容
key(n) //以索引值来获取存储内容
```
#### 8. html5------自定义播放器

```
(1) 全屏切换API：
	video.requestFullScreen()
    div.webkitRequestFullScreen();
    div.mozRequestFullScreen();
(2) 方法：load()、play()、pause()
(3) 属性: 
	currentTime:当前时间
    duration：总长时间
    timeupdate:播放进度更改时触发
    volume：控制音量
```

参考文档
http://www.w3school.com.cn/tags/html_ref_audio_video_dom.asp

主要目的是练习一下video的属性和方法，还有之前我们学过的js

推荐网站：[https://www.awesomes.cn/](https://www.awesomes.cn/video.js

#### 9. html5------文件读取

```
通过FileReader对象我们可以读取本地存储的文件（用户通过input:file上传的文件），可以使用 File 对象来指定所要读取的文件或数据。其中File对象可以是来自用户在一个<input>元素上选择文件后返回的FileList 对象，也可以来自由拖放操作生成的  DataTransfer

(1) file对象
	File对象中包含了文件的最后修改时间、文件名、文件类型等信息。
(2) fileReader对象
	FileReader是一个HTML5新增的对象，用于读取文件（必须通过input:file上传）
```

```
    //创建一个fileReader对象
    var fr = new FileReader();
    //读取文件的两个方法
    readAsText() 以文本的方式读取文件 ,文本文件
    readAsDataURL() 以DataURL形式读取文件，图片，视频
    //文件读取完成事件：
    fr.onload = function(){}
    //当文件读取完成，可以通过result属性获取结果
    fr.result
```

# ES5

#### 1. ES5------数组方法=>foreach

作用: `forEach()` 方法对数组的每个元素执行一次提供的函数。功能等同于`for`循环.

```
应用场景：为一些相同的元素，绑定事件处理器！

var arr = ["张飞","关羽","赵云","马超"];
//第一个参数：element，数组的每一项元素
//第二个参数：index，数组的下标
//第三个参数：array，正在遍历的数组
arr.forEach(function(element, index, array){
  console.log(element, index, array);
});
```

#### 2. ES5------数组方法=>map

作用:  map()方法创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后返回的结果。

```
//需求:遍历数组，求每一项的平方存在于一个数组中

var arr = [1,2,3,4,5];
//第一个参数：element，数组的每一项元素
//第二个参数：index，数组的下标
//第三个参数：array，正在遍历的数组
//返回值：一个新数组，每个元素都是回调函数的结果。
var newArray = arr.map(function(element, index, array){
  return element * element;
});
console.log(newArray);//[1,4,9,16,25]
```

#### 3.ES5------数组方法=>filter

作用: filter用于过滤掉"不合格"的元素,返回一个新数组，如果在回调函数中返回true，那么就留下来，如果返回false，就扔掉

```
//需求：遍历数组，将数组中工资超过5000的值删除[1000, 5000, 20000, 3000, 10000, 800, 1500]

var arr = [1000, 5000, 20000, 3000, 10000, 800, 1500];
//第一个参数：element，数组的每一项元素
//第二个参数：index，数组的下标
//第三个参数：array，正在遍历的数组
//返回值：一个新数组，存储了所有返回true的元素
var newArray = arr.filter(function(element, index, array){
  if(element > 5000) {
    return false;
  }else {
    return true;
  }
});
console.log(newArray);//[1000, 5000, 3000, 800, 1500]
```

#### ES5------数组方法=>some

作用: `some`用于遍历数组，如果有至少一个满足条件，就返回true，否则返回false。

```
//需求：遍历数组，判断数组是否包含奇数，[2,4,6,8,10,9]

var arr = [2,4,6,8,10,21];
//第一个参数：element，数组的每一项元素
//第二个参数：index，数组的下标
//第三个参数：array，正在遍历的数组
//返回值：布尔类型的值，只要有一个回调函数返回true，就返回true
var flag = arr.some(function(element, index, array){
  console.log(element, index, array);
  if(element %2 == 1){
    return true;
  }else {
    return false;
  }
});
console.log(flag);//true
```

####  ES5-------数组方法=>every

作用: `every`用于遍历数组，只有当所有的元素返回true，才返回true，否则返回false。

```
//需求：遍历数组，判断数组是否都是偶数，[2,4,6,8,10,9]

var arr = [2,4,6,8,10,21];
//第一个参数：element，数组的每一项元素
//第二个参数：index，数组的下标
//第三个参数：array，正在遍历的数组
//返回值：布尔类型的值，只有当所有的元素返回true，才返回true，否则返回false。
var flag = arr.every(function(element, index, array){
	console.log(element, index, array);
    if(element %2 == 0){
        return true;
    }else {
        return false;
    }
});
console.log(flag);//false
```