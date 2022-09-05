## Welcome to Zimon's Blog

### 6.16
***
类选择器，伪类选择器的使用，语法例如a:hover
静态伪类visited和link只用于超链接a，并且visited只改变颜色属性
动态伪类hover，active，focus，active是点击不松开
另一个伪类选择器first-child选择第一个子元素
背景图片平铺属性取值repeat, repeat-x, repeat-y, no-repeat

### 6.17
***
背景图片的固定，background-attachment，只有两个属性，scroll和fixed
背景图片五个属性一起写background:背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置
背景颜色的透明度rgba，最后一个0~1的参数表示透明度，0全透明，1完全不透明
一般超大的图片和较小的图标用背景图片来做，好控制位置

CSS的三大特性：层叠性，继承性，优先级
继承性中可以继承的元素属性有text- font- line-以及color属性
选择器的优先级!important > 行内样式 > ID > 类和伪类 > 元素 > 继承或者通配符*
!important参数写在属性键的后面比如color: pink!important
注意：无论父元素的优先级是多高，继承其的子元素优先级永远是0
复合选择器涉及优先级的叠加，权重有叠加但是永远不会进位

### 6.18
***
边框属性可以连写：border: width style color;
border四个边框可以拆开，比如border-top
制作表格时合并相邻边框使用border-collapse: collapse;这个属性写在表格而不是列表
border是本身盒子大小的扩充，盒子的宽高属性不包括border

padding的简写设置
一个值代表上下左右，两个值前上下后左右，三个值上，左右，下，四个值上右下左
padding同样会影响盒子的大小
在块级元素未设置宽高时设置padding不会改变其宽高，块级元素的特性是默认宽高为容纳其的盒子的宽高，宽高是不可以继承的

**块级元素的水平居中显示，设置width以及margin设置为auto，或者margin设置为auto并且text-align: center**
**行内元素和行内块元素的水平居中显示，父元素设置为text-align: center;**
**嵌套块元素塌陷问题**，解决方案：给父元素添加边框/内边框或者添加属性overflow: hidden;
**品优购快报实践**
去掉li前面的小圆点的方法list-style: none;
p167

### 6.19
***
在做品优购快报的时候出现的问题，首先是全局设置margin和padding为0后重新设置的属性不起作用，第二是不清楚如何使整个ul在边框下居中
盒子阴影属性box-shadow: h-shadow v-shadow blur spread color inset 
分别是水平距离，垂直距离，模糊程度，阴影大小，阴影颜色，是否外部阴影转为内部阴影
文字阴影也很类似text-shadow: h-shadow v-shadow blur color

浮动效果的主要作用：改变网页标签的排列模式
浮动元素的三个重要特性：1浮动元素会脱离标准流 2浮动元素一行内显示并且元素顶部对齐 3浮动元素具有行内块元素的特性
脱离标准流意味着没有浮动的盒子会自动填补位置，相当于浮动的元素换了一个图层
任何元素都可以浮动，浮动的元素属性类似于行内块元素
网页布局一般先用标准流父元素排列上下位置，之后内部子元素浮动排列左右位置
浮动要注意的点：1浮动和标准流的父盒子匹配 2一个元素浮动了，理论上其余的兄弟元素也要浮动
浮动的盒子只影响它后面的标准流，并不会影响之前的标准流
p183

### 6.21
***
清除浮动：想要用浮动的子元素撑开标准流的父盒子，使父盒子的高度自动调节
本质是清除浮动元素脱离标准流造成的影响，策略是闭合浮动，只让浮动在父盒子内部影响
清除浮动的四种方法：1额外标签法 2父级添加overflow属性 3父级添加after伪元素 4父级添加双伪元素
额外标签法：在最后一个浮动的元素后面添加一个空的块标签并设置clear: both;
父级添加overflow属性：可以设置为hidden, auto, scroll 一般选择hidden 缺点是无法显示溢出部分
父级添加伪元素类似于额外标签法的升级版，不需要手动添加标签

推荐的CSS顺序：
1布局定位属性 2自身属性 3文本属性 4其他属性
浮动的元素不存在外边距合并的问题
p212

### 6.23
***
**出现问题：**制作学成在线的精品推荐模块时发现margin被自动设置为了-48px导致元素不能移动到正确的位置
明天写学成在线的其他部分
定位=定位模式+边偏移
相对定位模式是指相对原始的位置偏移，但是本身还在标准流中不会变化
绝对定位模式是指相对第一个设置了定位的祖先元素的位置偏移，如果没有定位的祖先元素则相对浏览器Document偏移，并且绝对定位后元素相较浮动有更高级别的层次，脱离标准流，不再保留原先的位置
子绝父相：子元素绝对定位那么父元素就用相对定位
p229

### 6.24
***
固定定位：相对于浏览器的可视窗口的位置来定位，一般做滚动位置不变的元素，与父元素没有任何关系，不占用原来的位置
固定显示在版心的方法left: 50%; margin-left: 版心宽度一半

粘性定位：相对于浏览器的可视窗口的位置来定位，但是占用原先的位置，必须添加top left right bottom其中的一个才有效

盒子的重叠情况：未指定优先级的情况下，后来者居上，可以通过z-index指定优先级，**只有定位的盒子才会有index属性**

**解决了昨天的问题** 通过父盒子设置相对定位，子盒子绝对定位设置right: 0;解决了问题，但是为什么没有浮动到最右未解决

添加绝对定位的盒子不能通过margin: 0 auto;实现水平居中
绝对定位盒子居中的方法：先用top，left等50%，然后通过margin设置为负值，本盒子宽度的一半

添加了定位的行内元素会自动变成行内块元素
浮动的元素不会压住标准流元素的文字部分，但是绝对定位会

**修改总体的属性然后专门修改局部要注意选择器的优先级**

p245

### 6.25
***
元素的显示与隐藏：display: none隐藏元素，display: block除了变为块级显示之外还有显示元素，隐藏不保留元素原本位置
visibility: hidden隐藏元素visibility: visible显示元素，和display的重要区别是隐藏保留元素的位置
overflow: hidden隐藏溢出盒子的部分，scroll显示滚动条，auto有溢出的话添加滚动条
有定位属性的盒子一般慎用overflow属性

### 6.27
***
精灵图的使用：针对小的背景图片，主要借助于背景位置来实现background-position，一般坐标都是负值
CSS做小三角图案：盒子不写内容，直接用边框就会出现三角
一些比较杂的点：1form表单轮廓线属性outline 2textarea文本域大小更改属性resize
**vertical-align属性：只针对行内元素和行内块元素生效**
**解决图片底部默认存在空白的方法，1设置vertical-align只要不是默认的和基线对齐就可以 2将图片转化为块级元素**
单行文本溢出显示省略号--必须满足的三个条件：
    1 先强制一行内显示white-space: nowrap;
    2 超出部分隐藏overflow: hidden;
    3 文字用省略号替代超出的部分text-overflow: ellipsis;
类似于页面底部的选择上一页下一页功能使用行内块元素，可以父级元素使用text-align: center属性
并排显示的盒子的边框不变粗测试，斜三角的制作
p281

### 6.28
***
html5的新特性，视频音频和input的type属性限制输入的内容
css3新特性，[]选择器，新增可以通过元素的属性选择，**这种选择器不用添加双引号"" 并且属性选择器的优先级同类选择器**
比如 input[type=text] ^开头 $结尾 *含有 选择class="icon1-6"的六个li元素 li[class^=icon]
结构子类选择器nth-child(n)里面的n是多少就选择第几个，n也可以不是数字，even偶数，odd奇数
nth-child对父元素所有子元素排序，先找到第几个子元素再看是否和E匹配，而nth-of-type对指定的E子元素排序，找到第n个
伪元素新特性：before和after，这两个伪元素必须有content属性并且属于行内元素，伪元素选择器和标签选择器一样权重都为1

### 6.29
***
box-sizing: border-box;属性让盒子的宽度高度自动计算padding和border自动调节
img的图像模糊属性例如filter: blur(5px);
过渡属性 transition:要过渡的属性 花费时间 运动曲线 何时开始
1属性：想变化的css属性，宽高，背景颜色，内外边距都可以，如果所有就选all
2花费时间：单位是秒s，单位必须写
3运动曲线：默认是ease，可以省略
4何时开始：单位是秒，可以设置延迟触发时间，默认是0s，可以省略
过渡属性的位置，哪个元素过渡就写哪个元素，变化多个属性举例：transition: width 0.5s, height 0.5s;
搜索引擎优化：三个标签title, meta name="description", meta name="keywords" 网站标题，描述以及关键字

### 6.30
***
昨天弄了很久都没有解决的字体图标的问题是因为css不是内嵌在html中的，所以相对路径要用css文件的路径，路径没有更改所以字体图标不会显示
关于垂直居中：像是底部的导航栏还是用行高与高度相等来做，vertical-align可以实现垂直居中但是必须要求是行内块元素（浮动元素目前测试不行）
我目前针对垂直居中使用过的方法：
1 line-height=height
2 vertical-align: center;
3 已知font-size的情况下计算上下margin值
4 强行使用子绝父相定位
5* 父元素用text-align: center属性，使其中的行内块（但是测试的结果是全部的元素）元素水平居中

transition属性：一般写在变化的元素上，比如写在div而不是div:hover，但是如果写在hover上也同样可以实现效果

CSS的继承性：font开头的，text-indent，**text-align，line-height，**color，visibility，list-style，cursor

### 7.1
***
input属性中预显示的文字是placeholder属性
出现问题：最左边的品优购项目几个字改为定位后，纵向撑大了盒子使height增大，导致右边的购物车原定的top:50%出现问题
解决问题：logo不使用绝对定位，使用保留原始位置的相对定位

### 7.3
***
符合SEO要求的logo属性：
    1 logo内放一个h1标签，表示重要性
    2 h1内再放一个链接，可以返回首页
    3 链接里面放文字(网站的名称)，文字并不显示
    4 给链接title属性，以便鼠标放到上面看到提示文字
