###  JQuery在项目中的常用方法

- 一般在项目中经常通过jquery来实现DOM驱动;相比js原生,实现同一个功能,代码量更少,兼容性更好.



#### 1. JQuery中的$()函数

```
(1) 传入一个匿名函数 => 入口函数,DOM树加载完毕执行,可以避免ajax中通过模版渲染时,获取不到元素的问题
(2) 传入一个DOM对象 => 将DOM对象包装成JQuery对象 , 例如:$(this) / this 的区别
(3) 传入一个选择器形式的字符串 => 获取对应的DOM元素,并且把DOM元素包装成JQuery对象
```
#### 2. JQuery对象

```
(1) 是DOM对象的包装集
(2) 把JQuery对象转换成DOM 对象两种方式: 	I)通过下标获取 => JQuery对象[下标值]  ,返回下标对应的DOM对象
   II)通过get()方法 => JQuery对象.get(下标值) ,返回下标对应的DOM对象

```

#### 3. jquery选择器

作用:为了方便的获取页面元素,并把元素包装成jquery对象,编写程序更加快捷

```
(1) 基本选择器:
		id选择器=>$('#id名')
		标签选择器=>$('标签名')
		类选择器=>('.类名')
		并集选择器=>$(', ,')以逗号隔开
		交集选择器$('div.class') 紧挨着,又叫标签指定式选择器,指定类名为class的div标签  ,两个都要满足.
		
(2) 层级选择器 :
		子代选择器=>(使用 > 号)只找儿子层级元素,不找孙子.
        后代选择器=>(使用空格)找所有后代
        
(3) 筛选选择器(是方法): 
        children() =>找到直接子元素
        find() => 找到后代
        siblings() => 找到兄弟元素,不包括自己
        parent() =>找到直接父元素
        eq(index) =>找到对应下标的元素
      	next() => 下一个兄弟元素
     	index() =>返回对应的索引
     	prevAll() => 返回前面的兄弟
     	nextAll() => 返回后面的兄弟
注:index(): 返回自己的下标,会找到父元素根据父元素数自己的下标是第几个
			如果jquery对象里面只有一个元素,那么就找父亲中自己的下标
			如果jquery对象中有多个元素,那么找第一个元素在自己父元素中的下标
			如果传入的是dom,有范围找这个dom在范围中的下标

```

#### 4. jquery样式操作

```
(1) 设置行内样式
		设置单个样式: jquery对象.css('属性名','属性值')
        设置多个样式: jquery对象.css({属性名:属性值,属性名:属性值})
      
(2) 获取行内样式
		jquery对象.css('属性名')
		
(3) 操作class类名样式方法
	▷ 添加样式类 addclass()
		语法:jquery对象.addclass('类名')  注意:传入参数不需要加点
		
	▷ 移出所有样式类removeclass()
		语法:jquery对象.removeclass();
		注: 如果不传参数,会移除所有的类名;如果传参数,移除指定的类名
		
	▷ 判断是否有样式hasclass()
		语法:jquery对象.removeclass();
		
	▷ 切换样式类toggleclass('类名')
		如果有这个类名则移除改样式,没有就添加改类名
```

#### 5. jquery操作DOM元素

注: 参数:jquery对象 / html形式的字符串 / DOM对象 ;有剪切效果

```
(1) 创建元素:$('html形式的字符串') ,只创建没有添加到DOM树中

(2) 添加元素:
      append()方法: - 语法:JQuery对象.append()
      html()方法:- 语法:jQuery对象.html('html形式的字符串'),会覆盖原来的内容
      
(3) 清空子元素
  	empty()方法:
    - 语法:jQuery对象.empty()
    - 清空指定节点的所有子节点
   
(4) 删除元素
    remove()方法:
    - 语法:jQuery对象.remove(),把自己删除
    
(5) 克隆元素
    clone()方法
    - 语法:jQuery对象.clone(boolean)
    - 传true:会克隆所有内容,注册事件也会一起克隆
    - 传false / 默认: 会克隆所有内容
```

#### 6. jquery动画

注:  以后在执行所有的动画之前,加一个stop(true);

```
(1) 三组基本动画: 第一个参数speed;动画执行时间,ms
				 第二个参数easing;动画执行的方法(linear匀速线性/swing秋千,慢,快,慢   是默认的)
				 第三个参数: 动画执行完毕的回调函数
	▷ 显示与隐藏 => show(),hide(),toggle()切换
	  修改的是 元素 width height, opacity(阴影)
	▷ 滑入与滑出 => slideDown()展示;slideUp()隐藏;slideToggle()切换
	  修改的是height
	▷ 淡入与淡出 => fadeIn()展示,fadeOut()隐藏,fadeToggle()切换
	  修改的是opacity

(2) 自定义动画: animate()
	第一个参数:对象,对象里面写要修改的属性
	第二个参数:动画执行的时间
	第三个参数:动画执行的方式
	第四个参数:动画执行完毕的回调函数
	注: 但是只能修改值是数字的属性

(3) 动画队列
	▷ 为了解决动画冲突的问题,所以所有动画都要一个一个的执行
	▷ 为了解决动画队列导致的问题:用stop()方法:
	  stop();第一个参数:是否清空动画队列;第二个参数:是否跳到当前动画的最终效果	
```

