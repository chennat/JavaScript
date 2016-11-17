### <scirpt> 位置 ###
* <head> 浏览器解析head部分就会执行这个代码，然后才解析页面的其余部分。
* <body> JavaScript代码在网页读取到该语句的时候就会执行。
* 浏览器解释 html 时是按先后顺序的。 比如进行页面显示初始化的js必须放在head里面，因为初始化都要求提前进行（如给页面body设置css等);而如果是通过事件调用执行的function那么对位置没什么要求的。

### 变量 ###
* 变量用于存储某种/某些数值的存储器 (变量即盒子)

### confirm(str) 对话框 ###
* 常用于允许用户做选择的动作, 弹出的对话框包括一个确定按钮及一个取消按钮.
* str: 即框内显示的文本
* 返回值: 
    - 确认 (true)
    - 取消 (false)


### prompt(str1, str2) 消息对话框 ###
* 常用于询问需要与用户交互的信息。弹出的对话框包含一个确定按钮、取消按钮与一个文本输入框）。
* str1: 对话框中的文本，不可修改; str2：文本框中的内容，可以修改
* 返回值:
    - 确定 (文本框中的内容将作为函数返回值)
    - 取消 (返回null)
    
### window.open([URL], [窗口名称], [参数字符串]) ###
* 查找一个已经存在或者新建的浏览器窗口
* 参数
    - URL: (可选) 在窗口中显示网页的网址或路径. 省略这个参数或值为空字符串, 窗口将不显示任何文档.
    - 窗口名称: (可选) 被打开窗口的名称. 名称由字母, 数字和下划线字符组成.
        + "_top":  在框架网页中的上部窗口显示目标网页
        + "_blank": 在新窗口显示目标网页
        + "_self": 在当前窗口显示目标网页
        + 相同 name 的窗口只能创建一个. 创建多个窗口, name 不能相同, name 名不能含空格
    - 参数字符串: (可选) 设置窗口参数, 用逗号隔开
        + top: number, 窗口顶部离开屏幕顶部的像素数
        + left: number, 窗口左端离开屏幕左端的像素数
        + width: number, 窗口的宽度
        + height: number, 窗口的高度
        + menubar: yes/no, 窗口有没有菜单
        + toolbar: yes/no, 窗口有没有工具条
        + scrollbars: yes/no, 窗口有没有滚动条
        + status: yes/no, 窗口有没有状态栏
* 代码
```js
<script type="text/javascript"> window.open('http://www.imooc.com','_blank','width=300,height=200,menubar=no,toolbar=no, status=no,scrollbars=yes')
<\/script> 
```
    
### window.close() ###
* 用法: 
    - window.close(): 关闭本窗口
    - 窗口对象.close(): 关闭指定窗口

### Object.style.property ###
* 改变 HTML 样式
* 实例:
```js
Object.style.display = none (隐藏) / block (显示为块级元素);
```

### Object.className ###
* 返回或设置元素的 class 属性

### 二维数组 ###
* array[][]: 索引值均从 0 开始.
* 定义方法
```js
//方法一
var myarr = new Array();
for (var i = 0; i < 2; i++) {
    myarr[i] = new Array();
    for (var j = 0; j < 3; j++) {
        myarr[i][j] = i + j;
    }
}

//方法二
var myarr = [[0, 1, 2], [1, 2, 3]];
```

### break ###
* break 退出当前循环体.
* continue 仅跳出本次循环, 整个循环体继续执行.


### 函数调用 ###
*  在 script 标签内调用函数, 直接写上函数名
*  HTML 文档内, 在元素中设置事件属性

### 主要事件 ###
* onclick: 鼠标单击事件
* onmouseover: 鼠标经过事件
* onmouseout: 鼠标移开事件
* onchange: 文本框内容改变事件
* onselect: 文本框内容被选中事件
* onfocus: 光标聚焦
* onblur: 光标离开
* onload: 网页导入 (置于 <body> 标签内, 页面加载完成时触发, 常见用途为向用户弹出对话框, 表明正在加载中)
* onunload: 关闭网页 (当用户退出页面, 如关闭或刷新, 解发事件)

### 对象 ###
* 万物皆对象, 每个对象带有属性和方法.
* Date() 内置对象
    - getDay() 返回星期, 返回是 0~6 数字.
```js
var weekday=["星期日","星期一","星期二","星期三","星期四","星期五","星期六"];
var mydate  = new Date();
mydate.getDay(); // 返回值
mydate.weekday[mydate.getDay()]; // 返回对应星期数.
```
    
    - get/setTime() 返回/设置时间, 单位毫秒数.
```js
var mydate=new Date(); // 获得当前时间 
// 延迟一小时
mydate.setTime(mydate.getTime() + 60 * 60 * 1000); 
```

* String() 内置对象
    - charAt(index) 返回指定位置的单个字符, index 不在 0 与 string.length-1 之间，返回一个空字符串。
    - indexOf(substring, startPos) 返回某个指定的字符串值在字符串中首次出现的位置。否则为 -1;
        + substring (必需) 需检索的字符串值
        + startPos (可选) 指定字符串开始检索的位置.
    - split(separator, limit) 将字符串分割成字符串数组并返回.
        + separator (必需) 从指定位置 (可为)
        + limit (可选) 限制分割的次数.
```js
var mystr="86-010-85468578";
document.write(mystr.split("8") + "<br />");
// output: ,6-010-,546,57, (注意第一个为空字符)
document.write(mystr.split("8", 3));
// output: ,6-010-,546 
```

    - substring(starPos, stopPos) 提取字符串中介于两个指定下标之间的字符
        + startPos (必需) 一个非负的整数 (含 startPos 位置的字符)
        + stopPos (可选) 一个非负的整数 (不含 stopPos 位置的字符)
        + 两个参数相等时, 返回一个空字符串
        + 若 startPos 比 stopPos 大, 交换参数位置.
    - substr(starPos, length)
        + startPos (必需) 起始位置, 必须是数值. 当为负数且绝对值大于字符串长度, 设为 0.
        + length (可选) 提取字符串的长度, 默认为直到字符串尾部.
        + 