之前并未记录的文字和图片的对齐属性，默认是vertical-align: baseline修改这个值可以使行内块元素的对齐改变
p325

### 7.4
##### 一些记录-start
除了笔记，这也是我个人网站的一部分吧，还是记录下来一些心事，今天是颇为不同的一天，安恒实训的开始，看到了企业光辉亮丽的一面，自然也会有它难言之隐，不由自主会想到这些问题，有时候排斥考研确实也是因为太过讨厌数学那些东西吧，不过这些也是没有办法的事。有一件事最为明确，那就是我想就业的很大原因是知道考研可能会失败，本来就业是备选方案，防止考研失败留后路的，这下反而是因噎废食，被动的变成主动的，实训应该让我静下来想一想到底是要什么样的生活更加适合自己
##### 一些记录-end

做品优购网页是个缓慢的过程，先慢慢做，做完的部分会放到6.27-7.3的文件夹，目前的进度是到p356就业班开始，接下来开始一些js的内容

### 7.5
#### JS开始了
书p456，常见的JS预设的常量
声明变量后默认的值是undefined

### 7.6
未定义的数组元素默认是undefined，数组的长度length属性是可读写的
js中全局变量只有在浏览器关闭的时候才会销毁，占内存的资源，而局部变量程序执行完毕就会销毁
js中的预解析机制：
    1 预解析，js引擎把所有的var和function提升到当前作用域的最前面，但是变量声明并不赋值，函数也是声明但是不调用
    2 代码执行，按照代码自上而下的顺序执行
p142

### 7.7
new关键字的执行过程：
    1 new构造函数在内存中创建一个空对象
    2 this指向刚才创建的空对象
    3 执行构造函数里面的代码，给空对象添加属性和方法
    4 返回这个对象

**遍历对象使用for in，如果其中的变量是k则console.log(k)输出属性名，console.log(obj[k])输出属性值**

获取时间戳（从1970年1月1号到现在的总的毫秒数）的方法
    1 var date = new Date(); console.log(date.valueOf()/date.getTime())
    2 var date = +new Date(); 简单写法
    3 console.log(Date.now()); H5新增的写法
使用时间的月份和星期的时候要格外注意，月份是0-11而星期是0-6，从星期天开始
创建数组时，使用new Array()，里面的参数两个或者以上表示填充数组，一个表示数组的长度
数组内置函数indexOf和lastIndexOf方法除了找元素的索引，还可以用于找元素存不存在
字符串中的所有方法都不会修改字符串本身，都是操作后返回了新字符串，因为字符串实际上是申请了就不变的
typeof null返回的是对象object类型，而不是null类型，如果有未来准备存对象的变量，开始赋值可以给null
所有用new创建的数据类型都是复杂数据类型，简单数据类型只有string number boolean undefined null

#### Web APIs部分 - DOM - 文档对象模型
DOM树：
    1 文档：一个页面是一个文档，DOM中使用document表示
    2 元素：页面中的所有标签都是元素，DOM中使用element表示
    3 节点：网页中的内容都是节点（标签、属性、文本、注释），在DOM中用node表示
    DOM把以上的东西都看成对象
getElementById()通过标签的id属性获取DOM中的指定ID的元素对象，找不到则返回null
这种情况下写js代码往下写，因为文档是自上而下加载（后续会有解决方法）
使用console.dir()可以更好地打印用上述方法获取的DOM元素信息
getElementsByTagName()通过标签名获取这一类元素对象集合，返回的形式是伪数组，只有一个元素或者没有也是伪数组
p198

### 7.8
以下都是H5的选择元素方法：
getElementsByClassName()获取指定类名的所有元素
接昨天的内容，这种伪数组的实际类型是对象类型，内部通过元素序号: 元素类型+类名形式储存，可以用数组方式调用
伪数组的细节：arguments展示一个伪数组，可以遍历，具有length属性，按索引存储数据，不具有数组的push，pop方法
querySelector()获取指定选择器的第一个元素 querySelectorAll()获取指定选择器的所有元素
不考虑兼容性的的话推荐使用上面的H5选择器
获取body和html元素：body: document.body html: document.documentElement

事件部分：
事件有三部分组成: 事件源，事件类型，事件处理程序
innerText和innerHTML的区别，innerText只管标签里面的内容，无视html标签并且也会去除换行和空格，而innerHTML还可以在标签里面写html标签
innerHTML是更官方的标签，使用更多
元素属性的修改，拿到DOM中元素的对象，比如image.src = '...';新的图片url地址等
元素样式的修改，box.style.backgroundColor = 'pink';样式名改成驼峰命名法，js修改style是行内样式，优先级很高
p212

### 7.9
当要改变的样式比较多的时候可以开一个新的类，比如change类，然后this.className = 'change';
但是这种修改方式会直接改掉类名，覆盖原来的类名，如果要保留可以这么写this-className = 'origin change';
p217

### 7.10
给一组元素注册事件：使用循环，做一个五个div只有一个可以处于被点击的案例
按照时间来看这周到周末之前应该把DOM部分全部看完
重点是自定义的属性要通过下列的函数获取，设置或者删除
获取元素属性的方法element.getAttribute('属性')，属性是html的部分不是样式
html的属性是可以自定义的，通过上面的函数可以获得自定义的属性
设置属性的方法：element.setAttribute('属性', '值')另外还可以移除属性element.removeAttribute('属性')

### 7.11
H5自定义属性的命名规则：前面加上data-，比如data-time
H5新增了自定义元素的获取修改方法：dataset里面存放所有的自定义属性，前面不能加data
获取元素的例子：element.dataset.time / element.dataset['time']，如果是连字符还是转化为驼峰命名

DOM节点：
    节点的三个属性：nodeType节点类型 nodeName节点名称 nodeValue节点值
    nodeType 1元素节点 2属性节点 3文本节点（包括文字空格换行等） 实际开发主要操作的是元素节点
    可以通过.parentNode获取父节点，找不到的话返回null
    通过childNodes获取子节点的集合，不仅加入元素节点还有文本节点比如换行，因为获取到的节点类型复杂导致实际上并不常用
    实际上可使用children来获取所有元素类节点的集合，常用
    另外还有firstChlid / lastChild可以获取第一个子节点以及最后一个子节点，但是文本类节点也会算入其中
    解决方法是firstElementChlid / lastElementChild 不过这个方法有兼容性的问题
    **保证兼容性可以使用element.children[0] / element.children[element.children.length - 1]**
    .nextSibling可以获取下一个兄弟节点，但是会算入文本节点 .previousSibling可以获取上个兄弟节点
    解决这个问题使用nexElementSibling / previousElementSibling就可以了，不过仍然会有兼容性问题

    动态创建节点：document.createElement('标签名') 创建完毕后需要添加位置才能出现
    node.appendChild(child)添加节点到node的最后一个子元素，位置类似于CSS的after伪元素
    添加到子元素其他位置：node.insertBefore(child, origin_child)，插入到origin_child子元素之前
    node.removeChild(child)删除父节点的子节点，返回被删除的这个节点
    直接element.remove()删除自身节点
    在a标签的herf属性中写javascript:void(0) / javascript:;都可以阻止链接跳转，就不用写#当成按钮用
    复制节点 node.cloneNode()，如果参数为空或者false，是浅拷贝，只克隆节点本身不克隆子节点，参数是true则深拷贝

    **js获取对象的长度/大小 Object.keys(obj).length 实际上是转数组再求长度**
    不过实则遍历对象的时候可以直接使用for in
    p244

安恒实训：
    1 容器的概念和优点
    2 虚拟机和容器的区别
    3 镜像的概念
    4 隔离操作的局限性
    5 文件的隔离
    6 网络的隔离
    7 最基本的镜像的实现

### 7.12
并不推荐的js添加元素方法document.write('<div>123</div>')在文档流执行完毕后这个操作会导致页面全部重绘
innerHTML创建元素效率高于createElement，但是创建多个元素要用数组模式（push累加join连接）而不是字符串拼接

元素事件注册：
    1 传统方式，利用onclick等，特点是唯一性，同一个元素同一事件只能设置一个处理函数，最后注册的处理函数会覆盖前面注册的处理函数
    2 方法监听注册方式，addEventListener()，IE9之前可以用attachEvent()代替（只支持ie9以前，非标准极其不推荐），同一个元素同一个事件可以注册多个监听器，按注册顺序依次执行
    语法规则 element.addEventListener('click', function(){}) 第三个参数可以暂时不管

安恒实训：
    1 昨天两个思考题的解答
    2 Docker的分层文件系统
    3 容器中runC的作用：创建容器内部进程，创建命名空间，划分资源等
    4 创建自己的镜像：Dockerfile的命令

### 7.16
vscode出了一些问题导致保存丢失

删除事件的方法：
    1 传统方式 element.onclick = null
    2 addEventListener / removeEventListener('click', callback) 函数不能再写匿名函数
    3 attachEvent / detachEvent

DOM事件流：1 捕获阶段 2 当前目标阶段 3 冒泡阶段
    事件冒泡：事件开始时最具体的元素接受，然后逐级向上传播到DOM最顶层节点
    事件捕获：由DOM最顶层节点开始，然后逐级向下传播到最具体元素接受
JS代码只能执行捕获或者冒泡其中的一个阶段，onclick和attachEvent只能得到冒泡阶段
addEventListener第三个参数时true表示捕获阶段调用事件处理程序，默认情况false在冒泡阶段调用处理程序
**捕获和冒泡阶段主要是父子事件的执行顺序区别，捕获是父->子，而冒泡是子->父**
实际开发中很少使用事件捕获，关注事件冒泡，有些事件不会冒泡，比如onblur onfocus onmouseenter onmouseleave