#### 7. 操作元素的属性

```
(1) 添加属性attr()
    - 单个属性:jQuery对象.attr('属性名','属性值')
    - 多个属性:jQuery对象.attr({属性名:属性值})	
    - 可以操作w3c标准和自定义属性
    
(2) 获取属性 => jQuery对象.attr('属性名'),没有返回undefined

(3) 移除属性 => jQuery对象.removeAttr('属性名'),不传就什么都不做

(4) prop()方法:操作checked , selected , disable 这类boolean值类型的属性,不可以操作自定义属性
    - 设置单个属性:jQuery对象.prop('属性名','属性值')
    - 设置多个属性:jQuery对象.prop({属性名 : 属性值})
    - 获取属性:jQuery对象.prop('属性名') ,返回true /false
```

#### 8. jquery操作文本和内容

```
(1) val()方法:用于设置和获取表单元素的值
    - 设置: jQuery对象.val('值')
    - 获取: jQuery对象.val()
    
(2) html()方法
    - 设置内容: jQuery对象.html('html字符串')
    - 获取内容: jQuery对象.html()
    
(3) text()方法
    - 设置内容: jQuery对象.text('文本字符串')
    - 获取内容: jQuery对象.text()

小结:
  - val()操作表单元素
  - html()会识别html结构
  - text()只识别文本
```

#### 9. jQuery操作尺寸

```
(1) width() /  height() 返回元素的content
	设置或返回元素的宽和高 ,返回类型是数值类型
(2) innerWidth(); / innerHeight()   返回元素的content和padding
(3) outerWidth()   /  outerHeight()  返回元素的content + padding +border
(4) outerWidth(true)/outerHeight(true) 返回元素的content +padding + border+ margin
```

#### 10. jquery操作坐标值

```
(1) offset();
	获取/设置元素相对文档document的坐标位置
	获取坐标位置:jquery对象.offset()
	设置坐标位置:jquery对象.offset({left:num,top:num})
	注:如果通过offset()设置坐标,如果元素没有设置定位,默认(position:static),那么就会修改position修改为相对定位,会修改left和top

(2) position()只读;
	获取相对于自己最近的有定位父元素的位置
	语法:jquery对象.position();
	返回值为对象{left:num,top:num}

(3) scrollTop();
	获取/设置元素的内容相对底部滚动出去的距离
	设置:jquery对象.scrollTop(num);  
	获取:jquery对象.scrollTop();

(4) scrollLeft();
	获取/设置元素的内容相对左边滚动出去的距离
	设置:jquery对象.scrollLeft(num)
	获取:jquery对象.scrollLeft()
```

#### 11. jquery事件

```
(1) 注册事件
    on()方法:可以注册多个,空格隔开
    - 语法:$('已经存在的父盒子').on('事件类型','触发事件子元素',function(){})
    - 参数:
    - 第一个参数：events，绑定事件的名称可以是由空格分隔的多个事件
    - 第二个参数：selector, 执行事件的后代元素（可选），如果没有后代元素，那么事件将有自己执行。
    - 第三个参数：data，传递给处理函数的数据，事件触发的时候通过event.data来使用（不常使用）
    - 第四个参数：handler，事件处理函数
    
(2) 移除事件/解绑事件
    off()方法:
    - 语法: jQuery对象.off(参数)
    - 不传参数:解绑匹配元素的所有事件
    - 传入对应的事件类型:解绑匹配元素的对应事件
    - 传入off("click","**"):解绑所有代理的click事件,元素本身的事件不会被解绑
    
(3) 事件触发
	▷ 简单触发,手动触发
	▷ trigger()
	   语法:jquery对象.trigger('事件名');触发指定事件
	   会冒泡,会有默认行为
	▷ triggerHandler()
	   表单元素input不会发生默认行为
	   不会冒泡,不会发生浏览器默认行为

(4) jQuery事件对象----事件对象属性:
	▷ event.type;事件类型
	▷ event.data;存储绑定事件时传递的附加数据
	▷ event.currentTarget;当前DOM元素,等同于this
	▷ event.delegateTarget;代理对象
	▷ screenX/screenY 鼠标对应设备屏幕最左上角位置
	▷ offsetX/offsetY 鼠标距离元素内的最左上角位置
```

#### 12. end()方法

作用: 筛选选择器会改变jquery对象的DOM对象,想要返回到上一次状态,并且返回匹配元素之前的状态

#### 13. each()方法

```
遍历jquery对象:
语法:jquery对象.each(function(index,element))
```