* Math 对象
    - 固有的对象, 无需创建即可调用其所有所有属性和方法.
    - Math.ceil() 对一个数值向上取整.
    - Math.floor() 对一个数值向下取整.
    - Math.round() 四舍五入.
    - Math.random() 返回介于 0 (含 0) 到 1 之间的一个随机数

* Array 数组对象
    - 一个对象的集合, 里边的对象可以为不同类型. 每个成员对象都有一个下标, 用来表示它在数组中的位置.
    - 定义方法: 
        + var array = new Array(); // 定义一个空数组
        + var array = new Array(n); // 定义时指定有 n 个空元素的数组
        + var array = [2, 6, 8]; // 直接初始化数据
    - 属性: length
    - 方法: 
        + concat() 连接两个或更多的数组, 并返回新数组
        ```js
        var array = [1, 2, 3];
        array.concant(4, 5);
        output: 1, 2, 3, 4, 5
        ```
        + join() 把数组的所有元素放入一个字符串. 元素通过指定的分隔符进行分隔. 不含参数默认用 , 分隔.
        + pop() 删除并返回数组的最后一个元素
        + push() 向数组的末尾添加一个或更多元素, 并返回新的长度
        + reverse() 颠倒数组中元素的顺序
        + shift() 删除并返回数组的第一元素
        + slice() 返回一个新数组.
            * 一个参数时, 返回指定起始项到尾部的新数组; 当为负数, 从数组的尾部开始算起. (如 -1 即最后一个元素)
            * 两个参数时, 返回指定的起始项到结束项之间的新数组 (不含结束项); 当第二个参数为负数时, 从数组尾部开始算起.
            * .
        + sort(method) 对数组的元素进行一定的排序排列.
            * 不含参数时, 按 unicode 码顺序排列
            * 指定方法函数时, 按指定的排序方法排序.
        + splice() 删除元素, 并向数组添加新元素
        + toSource() 返回该对象的源代码
        + toLocaleString 把数组转换为本地数组, 并返回结果
        + unshift() 向数组的开头添加一个或更多元素, 并返回新的长度
        + valueOf() 返回数组对象的原始值

### window 对象 ###
* window 对象指当前的浏览器窗口
* 方法
    - alert() 显示带有一段消息和一个确认按钮的警告框
    - prompt() 显示可提示用户输入的对话框
    - confirm() 显示带有一段消息以及确认按钮和取消按钮的对话框
    - open() 打开一个新的浏览器窗口或查找一个已命名的窗口
    - close() 关闭浏览器窗口
    - print() 打印当前窗口的内容
    - focus() 把键盘焦点给予一个窗口
    - blur() 把键盘焦点从顶层窗口移开
    - moveBy() 可相对窗口的当前坐标把它移动到指定的像素
    - moveTo() 把窗口的左上角移动到一个指定的坐标
    - resizeBy() 按照指定的像素调整窗口的大小
    - resizeTo() 把窗口的大小调整到指定的宽度和高度
    - scrollBy() 按照指定的像素值来滚动内容
    - scrollTo() 把内容滚动到指定的坐标
    - setInterval() 每隔指定的时间执行代码
    - setTimeout() 在指定的延迟时间之后来执行代码
    - clearInterval() 取消 setInterval() 的设置
    - clearTimeout() 取消 setTimeout() 的设置
* 计时器
    - 类型: 
        + 一次性计时器: 仅在指定的延迟时间之后触发一次
        + 间隔性触发计时器: 每隔一定的时间间隔就触发一次
    - 方法
        + setTimeout(代码, 延迟时间) 在 (页面) 载入后延迟指定时间后, 执行代码 (仅一次), 返回值作为 clearTimeout() 的 ID.
            * 代码: 调用的函数或要执行的代码串
            * 延时时间: 在代码执行前需待的时间 (以毫秒为单位)
        + clearTimeout(id_of_setTimeout)
            * 取消由 setTimeout() 延迟执行代码.
        + setInterval(代码, 交互时间) 从载入页面后每隔指定的时间执行代码.
            * 代码: 要调用的函数或要执行的代码串
            * 交互时间: 周期性执行或调用表达之间的时间间隔 (毫秒单位)
            * 返回值: 一个可以传递给 clearInterval() 从而取消对 "代码"的周期性执行的值 
        ```js
        JS:
        var int = setInterval(clock, 100); // clock() 为函数
        // 第二种表示: setInterval("clock()", 1000)
        function clock() {
            var time = new Date();
            docuemnt.getElementById("clock").value = time;
        }
        //调用 html 文档中 id 为 clock 的项
        ```

        + clearInterval(id_of_setInterval)
            * 取消由 setInterval() 设置的交互时间
        ```js
        var int = setInterval(clock, 100);
        clearInterval(int);
        ```
* History 对象 
    - 记录用户曾经浏览过的页面 (URL), 并可以实现浏览器前进与后退相似导航的功能.
    - 从窗口被打开的那一刻开始记录, 每个浏览窗口, 每个标签页及至每个框架, 都有自己的 history 对象与特定的 window 对象关联.
    - 语法 window.history.[属性|方法] (window 可省略)
        + 属性: length 返回浏览器历史列表中的 URL 数量
        + 方法: 
            * back() 加载 history 列表中的前一个 URL
        ```js
        window.history.back();
        // 相当于
        window.history.go(-1);
        ```
            * forward() 加载 history 列表中的下一个 URL
        ```js
        window.history.forward();
        //相当于
        window.history.go(1);
        ```
            * go() 加载 history 列表中的某个具体的页面
        ```js
        window.history.go(其它值); // 要访问的 URL 在 History URL 列表中的相对位置
        window.history.go(0); // 当前页面
        ```
* Location 对象
    - 获取或设置窗体的 URL, 并且可以用于解析 URL.
    - 语法:
        + location.[属性|方法]
            * 属性:
                - hash 设置或返回从 # 开始的 URL (锚). <kbd>mediaid118</kbd>
                - host 设置或返回主机名和当前 URL 的端口号 <kbd>www.imooc.com:8080/</kbd>
                - hostname 设置或返回当前 URL 的主机名 <kbd>www.imooc.com</kbd>
                - href 设置或返回完整的 URL <kbd>整个 URL</kbd>
                - pathname 设置或返回当前 URL 的路径部分 <kbd>list.php</kbd>
                - port 设置或返回当前的 URL 的端口号 <kbd>8080</kbd>
                - protocol 设置或返回当前 URL 的协议 <kbd>http:</kbd>
                - search 设置或返回从 ? 开始的 URL (查询部分) <kbd>courseid=8&chapterid=86</kbd>          
            ```js
            http://www.imooc.com:8080/list.php?courseid=8&chapterid=86#mediaid118
            ```
            * 方法
                - assign() 加载新的文档
                - reload() 重新加载当前文档
                - replace() 用新的文档替换当前文档           