事件对象：
    1 event参数就是一个事件对象 写到侦听函数中，在小括号中当形参来看
    2 事件对象只有有事件才会存在，由系统自动创建，不用手动传参
    3 事件对象有事件的大量信息，比如鼠标事件的鼠标位置，键盘事件的案件信息
    4 事件的命名一般event / evt / e
    5 在ie678中只能使用window.event，可以使用e = e || window.event
    6 e.target返回注册事件的对象，this返回绑定事件的对象，ie678中使用e.srcElement
    7 e.type返回事件的类型，不带on
    8 e.preventDefault()阻止默认的事件，比如a的跳转，button的点击
    9 阻止事件冒泡 e.stopPropagation()，如果是老ie用 cancelBubble = true

    例子  去除右键菜单：document.addEventListener('contextmenu', function(e){e.preventDefault()})
          禁止鼠标选中：document.addEventListener('selectstart', function(e){e.preventDefault()})
          各种文库网站禁止复制的方法

鼠标事件的坐标属性：clientX/Y pageX/Y screenX/Y
键盘事件：onkeyup onkeydown onkeypress，press和down的区别是press不识别功能按键
    三个事件的执行顺序是 down->press->up
    e.keyCode返回按下的键的ascii码值，用key则返回字符，up和down不区分字母的大小写
    down和press在文本框中都是触发的时候文字还没有落入框中，而up文字就已经落入框中了

### 7.17
BOM：
    大于document的概念，顶层元素是window，下属有document location navigation screen history
    全局变量和全局函数会变成window下属的属性和方法
    解决之前出现的js必须写在元素后面的问题：js写在window.onload里面，等页面全部加载完毕再触发js
    如果有多个window.onload事件按最后一个算，当页面图片类比较多的时候可以用document.addEventListener('DOMContentLoaded', function())
    浏览器大小变化时可以使用window.resize事件 window.innerHeight / innerWidth可以反馈浏览器的

定时器：
    第一种定时器：window.setTimeout(callback, 毫秒数)，经过多少毫秒就执行callback函数，一般比如var timer1 = window.setTimeout(callback, 2000)
    window.clearTimeout(timerID)清除指定的那个定时器
    第二种定时器：window.setInterval，主要的区别是每隔设定的事件就会执行一次，同样也可以使用clearInterval(Interval_ID)消除
    
**在全局作用域和普通函数中this指向的都是window**

js的同步和异步：
    同步任务都在主线程执行，形成一个执行栈
    异步任务通过回调函数实现，回调函数放在任务队列中，异步任务主要三种类型：普通事件 / 资源加载 / 定时器
    执行顺序是先执行同步任务，异步任务放入任务队列中，同步任务执行完毕后，系统按次序读取任务队列中的异步任务并执行
    主线程执行栈->异步进程处理->任务队列 然后任务队列再按顺序进主线程执行栈 异步进程处理会判断是否该执行回调函数（是否有事件/定时器是否到时等）

js location是关于页面url的属性，上级是window，可以通过几个下级属性获取url的信息 .href返回全部url地址 .search返回url中的参数
location的三个方法，assign / replace / reload 前两个是换到其他页面，区别是是否保存回退历史，reload相当于刷新，如果参数是true强制刷新

navigator属性存储了关于浏览器的很多属性，最常用的是navigator.userAgent用来判断用户的浏览器类型
history的forward / back方法相当于浏览器按键的前进后退，go方法可以输入数字决定前进后退几步

元素的offset属性，offsetLeft / Top等表示和有定位的父元素的偏移距离，px返回值无单位
offsetWidth / Height 返回包括border padding width/height的属性 offsetParent返回带有定位的父元素
**offset和style的对比，style只能获取行内样式所以不能获取到一般使用的初始外部css样式表，但是可以更改，适合修改，offsetWidth / Height适合获取**
p291

### 7.18
p292

### 7.19
client属性：
    element.clientTop / Left 上左border大小 element.clientWidth / Height返回自身包括padding content，不含border的宽度高度
    **client和offset系列的区别主要在边框，offset有，client无**
立即执行函数：
(function(){})() / (function(){}()) 函数不需要调用直接执行 立即执行函数的最大好处是创建了一个局部作用域

### 7.20
pageshow事件是更好的解决load事件缓存的方式，所有重新加载的场景都可以用pageshow
scrollHeight / Width计算全部的宽高，包括超出部分的高度 / 宽度，另外还有scrollTop
p305

### 7.21
元素被滚动遮挡的头部是element.scrollTop，而页面被滚动遮挡的头部是window.pageYOffset，如果是水平滚动则是window.pageXOffset
总结三种位置：
    offset经常用于获得元素位置，client获取元素大小，scroll获取滚动距离，页面的滚动用window.pageYOffset
mouseover鼠标经过自身盒子触发，经过子盒子还会出发，mouseenter只经过自身盒子触发，对应的是mouseleave
js实现动画：
    主要原理是利用定时器setInterval()不断移动盒子位置
    实现的步骤是 1获得盒子当前位置 2让盒子移动一个单位 3利用定时器重复这个操作 4加一个结束定时器的条件 5这个元素必须添加定位
    可以使用一个函数来封装动画函数
p317

### 7.22
p329
今天主要看了轮播图的具体实现，还有一些细节比如轮播图节流阀（防止按按键会一直加速）
window.scroll(x, y)窗口滚动到下x y的坐标位置，可以用于回到顶部这种情况，写xy的时候不加单位

### 7.23
实际上手动画有点问题，需要回顾视频
调试动画过程中发现的问题，首先是没有offsetRight或者offsetBottom属性，只有left和top
获取通过offset，调整通过style.left类的属性，并且style类的属性赋值需要自己添加单位比如px，而offset类的属性不自带单位
比如说这么写 son.style.left = son.offsetLeft - 1 + 'px';
第二是定时器的中止条件写在定时器函数的内部，写在外部不行
为什么不能写在外部：因为定时器函数属于异步任务，结束条件写在外面相当于同步任务，先执行同步任务再执行异步任务，所以定时器结束条件写在里面

### 7.24
今天的任务是动画封装函数的上手以及非匀速动画 - 比较快的速度就完成了
非匀速动画的核心，计算target和当前的距离，每次移动的step是(target - offsetNow) / 10，这个结果再随正负数进行上下取整即可
封装函数完成，设置点击实现动画但是在动画还未点击完毕时再次点击会混乱，因为开启了多个定时器，要限制只能有一个定时器，只需要开定时器前关闭定时器即可
p332接下来的一部分是移动端的js，应该先补完就业班的CSS内容包括2D3D旋转，移动端等再回来看，看完这部分是jquery

### 7.25
**CSS提高部分**
transform CSS3的新特性，2D转换：可以实现元素的位移，旋转，缩放等，简单可以理解为变形
移动效果 transform: translate(x, y)或者也可以分开写transform: translateX(n)，写的时候要带单位
**translate最大的优点是不会影响其他元素的位置，会遮盖** translate写百分比是相对自身元素，对行内元素无效果
这个特性提供了新的移动子盒子到父盒子中间的方法 top: 50% left:50% transform: translate(-50%, -50%)

旋转效果 rotate(?deg)旋转?度，正数顺时针，负数逆时针，可以配合transition属性实现旋转的动画
默认情况下旋转的中心点就是元素的中心点，可以通过transform-origin设置到其他的位置去
默认情况下是transform-origin: 50% 50%或者transform: center center可以使用方位词 left bottom或者像素

放大缩小效果 scale transform: scale(x, y) x宽度y高度 默认不带单位写的是倍率 比如原封不动是scale(0, 0)，等比例缩放的话可以只写一个参数scale(s)
scale对比直接修改width和height的好处是可以设置缩放中心点，并且放缩不会影响到其他的元素，缩放中心点还是transform-origin

transform属性可以连着写，但是连着写顺序会有影响，rotate和scale会导致坐标的改变，有多个属性的情况下先写translate

CSS动画效果 先定义动画再调用动画
使用@keyframes定义一个动画，设置0%起始和100%结束时候的状态，然后在需要动画的元素中添加属性animation-name animation-duration
0%和100%这个属性是动画序列，可以改变任意多样式和任意多次数，用%规定变化发生的事件，或者用from to关键字，相当于0% 100%
p369

### 7.26
动画的其他属性：
    何时开始 animation-delay 默认是立即开始
    重复多少次 animation-iteration-count 写infinite就无限循环
    是否下一次逆向播放 animation-direction 默认是normal 写alternate则下一次反向
    动画结束后的状态 animationo-fill-mode 默认是backwards返回起始状态，写forwards停留在结束状态
    动画运行或者暂停 animation-play-state 默认是running，暂停是paused
动画的简写 animation: 动画名称 持续时间 运动曲线 何时开始 播放次数 是否反方向 动画起始结束的状态
name和duration是必须写的属性，另外简写的属性中不包括animation-play-state，简写的时候可以用逗号分隔多个动画
元素的透明度属性 opacity，写的就是透明度0-1
脉冲波纹属性中不写scale来放大的原因是如果改动sacle会导致box-shadow一起倍增
速度曲线中的细节animation-timing-function有一个特殊属性steps()是时间函数中的间隔数量，简单来说就是给动画分段，一段一段走

3D转换，增加了一个z轴，向屏幕外是正，屏幕里是负
3D位移 transform: translate3d(x, y, z)，z的坐标单位基本上只用px
想要产生3D效果，需要添加perspective透视属性，透视属性类似于添加眼睛看屏幕的距离
透视写到被观察元素的父盒子上面

3D旋转 rotate3d(x, y, z, deg)沿着自定义的轴(x,y,z)矢量旋转deg为角度，一般单独使用比如rotateX(x)
判断旋转的正方向可以使用左手准则，四指弯曲拇指伸直对准轴的正方向四指就指向旋转的正方向

3D呈现 transform-style 让父元素控制子元素是否开启三维立体的环境，默认是flat，改成preserve-3d就可以启动3d，注意是写给父元素的属性
**子元素想要3d效果 父元素必须提供perspective和transform-style属性**
**翻转类型的翻过来不显示背面的方法：backface-visibility: hidden**
3d导航栏部分遇到了很多障碍，总结：
    1 perspective和transform-style都只针对下面一层的子元素，这两个属性不需要同时出现，按需使用有3d效果跟近大远小没有必然的关系
    2 90度类型的旋转因为转轴的变化比较困难最好改成根据转轴是一个正方体类型的东西
