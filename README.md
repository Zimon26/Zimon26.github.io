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
制作表格时合并相邻边框使用border-collapse: collapse;
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
**捕获和冒泡阶段主要是父子事件的执行顺序区别，捕获是父->子，而冒泡是子->父