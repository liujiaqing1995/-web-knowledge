# web API

## DOM

##### 1. 什么是dom？

```
文档对象模型
```

##### 2. 获取元素

```
1) 获取html: document.documentElement;
2) 获取body：document.body;
3) 获取id： document.getElementById("id名");
4) 获取标签名：document.getElementsByTagName("标签名");//返回是一个伪数组
5) document.getElementsByName("name属性的值") //返回伪数组
6) document/element.getElementsByClassName("类名") //返回伪数组
7) document/element.querySelector("选择器") //返回符合条件的的第一个元素
8) document/element.querySelectorAll("选择器") //返回符合条件的所有内容
```

##### 3. 注册事件

```
1) 事件的三要素: 
	● 事件源 //给谁注册谁就是事件源
	● 事件名 //注册的是什么事件
	● 事件处理函数 //触发事件调用的函数
语法: 事件源.on+事件名 = 事件处理调用函数

注意: 给a注册事件时,可能会触发默认行为,我们需要在事件处理函数中最后一行写上return false.
```

##### 4. 操作非表单元素的属性

```
1) 常用的有: src,id,title,href,
2) innerText: 会覆盖原来的内容,只操作文本
3) innerHTML: 会覆盖原来的内容,不仅操作文本,还能操作标签
```

##### 5. 操作表单元素的属性

```
value,type,disabled,checked,selected
注意: 在html中如果是只需要写属性名的属性,在js中通过true/false控制.
```

##### 6. 操作样式

```
1) style 操作标签的行内样式
2) className 操作标签的类名 //注意: 赋值时,会覆盖原来的
```

##### 7. 操作自定义属性

```
1) 获取自定义属性: getAttribute("属性名");
2) 设置自定义属性: setAttribute("属性名","属性值");
3) 移除自定义属性: removeAttribute("属性名");
```

##### 8. 节点

```
1) 节点: 页面的所有内容都是节点.
2) dom树: 将页面上的所有节点,以一种树状形式组织起来,那么称之为dom树,不在dom树上的,就不会渲染.
```

##### 9. 节点的属性

```
1) 节点类型的属性
	● nodeType //标签节点
	● nodeName //标签节点 大写的标签名
	● nodeValue //标签节点始终是null
2) 节点层级的属性 
	● 找儿子
		childNodes //返回所有子节点
		children //返回所有子元素(ie6-8可能返回注释节点)
	● 爹
		parentNode 
	● 兄弟
		nextElementsibling //下一个兄弟元素(ie8及以前不能用)
		previousElementSibling //上一个兄弟元素(ie8及以前不能用)
```

##### 10. 节点的方法

```
1) appendChild(子元素)
2) insertBefore(添加的子元素,参考子元素)
3) replaceChild(新的子元素,被替换的子元素)
4) removeChild(子元素)移除子元素
5) cloneNode(true/false)如果传入就复制所有内容,否则只复制标签本身
```

##### 11. 动态创建元素

```
1) innerHTML
2) document.write
3) document.createElement
```

##### 12. 鼠标注册事件

```
1) click //鼠标点击事件
2) mouseover //鼠标移入
3) mouseout //鼠标移出
4) focus //鼠标获得焦点
5) mousemove //鼠标移动
```

##### 13.键盘注册事件

```
1) keydown  键盘按下; //不区分大小写
2) keypress 键盘按下; //区分大小写
3) keyup    键盘抬起; //不区分大小写
```

##### 14. 表单注册事件

```
1) onchange  在表单失去焦点时触发
2) oninput 当用户表单输入时触发
```

##### 15. 移除事件

```
1) on + 事件名 = null;
2) removeEventListener('click',事件处理函数,useCapture);
```

##### 16. 注册事件的其他事件

```
1) addEventListener('事件名',事件处理函数,useCapture)
   ● 事件名不加on
   ● 事件处理函数,如果要移除事件,不能使用匿名函数
   ● boolean true就是捕获阶段执行,false就是冒泡阶段执行(默认)
2) addEventListener的优点
   ● 可以给同一个事件注册多个listener
   ● 更精细的控制事件触发阶段
```

#####  17. 事件对象常用属性

```
兼容写法----e= e||window.event
1) e.type 事件类型
2) e.target 事件目标  //兼容:srcElement
3) e.clientX,e.clientY  鼠标在可视区的坐标
4) e.pageX,e.pageY  鼠标在页面的坐标
5) e.keyCode  键盘按键的ASCII码
```

##### 18. 事件对象常用方法

```
1) preventDefault()  阻止默认行为 //在addEventListener里面用
2) stopPropagation()  阻止事件传播
```

##### 19. 事件流

```
1) 捕获阶段
2) 目标阶段
3) 冒泡阶段
4) 事件委托:委托腹肌元素
```

# BOM

##### 1. window的两个事件

```
1) load 页面上所有资源加载完毕才触发//window.onload=function(){}
2) unload 页面关闭的时候触发
```

##### 2. location主要用来操作url

```
1) url的学名: 统一资源定位符(网络上的地址)
2) 完整的url: 协议://域名: 端口号/路径?用户信息#锚点
3) location的属性
   ● href返回浏览器地址栏中完整的url(注:通过给href赋值,可以设置页面跳转)
   ● search返回用户信息
   ● hash 返回锚点
4) location的方法
   ● reload(true/false)传true就是强制刷新,不传/false就是普通刷新
   ● assign("url地址")用于跳转页面  //会记录历史
   ● replace("url地址")用于跳转页面 //不会记录历史
```

##### **3**. history 操作页面的历史

```
1) back();  //回到上一个页面----后退
2) forword();//去往下一个页面---前进
3) go(步数); //步数取正数---前进;步数取负数---后退
```

##### 4. 定时器

```
1) setInterval(时间到了之后要调用的函数,间隔时间(ms)); //每隔一个指定时间就执行一次
2) setTimeout(时间到了之后要调用的函数,间隔时间(ms)); //只执行一次
3) 移除定时器
   ● clearInterval(定时器id);
   ● clearTimeout(定时器id);
```

##### 5. offset系列----不能赋值

```
返回的是css渲染完之后的结果
1) offsetParent离自己最近的定位父盒子
2) offsetWidth盒子的宽度(content+padding+border)
3) offsetHeight盒子的高度(content+padding+border)
4) offsetLeft返回距离offsetParent的左偏移量
5) offsetTop返回距离offsetParent的上偏移量
```

##### 6.client系列----不能赋值

```
返回的是css渲染完之后的结果
1) clientWidth盒子的可视区的宽度(content+padding)
2) clientHeigh盒子的可视区的高度(content+padding)
3) clientLeft左边框的宽度
4) clientTop上边框的高度
```

##### 7.scroll系列---部分可以赋值

```
注: scroll  监听滚动条事件
1) scrollWidth内容的宽度
2) scrollHeight内容的高度
3) scrollLeft内容左边滚动出去的距离---可以赋值
4) scrollTop内容顶部滚动出去的距离---可以赋值
```

##### 8. 获取浏览器可视区的宽/高

```
1) window.innerWidth
2) window.innerHeight
ie8之前的兼容写法: document.documentElement/body.clientWidth
```

##### 9.  获取整个页面滚动出去的距离

```
1) window.pageXoffset
2) window.pageYoffset
ie8之前的兼容写法: document.documentElement.scrollLeft
```

##### 10. in关键字

- 用于判断'属性'in对象   //当前这个属性是否是对象的属性