制作旋转木马时发现的新问题：一般位移和旋转同时存在时只要出现两个维度的位移就很容易出问题，圆形绕圈可以先旋转再位移
css动画部分完结 p388

### 7.27
浏览器的私有前缀：
    -moz- firefox
    -ms- ie
    -webkkit- chrome edge safari
    -o- opera
私有属性可以直接添加到属性的前面比如 -webkit-border-radius: 10px

**移动端布局开发**
兼容移动端的处理器只需要处理webkit内核
视口viewport是浏览器显示页面内容的屏幕区域，可以分为布局视口，视觉视口和理想视口
    布局视口：一般由移动端浏览器默认设置，解决早期pc端网页在移动端的显示问题，手机大部分将这个视口设置为980px，pc端网页能显示但是内容都很小
    视觉视口：用户能看到的网站区域，可以用缩放操作视觉视口
    理想视口：手动写meta视口标签通知浏览器，让布局视口的宽度和理想视口宽度一致，理想视口是最合适浏览的视口
meta视口标签属性
    width 宽度设置的是viewport宽度，可以设置device-width特殊值
    initial-scale 初始缩放比
    maximum-scale 最大缩放比
    minimum-scale 最小缩放比
    user-scalable 用户是否可以缩放 yes/no或者1/0
标准的viewport配置是width设备宽度，初始/最大/最小缩放比都为1，不允许用户自行缩放

二倍图：物理像素和物理像素比，pc端一般1像素就是真实1像素（高分屏不是），移动端经常这两个不对等
一个px能显示的物理像素点的个数称为物理像素比或者屏幕像素比，现在手机都是视网膜屏幕的情况下像素比都不是1
在视网膜屏幕中打开图片会因为更多像素导致模糊，可以使用倍图来解决这个问题
在视口中设置，准备的图片是实际大小*像素比，在图片显示中修改width和height除像素比，在手机中就可以正常显示
背景缩放 background-size: 宽度 高度 如果只写一个参数就是省略高度，高度随宽度等比例缩放，单位也可以跟%百分数对比父盒子
background-size有两个特殊属性cover和contain，cover等比例拉伸至完全盖住盒子，可能有损失图像，而contain是等比例拉伸到宽高任意一个到父盒子就停止
**背景图片的放大缩小使用的就是background-size属性，但是多倍图本身扩大还是得准备材料的过程完成，缩小可以使用background-size属性**
准备材料切图的过程可以使用cutterman切图工具切出多倍图

移动端的开发目前有两种主流方案：1 单独制作移动端的页面 2 响应式页面兼容移动端
单独制作是主流，通常在域名前面加一个m比如m.jd.com

移动端有推荐的初始化css代码 normalize.css 盒子模型一般使用CSS3的border-box
移动端单独需要注意的三个样式：
    -webkit-tap-highlight-color: transparent; 清除点击高亮
    -webkit-appearance: none; 清除ios自带的按钮和输入框样式
    img, a {-webkit-touch-callout: none;} 禁止长按页面出现菜单

流式布局：
    特点是通过百分比布局宽度，而不是传统方式用像素
    可以通过给max-width和min-width限制最大最小的宽度
    p403

### 7.28
图片的居中对齐有时候用line-height并不管用，原因是要用vertical-align设置图片的对齐属性，图片默认是基线对齐，改成居中对齐，行内块一般用vertical-align，但是做这一步还是必须注意设置行高

二倍图的精灵图：先把整个精灵图等比例缩放为原来的一半再测量坐标，代码里面使用background-size修改为原来的一半，核心问题是二倍图的坐标也会有变化

去除图片上下之间的空白缝隙（左右可以float）vertical-align: top/middle

flex布局：
    操作方便，布局简单移动端应用广泛，PC端浏览器支持情况较差
    ie11或者更低的版本不支持或仅部分支持

flex是弹性布局，任何容器都可以指定为flex布局
再父元素设置flex布局后子元素的float，clear，vertical-align属性失效
采用flex布局的元素称为flex容器，它的所有子元素称为flex项目
布局的原理是通过给父盒子添加flex属性控制子盒子的位置和排列方式

flex布局父元素（容器）的六个属性：
    1 flex-direction 设置主轴的方向
    2 justify-content 设置主轴的子元素排列方式
    3 flex-wrap 设置子元素是否换行
    4 align-content 设置侧轴上子元素的排列方式（多行）
    5 align-items 设置侧轴上子元素的排列方式（单行）
    6 flex-flow 复合属性，相当于同时设置flex-direction和flex-wrap
默认的主轴就是x轴，侧轴就是y轴，子元素是根据主轴来排列的
flex-direction可以选的属性有row（默认）row-reverse column column-reverse
**子元素本身的顺序由flex-direction决定**
justify-content的属性有
    flex-start（默认）从主轴头部开始
    flex-end 从主轴尾部开始
    center 在主轴居中对齐
    space-around 平分剩余空间
    space-between 先两边贴边再平分剩余空间
不像浮动，弹性布局子元素在一行塞不下的情况下会修改所有元素的宽度以至于强行能塞下，所谓弹性
flex-wrap设置换行，默认情况下不换行，属性值只有wrap和nowrap（默认）
align-items设置单行情况下侧轴子元素排列方式，属性有flex-start从上到下 flex-end从下到上 center居中 stretch拉伸（默认）
stretch这个属性在有高度的情况下无法体现，子元素没有设置高度的情况下会拉伸跟父元素同样的高度
**单行子元素设置水平和垂直都居中的话就justify-content和align-items都设置为center**
align-content设置多行情况侧轴子元素的排列方式，单行无效，在align-items属性的基础上增加了space-around和space-between
flex-flow可以简写属性，比如flex-flow: row wrap 主轴x轴，换行

flex布局子元素的属性：
    flex 定义子项目分配剩余空间，占多少份，比如flex: 0（默认）所谓的剩余空间指的是有宽度的子项目算完了，没给宽度的分剩余空间
    总份数是没有设置宽度的子项目的个数，这种适合做类似京东搜索条那种两边固定中间自适应的
    align-self 设置子元素本身在侧轴上的排列方式，可以覆盖父元素的align-items属性，默认为auto，如果没有父元素就是stretch
    order 定义子元素的排列顺序，默认是0，数值越小越靠前
p426

### 7.29
回顾固定定位，固定定位跟父级元素没有关系，以屏幕作为参考
使用border-box盒子模型的情况下，height=line-height的话会比正常居中靠下一点点，因为这种模型会把padding和border算入盒子的高度，解决的方法就是line-height减去这两个值

flex有些时候也可以单纯用来调节元素的对齐属性，子元素不是必须加flex分份，弹性的才需要加这个属性

背景颜色线性渐变：
    background: linear-gradient(起始方向, color1, color2) 比如background: -webkit-linear-gradient(left, red, blue)
    这个起始方向是比如从左到右，从左上到右下（top left），默认情况下是从上到下渐变，因为浏览器的支持原因这个属性必须添加私有前缀比如这个webkit

### 7.30
新知识：子元素的flex属性可以写百分比，占主轴那个属性（宽或者高）的多少
flex父元素的子元素不一定非要写flex属性，有时候flex子元素是自适应的

rem适配布局：主要能解决的问题是页面布局的高度也随着屏幕的变化而自动适配
    rem的基准是相对HTML根元素的字体大小，而em是针对父元素的字体大小
    rem最大的优点是通过修改html里面的文字大小来改变页面中元素的大小，可以整体控制

媒体查询：CSS3新语法
    @media，可以针对不同的屏幕尺寸设置不同的样式
    语法格式 @media mediatype and/not/only (media feature) {
        CSS代码
    }
    mediatype用于区分终端类型 all/print（用于打印）/screen（各种屏幕）
    关键字用于链接媒体类型和媒体特性 and连接多个媒体特性 not排除某个媒体特性 only只有某个媒体特性
    @media screen and (max-width: 800px) 在屏幕上且最大像素为800，如果有多个条件就多个and

当样式比较繁多的时候可以引入资源，核心是针对不同的媒体使用不同的样式表，原理就是在link中判断设备尺寸
语法格式 <link rel="stylesheet" media="mediatype and/not/only (media feature)" href="mystylesheet.css">

Less 一种CSS扩展语言，也称为CSS预处理器，为CSS增加了程序式语言的特性，写的时候写在专门的.less文件中
Less变量 @var: pink 使用 background-color: @var 其他的CSS可以直接写在.less文件中，需要经过编译自动转化为CSS
Less嵌套 子元素的样式可以写在父元素里面，如果是父元素的属性或者伪类选择器等，要添加&（相当于就是父元素的名字），比如&:hover {...} &::before {...}
less运算 less提供了简单的加减乘除运算，但是运算符两侧必须有空格，两个不同的单位的话运算结果以第一个单位为准，另外运算最外层可以添加括号
p451

### 7.31
在less中引入其他的less代码使用 @import "file name";或者@import url(...)
flexible.js优势是rem是随屏幕的像素无极变化的，但是官方已经不再维护，也有一些问题
p481

### 8.1
**HTML CSS p496 返回JS课程**
移动端网页特效三个新事件：
    touchstart 手指触摸到DOM元素触发
    touchmove 手指在DOM元素上滑动触发
    touchend 手指从DOM元素上移开触发
对应有触摸事件对象 TouchEvent 可以用来描述触点个数，检测触点移动，触点的增加和减少等
TouchEvent e 所对应的属性和含义
    touches 触摸屏幕的所有触点的列表
    targetTouches 正在触摸当前DOM元素手指的列表
    changedTouches 手指状态发生改变的列表，从无到有或者从有到无（记录的是变化的触点）
手指拖动元素需要当前手指的坐标值，单个手指时使用targetTouches[0]里面的pageX和pageY属性即可
**防止手指移动导致页面滚动 e.preventDefault();**
margin写百分比的话是相对于父元素的

### 8.2
可以用css来实现动画的效果，这比js实现要更简单，动画过渡完成的事件是transitionend
classList属性，可以返回元素的类名表，因为一个元素可能有多个类名，单纯使用className会返回所有的类名
可以添加类名element.classList.add('name') 删除类名 element.classList.remove('name') 切换类名（没有添加，有删除）element.classList.toggle('name')