* Navigator 对象 
    - 包含有关浏览器的信息, 通常用于检测浏览器与操作系统的版本.
    - 属性
        + appCodeName 浏览器代码名的字符串表示
        + appName 返回浏览器的名称
        + appVersion 返回浏览器的平台和版本信息
        + platform 返回运行浏览器的操作系统平台
        + userAgent 返回由客户机发送服务器的 user-agent 头部的值
            * 返回用户代理头的字符串表示 (即浏览器版本信息等的字符串)

* screen 对象
    - 用于获取用户的屏幕信息
    - 语法
        + window.screen.属性 (可省略 window 前缀)
            * availHeight 窗口可以使用的屏幕高度, 单位像素
                - 返回访问者屏幕的宽度, 减去界面特性, 比如任务栏
            * availHeight 窗口可能使用的屏幕宽度, 单位像素
                - 返回访问者屏幕的高度, 减去界面特性, 比如任务栏
            * colorDepth 用户浏览器表示的颜色位数, 通常为 32 位(每像素的位数)
            * pixelDepth 用户浏览器表示的颜色位数, 通常为 32 位(每像素的位数) (IE 不支持)
            * height 屏幕的高度, 单位像素
                - 返回屏幕分辨率的高
            * width 屏幕的宽度, 单位像素
                - 返回屏幕分辨率的宽

### DOM ###
* 节点属性
    - 方法
        + nodeName 返回一个字符串, 其内容是给定节点的名字
            * 元素节点的 nodeName 与标签名相同
            * 属性节点的 nodeName 是属性的名称
            * 文本节点的 nodeName 永远是 #text
            * 文档节点的 nodeName 永远是 #document
        + nodeType 返回一个整数, 这个数值代表给定节点的类型
            * 元素 1
            * 属性 2
            * 文本 3
            * 注释 8
            * 文档 9
        + nodeValue 返回给定节点的当前值
            * 元素节点的 nodeValue 是 undefined 或 null
            * 文本节点的 nodeValue 是文本自身
            * 属性节点的 nodeValue 是属性的值
* 遍历
    - 方法
        + childNodes 返回一个数组, 由给定元素节点的子节点构成
            * 若选定的节点没有子节点, 返回不包含节点的 NodeList
            * 节点之间的空白符在 firefox, chrome, opera, safari 是文本节点, 但IE 例外
        + firstChild 返回第一个子节点
            * 没有子节点, 该属性返回 NULL.
        + lastChild 返回最后一个子节点
            * 没有子节点, 该属性返回 NULL.
        + parentNode 返回一个给定节点的父节点
        + nextSilbing 返回给定节点的下一个子节点
            * 无此节点, 该属性返回 null.
        + previousSilbing 返回给定节点的上一个子节点
            * 无此节点, 该属性返回 null. <br />
    <strong>IE 将忽略节点间生成的空白文本节点 (如换行符), 解决方法为判断节点 nodeType 是否为 1</strong>
* DOM 操作
    - creatElement(element) 创建一个新的元素节点 (document 方法)
    ```js
    btn.setAttribute("onclick", "javascript:alert('This is a text!');");
    output: This is text!
    ```
    - creatTextNode(string) 创建一个包含着给定文本的新文本节点 (document 方法)
    - appendChild(newnode) 指定节点的最后一个子节点列表之后添加一个新的子节点
    - insertBefore(newnode, node) 将一个给定节点插入到一个给定元素节点的子节点的前面
    - removeChild(node) 从一个给定元素中删除一个子节点
        + 删除成功, 返回被删除的节点; 否则返回 NULL.
        + 被替换的节点为仍然还在文档中(即内存中), 但已经不在 DOM 树中.
        + 完成删除对象, 必须手动设置 null 值.
    - replaceChild(newnode, oldnew) 把一个给定父元素里的一个子节点替换为另外一个节点
        + oldnode 被替换时, 所有与之相关的属性内容都将被移除.
* getElementsByName() 返回带有指定名称的节点对象的集合, 含 length 属性.
* getElementsByTagName() 返回带有指定标签名的节点对象的集合, 与在文档中的顺序一致, 含 length 属性
* getElementById()
* getAttribute () 通过元素节点的属性名称获取属性的值。
    - elementNode.getAttribute(name) 使用前需获取元素节点.
    - 查询的元素节点的属性名字
* setAttribute() 增加一个指定名称和值的新属性，或者把一个现有的属性设定为指定的值。
    - elementNode.setAttribute(属性名, 属性值) 使用前需获取元素节点.
* 浏览器窗口可视区域大小
    - IE9+, Chorme, Firefox, Opera, Safari
        + window.innerHeight 浏览器窗口的内部高度 (不含工具栏滚动条)
        + window.innerWidth 浏览器窗口的内部宽度 (不含工具栏滚动条)
    - IE8
        + document.documentElement.clientHeight HTML 文档所在的窗口的当前高度
        + document.documentElement.clientWidth HTML 文档所在的窗口的当前宽度
        
    - Document 对象的 body 属性对应 HTML 文档的 body 标签
        * docuemnt.body.clientHeight;
        * docuemnt.body.clientWidth;
    ```js
    var w= document.documentElement.clientWidth || document.body.clientWidth;
    ```
* scrollHeight
    - IE, Opera
        + 网页内容实际高度, 可以小于 clientHeight;
    - Firefox, Safari, Chorme
        + 网页内容高度, 最小值为 clientHeight. 网页内容实际高度小于 clientHeight 时，scrollHeight 返回 clientHeight 。
    - 兼容
    ```js
    var w=document.documentElement.scrollWidth || document.body.scrollWidth;
    ```
    - scrollHeight和scrollWidth 可获取 Dom 元素中内容实际占用的高度和宽度。