移动端click事件会有300ms的延时，因为双击会缩放页面，解决这个问题的方法有三种（去除300ms判定）
    1 禁用缩放，在视口标签 content="user-scalable=no"
    2 利用touch事件封装事件解决300ms延迟，触摸屏幕到离开屏幕的事件小于150ms并且无滑动就定义为点击
    3 使用fastclick.js插件
灵活运用swiper可以大幅提高开发的效率

本地存储：
    1 数据存储在用户的浏览器
    2 设置读取方便，页面刷新也不会丢失数据
    3 容量比较大 sessionStorage 5M localStorage 20M
    4 只能存储字符串，可以将对象JSON.stringify()编码后存储
sessionStorage：
    1 生命周期为关闭浏览器窗口
    2 同一个窗口（页面）下数据可以共享
    3 键值对形式存储
    语法 sessionStorage.setItem(key, value) / getItem(key) / removeItem(key) / clear()
localStorage：
    1 生命周期永久生效，除非手动删除否则关闭页面也会存在
    2 可以多窗口（页面）共享，在一个浏览器内部都可以共享
    3 键值对形式存储
    本身语法跟sessionStorage相同
复选框的change事件可以用来判断复选框的内容有没有改变

**jQuery开始，移动端bootstrap**

jQuery对于页面DOM加载完毕再执行脚本的操作：相当于原生js的DOMContentLoaded
    1 $(document).ready(function() {
        要执行的代码
    })
    2 $(function() {
        要执行的代码
    })
在jQuery中$是jQuery的别称，是顶级对象，可以利用$包装对象
jQuery对象本质是利用$包装后产生的对象，以伪数组形式存储，jQuery对象只能使用jQuery的方法
DOM对象转化为jQuery对象 $(DOM对象) 里面可以直接用选择器
jQuery对象转化为DOM对象 $(...)[index] / $(...).get(index) 因为是伪数组，拿出来就行了
获取jQuery对象 $('选择器') 修改元素样式 jQuery对象.css('属性', '值') css()是一个内置的方法
获取jQuery对象的时候内部的选择器可以加入额外参数 :first / :last / :odd / :even / :eq(index) 选择索引号是第几个的
jQuery筛选方法：
    parent() / children(selector) 找亲儿子子代 / find(selector) 找所有子代 / siblings(selector) 找同级对象不包括自身
    nextAll([expr]) 后续所有同级/ prevAll([expr]) 之前所有同级/ hasClass(className) 有无这个类名/ eq(index)
    parents(selector) 根据选择器选祖先元素 / .index() 找伪数组中的第几个
p370

### 8.3
写jQuery事件的时候，可以用$(this)表示当前对象，jQuery有隐式迭代特性，选择器选出来如果是伪数组内部多个，每一个都会自动执行一次
**获得当前元素的索引号的方法jQuery对象.index() 可以用于精准操作一组元素**
操作css的方法 css() 参数只写属性名返回的是属性值，参数也可以是对象的形式，可以不加引号，但是如果值不是数字就还是需要加引号
比如 注意复合属性还是需要驼峰命名法
    $('div').css({
        width: 200px,
        height: 200px，
        backgroundColor: "pink"
    })
通过修改类名修改样式 jQuery对象.addClass(类名) / removeClass() / toggleClass() 切换类

jQuery封装的动画效果，太多了可以参考存在8.1-8.7的文件夹的图片

slideDown / slideUp / slideToggle 上拉下拉菜单
比如 $('div').children('ul').slideDown(200) 里面的参数是动画完成的时间
.hover(function() {} / function() {}) 里面第一个函数对应mouseenter，第二个对应mouseleave，如果只写一个的话鼠标经过离开都会触发
.stop()停止动画，相当于节流阀，写到动画的前面，谁有动画写在谁的前面 $(this).children('ul').stop().slideToggle();
fade系列，时间和透明度必须要写，一般使用fadeTo较多，fadeIn / fadeOut 淡入显示 / 淡出隐藏
.animate()方法 第一个参数对象，表示动画后的属性，第二个参数时间，第三个参数一般不修改默认swing可以改为linear，第四个参数回调函数

获取html元素的属性 jQuery对象.prop(属性名)，如果设置属性就写属性名和属性值，自定义的属性使用attr()获取或者修改
数据缓存 date() 把元素存放到元素的缓存中 存放$('div').data('uname', 'jack') 获取$('div').data('uname')
:checked选择器可以选出被勾选的有几个，适合判断是否全选
**获得或者修改原生js中相当于innerHTML的内容 .html()方法 如果是innerText就是.text()方法 获得设置表单值 .val()方法**
.toFixed()设定数字的小数保留到多少位
p394
**js高级**
类的创建和使用
class Car{
    constructor(uname) { 构造函数，不自己设定也会自动有，new的时候这个函数自动调用
        this.uname = uname;
    }
    drive() { 类里面的成员函数不写function关键字，方法之间不加逗号
        console.log('driving')'
    }
}
var real_car = new Car('benz'); 创建对象
class Son extends Father {...} 子类继承父类
使用super关键字可以访问和调用父类的函数，包括构造函数，有时候子类用父类方法必须super一个父类
子类可以重写父类的方法，就近原则，用super可以强行调用父类的方法 super写在子类构造器中的话必须写在子类的this之前，先父类再子类
对象方法中用对象自己的属性或者调用自身方法一定加上this，比如在构造器中调用函数需要加上this this.drive()
constructor中的this指向的是要构造的这个对象的实例，成员方法的this指向调用者（不一定是对象本身，谁调用this指向谁）

### 8.4
因为成员函数内部的this不一定指向对象自身，有时候又需要用对象自身，可以在类外面设置一个全局变量，在构造器中把this赋值给全局变量
this指向的就是调用者，谁调用指向谁，比如 this.lis[i].onclick = this.toggleTab; //调用成员函数toggleTab的调用者是lis[i]
添加和插入元素的新方法 insertAdjacentHTML('beforeend或者其他位置', 元素字符串);
js高级p20
jQuery对元素的遍历：
    $('div').each(function(index, domElement) {...})
    回调函数的参数是索引号和DOM元素对象（变量本身的名字可以随便取），如果使用jQuery方法就给这个DOM元素对象转换成jQuery对象
    $.each(object, function(index, element){...})
    这种遍历方法可以用于任何对象，主要用于数据处理，比如数组对象等，如果遍历dom元素就把$('div')写在object参数
    如果写的是一个对象，index属性名，element属性值，数组则index序号，element具体的值
jQuery创建和添加元素
    创建 $('<div>新创建的元素</div>') 创建主要是把元素写完
    内部添加
        $('ul').append(li) 这里的li是一个刚才方法创建的变量，放的位置是ul的子元素的最后面，类似原生js的appendChild
        .prepend()就是作为最前面的子元素
    外部添加
        $('div').before('内容') 内容把标签写齐
        $('div').after('内容')
    删除元素
        $('ul').remove() 删除自身
        $('ul').empty() 删除所有子节点
        $('ul').html('') 删除内容，也会删除子节点，跟上面效果相同
p399

### 8.5
jQuery尺寸：
    1 width() / height() content部分的宽高
    2 innerWidth() / innerHeight() content和padding
    3 outerWidth() / outerHeight() content padding border
    4 outerWidth(true) / outerHeight(true) content padding border margin
不仅可以获取，还可以修改，修改的话不需要添加单位，默认是像素
jQuery位置：
    1 offset() 获取设置元素对于文档document的属性，跟父元素无关，获取的是对象{top, left}，设置可以这么写element.offset({top: 50, left: 20});
    2 position() 相对带有定位的父级元素的偏移，也是对象跟上面相同
    3 scrollTop() 滚动滚动条被卷曲的头部，$(document).scrollTop()判断页面下滑了多少
    如果制作返回顶部的按钮，需要动画效果的情况下 $('body, html').stop().animate({scrollTop: 0})，因为这个函数只能给元素，document不是元素
动画函数的回调函数的重要作用是在动画执行完毕才会调用
jQuery事件处理
    on()绑定事件，on内部是对象，对象属性是各种事件和相应处理函数的集合，并且前面的事件可以写两个及以上，调用相同的事件处理函数
    on()还可以实现事件委托，子元素的事件绑定到父元素 $('ul').on('click', 'li', function() {...})通过子元素冒泡触发父元素处理
    on()可以给动态创建的元素绑定事件，默认情况下新元素也会被on绑定
    off()可以解绑事件，$('div').off('click') 如果不写就解除全部事件，通过写off('click', 'li')也可以解除委托的事件
    one()绑定的事件只能触发一次，使用方法和on相同
jQuery自动触发事件
    element.click() 类似原生js的写法
    element.trigger('click')
    element.triggerHandler('click') 和前面比的特点是不会触发元素的默认行为
jQuery p417

在ES6之前没有专门的类的概念，对象不基于类创造，基于构造函数
创建对象三种方式 1 对象字面量 2 new Object() 3 自定义构造函数
new在执行的时候会做的四件事：
    1 内存中创建一个新的对象
    2 让this指向这个对象
    3 执行构造函数中的代码，给对象添加属性和方法
    4 返回这个新的对象（所以说构造函数不需要return）
对象中有两种成员 实例成员和静态成员
    实例成员只能通过实例化的对象访问，不可以通过构造函数名访问
    静态成员是直接添加到构造函数上的比如构造函数是Car()，Car.brand = 'benz'就是直接添加到构造函数，只能通过构造函数名访问
构造函数方法创建对象存在浪费内存的问题，比如对象的实例函数就会反复开辟内存存放
构造函数可以通过原型prototype分配共享的函数，每一个构造函数都有prototype属性，指向另一个对象，prototype就是一个对象，对象的方法和属性都被构造函数拥有
**一般一些不变的方法可以直接定义到prototype对象上，这样对象的实例就可以共享方法**
对象都会有属性__proto__指向构造函数的prototype原型对象，对象可以使用构造函数的prototype属性和方法是因为有__proto__
__proto__是一个非标准的属性，意义是给对象的查找机制提供方向和路线，但是是一个非标准的属性，仅仅指向原型对象prototype，实际开发不使用这个属性
//目前MDN显示这个属性已经被废除，不再推荐修改原型，而是创建一个继承于原型的新对象，使用Object.create()
在对象调用方法的时候，先看自身有没有写内部的方法，如果没有再到构造函数对应的原型里面去找
在__proto__和prototype中都有constructor属性，存放的也就是构造函数本身，记录对象引用自哪一个构造函数
有些情况下直接通过 prototype = {一个新的对象} 重新赋值修改了原型，需要把原型的constructor属性指回构造函数 constructor: 构造函数的名字;
原型对象也有原型 构造函数名.prototype.__proto__指向的是Object中的prototype，作为最顶层Object.prototype.__proto__指向的是null
原型链图示存放在8.1-8.7中
从原型链引申出js的成员查找机制，先找对象自身，然后它构造方法的原型，然后Object的原型，如果还是没有就是null
原型对象函数和构造函数中的this都指向实例对象
修改内置对象的原型可以添加内置对象的自带函数，比如修改Array.prototype.func = function() {...}添加新方法
call(thisArg, arg1, arg2, ...)函数可以修改函数运行时候this的指向 call的使用：函数名.call()，第一个参数就是修改后的this
在ES6之前因为没有extends关键字，继承通过构造函数+原型对象模拟继承，称为组合继承，核心是子类构造函数通过call()修改this调用父类
p35

### 8.6
接昨天的组合继承，父类的方法是写在prototype原型对象的，子类构造函数仅call父元素构造函数，不包括原型对象所以也不能得到父类的方法
简单的Son.prototype = Father.prototype会出现问题，修改子原型对象会导致父原型对象也跟着变化（指向了同一个prototype原型对象）
解决方案Son.prototype = new Father(); Son.prototype.son_func = ... 为子类的继承专门创建一个父类的实例对象，然后修改constructor属性
**利用直接赋值对象的方法修改了原型对象，一定要修改constructor属性指回原来的构造方法**
从ES6开始引入了class类，类的本质还是一个函数function，可以简单认为类是构造函数的另一种写法
跟构造方法相同，类也有原型对象，原型对象有构造函数属性，也可以通过原型对象添加方法，创建的实例也有__proto__属性

ES5对于基础对象提供的新方法：
数组：
    forEach()遍历方法 arr.forEach(function(value, index, array) {...})
    filter()筛选方法 array.filter(function(currentValue, index, arr) {...}) 直接返回一个新的数组
    map()创建一个新数组，新数组的每一个元素都是调用了一次回调函数后的结果
    比如 var newArray = arr.filter(function(currentValue, index, array) {return currentValue >= 20;})
    some()查找是否有满足指定条件的元素，找到第一个就停止，返回值布尔值，语法同上
    filter和forEach遇到return也不会中止迭代
字符串：
    trim()方法，去除字符串两端的空白字符，包括空格换行制表等，不影响原字符串，返回的是新字符串
对象：
    Object.keys(obj)回去对象自身有的所有属性，返回由属性名组成的数组
    Object.defineProperty(obj, prop, descriptor)定义对象新属性或者修改原有属性 **属性本身就可以添加，主要应该是在于属性的修改和特性的调整**
    这个方法的使用对象是直接针对于构造函数，也就是类名而不是实例对象
        descriptor属性是一个对象，里面可以有四种属性：
        value（有就修改无则添加，默认是undefined）
        writable（属性的值是否可以修改默认false）
        enumerable（是否可以被枚举默认false）比如说遍历Object.keys()不能得到这个属性
        configurable（属性是否可以被删除或者修改特性默认false）

函数部分：
    使用new Function()创建函数时，小括号内部是字符串，参数和函数体都在字符串内，先写参数后写函数体
    所有函数都是Function的实例对象，函数也属于对象 函数内部的this指向可以参见8.1-8.7截图
    普通的函数的this指向是window，调用的时候简写了window，本身应该是window.fn()
    改变this指向的方法call() bind() apply()
    apply的使用 func.apply(thisArg, [argsArray])传参必须写在数组（伪数组也行）里面，thisArg写null就不改变，返回值就是本身该返回的值
p56

### 8.7
接函数部分：
    bind()不会调用函数，但是可以修改函数的this内部指向，语法跟call相同，返回值是由指定的this和初始化参数改造的原函数拷贝
    一般情况下参数是不写的，仅仅用这个来修改this的指向，比如本身func()的this指向的是window，写var fn = func.bind(obj)换绑
严格模式 strict mode:
    严格模式可以为整个脚本开启或者给个别函数开启，为脚本开启就在开头写 'use strict'; 为某个函数开启就放在函数体开头部分
    严格模式下变量必须先声明再赋值，不能使用delete删除已经声明的变量，**全局作用域下的函数的this是undefined**
    构造函数必须使用new调用，new实例化的构造函数还是指向创建的对象实例
高阶函数 对其他函数进行操作的函数（接收函数作为参数，将函数作为返回值输出）：
    回调函数的常见写法 callback && callback() 利用与的短路特性
闭包 有权访问另一个函数作用域中变量的函数：
    闭包实现的重点是返回一个函数，这个函数相当于另一个函数的内部函数，导致在外部调用这个函数可以拿到另一个函数作用域中的变量
    主要作用是延伸变量的作用范围
深浅拷贝：
    浅拷贝拷贝本层，更深层次对象只拷贝引用，深拷贝拷贝全部
    使用for循环的拷贝就是浅拷贝 ES6新增语法糖Object.assign(target, source)
    深拷贝可以使用函数递归实现，分为三种数组，对象，基础数据类型
p76

### 8.10
正则表达式：主要用于匹配字符串内容，替换字符串内容，从字符串中提取内容
    在js中正则表达式是作为一种对象的
    创建正则表达式有两种方法
        1 调用对象RegExp对象的构造函数创建 var regexp = new RegExp(/表达式/);
        2 利用字面量创建正则表达式 var regexp = /表达式/;
    正则表达式的对象方法：
        regexpObj.test(str)，验证字符串是不是符合正则的规范，返回true或false

正则表达式的特殊字符：
    边界符：提示字符出现的位置
        ^ 表示匹配行首的文本 /^abc/ 必须以abc开头
        $ 表示匹配行尾的文本 同上 可以连用实现精确匹配 /^abc$/ 必须是abc
    字符类：有一系列字符可以选择，匹配其中一个就行
        [] /[abc]/ 有abc三个任意一个就行
        [-] 方括号内的短横线表示范围 /[a-zA-Z0-9_]/ 有大小写字母，数字或者下划线就行
        [^] 方括号里面的^表示取反 /[^a-z]/ 不能包含小写字母 **和中括号外面的区分开**
    量词符：用于设定某个模式出现的次数
        * 重复>=0次 /^a*$/ 开头可以没有a，也可以很多a，空或者很多a，其他不行
        + 重复>=1次 /^a+$/ a或者很多a
        ? 重复0/1次 /^a?$/ 空字符串或者就一个a
        {n} 重复n次
        {n,} 重复>=n次
        {n.m} 重复n-m次
p85

### 8.11
接正则表达式：
    三种括号的使用：
        []中括号表示字符集合，匹配中括号里面的任意一个字符即可
        {}限制的区域是前一个字符，/^abc{3}$/ 满足这个正则表达式只能是abccc
        ()小括号可以提升优先级比如 /^(abc){3}$/ 这个只能是abcabcabc
    预定义类：
        \d 匹配0-9任意数字
        \D 匹配非0-9
        \w 匹配任意字母数字下划线
        \W 匹配非数字字母下划线
        \s 匹配空格类，包括换行符，制表符
        \S 非空格类
    正则的或者运算符 |
    正则表达式参数：
        写在两个//后面[switch]，有三种值 g全局匹配 i忽略大小写或者gi一起写 比如/.../g
    字符串的replace方法第一个参数除了写要被替换的字符串，还可以写正则表达式

**ES6-ES11**
let关键字声明变量的特点：
    1 不能重复声明，如果用var可以
    2 提供新的块级作用域，防止外层用var声明的变量都添加到全局window，**所谓的块级作用域就是一对大括号**
    3 不存在变量提升，不声明先使用会报错
    可以在for里面使用，限制于for的块级作用域

const关键字声明常量：
    1 必须赋初值，并且不能修改，**重点是内存地址不能修改**
    2 同样块级作用域
    3 对于数组内部元素，对象内部属性的修改不算对常量的修改，允许

变量解构赋值：
    可以创建连续变量匹配数组中的值，比如const arr = [1, 2, 3]; let [one, two, three] = arr;
    对象需要属性名完全相同，如果想不一样就要写别名比如 let {name: myname, age: myage} = obj;
    主要可以便于频繁调用，解构出来的对象方法可以省去调用方法需要先加对象的问题

模板字符串：
    除了单双引号还可以使用反引号`` 好处是内容可以直接添加换行符以及使用${}把变量或者函数直接拼接进去字符串

对象的简化写法：
    外层已经有let name = 'jack'; let age = '20' 那么可以直接let person = {name, age}
    等效内部 {name: name, age: age} 方法也可以省略function写到里面

箭头函数:
    语法格式：
        let fn = (参数列表) => {函数体};
    **找this最简单的方法是找箭头函数外层有没有函数，没有就是window，对象不产生作用域**
    主要特点：
    1 this静态，this始终指向函数声明时所在的作用域下this的值
    2 不能作为构造函数实例化对象
    3 不能使用arguments变量，没有prototype属性，不能用箭头函数写生成器函数
    形参有且只有一个可以省略小括号，比如 let add = n => {...};
    函数体只有一句可以省略大括号，但是必须也省略return 比如 let pow = n => n*n;
    箭头函数适合与this无关的回调，比如定时器，数组方法等，不适合事件回调，对象方法这种this需要动态变化的
    箭头函数的this始终指向定义箭头函数的对象，指向定义的箭头函数那一级块级作用域的this