* offsetHeight & offsetWidth
    - 获取网页内容高度和宽度(包括滚动条等边线，会随窗口的显示大小改变)。
    - offsetHeight: clientHeight + 滚动条 + 边框
    - 兼容
    ```js
    var w= document.documentElement.offsetWidth || document.body.offsetWidth;
    ```
* 网页卷去的距离与偏移量
    - scrollLeft:设置或获取位于给定对象左边界与窗口中目前可见内容的最左端之间的距离 ，即左边灰色的内容。
    - scrollTop:设置或获取位于对象最顶端与窗口中可见内容的最顶端之间的距离 ，即上边灰色的内容。
    - offsetLeft:获取指定对象相对于版面或由 offsetParent 属性指定的父坐标的计算左侧位置 。
    - offsetTop:获取指定对象相对于版面或由 offsetParent 属性指定的父坐标的计算顶端位置 。
    - offsetParent：布局中设置postion属性(Relative、Absolute、fixed)的父容器，从最近的父节点开始，一层层向上找，直到HTML的body。
![图片](http://img.mukewang.com/5347b2b10001e1a307520686.jpg)

### 数据类型 ###
* 隐式转化
    - 巧用 +/- 符号
    ```js
    // 相减时, 优先将字符串变数字
    // 利用 0 可将字符串转数字
    "37" - 0 = 37; 
    // 相加时, 进行字符串的合并
    // 利用 "" 可将数字转字符串
    "" + 37 = "37"; 
    ```
    - 类型比较:
        + <strong>===</strong> 无需转化, 比较类型及内容是否相同.
        ```js
        NaN !== NaN; 
        new Object  !== new Object; // [1, 2] !== [1. 2]
        ```
        + <strong>==</strong> 可先类型转换再比较
        ```js
        null == undefined;
        number == string ; // string 转化为数值
        boolean == number; // 布尔值转化为数值
        object == number/string; // 对象转化为基本类型
        ```
* 包装对象
    - 基本包装类型: string, number, boolean;
    - 基本包装类型不是对象, 但每当读取一个基本类型值的时候, 后台就会创建一个对应的基本包装类型的对象, 从而可调用一些方法操作数据.
    ```js
    var s1 = "text";
    s1.length; // 正常访问, 4
    s1.color = "red"; // 添加一个属性
    alert(s1.color); // undefine;

    原理:
    1. 先创建 String 类型的一个实例
    2. 在实例上调用指定的方法
    3. 销毁实例
    ```
* 类型检测
    - typeof 适用于函数对象和基本类型的判断
        + typeof 100 return "number"
        + typeof true return "boolean"
        + typeof function return "function"
        + typeof undefined return "undefined"
        + typeof new Object() return "object"
        + typeof [1, 2] return "object"
        + typeof NaN return "number"
        + typeof null return "object" // 历史原因, 曾尝试修正, 但造成大量网站崩溃; 可使用 "===" 补救. 
    - instanceof 适用于对象实例判断 (基于原型琏)
    ```js
    [1, 2] instanceof Array ===  true;
    new Object() instanceof Array === false;
    不同的 window 或 iframe 间的对象类型检测不能使用 instanceof!!
    ```
    - Object.prototype.toString.apply() 
    ```js
    Object.prototype.toString.apply([]); //return "[objet Array]"
    Object.prototype.toString.apply(function() {}); //return "[objet Function]"

    Object.prototype.toString.apply(null); // return "[object Null]"
    Object.prototype.toString.apply(undefined); //return "[object Undefined]"

    IE8 Object.prototype.toString.apply(null) 返回 "[object Object]"
    ```
    - constructor 可修复指向的构造函数. 
    - duck type
    
    ![判断两个数组是否相似](http://img.mukewang.com/54ae403600014f0d06060832.jpg)
    
### 表达式或运算符 ###
* 表达式
```js
[1, 2] == new Array(1, 2);
[1, , , 4] == [1, undefined, undefined, 4]
{x:1, y:2} == var o = new Object(); o.x = 1; o.y = 2;
// 属性访问表达式
var o = {x: 1};
o.x
o.['x']
```
* 运算符
```js
var val = (1, 2, 3); // val = 3

// 1
var obj = {x: 1};
obj.x; // 1
delete obj.x;
obj.x; // undefined
// 2
var obj = {};
Object.defineProperty(obj, 'x', {configurable: false,
    value: 1
});
delete obj.x; // false;
obj.x; // 1

window.x = 1;
'x' in window; //ture;

{} instanceof Object; // true
typeof 100 === 'number'; //true

function Foo(){}
Foo.prototype.x = 1;
var obj = new Foo();
obj.x; //1
obj.hasOwnPropterty('x'); //false
obj._proto_.hasOwnProperty('x'); //true

void 0 // undefined
void(0) // undefined
```

### 语句 ###
* block 语句: 块语句用一对花括号定义
    - 没有块级作用域
* var 语句: 
```js
var a = b = 1; // 不同于 C, b 为隐式创建的一个全局变量
var a = 1, b = 1; //  建议
```
* try-catch 语句 (异常处理机制)
    - try 从句定义了需要处理的异常所在的代码块。
    - 当 try 块内某处发生了异常时，调用 catch 内的代码逻辑。
    - 放置清理代码，不管try块中是否产生异常，finally块内的逻辑总是会执行。
```js
// 最全
try {
    throw "test";
} catch(ex) {
    console.log(ex); // test
} finally {
    console.log("finally");
}

// 
try {
    try {
        throw new Error("oops"); 
    } finally {
        console.log("finally");
    }
} catch(ex) {
    console.error("outer", ex.message);
}
output: (抛出异常时)
"finally"
"outer" "oops"

// 
try {
    try {
        throw new Error("oops");
    } catch(ex) {
        console.error("inner", ex.message);
        throw ex;
    } finally {
        console.log("finally");
    }
} catch(ex) {
    console.error("outer", ex.messagee);
}
output: 
"inner" "oops"
"finally"
"outer" "oops"
```
* for in 语句
```js
var p;
var obj = {x: 1, y: 2};

for(p in obj) {
}

/* 注意
1. 顺序不确定
2. enumerable 为 false 时不会出现
3. 属性受原型链影响
*/
```
* with 语句 修改当前的作用域, 深层访问 (不建议)
    - 让 JS 引擎优化更难
    - 可读性差
    - 可被变量定义取代
    - 严格模式下禁用 (SytaxError)
```js
with({x: 1}) {
    console.log(x);
}

with(document.forms[0]) {
    console.log(name.value);
}

var form = document.forms[0];
console.log(form.name.value);
```
* 严格模式 (适用高质量, 健壮性及安全系数高的代码)
    - 特殊的执行模式, 修复了部分语言上的不足, 提供更强的错误检查, 并增强安全性.
```js
function func(){
    'use strict';
}

'use strict';
function func() {

}
```
    - 禁用 with
    - 不允许未声明的变量被赋值 (RefereceError)
    - arguments 变为参数的静态副本
    ```js
    function(a) {
        arguments[0] = 100;
        console.log(a); // 100
    }(1); // 不传递参数, 值为 undefined

    function(a) {
        'use strict';
        arguments[0] = 100;
        console.log(a); // 1
    }(1);

    function(a) {
        'use strict';
        arguments[0].x = 100; // 属性是按照共享传递的 (band), 参数为对象时可修改属性
        console.log(a.x);
    }
    ```
    - delete 参数, 函数名报错
    ```js
    function(a) {
        console.log(delete a); // false
    }(1); 

    function(a) {
        'use strict';
        delete a; // SyntaxError
    }(1);
    ```
    - delete 不可配置的属性报错
    ```js
    function(a) {
        var obj = {};
        Object.defineProperty(obj, 'a', {configurable: false});
        console.log(delete obj.a); // false
    }(1); 

    function(a) {
        'use strict'
        var obj = {};
        Object.defineProperty(obj, 'a', {configurable: false});
        delete obj.a; // TypeError
    }(1); 
    ```
    - 对象字面最重复属性名报错
    ```js
    function() {
        var obj = {x: 1, x: 2};
        console.log(obj.x); // 2
    }();

    function() {
        'use strict'
        var obj = {x: 1, x: 2}; // SyntaxError
    }();
    ```
    - 禁止八进制字面
    - eval, arguments 变为关键字, 不能作为变量及函数名
    - eval 独立作用域
    ```js
    function() {
        eval("var evalVal = 2;");
        console.log(typeof evalVal); // number
    }()

    function() {
        'use strict';
        eval("var evalVal = 2;"); // 单独创建一个作用域, 并在 eval 返回时丢弃
        console.log(typeof evalVal); // undefined
    }()
    ```
    - 待补全

### 对象 ###
* 对象包含一系列属性, 这些属性是<strong>无序</strong>的. 每个属性都有一个<strong>字符串</strong>key 和对应的 value;
```js
var obj = {};
obj[1] = 1; // Object{1: 1} 后台运行 toString() 处理成字符串
obj['1'] = 2; // Object{1: 2}

obj[{}] = true;
obj[{x:1}] = true; //Object{1: 2, [object Object]: true}
```
* 创建对象
    - 对象字面量/new Object()
    - 原型链
    ```js
    function foo() {}
    foo.prototype.z = 3;
    var obj = new foo();

    // foo() -> Object.prototype -> null
    typeof obj.toString; // "function" 引用 Object 对象的方法
    'z' in obj; // true 原型链原理
    obj.hasOwnProperty('z'); // false

    obj.z = 5;
    foo.prototype.z; // still 3

    obj.z = undefined; (属性值为 undefined)
    delete obj.z; // 删除实例中的 z 属性
    obj.z; // 3
    ```
    - Object.create() 
       * 一个参数时, 创建原型指向参数的空对象。
       * 第二个参数是可以设置新对象的属性及权限
    ```js
    var obj = Object.create({x: 1});
    obj.x; //1
    typeof obj.toString // "function"
    obj.hasOwnPropterty("x"); // false
    // obj -> {x: 1} -> Object.prototype -> null

    var obj = Object.create(null);
    obj.toString; // undefined;
    // obj -> null
    ```
* 属性操作
    - 属性读写-异常
    ```js
    var obj = {x: 1};
    obj.y; // undefined
    var yz = obj.y.z; // TypeError: Cannot read property 'z' of undefiend
    obj.y.z = 2; // TypeError: Cannot set property 'z' of undefined
    
    var yz;
    if(obj.y) {
        yz = obj.y.z;
    }
    // 等同于
    var yz = obj && obj.y && obj.y.z;
    ```
    - 属性删除
    ```js
    var person = {age: 28, title: 'fe'};
    delete person.age; // true;
    delete person['title']; //true;
    person.age; // undefined;
    delete person.age; //true 表明对象上并不存在 age 属性了

    delete Object.prototype; // false 不允许删除 (configurable 为 false)

    var descriptor = Object.getOwnPropertyDescriptor(Object, 'prototype'); 
    // 获取属性的描述符; 
    // 接收两个参数, 属性所在的对象和要读取其描述符的属性名称, 返回值为对象
    descriptor.configurable; //false


    var globalVal = 1;
    delete globalVal; // false

    (function()) {
        var localVal = 1;
        return delete localVal;
    }()); //false

    function fd() {}
    delete fd; //false

    (function()) {
        function fd() {};
        return delete fd;
    }()); //false

    ohNo = 1; // 不推荐 隐式创建一个全局变量
    window.ohNo; //1
    delete ohNo; // true 
    ```
    - 属性检测
    ```js
    var cat = new Object;
    cat.legs = 4;

    'legs' in cat; // ture
    "toString" in cat; // true, inherited property!
    cat.hasOwnProperty("toString"); // false

    // 任一对象上继承自 Object/Object.propertype 上含有大量的属性
    // console 可查看到此信息
    // 但在输出对象时, 大部分原型链属性是不可枚举, 一般只能看到对象上的直接属性.
    cat.propertyIsEnumerable("toString"); // false
    ```
    - 修改属性
    ```
    Object defineProperty(cat, 'price', {enumerable: false, vlaue: 1000});
    cat.propertyIsEnumerable('price'); //false
    cat.hasOwnProperty('price'); //true

    if (cat && cat.legs) {
        cat.legs *= 2;
    }
    //等同
    if(cat.legs != undefined) {
        // !== undefined or null
        // null == undefined
    }
    //严格相等
    if(cat.legs !== undefined) {
    }
    ```
    - 属性枚举
    ```js
    var o = {x: 1, y: 2, z: 3};
    var obj = Object.creat(o); // 此类创建默认可枚举
    obj.a = 4;
    for(var key in obj) {
        console.log(key); //a, x, y, z 
    }

    // 解决办法
     for(var key in obj) {
        if(obj.hasOwnProperty(key)) {
            console.log(key); //a
        }
    }
    ```
* get/set 
    - 方法
    ```js
    var person = {
        name: 'nat',
        weibo: '@nat',
        get age(){
            return new Date().getFullYear() - 1992;
        },
        set age(val){
            console.log("Age can't be set to" + val);
        }
    };
    console.log(person.age); // 24
    person.age = 100; // Age cant be set to 100
    console.log(person.age); // still 24

    var person = {
        name: 'nat',
        $age: null, // $ 仅为符号, 无特殊意义
        get age(){
            if(this.$age == undefined){
                return new Date().getFullYear() - 1992;
            } else {
                return this.$age;
            }
        },
        set age(val) {
            val = +val; //此方法可自动将字符串转换为数字
            if(!isNaN(val) && val > 0 && val < 150) {
                this.$age = +val;
            } else{
                return throw new Error("Incorrect val =" + val);
            }  
        }
    };
    console.log(person.age); // 27
    person.age = 100; // 100
    person.age = 'abc'; // error:Incorrect val = NaN
    ```
    - get/set 与原型链
    ```js
    //示例一
    function foo(){}

    Object.defineProperty(foo.prototype, 'z', {
        get: function() {
            return 1;
        }});

    var obj = new foo();
    obj.z; //1
    obj.z = 10;
    obj.z; // still 1
    // 解决办法
    Object.defineProperty(obj, 'z', {
        value: 100, 
        configurable: true
        });
    obj.z; //100
    delete obj.z;
    obj.z; //back to 1


    //示例二
    var o = {};
    // writable = false, configurable = false
    Object.defineProperty(o, 'x', {value: 1}); 
    var obj = Object.create(o);
    obj.x; //1
    obj.x = 200;
    obj.x; // still 1
    //解决办法
    Object.defineProperty(obj, 'x', {
        writable: true,
        configurable; true, // 更改数值或 delete
        value: 100
    });
    obj.x; // 100
    obj.x = 500;
    obj.x; // 500
    ```
* 属性标签
```js
// 创建一个字面量对象 {pro:true}, 添加一个 'pro' 属性
Object.getOwnPropertyDescriptor({pro: true}, 'pro'); 
// Object {value: true, writable: true, enumerable: true, configurable: true}
Object.getOwnPropertyDescriptor({pro: true}, 'a'); // 未找到其指定属性 undefined

var person = {};
Object.defineProperty(person, 'name',  {
    configurable: false,
    writable: false,
    enumerable: true,
    value: 'nat'
});

person.name; // nat
person.name = 1; //still nat
delete person.name; // false

//定义一个属性
Object.defineProperty(person, 'type', {
    configurable: true;
    writable: true;
    enumerable: false;
    value: 'Object'
});

Object.keys(person); //["name"]
// 以上方法用于获取对象上所有的属性
// "type" 属性因设置为无法枚举, 未显示出来

//定义多个属性
Object.defineProperties(person, {
    title: {value: 'fe', enumerable: true},
    corp: {value: 'BABA', enumerable: true},
    salary: {value: 50000, enumerable: true, writable: true}
});
Object.getOwnPropertyDescriptor(person, 'salary');
//Object {value: 50000, writable: true, enumerable: true, configurable: false}

// 实例
Object.defineProperties(person, {
    title: {value: 'fe', enumerable: true},
    corp: {value: 'BABA', enumerable: true},
    salary: {value: 50000, enumerable: true, writable: true},
    luck: {
        get: function() {
            return Math.random() > 0.5 ? "good" : "bad";
        }
    },
    promote: {
        set: function(level) {
            this.salary *= 1 + level * 0.1;
        }
    }
});
person.salary; // 50000
person.promote = 2;
person.salary; // 60000
```
![属性标签](property_tag.jpg)

* 对象标签, 对象序列化 (待补充)

### 数组 ###
* 创建数组, 数组操作
    - 概述: 数组是值的有序集合. 每个值叫做元素. 数组是弱类型, 允许含有不同类型的元素, 可以为对象或是其它数组. 
    ```js
    var arr = [1, true, null, undefined, {x: 1}, [1, 2, 3]];
    var arr = [,,] //undefined * 2 数组允许最后一个元素带逗号而自动忽略    
    ```
    - length: (0 ~ 2*23-1)
    - new Array
    ```js
    var arr1 = new Array();
    var arr2 = new Array(100); //undefined * 100
    var arr3 = new Array(true, false, null, 1, 2, "hi"); //[true, false, null, 1, 2, "hi"]
    // 关键字 new 可省略 
    ```
    - 读写 (动态的, 无需指定的大小)
    ```js
    var arr = [1, 2, 3];
    arr[3] = 4; // length 将变为 4
    delete arr[0];
    arr[0]; //undefined; 但 length 仍为 4, 仅将第一元素指定为 undefined
    arr.length -= 1;
    arr; //[undefined, 2, 3] 4 is removed
    ```
    - 迭代
    ```js
    var i = 0, n = 10;
    var arr = [1, 2, 3, 4, 5];
    for (; i < n; i++) {
        console.log(arr[i]); // 1, 2, 3, 4, 5
    }

    Array.prototype.x = 'inerited';
    for (i in arr) {
        console.log(arr[i]); //1, 2, 3, 4, 5, inherited
    }
    for (i in arr) {
        if (arr.hasOwnProperty(i)) {
            console.log(arr[i]); //1, 2, 3, 4, 5 过滤掉原型链上属性
        }
    }
    // 用 for in 弊端: 1. 无序 2. 数组 arr 自带属性将一并读入 (arr.property)
    ```
* 二维数组, 稀疏数组
    - 稀疏数组并不含有从 0 开始的连续索引. 一般 length 属性值比实际元素个数大.
    ```js
    var arr1 = [undefined];
    var arr2 = new Array(1);
    0 in arr1; //true
    0 in arr2; //false
    arr1.length = 100;
    arr1[99] = 123;
    99 in arr1; //true
    98 in arr1; //false

    var arr = [,,];
    0 in arr; //false
    ```
* 数组方法
    - ES5 即要求 IE 版本为 9+.
    - Array.prototype.join (将数组转为字符串)
    ```js
    function repeatString(str, n){
        return new Array(n + 1).join(str);
    }
    repeatString("a", 3); //"aaa"
    ```
    - Array.prototype.reverse (将数组逆序, 原数组将逆序)
    ```js
    var arr = [1, 2, 3];
    arr.reverse(); //[3, 2, 1]
    arr; //[3, 2, 1] 
    ```
    - Array.prototype.sort (排序, 原数组被修改) 
    ```js
    var arr = ["a", "c", "b"];
    arr.sort(); //["a", "b", "c"] 保证按字母表排序
    arr = [13, 24, 51, 3];
    arr.sort(); //[13, 24, 3, 51]
    arr.sort(function(a, b) {
        return a - b;
    }); // 升序排列

    arr = [{age: 25}, {age: 39}, {age: 99}];
    arr.sort(function(a, b)) {
        return a.age - b.age;
    });
    arr.forEach(function(item)) {
        console.log('age', item.age);
    });
    /* result:
    age 25
    age 39
    age 99
    */
    ```
    - Array.prototype.concat (数组合并, 不会改变原数组)
    ```js
    var arr = [1, 2, 3];
    arr.concat(4, 5); //[1, 2, 3, 4, 5]
    arr; //[1, 2, 3]
    arr.concat([10, 11], 13); //[1, 2, 3, 10, 11, 13]
    arr.concat([1, [2, 3]]); //[1, 2, 3, 1, [2, 3]] 
    ```
    - Array.prototype.slice (返回部分数组, 左闭右开, 原数组未修改)
    ```js
    var arr = [1, 2, 3, 4, 5];
    arr.slice(1, 3); //[2, 3]
    arr.slice(1); //[2, 3, 4, 5]
    arr.slice(1, -1); //[2, 3, 4]
    arr.slice(-4, -3); //[2]
    ```
    - Array.prototype.splice (数组拼接, 原数组将修改)
    ```js
    var arr = [1, 2, 3, 4, 5];
    //实例一
    arr.splice(2); //[3, 4, 5]
    arr; //[1, 2]
    //实例二
    arr.splice(2, 2); //[3, 4]
    arr; // [1, 2, 5];
    //实例三
    arr.splice(1, 1, 'a', 'b'); // [2]
    arr; //[1, 'a', 'b', 3, 4, 5]
    ```
    - Array.prototype.forEach (数组遍历)
    ```js
    var arr = [1, 2, 3, 4, 5];
    arr.forEach(function(value, index, array) {
        console.log(value + '|' + index + '|' + (array === arr));
    });
    /* output: 
    1|0|true
    2|1|true
    3|2|true
    4|3|true
    5|4|true
    */
    ```
    - Array.prototype.map (数组映射, 原数组未被修改)
    ```js
    var arr = [1, 2, 3];
    arr.map(function(x) {
        return x + 10; //[11, 12, 13]
    }); 
    ```
    - Array.prototype.fitler (数组过滤, 原数组未被修改)
    ```js
    var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
    arr.filter(function(x, index) {
        return index % 3 === 0 || x >= 8; // [1, 4, 7, 8, 9, 10]
    });
    ```
    - Array.prototype.every (数组判断)
    ```js
    var arr = [1, 2, 3, 4, 5];
    arr.every(function(x) {
        return x < 10; //true
    });
    arr.every(function(x) {
        return x < 3;
    });
    ```
    - Array.prototype.some (数组判断) 
    ```js
    var arr = [1, 2, 3, 4, 5];
    arr.some(function(x) {
        return x === 3; //true
    });
    ```
    - Array.prototype.reduce & reduceRight (归并, 原数组未修改)
        + 参数一: 每一项上调用的函数
            * 函数接受四个参数: 前一个值, 当前值, 项的索引和数组对象.
            * 函数的任何返回值都将作为第一个参数自动传给下一项
            ```js
            var val = [1, 2, 3];
            var sum = val.reduce(function(prev, cur, index, array){
                return prev + cur; //15
            });
            ```
        + 参数二: (可选) 作为归并基础的初始值
    ```js
    var arr = [1, 2, 3];
    var sum = arr.reduce(function(x, y) {
        return x + y;
    }, 0); // 6
    arr = [3, 9, 6];
    var max = arr.reduce(function(x, y) {
        console.log(x + "|" + y);
        return x > y ? x : y;
    });
    //3|9
    //9|6
    max; //9

    //仅迭代的方向相反, 原理一样
    max = arr.reduceRight(function(x, y) {
        console.log(x + "|" + y);
        return x > y ? x : y;
    });
    //6|3
    //9|3
    max; //9
    ```
    - Array.prototype.index & lastIndexOf (数组索引的检索)
    ```js
    var arr = [1, 2, 3, 2, 1];
    arr.indexOf(2); //1
    arr.indexOf(99); //-1 查找失败
    arr.indexOf(1, 1); // 4 从索引 1 开始查找 1
    arr.indexOf(1, -3); // 4
    arr.indexOf(2, -1); // -1 查找失败
    arr.lastIndexOf(2, -1); //3
    arr.lastIndexOf(2, -3); // 1
    ```
    - Array.isArray (判断是否为数组)
    ```js
    Array.isArray([]);
    [] instanceof Array; //true
    ({}).toString.apply([]) === '[object Array]'; //true
    [].constructor === Array; //true
    ```
* 函数属性 & arguments
    - 函数属性 & arguments
    ```js
    function foo(x, y, z) {
        arguments.length; //2
        arguments[0]; //1
        arguments[0] = 10;
        x; // 10 绑定关系 [严格模式仍为1]

        arguments[2] = 100;
        z; //undefined! 未传参数, 失去绑定关系
        arguments.callee === foo; //true [严格模式下不能使用]
    }

    foo(1, 2);
    foo.length; //3 形参个数
    arguments.length; // 2 实参个数
    foo.name; //"foo"
    ```
    - apply/call
    ```js
    function foo(x, y) {
        console.log(x, y, this);
    }

    //单个数字传递
    foo.call(100, 1, 2); // 1, 2, Number(100) 自动转化为基本包装对象
    //传入数组
    foo.apply(true, [3, 4]); // 3, 4, Boolean(true);
    foo.apply(null); //undefined, undefined, window(最终指向顶端的全局 null)
    foo.apply(undefined); //undefined, undefined, window
    
    //严格模式
    foo.apply(null); //undefined, undefined, null
    foo.apply(undefined); //undefined, undefined, undefined
    ```
    - bind & curry (待补充)

### 函数和作用域 (闭包, 作用域)
* 闭包: 有权访问另一个函数作用域中的变量的函数
    - 实例
    ```js
    function outer() {
        var localVal = 30;
        return function() {
            return localVal;
        }
    }
    var func = outer();//省略此步直接调用 func(), 将返回 function(return localval);
    func(); //30
    ```
    - 常见错误之循环闭包
    ```js
    document.body.innerHTML = "<div id = div1>aaa</div>" 
        + "<div id = div2>bbb</div><div id = div3>ccc</div>";
    for(var i = 1; i < 4; i++) {
        document.getElementById("div" + i).
            addEventListener("click", function() {
                alert(i); //all are 4!
            });
    }

    //解决方法
    for(var i = 1; i < 4; i++) {
        !function(i) { // 表示立即调用
            document.getElementById("div" + i).
                addEventListener("click", function(){
                    alert(i); //1, 2, 3
            });
        }(i); 
    }
    ```
    - 封装
    ```js
    (function() {
        var _userId = 23492;
        var _typeId = 'item';
        var export = {};

        function converter(userId){
            return +userId;
        }

        export.getUserId = function(){
            return converter(_userId);
        }

        export.getTypeId = function(){
            return _typeId;
        }

        winodw.export = export; //方便外部变量调用, 没理透
    }());

    export.getUserId(); //23492
    export.getTypeId(); //item

    export._userId; //undefined
    export._typeId; //undefined
    export.converter; //undefined
    ```
    - 利弊
        + 灵活和方便, 封装
        + 空间浪费, 内存泄露, 性能消耗
* 作用域
    - 作用域链
        + 全局
        + 函数
        + eval
    ```js
    function outer2(){
        var local2 = 1;
        function outer1() {
            var local1 = 1;
            // visit local1, local2 or global3
        }
        outer1();
    }
    var global3 = 1;
    outer2();

    function outer(){
        var i = 1;
        var func = new Function("console.log(typeof i);");
        func(); //undefined
    }
    ```
    - 利用函数作用域封装
    ```js
    //两种函数表达式的方法
    !function main() {
        var a, b;
        ...
    }();
    //等同于
    (function main() {
        var a, b;
        ...
    })();
    //将函数内部的变量声明为局部变量, 防止冲突
    ```
* ES3 执行上下文 (Execution Context EC)
    - 实例
    ```js
    console.log("EC0");
    function funcEC1(){
        console.log("EC1");
        var funcEC2 = function(){
            console.log("EC2");
            var funcEC3 = function(){
                console.log("EC3");
            };
            funcEC3();
        }
        funcEC2();
    }
    funcEC1();
    //EC0 EC1 EC2 EC3 (从最上面的全局开始)
    ```
    - 变量对象 (待补充)
        + JS 解释器如何找到定义的函数和变量?
            * 变量对象(variable Object VO)是一个抽象概念中的"对象", 它用于存储执行上下文中的:
                - 变量
                - 函数声明
                - 函数参数

### 面向对象编程 ###
* 概念与继承
    - 基于原型的继承
    ```js
    function Foo(){
        this.y = 2;
    }
    typeof Foo.prototype; //"object"
    Foo.prototype.x = 1;
    var obj3 = new Foo();

    obj3.y; //2 (y = 2 为 obj3 自带的属性??)
    obj3.x; //1
    ```
    - prototype 属性与原型
    ```js
    function Foo(){}
    typeof Foo.prototype; //"object"
    Foo.prototype.x = 1;
    var obj3 = new Foo();

    Foo.prototype
    {
        constructor: Foo,
        _proto_: Object.prototype,
        x: 1
    }

    //应用
    function Person(name, age){
        this.name = name; // 在函数声明内, this 为全局对象 window
        this.age = age; 
    }

    Person.prototype.hi = function(){
        console.log("Hi, my name is " + this.name + "I'm" + 
        this.age + "years old now.");
    };

    Person.prototype.LEGS_NUM = 2;
    Person.prototype.ARMS_NUM = 2;
    Person.prototype.walk = function(){
        console.log(this.name + "is walking...");
    };

    function Student(name, age, className) {
        Person.call(this, name, age);
        this.className = className;
    }

    Student.prototype = Object.create(Person.prototype);
    Student.prototype.constructor = Student;

    Student.prototype.hi = function(){
        console.log("Hi, my name is" + this.name + "I'm" + 
            this.age + " years old now, and from " + this className + ".");
    };

    Student.prototype.learn = function(subject){
        console.log(this.name + 'is learning' + subject +
            'at' + this.className + '.');
    };

    var nat = new Student("Nat", 24, "Class 3, Grade 2");
    nat.hi(); //Hi, my name is Nat, I'm 27 years old now. and from C3,G2
    nat.LEGS_NUM; // 2
    nat.walk(); //Nat is walking...
    nat.learn('math'); //Nat is learning math at Class3, Grade 2.
    ```
    ![原型链](prototype.jpg)
    - Object.getPrototypeOf() 返回对象的原型
* prototype 属性
    - 改变 prototype
    ```js
    Student.prototype.x = 101;
    nat.x; // 101

    Student.prototype = {y: 2};
    nat.y; //undefined
    nat.x; //101 新的指向不会影响到原先 nat 已指向 Stdudent.prototype.

    var Mat = new Student('mat', 3, 'thew');
    Mat.x; //undefined
    Mat.y; //2
    ```