函数参数可以赋初值：一般有默认值的参数放后面
    function add(a, b, c=10) {...}

rest参数获取不定实参：
    替代arguments，使用arguments获取的不定实参是对象而rest参数获得的是数组，更加方便
    语法格式 function data(name1, ...args) {...} data('jack', 'sam', 'peter') 获取的是'sam', 'peter'构成的数组
    因为获取的是最后不定长的参数列表，rest参数必须放最后，并且参数名前面添加...

扩展运算符...让数组转化为逗号分割的参数序列：
    fn(...array_name)，把数组每个元素分开都传进fn函数
    rest参数的...放在函数的声明位置，扩展运算符的...放在函数的调用位置
    提供了简单的合并数组方法 arr = [...A, ...B]
    克隆数组的方法（浅拷贝） A_copy = [...A];
    伪数组转数组的方法 divs_arr = [...divs];

新的原始数据类型Symbol
    最主要的意义是生成绝对独一无二的值
    1 唯一的，用于解决命名冲突
    2 不能和其他数据进行运算
    3 定义的对象属性不能使用forin循环遍历，可以使用Reflect.ownKeys获取对象的所有键名
    主要作用是给对象添加方法
p18

### 8.12
**深水区进度放缓**
迭代器：一种接口，为各种不同的数据结构提供统一的访问机制，任何数据结构部署iterator接口板就可以完成遍历
    原生具有iterator接口的数据：Array Arguments Set Map String TypedArray NodeList
    迭代器一般配合forof方法使用，forin循环变量保留的是键名，而forof保留的是键值
    forof会自动调用迭代器Symbol.iterator
生成器：用于解决异步
    语法是function * fn() {...} 函数体里面可以写yield进行分隔，每次迭代器执行一次进行一段分隔的代码

Array扩展方法：
    转化伪数组的第二种方法 Array.from(伪数组)返回值为转换后的数组，伪数组后还可以添加函数实现比如说全部*2
    Array.find()里面的参数是查找条件的函数，找到第一个满足条件的就返回，没有就返回undefined，而some是返回真假
    Array.findIndex()找第一个符合条件的数组成员的索引，没有就返回-1
    Array.includes(value)找数组中是否有value值，返回真假，相比some功能更简单

### 8.13
字符串扩展方法：
    String.startsWith(str) / String.endsWith(str) 参数字符串str是否在开头或者结尾，返回真假
    String.repeat(n) 将原字符串重复n次返回新字符串

Set数据结构：类似于数组但是成员都是唯一的
    直接使用构造函数生成Set数据结构 const s = new Set(1, 2, 3)
    自带属性有size，相当于length，构造函数也可以直接传入数组，传入的数组自动去重
    自带方法add(value)返回set本身 delete(value)返回真假是否删除成功 has(value)返回真假 clear()无返回值
    forEach方法对每个成员执行一些操作，没有返回值

ES6浏览器中，使用let在块级作用域声明函数存在变量提升，类似于var，这个特殊规定仅限于ES6浏览器，**最好尽量不在块级作用域声明函数**
//函数声明类似于var，即会提升到全局作用域或函数作用域的头部。同时，函数声明还会提升到所在的块级作用域的头部
实在需要可以在块级作用域写函数表达式类似 let fn = function() {...};
在纯块级作用域前面可以添加do，替代部分简单函数的功能，返回值是块级作用域最后一条语句的结果
想要完全锁死一个对象，使用Object.freeze(obj)，返回值也是obj
在顶级作用域的使用var或者function声明的变量直接添加到顶级对象window的属性，而使用let或const只创建全局变量，不添加到顶级对象
关于解构赋值：
    只要某种数据结构具有Iterator接口，都可以采用数组形式的解构赋值，解构赋值也可以有默认值，但是只有是undefined的时候才会采用默认值
    解构赋值的规则是，只要等号右边的值不是对象或数组，就先将其转为对象。由于undefined和null无法转为对象，所以对它们进行解构赋值时都会报错。

字符串扩展方法2：
    str.padStart(length, str2) / str.padEnd(length, str2) 用str2在首/尾补充str到length长度，如果省略str2参数就使用空格

数值类型的扩展方法：
    Number.isFinite() 判断是否是有限的以及是否是数字，返回真假
    Number.isNaN() 判断是否是NaN
    Number.parseInt() / Number.parseFloat() 和自带的全局parse函数完全相同
    Number.isInteger() 判断是否是整数
    Number.EPSILON 一个极小的常量数量级为10的-16次方，一般用于检测浮点值的精度
    JavaScript能够准确表示的整数范围在 -2的53次方 到 2的53次方 之间（不含两个端点），超过这个范围就无法精确表示，为此提供方法Number.isSafeInteger()
    ES6引入了Number.MAX_SAFE_INTEGER和Number.MIN_SAFE_INTEGER两个常量，用来表示这个范围的上下限
    新增指数运算符 ** 比如 2 ** 2 = 4

函数：
    函数添加了默认参数后参数本身会形成一个作用域，找不到会到外层去找而不是函数体

### 8.14
接函数：
    通过抛出错误的方法可以指定某个函数的参数是必须写的
    函数的length属性不包括rest参数
    规定只要函数参数使用了默认值、解构赋值或者扩展运算符，那么函数内部就不能显式设定为严格模式，否则就会报错
    上述的严格模式有两种解决方法，全局使用严格模式或者把函数放在一个无参数的立即执行函数中
外出旅游...

### 8.17
普通for循环的迭代常量因为会不断修改所以不能使用const，但是对于forin或者forof这样每次都在修改的变量还是可以使用const
类似于instanceof运算符，typeof运算符也会返回变量的类型，null返回Object 
只是以字符串的方式返回7种数据类型（包括Symbol的简单数据类型和包括数组的Object类）
基础六种数据类型undefined null boolean number String Symbol 一种复杂数据类型Object常见的包括数组函数等
判断是否是NaN的方法不是if(value == NaN)因为NaN不等于任何值包括NaN，必须使用方法isNaN()
除了null和undefined都有toString方法，转化为和原始值等价的字符串，更为通用可以使用String()转型函数，实际上还是会调用toString
创建Symbol类型使用Symbol()方法，这个方法传入的参数字符串仅仅用于描述，与实际的值无关
Symbol.for(key)方法，根据传入的key字符串键值，在全局符号表内找符号，有就返回，没有就创建后返回，跟直接Symbol()创建的区别在于全局
全局注册表中的符号必须使用字符串键来创建，使用Symbol.keyFor(symbol)根据传入的符号返回全局符号对应的字符串键，没有返回undefined

### 8.25
除了直接添加Symbol变量的属性，还可以使用defineProperty()添加属性
Object.getOwnPropertyNames()返回对象实例的常规属性数组，Object.getOwnPropertySymbols()返回对象实例的符号属性数组。这两个方法的返回值彼此互斥
Object.getOwnPropertyDescriptors()会返回同时包含常规和符号属性描述符的对象，值是什么也会返回
Reflect.ownKeys()会返回两种类型的键，类似于Object.keys()但是不会受enumerable的影响，Reflect是一个内置对象，主要可以替代Object类对对象进行操作
Reflect实现反射，使得程序可以在运行时获取自己的信息
ES6也引入了一批常用内置符号（well-known symbol），用于暴露语言内部行为，可以直接访问、重写或模拟这些行为
这些内置符号都以 Symbol 工厂函数字符串属性的形式存在，所有内置符号属性都是不可写、不可枚举、不可配置的
常用内置符号有很多，比如Symbol.iterator，修改这个属性对应的函数就可以修改forof循环的迭代过程
每个 Object 实例都有如下属性和方法。
    constructor：用于创建当前对象的函数
    hasOwnProperty(propertyName)：用于判断当前对象实例（不是原型）上是否存在给定的属性。要检查的属性名必须是字符串（如 o.hasOwnProperty("name")）或符号
    isPrototypeOf(object)：用于判断当前对象是否为另一个对象的原型
    propertyIsEnumerable(propertyName)：用于判断给定的属性是否可以使用for-in 语句枚举。与 hasOwnProperty()一样，属性名必须是字符串
    toLocaleString()：返回对象的字符串表示，该字符串反映对象所在的本地化执行环境
    toString()：返回对象的字符串表示
    valueOf()：返回对象对应的字符串、数值或布尔值表示。通常与 toString()的返回值相同
因为在 ECMAScript 中 Object 是所有对象的基类，所以任何对象都有这些属性和方法

逻辑与&&并不一定会返回布尔值，而是遵循如下规则
    如果第一个操作数是对象，则返回第二个操作数
    如果第二个操作数是对象，则只有第一个操作数求值为 true 才会返回该对象
    如果两个操作数都是对象，则返回第二个操作数
    如果有一个操作数是 null，则返回 null
    如果有一个操作数是 NaN，则返回 NaN
    如果有一个操作数是 undefined，则返回 undefined

### 8.26
与逻辑与类似，如果有一个操作数不是布尔值，那么逻辑或||也不一定返回布尔值，它遵循如下规则
    如果第一个操作数是对象，则返回第一个操作数。
    如果第一个操作数求值为 false，则返回第二个操作数。
    如果两个操作数都是对象，则返回第一个操作数。
    如果两个操作数都是 null，则返回 null。
    如果两个操作数都是 NaN，则返回 NaN。
    如果两个操作数都是 undefined，则返回 undefined
使用==对比时，null和undefined是相等的，因为==默认会加入转换的操作，所以一般使用===更为保险
例如使用==时，55和'55'是相等的，这个时候就必须使用===

**AJAX**
可以在浏览器中向服务器发送异步请求，可以用于在无刷新的情况下获取或发送数据，比如动态请求数据
XML与HTML类似，不同的是HTML都是预定义标签，XML中的标签都是自己定义的，没有预定义标签，XML设计用来传输和存储数据
目前AJAX的信息传递一般不再选用XML格式，转为使用JSON
AJAX的缺点是无浏览历史，不可回退，存在跨域问题，SEO不友好
p5

### 8.27
HTTP的请求报文：
    重点是格式和参数
    格式是 行\n头\n空行\n体
    行的格式 GET/POST url HTTP协议版本号
响应报文：
    行的格式 HTTP协议版本号 状态码 状态码对应字符串
    响应体里面就是HTML内容
p13

### 8.31
HTTP的请求都在xhr的方法中设置，xhr.open()方法设置GET/POST选项以及URL地址
xhr是XMLHttpRequest的简称，发送参数的时候使用xhr.send()比如xhr.send('a=100&b=100&c=100')
xhr.setRequestHeader(请求头名, 请求头值)
通过直接设置xhr.responseType = 'json';可以不需要使用JSON对象下的转换方法
AJAX p17
**同步开始进行vue**
webpack可以自动转化兼容性代码，代码压缩混淆一类的问题
npm下载的选项，-S是--save的简写，-D是-- save-dev的简写，只在开发阶段使用的包用这个
配置webpack的流程：
    1 项目的根目录创建webpack.config.js配置文件
    2 package.json的script节点下新增dev脚本
    3 终端运行npm run dev命令，启动webpack进行项目打包构建
webpack.config.js中配置的mode有两个选项分别是development和production对应开发和实际上线
把mode选项改成production生成的main.js就自动变成经过压缩的
执行npm run dev后会生成一个新的目录dist，里面的main.js才是webpack处理后的js文件
封存尚硅谷AJAX p17 黑马vue p8 应该先把node.js学完再转vue，明天开始转nodejs，预算时间大概1周，最晚9.10中秋之前

### 9.1
浏览器中的js主要有两部分组成，JS核心语法和WebAPI
node运行环境包括V8引擎和内置API（和WebAPI不同），所以在node中不能调用DOM，BOM，AJAX的APInode
node基本实现了所有的ES6新特性，但是在模块的引入和导出过程中选用COMMONJS规范
新的node版本require不再内置，使用需要添加如下的代码：
import { createRequire } from 'module';
const require = createRequire(import.meta.url);
实际上添加了这两行代码还是有一些问题，将文件后缀改为.mjs就可以成功了，强制使用ES6规范

fs模块：
    node提供的可以操作文件的模块
    使用前需要先导入 const fs = require('fs'); require是commonjs的规范
    fs.readFile(path[, options], callback)
        **options表示以什么类型的编码格式来读取文件，这个默认情况下不是utf8，一般情况下需要指定**
        callback回调函数有两个参数err和dataStr对应的是读取成功和失败，读取失败err值是错误对象，dataStr是文件的内容
        通过判断err是否是null就可以确定是否读取成功，如果成功一定是null，如果读取失败可以使用err.message获取失败的消息
    fs.writeFile(file, data[, options], callback)
        file参数指定一个文件路径的字符串，data表示写入的内容，options表示什么编码类型，默认utf8
        回调函数参数只有err，记录写入的错误对象，也可以用来查看是否写入成功
    使用./或者../这种相对路径容易出现路径拼接的问题，代码运行的时候以执行node命令这一层的目录动态拼接出路径
    **为了解决上述的问题，除了使用绝对路径以外，还可以添加node的成员__dirname表示当前文件所在的目录，然后进行路径的拼接**
    **在使用__dirname之前需要添加const __dirname = path.resolve()声明**

path模块：
    path.join()方法可以实现路径的拼接，对参数的个数不限，返回值就是拼接好的路径
    path.basename(path[, ext])方法可以从路径字符串中将文件名解析出来，第一个参数是路径字符串，第二个可选参数表示文件扩展名
    返回值是最后文件的名，如果有ext参数会省略最后的文件后缀
    path.extname(path)获取路径字符串最后文件的后缀扩展名，返回值比如.html
正则表达式的成员方法regexp.exec(str)，捕获所有满足正则表达式的部分，构成数组，没有的话返回null
p14

### 9.2
http模块是node提供的可以创建web服务器的模块，主要是使用http.createServer()
计算机网络端口号的概念，在一台服务器中可能运行大量的web服务，每一个服务都对应一个唯一的端口号，客户端送来的请求通过端口号到对应的web服务
实际使用过程中80号端口可以省略，默认情况下就是使用的80端口
**创建web服务器的基本步骤：**
    导入http模块
    创建web服务器实例 http.createServer()
    为服务器实例绑定request事件，监听客户端请求 server.on('request', (req, res) => {})
        只要服务器接收到客户端的请求就会调用on绑定的回调函数
        req是请求对象，包含客户端的数据和属性，比如req.url请求的地址是什么 req.method请求的http方法
        向客户端相应内容是res.end()方法，里面的参数可以直接是html字符串
        解决中文显示乱码的问题：res.setHeader('Content-Type', 'text/html; charset=utf-8')
    启动服务器
根据不同的url请求相应不同的html内容：根据req.url通过res.end()返回不同的内容：
默认响应内容是404，判断req.url是/或者/index.html则返回主页，是/about.html则返回关于页面
let fpath = path.join(__dirname, req.url);
fs.readFile(fpath, 'utf8', (err, dataStr) => {};
上述情况一定不要不写req.url，直接写index.html这种不会请求到关联的css和js资源，导致页面只有html
html关联css和js，这两个文件也必须被请求从硬盘中读取到，并且不会res.end()自动显示出来

node模块化：

根据模块来源的不同，将模块分为三种：内置模块，自定义模块，第三方模块

加载模块：
    旧的方法是require，跟import差不多，如果是自定义的模块要写出相对路径，.js的后缀名可以省略
    使用require方法加载模块的时候，模块里面的代码会执行
模块之中也有模块作用域，自定义模块中的变量方法等成员都只能在当前模块内中访问

向外共享模块中的成员：
    每个自定义模块中都有module成员，记录了和当前模块有关的信息
    module.exports对象中存放了共享的成员，导入模块的时候比如import m from 'm'得到的就是module.exports默认状态是空对象
    为了简化node提供了一个新的对象exports，和module.exports指向是一样的，但是实际使用还是以module.exports为准
    CommonJS的规定：
        每个模块内部，module变量代表当前模块
        module变量是一个对象，它的exports属性，即module.exports是对外的接口
        加载某个模块，其实是加载该模块的module.exports属性，require()用于加载模块
p26

### 9.3
不同于内置模块和自定义模块，包是由第三方团队开发的，下载包使用npm，网站是npmjs.com
npm公司提供了包管理工具npm，npm工具集成在node中

安装包使用命令npm i 包名称，其中i是install的简写，安装完包就可以使用import或者require导入包
在初次安装完包后项目文件夹下会多一个node_modules的文件夹和package-lock.json配置文件
    **node_modules文件夹存放所有已经安装到项目中的包，导入包的时候就从这个目录查找加载**
    **package-lock.json配置文件用来记录node_modules目录下每个包的下载信息，例如包名，版本号，下载地址等等**
    一般情况下不要手动修改这两个，npm会自动维护

默认情况下安装的是最新版本的包，在包名后添加@版本号就可以添加指定版本的包

npm规定，在项目的根目录必须提供package.json的包管理配置文件，记录与项目有关的一些配置信息，比如如下的信息：
    项目名称，版本号，描述等
    项目中使用了哪些包
    哪些包只在开发阶段使用
    哪些包在开发和部署的时候都需要使用
**快速创建package.json使用命令npm init -y 安装包的时候npm会自动把包名称和版本号记录到package.json中**
**package.json中有dependencies节点，专门用来记录使用npm install安装了哪些包**
在有package.json的情况下，直接使用npm i就可以直接根据package.json的dependencies节点直接下载

运行npm uninstall 包名 可以卸载指定的包，并且package.json也会自动修改

package.json中还有devDependencies节点，用于存放只在项目开发阶段使用的包
**使用npm i 包名 -D或者--save-dev就可以自动记录到devDependencies节点中**

使用npm config set registry=https://registry.npm.taobao.org/ 可以切换下包地址是淘宝的镜像源
另一种方法也可以使用nrm工具，先使用npm下载nrm，然后nrm ls显示可用镜像，nrm use taobao即可切换

被安装的到node_modules目录的包都是项目包，而在执行npm i时添加-g参数的话就会安装全局包
全局包被安装到C:\Users\zzm\AppData\Roaming\npm\node_modules，判断是否需要全局安装可以参考npmjs官网的说明

包的内部结构：
    包必须以单独目录存在
    包的顶级目录下必须包含package.json这个包管理管理配置文件
    package.json中必须包含name version main三个属性，分别代表包名，版本号，包的入口
    main属性就是在包顶层目录，指定去找哪个js文件作为包的源代码，比如'index.js'意思就是 包顶层目录/index.js 是入口

在包的根目录使用npm publish命令就可以把包发布到npm上
使用npm unpublish 包名 --force可以撤销已经发布的包

模块的加载默认是从缓存中出来，内置模块有最高的优先级，如果同名，先加载内置模块
自定义模块先加载原文件名，再补.js，再.json，再.node，还是没有就会报错
第三方模块先在node_modules里面找，找不到的话会一级一级沿目录往上走
如果把目录作为模板标识符使用require加载，先找package.json的main，没有的话找index.js还是没有就会报错

node p38 正式开始Express，可能需要绕回去学ajax

### 9.5
URL地址的三个组成部分
    客户端和服务器的通信协议
    存有该资源的服务器名称
    资源在服务器上具体的存放位置

在网页中请求服务器的数据资源，会使用到XMLHttpRequest对象，xhr是浏览器提供的js成员

客户端对服务器的请求：获取资源get，发送资源post
使用jquery操作ajax相对简单，提供了三个函数
    $.get(url, [data], [callback]) 请求资源地址，请求资源时携带的参数对象，请求资源成功的回调函数
        参数比如{id = 1}就只会返回id是1的系列数据，回调函数function(res) {} 其中的res就是请求回来的资源
    $.post(url, [data], [callback]) data是传给服务器的对象，其他相同
        回调函数function(res) {} 其中的res是传输后的返回值，可以看出传输的状态
    $.ajax({type, url, data, callback})传入的是配置对象，四个参数是配置对象的成员
        type是'get'或者'post'，其他相同
ajax p11