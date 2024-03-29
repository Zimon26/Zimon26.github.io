## Welcome to Zimon's Blog

### 6.16

---

类选择器，伪类选择器的使用，语法例如 a:hover
静态伪类 visited 和 link 只用于超链接 a，并且 visited 只改变颜色属性
动态伪类 hover，active，focus，active 是点击不松开
另一个伪类选择器 first-child 选择第一个子元素
背景图片平铺属性取值 repeat, repeat-x, repeat-y, no-repeat

### 6.17

---

背景图片的固定，background-attachment，只有两个属性，scroll 和 fixed
背景图片五个属性一起写 background:背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置
背景颜色的透明度 rgba，最后一个 0~1 的参数表示透明度，0 全透明，1 完全不透明
一般超大的图片和较小的图标用背景图片来做，好控制位置

CSS 的三大特性：层叠性，继承性，优先级
继承性中可以继承的元素属性有 text- font- line-以及 color 属性
选择器的优先级!important > 行内样式 > ID > 类和伪类 > 元素 > 继承或者通配符\*
!important 参数写在属性键的后面比如 color: pink!important
注意：无论父元素的优先级是多高，继承其的子元素优先级永远是 0
复合选择器涉及优先级的叠加，权重有叠加但是永远不会进位

### 6.18

---

边框属性可以连写：border: width style color;
border 四个边框可以拆开，比如 border-top
制作表格时合并相邻边框使用 border-collapse: collapse;这个属性写在表格而不是列表
border 是本身盒子大小的扩充，盒子的宽高属性不包括 border

padding 的简写设置
一个值代表上下左右，两个值前上下后左右，三个值上，左右，下，四个值上右下左
padding 同样会影响盒子的大小
在块级元素未设置宽高时设置 padding 不会改变其宽高，块级元素的特性是默认宽高为容纳其的盒子的宽高，宽高是不可以继承的

**块级元素的水平居中显示，设置 width 以及 margin 设置为 auto，或者 margin 设置为 auto 并且 text-align: center**
**行内元素和行内块元素的水平居中显示，父元素设置为 text-align: center;**
**嵌套块元素塌陷问题**，解决方案：给父元素添加边框/内边框或者添加属性 overflow: hidden;
**品优购快报实践**
去掉 li 前面的小圆点的方法 list-style: none;
p167

### 6.19

---

在做品优购快报的时候出现的问题，首先是全局设置 margin 和 padding 为 0 后重新设置的属性不起作用，第二是不清楚如何使整个 ul 在边框下居中
盒子阴影属性 box-shadow: h-shadow v-shadow blur spread color inset
分别是水平距离，垂直距离，模糊程度，阴影大小，阴影颜色，是否外部阴影转为内部阴影
文字阴影也很类似 text-shadow: h-shadow v-shadow blur color

浮动效果的主要作用：改变网页标签的排列模式
浮动元素的三个重要特性：1 浮动元素会脱离标准流 2 浮动元素一行内显示并且元素顶部对齐 3 浮动元素具有行内块元素的特性
脱离标准流意味着没有浮动的盒子会自动填补位置，相当于浮动的元素换了一个图层
任何元素都可以浮动，浮动的元素属性类似于行内块元素
网页布局一般先用标准流父元素排列上下位置，之后内部子元素浮动排列左右位置
浮动要注意的点：1 浮动和标准流的父盒子匹配 2 一个元素浮动了，理论上其余的兄弟元素也要浮动
浮动的盒子只影响它后面的标准流，并不会影响之前的标准流
p183

### 6.21

---

清除浮动：想要用浮动的子元素撑开标准流的父盒子，使父盒子的高度自动调节
本质是清除浮动元素脱离标准流造成的影响，策略是闭合浮动，只让浮动在父盒子内部影响
清除浮动的四种方法：1 额外标签法 2 父级添加 overflow 属性 3 父级添加 after 伪元素 4 父级添加双伪元素
额外标签法：在最后一个浮动的元素后面添加一个空的块标签并设置 clear: both;
父级添加 overflow 属性：可以设置为 hidden, auto, scroll 一般选择 hidden 缺点是无法显示溢出部分
父级添加伪元素类似于额外标签法的升级版，不需要手动添加标签

推荐的 CSS 顺序：
1 布局定位属性 2 自身属性 3 文本属性 4 其他属性
浮动的元素不存在外边距合并的问题
p212

### 6.23

---

**出现问题：**制作学成在线的精品推荐模块时发现 margin 被自动设置为了-48px 导致元素不能移动到正确的位置
明天写学成在线的其他部分
定位=定位模式+边偏移
相对定位模式是指相对原始的位置偏移，但是本身还在标准流中不会变化
绝对定位模式是指相对第一个设置了定位的祖先元素的位置偏移，如果没有定位的祖先元素则相对浏览器 Document 偏移，并且绝对定位后元素相较浮动有更高级别的层次，脱离标准流，不再保留原先的位置
子绝父相：子元素绝对定位那么父元素就用相对定位
p229

### 6.24

---

固定定位：相对于浏览器的可视窗口的位置来定位，一般做滚动位置不变的元素，与父元素没有任何关系，不占用原来的位置
固定显示在版心的方法 left: 50%; margin-left: 版心宽度一半

粘性定位：相对于浏览器的可视窗口的位置来定位，但是占用原先的位置，必须添加 top left right bottom 其中的一个才有效

盒子的重叠情况：未指定优先级的情况下，后来者居上，可以通过 z-index 指定优先级，**只有定位的盒子才会有 index 属性**

**解决了昨天的问题** 通过父盒子设置相对定位，子盒子绝对定位设置 right: 0;解决了问题，但是为什么没有浮动到最右未解决

添加绝对定位的盒子不能通过 margin: 0 auto;实现水平居中
绝对定位盒子居中的方法：先用 top，left 等 50%，然后通过 margin 设置为负值，本盒子宽度的一半

添加了定位的行内元素会自动变成行内块元素
浮动的元素不会压住标准流元素的文字部分，但是绝对定位会

**修改总体的属性然后专门修改局部要注意选择器的优先级**

p245

### 6.25

---

元素的显示与隐藏：display: none 隐藏元素，display: block 除了变为块级显示之外还有显示元素，隐藏不保留元素原本位置
visibility: hidden 隐藏元素 visibility: visible 显示元素，和 display 的重要区别是隐藏保留元素的位置
overflow: hidden 隐藏溢出盒子的部分，scroll 显示滚动条，auto 有溢出的话添加滚动条
有定位属性的盒子一般慎用 overflow 属性

### 6.27

---

精灵图的使用：针对小的背景图片，主要借助于背景位置来实现 background-position，一般坐标都是负值
CSS 做小三角图案：盒子不写内容，直接用边框就会出现三角
一些比较杂的点：1form 表单轮廓线属性 outline 2textarea 文本域大小更改属性 resize
**vertical-align 属性：只针对行内元素和行内块元素生效**
**解决图片底部默认存在空白的方法，1 设置 vertical-align 只要不是默认的和基线对齐就可以 2 将图片转化为块级元素**
单行文本溢出显示省略号--必须满足的三个条件：
1 先强制一行内显示 white-space: nowrap;
2 超出部分隐藏 overflow: hidden;
3 文字用省略号替代超出的部分 text-overflow: ellipsis;
类似于页面底部的选择上一页下一页功能使用行内块元素，可以父级元素使用 text-align: center 属性
并排显示的盒子的边框不变粗测试，斜三角的制作
p281

### 6.28

---

html5 的新特性，视频音频和 input 的 type 属性限制输入的内容
css3 新特性，[]选择器，新增可以通过元素的属性选择，**这种选择器不用添加双引号"" 并且属性选择器的优先级同类选择器**
比如 input[type=text] ^开头 $结尾 \*含有 选择 class="icon1-6"的六个 li 元素 li[class^=icon]
结构子类选择器 nth-child(n)里面的 n 是多少就选择第几个，n 也可以不是数字，even 偶数，odd 奇数
nth-child 对父元素所有子元素排序，先找到第几个子元素再看是否和 E 匹配，而 nth-of-type 对指定的 E 子元素排序，找到第 n 个
伪元素新特性：before 和 after，这两个伪元素必须有 content 属性并且属于行内元素，伪元素选择器和标签选择器一样权重都为 1

### 6.29

---

box-sizing: border-box;属性让盒子的宽度高度自动计算 padding 和 border 自动调节
img 的图像模糊属性例如 filter: blur(5px);
过渡属性 transition:要过渡的属性 花费时间 运动曲线 何时开始
1 属性：想变化的 css 属性，宽高，背景颜色，内外边距都可以，如果所有就选 all
2 花费时间：单位是秒 s，单位必须写
3 运动曲线：默认是 ease，可以省略
4 何时开始：单位是秒，可以设置延迟触发时间，默认是 0s，可以省略
过渡属性的位置，哪个元素过渡就写哪个元素，变化多个属性举例：transition: width 0.5s, height 0.5s;
搜索引擎优化：三个标签 title, meta name="description", meta name="keywords" 网站标题，描述以及关键字

### 6.30

---

昨天弄了很久都没有解决的字体图标的问题是因为 css 不是内嵌在 html 中的，所以相对路径要用 css 文件的路径，路径没有更改所以字体图标不会显示
关于垂直居中：像是底部的导航栏还是用行高与高度相等来做，vertical-align 可以实现垂直居中但是必须要求是行内块元素（浮动元素目前测试不行）
我目前针对垂直居中使用过的方法：
1 line-height=height
2 vertical-align: center;
3 已知 font-size 的情况下计算上下 margin 值
4 强行使用子绝父相定位
5\* 父元素用 text-align: center 属性，使其中的行内块（但是测试的结果是全部的元素）元素水平居中

transition 属性：一般写在变化的元素上，比如写在 div 而不是 div:hover，但是如果写在 hover 上也同样可以实现效果

CSS 的继承性：font 开头的，text-indent，**text-align，line-height，**color，visibility，list-style，cursor

### 7.1

---

input 属性中预显示的文字是 placeholder 属性
出现问题：最左边的品优购项目几个字改为定位后，纵向撑大了盒子使 height 增大，导致右边的购物车原定的 top:50%出现问题
解决问题：logo 不使用绝对定位，使用保留原始位置的相对定位

### 7.3

---

符合 SEO 要求的 logo 属性：
1 logo 内放一个 h1 标签，表示重要性
2 h1 内再放一个链接，可以返回首页
3 链接里面放文字(网站的名称)，文字并不显示
4 给链接 title 属性，以便鼠标放到上面看到提示文字
之前并未记录的文字和图片的对齐属性，默认是 vertical-align: baseline 修改这个值可以使行内块元素的对齐改变
p325

### 7.4

##### 一些记录-start

除了笔记，这也是我个人网站的一部分吧，还是记录下来一些心事，今天是颇为不同的一天，安恒实训的开始，看到了企业光辉亮丽的一面，自然也会有它难言之隐，不由自主会想到这些问题，有时候排斥考研确实也是因为太过讨厌数学那些东西吧，不过这些也是没有办法的事。有一件事最为明确，那就是我想就业的很大原因是知道考研可能会失败，本来就业是备选方案，防止考研失败留后路的，这下反而是因噎废食，被动的变成主动的，实训应该让我静下来想一想到底是要什么样的生活更加适合自己

##### 一些记录-end

做品优购网页是个缓慢的过程，先慢慢做，做完的部分会放到 6.27-7.3 的文件夹，目前的进度是到 p356 就业班开始，接下来开始一些 js 的内容

### 7.5

#### JS 开始了

书 p456，常见的 JS 预设的常量
声明变量后默认的值是 undefined

### 7.6

未定义的数组元素默认是 undefined，数组的长度 length 属性是可读写的
js 中全局变量只有在浏览器关闭的时候才会销毁，占内存的资源，而局部变量程序执行完毕就会销毁
js 中的预解析机制：
1 预解析，js 引擎把所有的 var 和 function 提升到当前作用域的最前面，但是变量声明并不赋值，函数也是声明但是不调用
2 代码执行，按照代码自上而下的顺序执行
p142

### 7.7

new 关键字的执行过程：
1 new 构造函数在内存中创建一个空对象
2 this 指向刚才创建的空对象
3 执行构造函数里面的代码，给空对象添加属性和方法
4 返回这个对象

**遍历对象使用 for in，如果其中的变量是 k 则 console.log(k)输出属性名，console.log(obj[k])输出属性值**

获取时间戳（从 1970 年 1 月 1 号到现在的总的毫秒数）的方法
1 var date = new Date(); console.log(date.valueOf()/date.getTime())
2 var date = +new Date(); 简单写法
3 console.log(Date.now()); H5 新增的写法
使用时间的月份和星期的时候要格外注意，月份是 0-11 而星期是 0-6，从星期天开始
创建数组时，使用 new Array()，里面的参数两个或者以上表示填充数组，一个表示数组的长度
数组内置函数 indexOf 和 lastIndexOf 方法除了找元素的索引，还可以用于找元素存不存在
字符串中的所有方法都不会修改字符串本身，都是操作后返回了新字符串，因为字符串实际上是申请了就不变的
typeof null 返回的是对象 object 类型，而不是 null 类型，如果有未来准备存对象的变量，开始赋值可以给 null
所有用 new 创建的数据类型都是复杂数据类型，简单数据类型只有 string number boolean undefined null

#### Web APIs 部分 - DOM - 文档对象模型

DOM 树：
1 文档：一个页面是一个文档，DOM 中使用 document 表示
2 元素：页面中的所有标签都是元素，DOM 中使用 element 表示
3 节点：网页中的内容都是节点（标签、属性、文本、注释），在 DOM 中用 node 表示
DOM 把以上的东西都看成对象
getElementById()通过标签的 id 属性获取 DOM 中的指定 ID 的元素对象，找不到则返回 null
这种情况下写 js 代码往下写，因为文档是自上而下加载（后续会有解决方法）
使用 console.dir()可以更好地打印用上述方法获取的 DOM 元素信息
getElementsByTagName()通过标签名获取这一类元素对象集合，返回的形式是伪数组，只有一个元素或者没有也是伪数组
p198

### 7.8

以下都是 H5 的选择元素方法：
getElementsByClassName()获取指定类名的所有元素
接昨天的内容，这种伪数组的实际类型是对象类型，内部通过元素序号: 元素类型+类名形式储存，可以用数组方式调用
伪数组的细节：arguments 展示一个伪数组，可以遍历，具有 length 属性，按索引存储数据，不具有数组的 push，pop 方法
querySelector()获取指定选择器的第一个元素 querySelectorAll()获取指定选择器的所有元素
不考虑兼容性的的话推荐使用上面的 H5 选择器
获取 body 和 html 元素：body: document.body html: document.documentElement

事件部分：
事件有三部分组成: 事件源，事件类型，事件处理程序
innerText 和 innerHTML 的区别，innerText 只管标签里面的内容，无视 html 标签并且也会去除换行和空格，而 innerHTML 还可以在标签里面写 html 标签
innerHTML 是更官方的标签，使用更多
元素属性的修改，拿到 DOM 中元素的对象，比如 image.src = '...';新的图片 url 地址等
元素样式的修改，box.style.backgroundColor = 'pink';样式名改成驼峰命名法，js 修改 style 是行内样式，优先级很高
p212

### 7.9

当要改变的样式比较多的时候可以开一个新的类，比如 change 类，然后 this.className = 'change';
但是这种修改方式会直接改掉类名，覆盖原来的类名，如果要保留可以这么写 this-className = 'origin change';
p217

### 7.10

给一组元素注册事件：使用循环，做一个五个 div 只有一个可以处于被点击的案例
按照时间来看这周到周末之前应该把 DOM 部分全部看完
重点是自定义的属性要通过下列的函数获取，设置或者删除
获取元素属性的方法 element.getAttribute('属性')，属性是 html 的部分不是样式
html 的属性是可以自定义的，通过上面的函数可以获得自定义的属性
设置属性的方法：element.setAttribute('属性', '值')另外还可以移除属性 element.removeAttribute('属性')

### 7.11

H5 自定义属性的命名规则：前面加上 data-，比如 data-time
H5 新增了自定义元素的获取修改方法：dataset 里面存放所有的自定义属性，前面不能加 data
获取元素的例子：element.dataset.time / element.dataset['time']，如果是连字符还是转化为驼峰命名

DOM 节点：
节点的三个属性：nodeType 节点类型 nodeName 节点名称 nodeValue 节点值
nodeType 1 元素节点 2 属性节点 3 文本节点（包括文字空格换行等） 实际开发主要操作的是元素节点
可以通过.parentNode 获取父节点，找不到的话返回 null
通过 childNodes 获取子节点的集合，不仅加入元素节点还有文本节点比如换行，因为获取到的节点类型复杂导致实际上并不常用
实际上可使用 children 来获取所有元素类节点的集合，常用
另外还有 firstChlid / lastChild 可以获取第一个子节点以及最后一个子节点，但是文本类节点也会算入其中
解决方法是 firstElementChlid / lastElementChild 不过这个方法有兼容性的问题
**保证兼容性可以使用 element.children[0] / element.children[element.children.length - 1]**
.nextSibling 可以获取下一个兄弟节点，但是会算入文本节点 .previousSibling 可以获取上个兄弟节点
解决这个问题使用 nexElementSibling / previousElementSibling 就可以了，不过仍然会有兼容性问题

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

并不推荐的 js 添加元素方法 document.write('<div>123</div>')在文档流执行完毕后这个操作会导致页面全部重绘
innerHTML 创建元素效率高于 createElement，但是创建多个元素要用数组模式（push 累加 join 连接）而不是字符串拼接

元素事件注册：
1 传统方式，利用 onclick 等，特点是唯一性，同一个元素同一事件只能设置一个处理函数，最后注册的处理函数会覆盖前面注册的处理函数
2 方法监听注册方式，addEventListener()，IE9 之前可以用 attachEvent()代替（只支持 ie9 以前，非标准极其不推荐），同一个元素同一个事件可以注册多个监听器，按注册顺序依次执行
语法规则 element.addEventListener('click', function(){}) 第三个参数可以暂时不管

安恒实训：
1 昨天两个思考题的解答
2 Docker 的分层文件系统
3 容器中 runC 的作用：创建容器内部进程，创建命名空间，划分资源等
4 创建自己的镜像：Dockerfile 的命令

### 7.16

vscode 出了一些问题导致保存丢失

删除事件的方法：
1 传统方式 element.onclick = null
2 addEventListener / removeEventListener('click', callback) 函数不能再写匿名函数
3 attachEvent / detachEvent

DOM 事件流：1 捕获阶段 2 当前目标阶段 3 冒泡阶段
事件冒泡：事件开始时最具体的元素接受，然后逐级向上传播到 DOM 最顶层节点
事件捕获：由 DOM 最顶层节点开始，然后逐级向下传播到最具体元素接受
JS 代码只能执行捕获或者冒泡其中的一个阶段，onclick 和 attachEvent 只能得到冒泡阶段
addEventListener 第三个参数时 true 表示捕获阶段调用事件处理程序，默认情况 false 在冒泡阶段调用处理程序
**捕获和冒泡阶段主要是父子事件的执行顺序区别，捕获是父->子，而冒泡是子->父**
实际开发中很少使用事件捕获，关注事件冒泡，有些事件不会冒泡，比如 onblur onfocus onmouseenter onmouseleave

事件对象：
1 event 参数就是一个事件对象 写到侦听函数中，在小括号中当形参来看
2 事件对象只有有事件才会存在，由系统自动创建，不用手动传参
3 事件对象有事件的大量信息，比如鼠标事件的鼠标位置，键盘事件的案件信息
4 事件的命名一般 event / evt / e
5 在 ie678 中只能使用 window.event，可以使用 e = e || window.event
6 e.target 返回注册事件的对象，this 返回绑定事件的对象，ie678 中使用 e.srcElement
7 e.type 返回事件的类型，不带 on
8 e.preventDefault()阻止默认的事件，比如 a 的跳转，button 的点击
9 阻止事件冒泡 e.stopPropagation()，如果是老 ie 用 cancelBubble = true

    例子  去除右键菜单：document.addEventListener('contextmenu', function(e){e.preventDefault()})
          禁止鼠标选中：document.addEventListener('selectstart', function(e){e.preventDefault()})
          各种文库网站禁止复制的方法

鼠标事件的坐标属性：clientX/Y pageX/Y screenX/Y
键盘事件：onkeyup onkeydown onkeypress，press 和 down 的区别是 press 不识别功能按键
三个事件的执行顺序是 down->press->up
e.keyCode 返回按下的键的 ascii 码值，用 key 则返回字符，up 和 down 不区分字母的大小写
down 和 press 在文本框中都是触发的时候文字还没有落入框中，而 up 文字就已经落入框中了

### 7.17

BOM：
大于 document 的概念，顶层元素是 window，下属有 document location navigation screen history
全局变量和全局函数会变成 window 下属的属性和方法
解决之前出现的 js 必须写在元素后面的问题：js 写在 window.onload 里面，等页面全部加载完毕再触发 js
如果有多个 window.onload 事件按最后一个算，当页面图片类比较多的时候可以用 document.addEventListener('DOMContentLoaded', function())
浏览器大小变化时可以使用 window.resize 事件 window.innerHeight / innerWidth 可以反馈浏览器的

定时器：
第一种定时器：window.setTimeout(callback, 毫秒数)，经过多少毫秒就执行 callback 函数，一般比如 var timer1 = window.setTimeout(callback, 2000)
window.clearTimeout(timerID)清除指定的那个定时器
第二种定时器：window.setInterval，主要的区别是每隔设定的事件就会执行一次，同样也可以使用 clearInterval(Interval_ID)消除

**在全局作用域和普通函数中 this 指向的都是 window**

js 的同步和异步：
同步任务都在主线程执行，形成一个执行栈
异步任务通过回调函数实现，回调函数放在任务队列中，异步任务主要三种类型：普通事件 / 资源加载 / 定时器
执行顺序是先执行同步任务，异步任务放入任务队列中，同步任务执行完毕后，系统按次序读取任务队列中的异步任务并执行
主线程执行栈->异步进程处理->任务队列 然后任务队列再按顺序进主线程执行栈 异步进程处理会判断是否该执行回调函数（是否有事件/定时器是否到时等）

js location 是关于页面 url 的属性，上级是 window，可以通过几个下级属性获取 url 的信息 .href 返回全部 url 地址 .search 返回 url 中的参数
location 的三个方法，assign / replace / reload 前两个是换到其他页面，区别是是否保存回退历史，reload 相当于刷新，如果参数是 true 强制刷新

navigator 属性存储了关于浏览器的很多属性，最常用的是 navigator.userAgent 用来判断用户的浏览器类型
history 的 forward / back 方法相当于浏览器按键的前进后退，go 方法可以输入数字决定前进后退几步

元素的 offset 属性，offsetLeft / Top 等表示和有定位的父元素的偏移距离，px 返回值无单位
offsetWidth / Height 返回包括 border padding width/height 的属性 offsetParent 返回带有定位的父元素
**offset 和 style 的对比，style 只能获取行内样式所以不能获取到一般使用的初始外部 css 样式表，但是可以更改，适合修改，offsetWidth / Height 适合获取**
p291

### 7.18

p292

### 7.19

client 属性：
element.clientTop / Left 上左 border 大小 element.clientWidth / Height 返回自身包括 padding content，不含 border 的宽度高度
**client 和 offset 系列的区别主要在边框，offset 有，client 无**
立即执行函数：
(function(){})() / (function(){}()) 函数不需要调用直接执行 立即执行函数的最大好处是创建了一个局部作用域

### 7.20

pageshow 事件是更好的解决 load 事件缓存的方式，所有重新加载的场景都可以用 pageshow
scrollHeight / Width 计算全部的宽高，包括超出部分的高度 / 宽度，另外还有 scrollTop
p305

### 7.21

元素被滚动遮挡的头部是 element.scrollTop，而页面被滚动遮挡的头部是 window.pageYOffset，如果是水平滚动则是 window.pageXOffset
总结三种位置：
offset 经常用于获得元素位置，client 获取元素大小，scroll 获取滚动距离，页面的滚动用 window.pageYOffset
mouseover 鼠标经过自身盒子触发，经过子盒子还会出发，mouseenter 只经过自身盒子触发，对应的是 mouseleave
js 实现动画：
主要原理是利用定时器 setInterval()不断移动盒子位置
实现的步骤是 1 获得盒子当前位置 2 让盒子移动一个单位 3 利用定时器重复这个操作 4 加一个结束定时器的条件 5 这个元素必须添加定位
可以使用一个函数来封装动画函数
p317

### 7.22

p329
今天主要看了轮播图的具体实现，还有一些细节比如轮播图节流阀（防止按按键会一直加速）
window.scroll(x, y)窗口滚动到下 x y 的坐标位置，可以用于回到顶部这种情况，写 xy 的时候不加单位

### 7.23

实际上手动画有点问题，需要回顾视频
调试动画过程中发现的问题，首先是没有 offsetRight 或者 offsetBottom 属性，只有 left 和 top
获取通过 offset，调整通过 style.left 类的属性，并且 style 类的属性赋值需要自己添加单位比如 px，而 offset 类的属性不自带单位
比如说这么写 son.style.left = son.offsetLeft - 1 + 'px';
第二是定时器的中止条件写在定时器函数的内部，写在外部不行
为什么不能写在外部：因为定时器函数属于异步任务，结束条件写在外面相当于同步任务，先执行同步任务再执行异步任务，所以定时器结束条件写在里面

### 7.24

今天的任务是动画封装函数的上手以及非匀速动画 - 比较快的速度就完成了
非匀速动画的核心，计算 target 和当前的距离，每次移动的 step 是(target - offsetNow) / 10，这个结果再随正负数进行上下取整即可
封装函数完成，设置点击实现动画但是在动画还未点击完毕时再次点击会混乱，因为开启了多个定时器，要限制只能有一个定时器，只需要开定时器前关闭定时器即可
p332 接下来的一部分是移动端的 js，应该先补完就业班的 CSS 内容包括 2D3D 旋转，移动端等再回来看，看完这部分是 jquery

### 7.25

**CSS 提高部分**
transform CSS3 的新特性，2D 转换：可以实现元素的位移，旋转，缩放等，简单可以理解为变形
移动效果 transform: translate(x, y)或者也可以分开写 transform: translateX(n)，写的时候要带单位
**translate 最大的优点是不会影响其他元素的位置，会遮盖** translate 写百分比是相对自身元素，对行内元素无效果
这个特性提供了新的移动子盒子到父盒子中间的方法 top: 50% left:50% transform: translate(-50%, -50%)

旋转效果 rotate(?deg)旋转?度，正数顺时针，负数逆时针，可以配合 transition 属性实现旋转的动画
默认情况下旋转的中心点就是元素的中心点，可以通过 transform-origin 设置到其他的位置去
默认情况下是 transform-origin: 50% 50%或者 transform: center center 可以使用方位词 left bottom 或者像素

放大缩小效果 scale transform: scale(x, y) x 宽度 y 高度 默认不带单位写的是倍率 比如原封不动是 scale(0, 0)，等比例缩放的话可以只写一个参数 scale(s)
scale 对比直接修改 width 和 height 的好处是可以设置缩放中心点，并且放缩不会影响到其他的元素，缩放中心点还是 transform-origin

transform 属性可以连着写，但是连着写顺序会有影响，rotate 和 scale 会导致坐标的改变，有多个属性的情况下先写 translate

CSS 动画效果 先定义动画再调用动画
使用@keyframes 定义一个动画，设置 0%起始和 100%结束时候的状态，然后在需要动画的元素中添加属性 animation-name animation-duration
0%和 100%这个属性是动画序列，可以改变任意多样式和任意多次数，用%规定变化发生的事件，或者用 from to 关键字，相当于 0% 100%
p369

### 7.26

动画的其他属性：
何时开始 animation-delay 默认是立即开始
重复多少次 animation-iteration-count 写 infinite 就无限循环
是否下一次逆向播放 animation-direction 默认是 normal 写 alternate 则下一次反向
动画结束后的状态 animationo-fill-mode 默认是 backwards 返回起始状态，写 forwards 停留在结束状态
动画运行或者暂停 animation-play-state 默认是 running，暂停是 paused
动画的简写 animation: 动画名称 持续时间 运动曲线 何时开始 播放次数 是否反方向 动画起始结束的状态
name 和 duration 是必须写的属性，另外简写的属性中不包括 animation-play-state，简写的时候可以用逗号分隔多个动画
元素的透明度属性 opacity，写的就是透明度 0-1
脉冲波纹属性中不写 scale 来放大的原因是如果改动 sacle 会导致 box-shadow 一起倍增
速度曲线中的细节 animation-timing-function 有一个特殊属性 steps()是时间函数中的间隔数量，简单来说就是给动画分段，一段一段走

3D 转换，增加了一个 z 轴，向屏幕外是正，屏幕里是负
3D 位移 transform: translate3d(x, y, z)，z 的坐标单位基本上只用 px
想要产生 3D 效果，需要添加 perspective 透视属性，透视属性类似于添加眼睛看屏幕的距离
透视写到被观察元素的父盒子上面

3D 旋转 rotate3d(x, y, z, deg)沿着自定义的轴(x,y,z)矢量旋转 deg 为角度，一般单独使用比如 rotateX(x)
判断旋转的正方向可以使用左手准则，四指弯曲拇指伸直对准轴的正方向四指就指向旋转的正方向

3D 呈现 transform-style 让父元素控制子元素是否开启三维立体的环境，默认是 flat，改成 preserve-3d 就可以启动 3d，注意是写给父元素的属性
**子元素想要 3d 效果 父元素必须提供 perspective 和 transform-style 属性**
**翻转类型的翻过来不显示背面的方法：backface-visibility: hidden**
3d 导航栏部分遇到了很多障碍，总结：
1 perspective 和 transform-style 都只针对下面一层的子元素，这两个属性不需要同时出现，按需使用有 3d 效果跟近大远小没有必然的关系
2 90 度类型的旋转因为转轴的变化比较困难最好改成根据转轴是一个正方体类型的东西
制作旋转木马时发现的新问题：一般位移和旋转同时存在时只要出现两个维度的位移就很容易出问题，圆形绕圈可以先旋转再位移
css 动画部分完结 p388

### 7.27

浏览器的私有前缀：
-moz- firefox
-ms- ie
-webkkit- chrome edge safari
-o- opera
私有属性可以直接添加到属性的前面比如 -webkit-border-radius: 10px

**移动端布局开发**
兼容移动端的处理器只需要处理 webkit 内核
视口 viewport 是浏览器显示页面内容的屏幕区域，可以分为布局视口，视觉视口和理想视口
布局视口：一般由移动端浏览器默认设置，解决早期 pc 端网页在移动端的显示问题，手机大部分将这个视口设置为 980px，pc 端网页能显示但是内容都很小
视觉视口：用户能看到的网站区域，可以用缩放操作视觉视口
理想视口：手动写 meta 视口标签通知浏览器，让布局视口的宽度和理想视口宽度一致，理想视口是最合适浏览的视口
meta 视口标签属性
width 宽度设置的是 viewport 宽度，可以设置 device-width 特殊值
initial-scale 初始缩放比
maximum-scale 最大缩放比
minimum-scale 最小缩放比
user-scalable 用户是否可以缩放 yes/no 或者 1/0
标准的 viewport 配置是 width 设备宽度，初始/最大/最小缩放比都为 1，不允许用户自行缩放

二倍图：物理像素和物理像素比，pc 端一般 1 像素就是真实 1 像素（高分屏不是），移动端经常这两个不对等
一个 px 能显示的物理像素点的个数称为物理像素比或者屏幕像素比，现在手机都是视网膜屏幕的情况下像素比都不是 1
在视网膜屏幕中打开图片会因为更多像素导致模糊，可以使用倍图来解决这个问题
在视口中设置，准备的图片是实际大小\*像素比，在图片显示中修改 width 和 height 除像素比，在手机中就可以正常显示
背景缩放 background-size: 宽度 高度 如果只写一个参数就是省略高度，高度随宽度等比例缩放，单位也可以跟%百分数对比父盒子
background-size 有两个特殊属性 cover 和 contain，cover 等比例拉伸至完全盖住盒子，可能有损失图像，而 contain 是等比例拉伸到宽高任意一个到父盒子就停止
**背景图片的放大缩小使用的就是 background-size 属性，但是多倍图本身扩大还是得准备材料的过程完成，缩小可以使用 background-size 属性**
准备材料切图的过程可以使用 cutterman 切图工具切出多倍图

移动端的开发目前有两种主流方案：1 单独制作移动端的页面 2 响应式页面兼容移动端
单独制作是主流，通常在域名前面加一个 m 比如 m.jd.com

移动端有推荐的初始化 css 代码 normalize.css 盒子模型一般使用 CSS3 的 border-box
移动端单独需要注意的三个样式：
-webkit-tap-highlight-color: transparent; 清除点击高亮
-webkit-appearance: none; 清除 ios 自带的按钮和输入框样式
img, a {-webkit-touch-callout: none;} 禁止长按页面出现菜单

流式布局：
特点是通过百分比布局宽度，而不是传统方式用像素
可以通过给 max-width 和 min-width 限制最大最小的宽度
p403

### 7.28

图片的居中对齐有时候用 line-height 并不管用，原因是要用 vertical-align 设置图片的对齐属性，图片默认是基线对齐，改成居中对齐，行内块一般用 vertical-align，但是做这一步还是必须注意设置行高

二倍图的精灵图：先把整个精灵图等比例缩放为原来的一半再测量坐标，代码里面使用 background-size 修改为原来的一半，核心问题是二倍图的坐标也会有变化

去除图片上下之间的空白缝隙（左右可以 float）vertical-align: top/middle

flex 布局：
操作方便，布局简单移动端应用广泛，PC 端浏览器支持情况较差
ie11 或者更低的版本不支持或仅部分支持

flex 是弹性布局，任何容器都可以指定为 flex 布局
再父元素设置 flex 布局后子元素的 float，clear，vertical-align 属性失效
采用 flex 布局的元素称为 flex 容器，它的所有子元素称为 flex 项目
布局的原理是通过给父盒子添加 flex 属性控制子盒子的位置和排列方式

flex 布局父元素（容器）的六个属性：
1 flex-direction 设置主轴的方向
2 justify-content 设置主轴的子元素排列方式
3 flex-wrap 设置子元素是否换行
4 align-content 设置侧轴上子元素的排列方式（多行）
5 align-items 设置侧轴上子元素的排列方式（单行）
6 flex-flow 复合属性，相当于同时设置 flex-direction 和 flex-wrap
默认的主轴就是 x 轴，侧轴就是 y 轴，子元素是根据主轴来排列的
flex-direction 可以选的属性有 row（默认）row-reverse column column-reverse
**子元素本身的顺序由 flex-direction 决定**
justify-content 的属性有
flex-start（默认）从主轴头部开始
flex-end 从主轴尾部开始
center 在主轴居中对齐
space-around 平分剩余空间
space-between 先两边贴边再平分剩余空间
不像浮动，弹性布局子元素在一行塞不下的情况下会修改所有元素的宽度以至于强行能塞下，所谓弹性
flex-wrap 设置换行，默认情况下不换行，属性值只有 wrap 和 nowrap（默认）
align-items 设置单行情况下侧轴子元素排列方式，属性有 flex-start 从上到下 flex-end 从下到上 center 居中 stretch 拉伸（默认）
stretch 这个属性在有高度的情况下无法体现，子元素没有设置高度的情况下会拉伸跟父元素同样的高度
**单行子元素设置水平和垂直都居中的话就 justify-content 和 align-items 都设置为 center**
align-content 设置多行情况侧轴子元素的排列方式，单行无效，在 align-items 属性的基础上增加了 space-around 和 space-between
flex-flow 可以简写属性，比如 flex-flow: row wrap 主轴 x 轴，换行

flex 布局子元素的属性：
flex 定义子项目分配剩余空间，占多少份，比如 flex: 0（默认）所谓的剩余空间指的是有宽度的子项目算完了，没给宽度的分剩余空间
总份数是没有设置宽度的子项目的个数，这种适合做类似京东搜索条那种两边固定中间自适应的
align-self 设置子元素本身在侧轴上的排列方式，可以覆盖父元素的 align-items 属性，默认为 auto，如果没有父元素就是 stretch
order 定义子元素的排列顺序，默认是 0，数值越小越靠前
p426

### 7.29

回顾固定定位，固定定位跟父级元素没有关系，以屏幕作为参考
使用 border-box 盒子模型的情况下，height=line-height 的话会比正常居中靠下一点点，因为这种模型会把 padding 和 border 算入盒子的高度，解决的方法就是 line-height 减去这两个值

flex 有些时候也可以单纯用来调节元素的对齐属性，子元素不是必须加 flex 分份，弹性的才需要加这个属性

背景颜色线性渐变：
background: linear-gradient(起始方向, color1, color2) 比如 background: -webkit-linear-gradient(left, red, blue)
这个起始方向是比如从左到右，从左上到右下（top left），默认情况下是从上到下渐变，因为浏览器的支持原因这个属性必须添加私有前缀比如这个 webkit

### 7.30

新知识：子元素的 flex 属性可以写百分比，占主轴那个属性（宽或者高）的多少
flex 父元素的子元素不一定非要写 flex 属性，有时候 flex 子元素是自适应的

rem 适配布局：主要能解决的问题是页面布局的高度也随着屏幕的变化而自动适配
rem 的基准是相对 HTML 根元素的字体大小，而 em 是针对父元素的字体大小
rem 最大的优点是通过修改 html 里面的文字大小来改变页面中元素的大小，可以整体控制

媒体查询：CSS3 新语法
@media，可以针对不同的屏幕尺寸设置不同的样式
语法格式 @media mediatype and/not/only (media feature) {
CSS 代码
}
mediatype 用于区分终端类型 all/print（用于打印）/screen（各种屏幕）
关键字用于链接媒体类型和媒体特性 and 连接多个媒体特性 not 排除某个媒体特性 only 只有某个媒体特性
@media screen and (max-width: 800px) 在屏幕上且最大像素为 800，如果有多个条件就多个 and

当样式比较繁多的时候可以引入资源，核心是针对不同的媒体使用不同的样式表，原理就是在 link 中判断设备尺寸
语法格式 <link rel="stylesheet" media="mediatype and/not/only (media feature)" href="mystylesheet.css">

Less 一种 CSS 扩展语言，也称为 CSS 预处理器，为 CSS 增加了程序式语言的特性，写的时候写在专门的.less 文件中
Less 变量 @var: pink 使用 background-color: @var 其他的 CSS 可以直接写在.less 文件中，需要经过编译自动转化为 CSS
Less 嵌套 子元素的样式可以写在父元素里面，如果是父元素的属性或者伪类选择器等，要添加&（相当于就是父元素的名字），比如&:hover {...} &::before {...}
less 运算 less 提供了简单的加减乘除运算，但是运算符两侧必须有空格，两个不同的单位的话运算结果以第一个单位为准，另外运算最外层可以添加括号
p451

### 7.31

在 less 中引入其他的 less 代码使用 @import "file name";或者@import url(...)
flexible.js 优势是 rem 是随屏幕的像素无极变化的，但是官方已经不再维护，也有一些问题
p481

### 8.1

**HTML CSS p496 返回 JS 课程**
移动端网页特效三个新事件：
touchstart 手指触摸到 DOM 元素触发
touchmove 手指在 DOM 元素上滑动触发
touchend 手指从 DOM 元素上移开触发
对应有触摸事件对象 TouchEvent 可以用来描述触点个数，检测触点移动，触点的增加和减少等
TouchEvent e 所对应的属性和含义
touches 触摸屏幕的所有触点的列表
targetTouches 正在触摸当前 DOM 元素手指的列表
changedTouches 手指状态发生改变的列表，从无到有或者从有到无（记录的是变化的触点）
手指拖动元素需要当前手指的坐标值，单个手指时使用 targetTouches[0]里面的 pageX 和 pageY 属性即可
**防止手指移动导致页面滚动 e.preventDefault();**
margin 写百分比的话是相对于父元素的

### 8.2

可以用 css 来实现动画的效果，这比 js 实现要更简单，动画过渡完成的事件是 transitionend
classList 属性，可以返回元素的类名表，因为一个元素可能有多个类名，单纯使用 className 会返回所有的类名
可以添加类名 element.classList.add('name') 删除类名 element.classList.remove('name') 切换类名（没有添加，有删除）element.classList.toggle('name')

移动端 click 事件会有 300ms 的延时，因为双击会缩放页面，解决这个问题的方法有三种（去除 300ms 判定）
1 禁用缩放，在视口标签 content="user-scalable=no"
2 利用 touch 事件封装事件解决 300ms 延迟，触摸屏幕到离开屏幕的事件小于 150ms 并且无滑动就定义为点击
3 使用 fastclick.js 插件
灵活运用 swiper 可以大幅提高开发的效率

本地存储：
1 数据存储在用户的浏览器
2 设置读取方便，页面刷新也不会丢失数据
3 容量比较大 sessionStorage 5M localStorage 20M
4 只能存储字符串，可以将对象 JSON.stringify()编码后存储
sessionStorage：
1 生命周期为关闭浏览器窗口
2 同一个窗口（页面）下数据可以共享
3 键值对形式存储
语法 sessionStorage.setItem(key, value) / getItem(key) / removeItem(key) / clear()
localStorage：
1 生命周期永久生效，除非手动删除否则关闭页面也会存在
2 可以多窗口（页面）共享，在一个浏览器内部都可以共享
3 键值对形式存储
本身语法跟 sessionStorage 相同
复选框的 change 事件可以用来判断复选框的内容有没有改变

**jQuery 开始，移动端 bootstrap**

jQuery 对于页面 DOM 加载完毕再执行脚本的操作：相当于原生 js 的 DOMContentLoaded
1 $(document).ready(function() {
        要执行的代码
    })
    2 $(function() {
        要执行的代码
    })
在jQuery中$是 jQuery 的别称，是顶级对象，可以利用$包装对象
jQuery对象本质是利用$包装后产生的对象，以伪数组形式存储，jQuery 对象只能使用 jQuery 的方法
DOM 对象转化为 jQuery 对象 $(DOM 对象) 里面可以直接用选择器
jQuery 对象转化为 DOM 对象 $(...)[index] / $(...).get(index) 因为是伪数组，拿出来就行了
获取 jQuery 对象 $('选择器') 修改元素样式 jQuery 对象.css('属性', '值') css()是一个内置的方法
获取 jQuery 对象的时候内部的选择器可以加入额外参数 :first / :last / :odd / :even / :eq(index) 选择索引号是第几个的
jQuery 筛选方法：
parent() / children(selector) 找亲儿子子代 / find(selector) 找所有子代 / siblings(selector) 找同级对象不包括自身
nextAll([expr]) 后续所有同级/ prevAll([expr]) 之前所有同级/ hasClass(className) 有无这个类名/ eq(index)
parents(selector) 根据选择器选祖先元素 / .index() 找伪数组中的第几个
p370

### 8.3

写 jQuery 事件的时候，可以用$(this)表示当前对象，jQuery 有隐式迭代特性，选择器选出来如果是伪数组内部多个，每一个都会自动执行一次
**获得当前元素的索引号的方法 jQuery 对象.index() 可以用于精准操作一组元素**
操作 css 的方法 css() 参数只写属性名返回的是属性值，参数也可以是对象的形式，可以不加引号，但是如果值不是数字就还是需要加引号
比如 注意复合属性还是需要驼峰命名法
$('div').css({
width: 200px,
height: 200px，
backgroundColor: "pink"
})
通过修改类名修改样式 jQuery 对象.addClass(类名) / removeClass() / toggleClass() 切换类

jQuery 封装的动画效果，太多了可以参考存在 8.1-8.7 的文件夹的图片

slideDown / slideUp / slideToggle 上拉下拉菜单
比如 $('div').children('ul').slideDown(200) 里面的参数是动画完成的时间
.hover(function() {} / function() {}) 里面第一个函数对应 mouseenter，第二个对应 mouseleave，如果只写一个的话鼠标经过离开都会触发
.stop()停止动画，相当于节流阀，写到动画的前面，谁有动画写在谁的前面 $(this).children('ul').stop().slideToggle();
fade 系列，时间和透明度必须要写，一般使用 fadeTo 较多，fadeIn / fadeOut 淡入显示 / 淡出隐藏
.animate()方法 第一个参数对象，表示动画后的属性，第二个参数时间，第三个参数一般不修改默认 swing 可以改为 linear，第四个参数回调函数

获取 html 元素的属性 jQuery 对象.prop(属性名)，如果设置属性就写属性名和属性值，自定义的属性使用 attr()获取或者修改
数据缓存 date() 把元素存放到元素的缓存中 存放$('div').data('uname', 'jack') 获取$('div').data('uname')
:checked 选择器可以选出被勾选的有几个，适合判断是否全选
**获得或者修改原生 js 中相当于 innerHTML 的内容 .html()方法 如果是 innerText 就是.text()方法 获得设置表单值 .val()方法**
.toFixed()设定数字的小数保留到多少位
p394
**js 高级**
类的创建和使用
class Car{
constructor(uname) { 构造函数，不自己设定也会自动有，new 的时候这个函数自动调用
this.uname = uname;
}
drive() { 类里面的成员函数不写 function 关键字，方法之间不加逗号
console.log('driving')'
}
}
var real_car = new Car('benz'); 创建对象
class Son extends Father {...} 子类继承父类
使用 super 关键字可以访问和调用父类的函数，包括构造函数，有时候子类用父类方法必须 super 一个父类
子类可以重写父类的方法，就近原则，用 super 可以强行调用父类的方法 super 写在子类构造器中的话必须写在子类的 this 之前，先父类再子类
对象方法中用对象自己的属性或者调用自身方法一定加上 this，比如在构造器中调用函数需要加上 this this.drive()
constructor 中的 this 指向的是要构造的这个对象的实例，成员方法的 this 指向调用者（不一定是对象本身，谁调用 this 指向谁）

### 8.4

因为成员函数内部的 this 不一定指向对象自身，有时候又需要用对象自身，可以在类外面设置一个全局变量，在构造器中把 this 赋值给全局变量
this 指向的就是调用者，谁调用指向谁，比如 this.lis[i].onclick = this.toggleTab; //调用成员函数 toggleTab 的调用者是 lis[i]
添加和插入元素的新方法 insertAdjacentHTML('beforeend 或者其他位置', 元素字符串);
js 高级 p20
jQuery 对元素的遍历：
$('div').each(function(index, domElement) {...})
    回调函数的参数是索引号和DOM元素对象（变量本身的名字可以随便取），如果使用jQuery方法就给这个DOM元素对象转换成jQuery对象
    $.each(object, function(index, element){...})
    这种遍历方法可以用于任何对象，主要用于数据处理，比如数组对象等，如果遍历dom元素就把$('div')写在 object 参数
如果写的是一个对象，index 属性名，element 属性值，数组则 index 序号，element 具体的值
jQuery 创建和添加元素
创建 $('<div>新创建的元素</div>') 创建主要是把元素写完
内部添加
$('ul').append(li) 这里的 li 是一个刚才方法创建的变量，放的位置是 ul 的子元素的最后面，类似原生 js 的 appendChild
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

jQuery 尺寸：
1 width() / height() content 部分的宽高
2 innerWidth() / innerHeight() content 和 padding
3 outerWidth() / outerHeight() content padding border
4 outerWidth(true) / outerHeight(true) content padding border margin
不仅可以获取，还可以修改，修改的话不需要添加单位，默认是像素
jQuery 位置：
1 offset() 获取设置元素对于文档 document 的属性，跟父元素无关，获取的是对象{top, left}，设置可以这么写 element.offset({top: 50, left: 20});
2 position() 相对带有定位的父级元素的偏移，也是对象跟上面相同
3 scrollTop() 滚动滚动条被卷曲的头部，$(document).scrollTop()判断页面下滑了多少
    如果制作返回顶部的按钮，需要动画效果的情况下 $('body, html').stop().animate({scrollTop: 0})，因为这个函数只能给元素，document不是元素
动画函数的回调函数的重要作用是在动画执行完毕才会调用
jQuery事件处理
    on()绑定事件，on内部是对象，对象属性是各种事件和相应处理函数的集合，并且前面的事件可以写两个及以上，调用相同的事件处理函数
    on()还可以实现事件委托，子元素的事件绑定到父元素 $('ul').on('click', 'li', function() {...})通过子元素冒泡触发父元素处理
    on()可以给动态创建的元素绑定事件，默认情况下新元素也会被on绑定
    off()可以解绑事件，$('div').off('click') 如果不写就解除全部事件，通过写 off('click', 'li')也可以解除委托的事件
one()绑定的事件只能触发一次，使用方法和 on 相同
jQuery 自动触发事件
element.click() 类似原生 js 的写法
element.trigger('click')
element.triggerHandler('click') 和前面比的特点是不会触发元素的默认行为
jQuery p417

在 ES6 之前没有专门的类的概念，对象不基于类创造，基于构造函数
创建对象三种方式 1 对象字面量 2 new Object() 3 自定义构造函数
new 在执行的时候会做的四件事：
1 内存中创建一个新的对象
2 让 this 指向这个对象
3 执行构造函数中的代码，给对象添加属性和方法
4 返回这个新的对象（所以说构造函数不需要 return）
对象中有两种成员 实例成员和静态成员
实例成员只能通过实例化的对象访问，不可以通过构造函数名访问
静态成员是直接添加到构造函数上的比如构造函数是 Car()，Car.brand = 'benz'就是直接添加到构造函数，只能通过构造函数名访问
构造函数方法创建对象存在浪费内存的问题，比如对象的实例函数就会反复开辟内存存放
构造函数可以通过原型 prototype 分配共享的函数，每一个构造函数都有 prototype 属性，指向另一个对象，prototype 就是一个对象，对象的方法和属性都被构造函数拥有
**一般一些不变的方法可以直接定义到 prototype 对象上，这样对象的实例就可以共享方法**
对象都会有属性**proto**指向构造函数的 prototype 原型对象，对象可以使用构造函数的 prototype 属性和方法是因为有**proto**
**proto**是一个非标准的属性，意义是给对象的查找机制提供方向和路线，但是是一个非标准的属性，仅仅指向原型对象 prototype，实际开发不使用这个属性
//目前 MDN 显示这个属性已经被废除，不再推荐修改原型，而是创建一个继承于原型的新对象，使用 Object.create()
在对象调用方法的时候，先看自身有没有写内部的方法，如果没有再到构造函数对应的原型里面去找
在**proto**和 prototype 中都有 constructor 属性，存放的也就是构造函数本身，记录对象引用自哪一个构造函数
有些情况下直接通过 prototype = {一个新的对象} 重新赋值修改了原型，需要把原型的 constructor 属性指回构造函数 constructor: 构造函数的名字;
原型对象也有原型 构造函数名.prototype.**proto**指向的是 Object 中的 prototype，作为最顶层 Object.prototype.**proto**指向的是 null
原型链图示存放在 8.1-8.7 中
从原型链引申出 js 的成员查找机制，先找对象自身，然后它构造方法的原型，然后 Object 的原型，如果还是没有就是 null
原型对象函数和构造函数中的 this 都指向实例对象
修改内置对象的原型可以添加内置对象的自带函数，比如修改 Array.prototype.func = function() {...}添加新方法
call(thisArg, arg1, arg2, ...)函数可以修改函数运行时候 this 的指向 call 的使用：函数名.call()，第一个参数就是修改后的 this
在 ES6 之前因为没有 extends 关键字，继承通过构造函数+原型对象模拟继承，称为组合继承，核心是子类构造函数通过 call()修改 this 调用父类
p35

### 8.6

接昨天的组合继承，父类的方法是写在 prototype 原型对象的，子类构造函数仅 call 父元素构造函数，不包括原型对象所以也不能得到父类的方法
简单的 Son.prototype = Father.prototype 会出现问题，修改子原型对象会导致父原型对象也跟着变化（指向了同一个 prototype 原型对象）
解决方案 Son.prototype = new Father(); Son.prototype.son_func = ... 为子类的继承专门创建一个父类的实例对象，然后修改 constructor 属性
**利用直接赋值对象的方法修改了原型对象，一定要修改 constructor 属性指回原来的构造方法**
从 ES6 开始引入了 class 类，类的本质还是一个函数 function，可以简单认为类是构造函数的另一种写法
跟构造方法相同，类也有原型对象，原型对象有构造函数属性，也可以通过原型对象添加方法，创建的实例也有**proto**属性

ES5 对于基础对象提供的新方法：
数组：
forEach()遍历方法 arr.forEach(function(value, index, array) {...})
filter()筛选方法 array.filter(function(currentValue, index, arr) {...}) 直接返回一个新的数组
map()创建一个新数组，新数组的每一个元素都是调用了一次回调函数后的结果
比如 var newArray = arr.filter(function(currentValue, index, array) {return currentValue >= 20;})
some()查找是否有满足指定条件的元素，找到第一个就停止，返回值布尔值，语法同上
filter 和 forEach 遇到 return 也不会中止迭代
字符串：
trim()方法，去除字符串两端的空白字符，包括空格换行制表等，不影响原字符串，返回的是新字符串
对象：
Object.keys(obj)回去对象自身有的所有属性，返回由属性名组成的数组
Object.defineProperty(obj, prop, descriptor)定义对象新属性或者修改原有属性 **属性本身就可以添加，主要应该是在于属性的修改和特性的调整**
这个方法的使用对象是直接针对于构造函数，也就是类名而不是实例对象
descriptor 属性是一个对象，里面可以有四种属性：
value（有就修改无则添加，默认是 undefined）
writable（属性的值是否可以修改默认 false）
enumerable（是否可以被枚举默认 false）比如说遍历 Object.keys()不能得到这个属性
configurable（属性是否可以被删除或者修改特性默认 false）

函数部分：
使用 new Function()创建函数时，小括号内部是字符串，参数和函数体都在字符串内，先写参数后写函数体
所有函数都是 Function 的实例对象，函数也属于对象 函数内部的 this 指向可以参见 8.1-8.7 截图
普通的函数的 this 指向是 window，调用的时候简写了 window，本身应该是 window.fn()
改变 this 指向的方法 call() bind() apply()
apply 的使用 func.apply(thisArg, [argsArray])传参必须写在数组（伪数组也行）里面，thisArg 写 null 就不改变，返回值就是本身该返回的值
p56

### 8.7

接函数部分：
bind()不会调用函数，但是可以修改函数的 this 内部指向，语法跟 call 相同，返回值是由指定的 this 和初始化参数改造的原函数拷贝
一般情况下参数是不写的，仅仅用这个来修改 this 的指向，比如本身 func()的 this 指向的是 window，写 var fn = func.bind(obj)换绑
严格模式 strict mode:
严格模式可以为整个脚本开启或者给个别函数开启，为脚本开启就在开头写 'use strict'; 为某个函数开启就放在函数体开头部分
严格模式下变量必须先声明再赋值，不能使用 delete 删除已经声明的变量，**全局作用域下的函数的 this 是 undefined**
构造函数必须使用 new 调用，new 实例化的构造函数还是指向创建的对象实例
高阶函数 对其他函数进行操作的函数（接收函数作为参数，将函数作为返回值输出）：
回调函数的常见写法 callback && callback() 利用与的短路特性
闭包 有权访问另一个函数作用域中变量的函数：
闭包实现的重点是返回一个函数，这个函数相当于另一个函数的内部函数，导致在外部调用这个函数可以拿到另一个函数作用域中的变量
主要作用是延伸变量的作用范围
深浅拷贝：
浅拷贝拷贝本层，更深层次对象只拷贝引用，深拷贝拷贝全部
使用 for 循环的拷贝就是浅拷贝 ES6 新增语法糖 Object.assign(target, source)
深拷贝可以使用函数递归实现，分为三种数组，对象，基础数据类型
p76

### 8.10

正则表达式：主要用于匹配字符串内容，替换字符串内容，从字符串中提取内容
在 js 中正则表达式是作为一种对象的
创建正则表达式有两种方法
1 调用对象 RegExp 对象的构造函数创建 var regexp = new RegExp(/表达式/);
2 利用字面量创建正则表达式 var regexp = /表达式/;
正则表达式的对象方法：
regexpObj.test(str)，验证字符串是不是符合正则的规范，返回 true 或 false

正则表达式的特殊字符：
边界符：提示字符出现的位置
^ 表示匹配行首的文本 /^abc/ 必须以 abc 开头
$ 表示匹配行尾的文本 同上 可以连用实现精确匹配 /^abc$/ 必须是abc
    字符类：有一系列字符可以选择，匹配其中一个就行
        [] /[abc]/ 有abc三个任意一个就行
        [-] 方括号内的短横线表示范围 /[a-zA-Z0-9_]/ 有大小写字母，数字或者下划线就行
        [^] 方括号里面的^表示取反 /[^a-z]/ 不能包含小写字母 **和中括号外面的区分开**
    量词符：用于设定某个模式出现的次数
        * 重复>=0次 /^a*$/ 开头可以没有 a，也可以很多 a，空或者很多 a，其他不行 + 重复>=1 次 /^a+$/ a或者很多a
        ? 重复0/1次 /^a?$/ 空字符串或者就一个 a
{n} 重复 n 次
{n,} 重复>=n 次
{n.m} 重复 n-m 次
p85

### 8.11

接正则表达式：
三种括号的使用：
[]中括号表示字符集合，匹配中括号里面的任意一个字符即可
{}限制的区域是前一个字符，/^abc{3}$/ 满足这个正则表达式只能是abccc
        ()小括号可以提升优先级比如 /^(abc){3}$/ 这个只能是 abcabcabc
预定义类：
\d 匹配 0-9 任意数字
\D 匹配非 0-9
\w 匹配任意字母数字下划线
\W 匹配非数字字母下划线
\s 匹配空格类，包括换行符，制表符
\S 非空格类
正则的或者运算符 |
正则表达式参数：
写在两个//后面[switch]，有三种值 g 全局匹配 i 忽略大小写或者 gi 一起写 比如/.../g
字符串的 replace 方法第一个参数除了写要被替换的字符串，还可以写正则表达式

**ES6-ES11**
let 关键字声明变量的特点：
1 不能重复声明，如果用 var 可以
2 提供新的块级作用域，防止外层用 var 声明的变量都添加到全局 window，**所谓的块级作用域就是一对大括号**
3 不存在变量提升，不声明先使用会报错
可以在 for 里面使用，限制于 for 的块级作用域

const 关键字声明常量：
1 必须赋初值，并且不能修改，**重点是内存地址不能修改**
2 同样块级作用域
3 对于数组内部元素，对象内部属性的修改不算对常量的修改，允许

变量解构赋值：
可以创建连续变量匹配数组中的值，比如 const arr = [1, 2, 3]; let [one, two, three] = arr;
对象需要属性名完全相同，如果想不一样就要写别名比如 let {name: myname, age: myage} = obj;
主要可以便于频繁调用，解构出来的对象方法可以省去调用方法需要先加对象的问题

模板字符串：
除了单双引号还可以使用反引号`` 好处是内容可以直接添加换行符以及使用${}把变量或者函数直接拼接进去字符串

对象的简化写法：
外层已经有 let name = 'jack'; let age = '20' 那么可以直接 let person = {name, age}
等效内部 {name: name, age: age} 方法也可以省略 function 写到里面

箭头函数:
语法格式：
let fn = (参数列表) => {函数体};
**找 this 最简单的方法是找箭头函数外层有没有函数，没有就是 window，对象不产生作用域**
主要特点：
1 this 静态，this 始终指向函数声明时所在的作用域下 this 的值
2 不能作为构造函数实例化对象
3 不能使用 arguments 变量，没有 prototype 属性，不能用箭头函数写生成器函数
形参有且只有一个可以省略小括号，比如 let add = n => {...};
函数体只有一句可以省略大括号，但是必须也省略 return 比如 let pow = n => n\*n;
箭头函数适合与 this 无关的回调，比如定时器，数组方法等，不适合事件回调，对象方法这种 this 需要动态变化的
箭头函数的 this 始终指向定义箭头函数的对象，指向定义的箭头函数那一级块级作用域的 this

函数参数可以赋初值：一般有默认值的参数放后面
function add(a, b, c=10) {...}

rest 参数获取不定实参：
替代 arguments，使用 arguments 获取的不定实参是对象而 rest 参数获得的是数组，更加方便
语法格式 function data(name1, ...args) {...} data('jack', 'sam', 'peter') 获取的是'sam', 'peter'构成的数组
因为获取的是最后不定长的参数列表，rest 参数必须放最后，并且参数名前面添加...

扩展运算符...让数组转化为逗号分割的参数序列：
fn(...array_name)，把数组每个元素分开都传进 fn 函数
rest 参数的...放在函数的声明位置，扩展运算符的...放在函数的调用位置
提供了简单的合并数组方法 arr = [...A, ...B]
克隆数组的方法（浅拷贝） A_copy = [...A];
伪数组转数组的方法 divs_arr = [...divs];

新的原始数据类型 Symbol
最主要的意义是生成绝对独一无二的值
1 唯一的，用于解决命名冲突
2 不能和其他数据进行运算
3 定义的对象属性不能使用 forin 循环遍历，可以使用 Reflect.ownKeys 获取对象的所有键名
主要作用是给对象添加方法
p18

### 8.12

**深水区进度放缓**
迭代器：一种接口，为各种不同的数据结构提供统一的访问机制，任何数据结构部署 iterator 接口板就可以完成遍历
原生具有 iterator 接口的数据：Array Arguments Set Map String TypedArray NodeList
迭代器一般配合 forof 方法使用，forin 循环变量保留的是键名，而 forof 保留的是键值
forof 会自动调用迭代器 Symbol.iterator
生成器：用于解决异步
语法是 function \* fn() {...} 函数体里面可以写 yield 进行分隔，每次迭代器执行一次进行一段分隔的代码

Array 扩展方法：
转化伪数组的第二种方法 Array.from(伪数组)返回值为转换后的数组，伪数组后还可以添加函数实现比如说全部\*2
Array.find()里面的参数是查找条件的函数，找到第一个满足条件的就返回，没有就返回 undefined，而 some 是返回真假
Array.findIndex()找第一个符合条件的数组成员的索引，没有就返回-1
Array.includes(value)找数组中是否有 value 值，返回真假，相比 some 功能更简单

### 8.13

字符串扩展方法：
String.startsWith(str) / String.endsWith(str) 参数字符串 str 是否在开头或者结尾，返回真假
String.repeat(n) 将原字符串重复 n 次返回新字符串

Set 数据结构：类似于数组但是成员都是唯一的
直接使用构造函数生成 Set 数据结构 const s = new Set(1, 2, 3)
自带属性有 size，相当于 length，构造函数也可以直接传入数组，传入的数组自动去重
自带方法 add(value)返回 set 本身 delete(value)返回真假是否删除成功 has(value)返回真假 clear()无返回值
forEach 方法对每个成员执行一些操作，没有返回值

ES6 浏览器中，使用 let 在块级作用域声明函数存在变量提升，类似于 var，这个特殊规定仅限于 ES6 浏览器，**最好尽量不在块级作用域声明函数**
//函数声明类似于 var，即会提升到全局作用域或函数作用域的头部。同时，函数声明还会提升到所在的块级作用域的头部
实在需要可以在块级作用域写函数表达式类似 let fn = function() {...};
在纯块级作用域前面可以添加 do，替代部分简单函数的功能，返回值是块级作用域最后一条语句的结果
想要完全锁死一个对象，使用 Object.freeze(obj)，返回值也是 obj
在顶级作用域的使用 var 或者 function 声明的变量直接添加到顶级对象 window 的属性，而使用 let 或 const 只创建全局变量，不添加到顶级对象
关于解构赋值：
只要某种数据结构具有 Iterator 接口，都可以采用数组形式的解构赋值，解构赋值也可以有默认值，但是只有是 undefined 的时候才会采用默认值
解构赋值的规则是，只要等号右边的值不是对象或数组，就先将其转为对象。由于 undefined 和 null 无法转为对象，所以对它们进行解构赋值时都会报错。

字符串扩展方法 2：
str.padStart(length, str2) / str.padEnd(length, str2) 用 str2 在首/尾补充 str 到 length 长度，如果省略 str2 参数就使用空格

数值类型的扩展方法：
Number.isFinite() 判断是否是有限的以及是否是数字，返回真假
Number.isNaN() 判断是否是 NaN
Number.parseInt() / Number.parseFloat() 和自带的全局 parse 函数完全相同
Number.isInteger() 判断是否是整数
Number.EPSILON 一个极小的常量数量级为 10 的-16 次方，一般用于检测浮点值的精度
JavaScript 能够准确表示的整数范围在 -2 的 53 次方 到 2 的 53 次方 之间（不含两个端点），超过这个范围就无法精确表示，为此提供方法 Number.isSafeInteger()
ES6 引入了 Number.MAX_SAFE_INTEGER 和 Number.MIN_SAFE_INTEGER 两个常量，用来表示这个范围的上下限
新增指数运算符 ** 比如 2 ** 2 = 4

函数：
函数添加了默认参数后参数本身会形成一个作用域，找不到会到外层去找而不是函数体

### 8.14

接函数：
通过抛出错误的方法可以指定某个函数的参数是必须写的
函数的 length 属性不包括 rest 参数
规定只要函数参数使用了默认值、解构赋值或者扩展运算符，那么函数内部就不能显式设定为严格模式，否则就会报错
上述的严格模式有两种解决方法，全局使用严格模式或者把函数放在一个无参数的立即执行函数中
外出旅游...

### 8.17

普通 for 循环的迭代常量因为会不断修改所以不能使用 const，但是对于 forin 或者 forof 这样每次都在修改的变量还是可以使用 const
类似于 instanceof 运算符，typeof 运算符也会返回变量的类型，null 返回 Object
只是以字符串的方式返回 7 种数据类型（包括 Symbol 的简单数据类型和包括数组的 Object 类）
基础六种数据类型 undefined null boolean number String Symbol 一种复杂数据类型 Object 常见的包括数组函数等
判断是否是 NaN 的方法不是 if(value == NaN)因为 NaN 不等于任何值包括 NaN，必须使用方法 isNaN()
除了 null 和 undefined 都有 toString 方法，转化为和原始值等价的字符串，更为通用可以使用 String()转型函数，实际上还是会调用 toString
创建 Symbol 类型使用 Symbol()方法，这个方法传入的参数字符串仅仅用于描述，与实际的值无关
Symbol.for(key)方法，根据传入的 key 字符串键值，在全局符号表内找符号，有就返回，没有就创建后返回，跟直接 Symbol()创建的区别在于全局
全局注册表中的符号必须使用字符串键来创建，使用 Symbol.keyFor(symbol)根据传入的符号返回全局符号对应的字符串键，没有返回 undefined

### 8.25

除了直接添加 Symbol 变量的属性，还可以使用 defineProperty()添加属性
Object.getOwnPropertyNames()返回对象实例的常规属性数组，Object.getOwnPropertySymbols()返回对象实例的符号属性数组。这两个方法的返回值彼此互斥
Object.getOwnPropertyDescriptors()会返回同时包含常规和符号属性描述符的对象，值是什么也会返回
Reflect.ownKeys()会返回两种类型的键，类似于 Object.keys()但是不会受 enumerable 的影响，Reflect 是一个内置对象，主要可以替代 Object 类对对象进行操作
Reflect 实现反射，使得程序可以在运行时获取自己的信息
ES6 也引入了一批常用内置符号（well-known symbol），用于暴露语言内部行为，可以直接访问、重写或模拟这些行为
这些内置符号都以 Symbol 工厂函数字符串属性的形式存在，所有内置符号属性都是不可写、不可枚举、不可配置的
常用内置符号有很多，比如 Symbol.iterator，修改这个属性对应的函数就可以修改 forof 循环的迭代过程
每个 Object 实例都有如下属性和方法。
constructor：用于创建当前对象的函数
hasOwnProperty(propertyName)：用于判断当前对象实例（不是原型）上是否存在给定的属性。要检查的属性名必须是字符串（如 o.hasOwnProperty("name")）或符号
isPrototypeOf(object)：用于判断当前对象是否为另一个对象的原型
propertyIsEnumerable(propertyName)：用于判断给定的属性是否可以使用 for-in 语句枚举。与 hasOwnProperty()一样，属性名必须是字符串
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
使用==对比时，null 和 undefined 是相等的，因为==默认会加入转换的操作，所以一般使用===更为保险
例如使用==时，55 和'55'是相等的，这个时候就必须使用===

**AJAX**
可以在浏览器中向服务器发送异步请求，可以用于在无刷新的情况下获取或发送数据，比如动态请求数据
XML 与 HTML 类似，不同的是 HTML 都是预定义标签，XML 中的标签都是自己定义的，没有预定义标签，XML 设计用来传输和存储数据
目前 AJAX 的信息传递一般不再选用 XML 格式，转为使用 JSON
AJAX 的缺点是无浏览历史，不可回退，存在跨域问题，SEO 不友好
p5

### 8.27

HTTP 的请求报文：
重点是格式和参数
格式是 行\n 头\n 空行\n 体
行的格式 GET/POST url HTTP 协议版本号
响应报文：
行的格式 HTTP 协议版本号 状态码 状态码对应字符串
响应体里面就是 HTML 内容
p13

### 8.31

HTTP 的请求都在 xhr 的方法中设置，xhr.open()方法设置 GET/POST 选项以及 URL 地址
xhr 是 XMLHttpRequest 的简称，发送参数的时候使用 xhr.send()比如 xhr.send('a=100&b=100&c=100')
xhr.setRequestHeader(请求头名, 请求头值)
通过直接设置 xhr.responseType = 'json';可以不需要使用 JSON 对象下的转换方法
AJAX p17
**同步开始进行 vue**
webpack 可以自动转化兼容性代码，代码压缩混淆一类的问题
npm 下载的选项，-S 是--save 的简写，-D 是-- save-dev 的简写，只在开发阶段使用的包用这个
配置 webpack 的流程：
1 项目的根目录创建 webpack.config.js 配置文件
2 package.json 的 script 节点下新增 dev 脚本
3 终端运行 npm run dev 命令，启动 webpack 进行项目打包构建
webpack.config.js 中配置的 mode 有两个选项分别是 development 和 production 对应开发和实际上线
把 mode 选项改成 production 生成的 main.js 就自动变成经过压缩的
执行 npm run dev 后会生成一个新的目录 dist，里面的 main.js 才是 webpack 处理后的 js 文件
封存尚硅谷 AJAX p17 黑马 vue p8 应该先把 node.js 学完再转 vue，明天开始转 nodejs，预算时间大概 1 周，最晚 9.10 中秋之前

### 9.1

浏览器中的 js 主要有两部分组成，JS 核心语法和 WebAPI
node 运行环境包括 V8 引擎和内置 API（和 WebAPI 不同），所以在 node 中不能调用 DOM，BOM，AJAX 的 APInode
node 基本实现了所有的 ES6 新特性，但是在模块的引入和导出过程中选用 COMMONJS 规范
新的 node 版本 require 不再内置，使用需要添加如下的代码：
import { createRequire } from 'module';
const require = createRequire(import.meta.url);
实际上添加了这两行代码还是有一些问题，将文件后缀改为.mjs 就可以成功了，强制使用 ES6 规范

fs 模块：
node 提供的可以操作文件的模块
使用前需要先导入 const fs = require('fs'); require 是 commonjs 的规范
fs.readFile(path[, options], callback)
**options 表示以什么类型的编码格式来读取文件，这个默认情况下不是 utf8，一般情况下需要指定**
callback 回调函数有两个参数 err 和 dataStr 对应的是读取成功和失败，读取失败 err 值是错误对象，dataStr 是文件的内容
通过判断 err 是否是 null 就可以确定是否读取成功，如果成功一定是 null，如果读取失败可以使用 err.message 获取失败的消息
fs.writeFile(file, data[, options], callback)
file 参数指定一个文件路径的字符串，data 表示写入的内容，options 表示什么编码类型，默认 utf8
回调函数参数只有 err，记录写入的错误对象，也可以用来查看是否写入成功
使用./或者../这种相对路径容易出现路径拼接的问题，代码运行的时候以执行 node 命令这一层的目录动态拼接出路径
**为了解决上述的问题，除了使用绝对路径以外，还可以添加 node 的成员\_\_dirname 表示当前文件所在的目录，然后进行路径的拼接**
**在使用**dirname 之前需要添加 const **dirname = path.resolve()声明**

path 模块：
path.join()方法可以实现路径的拼接，对参数的个数不限，返回值就是拼接好的路径
path.basename(path[, ext])方法可以从路径字符串中将文件名解析出来，第一个参数是路径字符串，第二个可选参数表示文件扩展名
返回值是最后文件的名，如果有 ext 参数会省略最后的文件后缀
path.extname(path)获取路径字符串最后文件的后缀扩展名，返回值比如.html
正则表达式的成员方法 regexp.exec(str)，捕获所有满足正则表达式的部分，构成数组，没有的话返回 null
p14

### 9.2

http 模块是 node 提供的可以创建 web 服务器的模块，主要是使用 http.createServer()
计算机网络端口号的概念，在一台服务器中可能运行大量的 web 服务，每一个服务都对应一个唯一的端口号，客户端送来的请求通过端口号到对应的 web 服务
实际使用过程中 80 号端口可以省略，默认情况下就是使用的 80 端口
**创建 web 服务器的基本步骤：**
1 导入 http 模块
2 创建 web 服务器实例 http.createServer()
3 为服务器实例绑定 request 事件，监听客户端请求 server.on('request', (req, res) => {})
只要服务器接收到客户端的请求就会调用 on 绑定的回调函数
req 是请求对象，包含客户端的数据和属性，比如 req.url 请求的地址是什么 req.method 请求的 http 方法
向客户端相应内容是 res.end()方法，里面的参数可以直接是 html 字符串
解决中文显示乱码的问题：res.setHeader('Content-Type', 'text/html; charset=utf-8')
4 启动服务器
根据不同的 url 请求相应不同的 html 内容：根据 req.url 通过 res.end()返回不同的内容：
默认响应内容是 404，判断 req.url 是/或者/index.html 则返回主页，是/about.html 则返回关于页面
let fpath = path.join(\_\_dirname, req.url);
fs.readFile(fpath, 'utf8', (err, dataStr) => {};
上述情况一定不要不写 req.url，直接写 index.html 这种不会请求到关联的 css 和 js 资源，导致页面只有 html
html 关联 css 和 js，这两个文件也必须被请求从硬盘中读取到，并且不会 res.end()自动显示出来

node 模块化：

根据模块来源的不同，将模块分为三种：内置模块，自定义模块，第三方模块

加载模块：
旧的方法是 require，跟 import 差不多，如果是自定义的模块要写出相对路径，.js 的后缀名可以省略
使用 require 方法加载模块的时候，模块里面的代码会执行
模块之中也有模块作用域，自定义模块中的变量方法等成员都只能在当前模块内中访问

向外共享模块中的成员：
每个自定义模块中都有 module 成员，记录了和当前模块有关的信息
module.exports 对象中存放了共享的成员，导入模块的时候比如 import m from 'm'得到的就是 module.exports 默认状态是空对象
为了简化 node 提供了一个新的对象 exports，和 module.exports 指向是一样的，但是实际使用还是以 module.exports 为准
CommonJS 的规定：
每个模块内部，module 变量代表当前模块
module 变量是一个对象，它的 exports 属性，即 module.exports 是对外的接口
加载某个模块，其实是加载该模块的 module.exports 属性，require()用于加载模块
p26

### 9.3

不同于内置模块和自定义模块，包是由第三方团队开发的，下载包使用 npm，网站是 npmjs.com
npm 公司提供了包管理工具 npm，npm 工具集成在 node 中

安装包使用命令 npm i 包名称，其中 i 是 install 的简写，安装完包就可以使用 import 或者 require 导入包
在初次安装完包后项目文件夹下会多一个 node_modules 的文件夹和 package-lock.json 配置文件
**node_modules 文件夹存放所有已经安装到项目中的包，导入包的时候就从这个目录查找加载**
**package-lock.json 配置文件用来记录 node_modules 目录下每个包的下载信息，例如包名，版本号，下载地址等等**
一般情况下不要手动修改这两个，npm 会自动维护

默认情况下安装的是最新版本的包，在包名后添加@版本号就可以添加指定版本的包

npm 规定，在项目的根目录必须提供 package.json 的包管理配置文件，记录与项目有关的一些配置信息，比如如下的信息：
项目名称，版本号，描述等
项目中使用了哪些包
哪些包只在开发阶段使用
哪些包在开发和部署的时候都需要使用
**快速创建 package.json 使用命令 npm init -y 安装包的时候 npm 会自动把包名称和版本号记录到 package.json 中**
**package.json 中有 dependencies 节点，专门用来记录使用 npm install 安装了哪些包**
在有 package.json 的情况下，直接使用 npm i 就可以直接根据 package.json 的 dependencies 节点直接下载

运行 npm uninstall 包名 可以卸载指定的包，并且 package.json 也会自动修改

package.json 中还有 devDependencies 节点，用于存放只在项目开发阶段使用的包
**使用 npm i 包名 -D 或者--save-dev 就可以自动记录到 devDependencies 节点中**

使用 npm config set registry=https://registry.npm.taobao.org/ 可以切换下包地址是淘宝的镜像源
另一种方法也可以使用 nrm 工具，先使用 npm 下载 nrm，然后 nrm ls 显示可用镜像，nrm use taobao 即可切换

被安装的到 node_modules 目录的包都是项目包，而在执行 npm i 时添加-g 参数的话就会安装全局包
全局包被安装到 C:\Users\zzm\AppData\Roaming\npm\node_modules，判断是否需要全局安装可以参考 npmjs 官网的说明

包的内部结构：
包必须以单独目录存在
包的顶级目录下必须包含 package.json 这个包管理管理配置文件
package.json 中必须包含 name version main 三个属性，分别代表包名，版本号，包的入口
main 属性就是在包顶层目录，指定去找哪个 js 文件作为包的源代码，比如'index.js'意思就是 包顶层目录/index.js 是入口

在包的根目录使用 npm publish 命令就可以把包发布到 npm 上
使用 npm unpublish 包名 --force 可以撤销已经发布的包

模块的加载默认是从缓存中出来，内置模块有最高的优先级，如果同名，先加载内置模块
自定义模块先加载原文件名，再补.js，再.json，再.node，还是没有就会报错
第三方模块先在 node_modules 里面找，找不到的话会一级一级沿目录往上走
如果把目录作为模板标识符使用 require 加载，先找 package.json 的 main，没有的话找 index.js 还是没有就会报错

node p38 正式开始 Express，可能需要绕回去学 ajax

### 9.5

URL 地址的三个组成部分
客户端和服务器的通信协议
存有该资源的服务器名称
资源在服务器上具体的存放位置

在网页中请求服务器的数据资源，会使用到 XMLHttpRequest 对象，xhr 是浏览器提供的 js 成员

客户端对服务器的请求：获取资源 get，发送资源 post
使用 jquery 操作 ajax 相对简单，提供了三个函数
$.get(url, [data], [callback]) 请求资源地址，请求资源时携带的参数对象，请求资源成功的回调函数
参数比如{id = 1}就只会返回 id 是 1 的系列数据，**回调函数 function(res) {} 其中的 res 就是请求回来的资源**
$.post(url, [data], [callback]) data 是传给服务器的对象，其他相同
**回调函数 function(res) {} 其中的 res 是传输后的返回值，返回的对象实际上由服务器决定，可以看出传输的状态**
$.ajax({method, url, data, callback})传入的是配置对象，四个参数是配置对象的成员
method 是'get'或者'post'，其他相同，配置对象里面最常用的回调函数就是名为 success 的函数
ajax p11

### 9.6

某些情况下新增的元素可以通过绑定其父元素为其绑定事件，比如使用 on 方法$(selector).on(event, childSelector, data, function)
对于 html 的 audio 标签，只要指定了新的 src 属性，并且带有 autoplay 属性，就会自动播放

**form 的 html 属性**
form 标签用于采集数据，form 标签的属性用来规定如何把采集的数据发送到服务器
主要有四个 html 属性：
action 值就是 url 地址 如果不指定就是当前页面本身，当表单提交后，会自动跳转到 action url 对应的地址
method get/post 规定以什么方式把表单提交到 action url **表单都是提交，get 数据参数直接放在地址栏，而 post 是隐藏的**
enctype 规定在发送表单数据之前应该如何对其编码
application/x-www-form-urlencoded（默认）发送前就编码数据
multipart/form-data 不对字符编码，**表单包含文件控件就需要使用这个**
text/plain 空格转换为+ 特殊字符不转码 很少使用
target \_blank 新窗口/\_self 当前窗口/\_parent/\_top/framename 规定在什么地方打开 action url

因为表单提交数据会导致页面跳转等问题，一般表单负责收集数据，提交过程使用 ajax
**提交表单会导致页面的自动刷新，所以实际上一般把它 preventDefault**
使用 ajax 操作表单的操作：
1 表单的提交对应 submit 事件，可以直接使用 form.submit(callback)或者使用 form.on('submit', callback)
2 使用 e.preventDefault()清除表单的默认提交行为，在 callback 中使用
3 .serialize()可以一次性获取表单的全部数据，需要表单每一项都有 name 属性，获取到的格式是 username=jack&pwd=123 这种
4 使用$('#form')[0].reset()重置表单 因为 reset 是原生 js 对象的方法，需要将 jquery 对象转化为原生对象
p27

### 9.7

使用模板引擎可以减少数据渲染过程中的重复操作，常用的模板引擎是 art-template
使用前先导入对应的 js 源代码，然后使用 template(模板字符串的 id，渲染的数据)
模板指定的方法是<script type='text/html' id="template"><h1>{{name}}</h1></script>
**模板的重点就是 script 里面的 type 是 text/html，以及 id 属性，{{name}}表示占位符，之后要填数据**
传入的第二个参数渲染的数据是一个对象，对象里面是上面 name 类似的属性键值对
template 方法的返回值就是渲染完毕的字符串，把这个字符串给需要渲染的地方即可
art-template 的标准语法就是{{}}，可以填写变量，对象属性，以及可以求出值的表达式
如果{{}}中需要渲染新的 html 元素，那就需要在变量前添加@表示原文输出
如果有判断条件可以使用 if else if /if 使用的时候中间的内容是需要渲染的，而条件 if else if /if 等放在{{}}中
可以使用{{each arr}} {{/each}}中间的{{$index}}{{$value}}表示循环项的索引和值
过滤器语法{{value | filterName}}类似于 linux 的管道操作符
template.defaults.imports.filterName = function(value) {return 处理的结果}

之前记录过正则表达式的 exec 方法，实际上 exec 方法很类似于 test 方法，只是 test 返回布尔值，而 exec 返回直接符合的内容
**exec 的返回值是一个数组，数组的[0]是匹配到的值，[1]是分组后再筛选的结果**
在正则表达式中使用()包起来表示分组，分组可以用于 exec 的检索
p39

### 9.8

使用 xhr 发起 get 请求的步骤：
1 创建 xhr 对象
2 调用 xhr.open('GET', url)函数，作用是创建请求
3 调用 xhr.send()函数 不加参数，作用就是发起 ajax 请求
4 监听 xhr.onreadystatechange 事件，监听 xhr 请求状态 readystate 和服务器的响应状态 status
正确情况是 xhr.readystate === 4 && xhr.status === 200，随后获取服务器响应的数据 xhr.responseText

readystate 用来表示 ajax 请求所处的状态，每个请求必然处于下列五个中一个
0 UNSENT xhr 对象已经创建，还没有调用 open 方法
1 OPENED open 方法已经调用
2 HEADERS_RECEIVED send 已经调用，响应头也被接受
3 LOADING 数据接收中，此时 response 属性中已经包含部分数据
4 DONE ajax 请求完成，意味着数据传输彻底完成或者失败，所以可以使用 xhr.status 判断是否成功
提供带参数的 get 请求：只需要在 url 地址后添加?再加上参数即可，多个参数之间加&，在 url 地址后拼接的参数字符串被称为查询字符串
实际上在之前使用的$.get()$.ajax(method: 'get')中，get 方式传递的参数都是以查询字符串的方式传入的

url 编码，因为 url 中只允许出现英文相关的字母，标点符号，数字等，为了解决其他语言字符，需要进行编码转义
编码和解码的 api 是 encodeURI(字符串)和 decodeURI(字符串)，一个汉字以三个%开始的编码组成，因为浏览器自动编码解码，一般不需要操作

使用 xhr 发起 post 请求的步骤：
1 创建 xhr 对象
2 调用 xhr.open('POST')
3 设置 Content-Type 属性 xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded') 这个是固定写法
4 调用 xhr.send(查询字符串表示参数)，同时指定要发送的数据，这里的查询字符串不加?作为分隔符
5 监听 xhr.onreadystatechange 事件，与 get 相同，xhr.responseText 是服务器返回的信息

JSON 的两种结构：**在 JSON 中字符串使用双引号包裹**
对象结构：对象结构在 JSON 中表示为{}括起来的内容，结构是键值对的集合
**其中 key 必须是英文双引号包裹的字符串，value 可以是数字，字符串，布尔值，null，数组，对象，不包括 undefined 和函数**
数组结构，数组结构在 JSON 中表示为[]括起来的内容，只有 value，同样可以是以上的六种类型
JSON 的本质是字符串，就是 js 对象的字符串表示方法

JSON 和 JS 对象的相互转换：
JSON -> JS 对象 使用 JSON.parse(JSON)，返回值就是 JS 对象 反序列化，**一般处理服务器返回的 responseText 这个 JSON 格式的文件**
JS 对象 -> JSON 使用 JSON.Stringify(JS 对象)，返回值是 JSON 字符串 序列化

**GET 请求中参数是通过?查询字符串挂载到 url 从 open 方法传输的，而 POST 请求中参数是通过 send 方法传入查询字符串传输的**
p49

### 9.9

xhr2.0 解决旧版的一些问题：只能传输文本，不能传输文件以及传输没有进度的信息
提供的新功能：
设置 HTTP 请求的时限 使用 xhr 的 timeout 属性，单位是毫秒，ontimeout 事件可以处理超时
可以使用 FormData 对象管理表单数据 newFormData()，然后使用 fd.append(key, value)方法添加，最后 xhr.send(fd)
之前使用的 form.serialize()一次性获取表单数据是 jquery 的方法
可以在 form 的 submit 事件处理函数中 new FormData(form 本身)，就可以直接在 send 中传输
使用 FormData 自动包括了 Content-Type 的设置
**可以上传文件**
1 创建文件上传结构，input 标签，type 设置为 file
2 通过上传事件(可能是其他按钮的点击)，使用 input_file.files 属性获取文件
3 判断 files 属性中的 length，如果大于 0 就有文件
4 使用 fd.append(file_key, files[0])就可以上传文件，还是以属性名属性值的方式上传
可以获得数据传输的进度信息
监听 xhr.upload.onprogress 事件可以获取到文件的上传进度
这个事件对应的回调函数参数 e 中有三个属性：
e.lengthComputable 布尔值，表示上传的资源是否是可以计算的长度
e.loaded 已传输的字节
e.total 需传输的字节
使用 Math.ceil(e.loaded / e.total \* 100)即可计算文件的传输进度
xhr.upload.onload 表示上传完成
在 html 标签 input 中添加 autocomplete="off"可以关闭自动填充的行为

使用 jquery 实现文件上传：
1 创建文件上传结构，同原生
2 获取文件过程需要将 jquery 对象重新转化为原生对象
3 同原生，使用 fd.append()添加文件
4 $.ajax({
method: 'POST',
url: ...,
data: fd,
contentType: false,
processData: false,
success: function(res) {
console.log(res);等
}
})
重点是中间两个属性
实现 loading 的效果：
当 ajax 请求开始时执行 ajaxStart 函数，可以在 ajaxStart 的 callback 中显示 loading 效果
$('document').ajaxStart(callback)这个函数必须写在文档身上，会监听当前页面的全部 ajax 请求
相应的也有 ajaxStop(callback)，可以对应实现 ajax 请求完的操作

**使用 axios 完成网络请求**

发起 get 请求 axios.get('url', {params: {参数}}).then(callback)
参数是一个对象，属于 params 属性，把这两个还要继续框起来，记住格式
callback 中参数 res，最后服务器的返回值是 res.data，这个对应的就是传统方法的 res.responseText
res 是 axios 包装的对象，里面的属性有 config data headers request status statusText 这六个

发起 post 请求 axios.post('url', {参数对象}).then(callback)
各项属性基本和上面相同，也是 res.data 代替了原生的 res.responseText

类似于 ajax()的函数 axios({method: 'get/post', url: ..., data: {post 的数据}, params: {get 的数据} }).then(callback)
在 axios 中有 get 和 post 给服务器的参数有区别，get 是 params，post 是 data，也就是说要么 params 要么 data，不会同时出现

同源和 JSONP 关键词有 Access-Control-Allow-Origin
如果两个页面的协议域名端口号都相同，就称这个两个页面同源，区别就在于后续的 url 部分
同源策略是浏览器提供的一个安全功能，大概就是一个网站的 js 不能和非同源的其他网站交互，不能发送 ajax，不能操作 dom 等
与同源对应的就是跨域，跨域请求本身可以发起，也会收到跨域的数据，但是收到的时候会被浏览器同源策略拦截

解决跨域主要有两种方法：JSONP 和 CORS
JSONP 出现早，但不是官方规范，且仅支持 GET，好处是可以兼容低版本浏览器
CORS 符合官方标准，支持 GET 和 POST，但是不支持低版本浏览器

JSONP 的实现原理：script 标签不受浏览器的同源策略的影响，可以使用 src 属性请求跨域接口，通过函数调用接受数据

JSONP 的使用方法：定义一个回调函数，通过 script 标签的 src 属性把回调函数名和参数通过查询字符串传入，让服务器执行这个回调函数，从而跳过跨域
因为相当于发起的请求是 script 类型的，脚本请求默认只能是 get，所以 JSONP 不支持 post 请求，也因为发送的是脚本，不使用 xhr，JSONP 和 ajax 无关

**使用 jquery 中的$.ajax()也可以发送 JSONP 请求，其中传入的参数对象中需要设置 dataType 属性为 JSONP，并且 JSONP 请求不需要指定 method 属性**
默认情况下，使用 jquery 发送 JSONP 请求，查询字符串会自动携带一个 callback=jQueryxxx 的参数，是随机生成的回调函数名
设置$.ajax()中的参数对象的 jsonp 属性可以修改查询字符串的 callback 名称，而修改 jsonpCallback 可以修改回调函数的名称
jquery 会根据 JSONP 动态创建和移除 script 标签，位置在 header 中
p60

### 9.10

在 jquery 中，直接使用 this 是 js 原生对象，可以使用$(this)，这样就是jq对象可以使用jquery的方法
虽然以前记过，但是暂时找不到位置了，边框重叠可以使用margin-left: -1px这种方法解决，如果盖住的问题可以选中的添加position: relative的属性等
不知道为什么代码防抖不能实现，这个问题已经解决，原因是函数没有定义在jq顶级对象$中，其他函数拿不到顶层的参数
ajax p69
倒转回 nodejs

Express 类似于内置的 http 模块，用于快速创建 web 网站服务器或者 api 接口服务器
使用 Express 创建服务器的流程：
1 使用 import 或者 require 导入
2 const server = express();
3 server.listen(端口号, callback)

监听 get 请求：
server.get(请求 url, function(req, res) {})
req 是请求对象，res 是响应对象

监听 post 请求：
server.post(请求 url, function(req, res) {})

响应请求：
使用 res.send(参数) 参数如果是对象的话自动转化为 json，所以说收到的是字符串 json

获取 url 中的查询字符串参数：
**通过 req.query 对象就可以访问到客户端通过查询字符串形式发送到服务器的参数**
获取到的是对象的参数列表，是对象的形式

获取 url 中的动态参数：动态参数是跟在 url 后面使用:的参数
req.params 对象可以访问到 url 中通过:匹配的动态参数，默认是空对象
**所谓的动态参数就是有什么是什么 比如代码中/user/:id，用户输入/user/1，那么 params 就是{id: 1}**
动态参数也可以有多个，多个的话 params 中键值对数量也是多个

p40

### 9.11

托管静态资源：
express.static(指定目录)，可以将指定目录下的图片，css 文件，js 文件等对外支持开放
server.use(express.static('./public')) 可以访问 public 目录下的所有文件了
Express 在指定的静态目录查找文件，对外提供资源的访问路径，所以本身存放静态文件的目录名，如 public，不会出现在 url
比如实际上 public 目录还是不能在 url 访问，但是 public 以下的所有都可以
也可以挂载路径前缀 server.use('./public', express.static('./public'))这样 public 就可以添加到 url 中了

Express 路由：
在 Express 中路由指的是客户端请求和服务器处理函数之间的映射关系
路由分为三部分：请求的类型，请求的 url 地址，处理函数 语法结构 server.METHOD(PATH, HANDLER)
之前的 server.get/post(url, callback(req, res) {})等就是路由的例子
每一个请求到达服务器后都先经过路由的匹配，请求类型和 url 都匹配成功后才会调用对应的处理函数

模块化路由：
为了方便对路由进行模块化的管理，Express 不建议把路由直接挂载到 server 上，推荐将路由抽离为单独模块
步骤如下：
1 创建路由模块对应的 js 文件
2 调用 express.Router()创建路由对象
3 向路由对象上挂载具体的路由
4 使用 module.exports 向外共享路由对象
5 使用 server.use(router)注册路由 这一步是在主文件添加导入的路由使用
这一步也可以 server.use('/api', router)添加访问前缀

中间件：
作用就是对请求进行预处理，可以有很多个中间件
比如 server.get('/', function(req, res, next)) {
next()
}
中间件的形参列表中必须包含 req res next，是一个函数
next 函数的作用可以实现多个中间件连续调用，表示把流转关系转交给下一个中间件或者路由，类似于链表

全局生效的中间件：
客户端发起的任何请求到达服务器都会触发中间件，被称为全局生效的中间件
server.use(中间件函数)就可以定义一个全局生效的中间件，这个中间件任何的 get/post 请求都会触发执行
可以连续定义多个中间件函数，会按照定义的顺序依次执行

中间件的特性：
**多个中间件之间共享同一份 req res，可以在上游中间件统一为 req 或者 res 对象添加自定义的属性或者方法，供下游的中间件使用**
中间件也可以往模块化路由写，挂载的时候就是 router.use(中间件函数)，主函数还是只需要 server.use(router)

局部生效的中间件：
**不使用 server.use()的中间件就是局部中间件，作为参数添加到路由函数**
使用局部中间件要在路由函数中添加参数如 server.get('/', middleware, function(req, res) {...})
使用多个局部中间件可以用逗号连续分隔，也可以直接打包成数组

中间件的使用注意事项：
**路由之前注册中间件**
可以连续调用中间件，不要忘记在最后写 next()
连续中间件之间共享 req 和 res 对象

中间件的分类：
1 应用中间件：绑定到 server 的就是应用中间件，全局和局部都有
2 路由中间件：绑定到 express.Router()上的就称之为路由中间件
3 错误中间件：用于捕获整个项目中发生的异常错误
处理函数中有四个参数 function(err, req, res, next)，err.message 中就有错误信息
错误中间件必须注册在所有路由之后，可以不写 next
4 Express 内置中间件：使用都是 server.use(...)
1 express.static() 无兼容性问题
2 express.json() 解析 JSON 格式的请求体数据，仅 4.16.0 以上
3 express.urlencoded({extended: false}) 解析 url-encoded 格式的请求体数据，同样的高版本才支持
如果版本不合适可以导入第三方中间件 body-parser，语法基本相同
如果不配置解析表单数据的中间件，req.body 为 undefined，配置后可以获取请求体数据
想要拿到 post 过来的表单数据 req.body，一定要配置解析表单数据的中间件
5 第三方中间件：跟包一样需要下载导入，然后使用 server.use()导入即可
p50

### 9.12

在编写自己的服务器的过程中，将 urlencoded 格式的查询字符串转码可以使用 qs.parse(str)，querystring 是 node 内置的模块
JSON 和 js 对象的转换需要自己完成，但是实际上查询字符串的转换是不需要的，框架会自动完成

使用 cors 解决跨域问题：
1 使用 npm 安装 cors
2 导入 cors
3 server.use(cors())导入中间件，也一定在路由之前
cors 由一系列的响应头组成，这些响应头决定浏览器是否阻止前端 js 代码跨域获取资源
cors 在服务器配置 http 响应头，解除浏览器端的跨域访问限制，客户端只需要是支持 xhr2.0 的稍微新一点的浏览器即可

cors 响应头：
res.setHeader('Access-Control-Allow-Origin', '\*') 允许所有网页访问本服务器资源，如果有限制可以换成其他域名
Access-Control-Allow-Headers，默认情况下 cors 仅支持 9 个响应头（详见 9.5-9.11），如果添加需要用 res.setHeader(...)
Access-Control-Allow-Methods，默认情况下仅支持 GET POST HEAD 三个请求，其他方法需要额外添加

node p57

http 协议加强：
http 的请求头部由多行键值对组成，用来描述客户端的基本信息，从而把客户端的相关信息告知服务器
常见的请求头字段：
1 Host 要请求的服务器域名
2 Connection 客户端和服务器的连接方式
3 Content-Length 用来描述请求体的大小
4 Accept 客户端可识别的相应内容列表
5 User-Agent 产生请求的浏览器类型
6 Content-Type 客户端告诉服务器实际发送的数据类型
7 Accept-Encoding 客户端可接收的内容压缩编码形式
8 Accept-Language 用户希望获得的自然语言优先顺序
在请求体中存放的是用 post 方式提交给服务器的数据，只有 post 请求才有请求体，get 没有请求体
响应体和请求体整体比较类似

    常见的http请求方法还有PUT DELETE作用是修改和删除服务器资源
    
    http响应状态码，可以用来表示响应的状态
        响应状态码是一个三位数，最高位定义了状态码的类型，后两位进行细分
        1xx 表示信息，很少见
        2xx 表示成功
            200 请求成功 201已经创建了新的资源对应POST或者PUT
        3xx 表示重定向，需要进一步操作完成请求
            301 请求的资源已经永久移动到新的url，返回的信息包括新的url，浏览器自动定向
            302 请求的资源临时被移动，客户端应该继续使用原来的url
            304 请求的资源没有修改，不会返回任何资源，客户端直接从缓存访问
        4xx 客户端错误，请求有语法错误或者无法完成请求
            400 请求语义有误或者参数有误
            401 当前请求需要用户验证
            403 服务器拒绝执行
            404 访问找不到的资源
            408 请求超时
        5xx 服务器错误，服务器在处理请求的过程中发生了错误
            500 服务器内部错误
            501 服务器不支持该请求方法，只有GET和HEAD是服务器必须支持的
            503 由于超载或系统维护服务器暂时无法处理客户端的请求

ajax p75 接下来都是 git 内容
重新进入 vue 部分

npm install 时添加-S 参数的作用就是把包名和版本记录到 package.json 的 dependencies 下
-S 相当于--save，作为默认行为实际上可以省略 -D 相当于--save-dev 把包记录到 devDependencies

项目的根目录下创建 webpack.config.js 配置文件 初始化 module.exports = {mode: 'development'}，这里选 production 表示上线模式
在 package.json 的 script 节点下，新增 dev 脚本 "scripts":{"dev": "webpack"}

webpack4.x 和 5.x 版本中打包有默认的设定，在 webpack.config.js 中可以调节
默认的打包入口是 src -> index.js，默认的输出文件路径 dist -> main.js
可以通过 entry 节点指定打包入口，output 节点指定打包出口，语法可以参见 9.12-9.18columns 的 webpack 配置文件

webpack 常用插件：
webpack-dev-server
类似于 nodemon，代码修改就自动进行项目打包和构建
会启动一个实时打包的 http 服务器，访问页面的时候使用 localhost:8080/src
打包的 js 文件是放在内存中的，因为频繁更改，不放在物理硬盘
html-webpack-plugin
可以自动将 src 下的 index.html 复制到项目的根目录(其实还是内存)，方便可以直接访问 localhost:8080 来访问到网页
并且在复制出来的页面会自动添加 script，保证能引用到内存中的 bundle.js

webpack.config.js 在 module.exports 中配置 devServer 参数自动打开网页
devServer: {
open: true,
port: 80,
host: '127.0.0.1'
}

webpack 中的 loader，实际开发中 webpack 只能打包.js 后缀的模块，非.js 后缀结尾的模块需要使用 loader
loader 可以协助 webpack 打包特定的文件模块，比如 css-loader，less-loader，babel-loader(处理高级的 js 语法)
在 webpack 中一切皆模块，都可以通过 ES6 导入语法，所以 css，jpg 图片等也可以使用 import 从入口 js 文件中导入
直接 import './index.css'而没有 from 表示只需要加载进来，不需要得到加载的结果，加载 css 的结果是 undefined

使用 loader：
1 使用 npm 下载 style-loader 和 css-loader(css 使用)
2 在 webpack.config.js 的 module->rules 数组中，添加 loader 规则，rules 中的 use 数组，从后 loader 往前调用
在出现 webpack 本身无法打包的文件时，会查找其配置文件，找 module.rules 数组中是否配置对应的 loader，loader 处理完合并到 js 代码
详见 9.12-9.18 的 columns 中的 webpack 配置文件

    css对应的使用[style-loader, css-loader]
    less对应的使用[style-loader, css-loader, less-loader]
    与url路径有关的文件对应的使用[url-loader?limit=22229] limit指定图片的大小，只有小于limit字节才转为base64
    
    使用base64可以解决小图片反复向服务器请求的问题，大图片还是适合原生方法
    使用import导入图片之后自动变成base64格式的字符串，最后设置的src属性也是base64字符串
    
    使用babel-loader处理高级语法兼容性问题，转换的时候会排除node_modules第三方包的转换
    {test: /\.js$/, use: 'babel-loader', exclude: /node_modules/}
    除此之外还要项目根目录创建babel.config.js配置文件等，详情见vue p22

webpack 项目发布：
在 package.json 的 scripts 节点下新增 build 命令 "build": "webpack --mode production"
执行 npm run build 命令就可以打包发布，从内存中转到真实物理硬盘(在使用了 webpack 的两个开发插件后打包的东西都在内存)

SourceMap：是一个文件，里面存储的是位置信息，存储压缩代码对应的转换前的位置
在开发环境中为保证浏览器报错行号一致只需要在 webpack 配置文件的 module.exports 中添加
开发：devtool: 'eval-source-map'
在发布的时候为了安全性最好关闭 source-map 功能，为了进一步实现方便，发布后可以配置只定位行号不标记源码
发布：devtool: 'nosources-source-map'或者直接注释掉不要

实际开发中使用命令行工具 CLI 一键生成带有 webpack 的项目，不会自己配置

使用@表示 src 目录，一般建议导入的时候从 src 往里找而不是一直../../
但是@表示 src 目录需要配置，在 webpack 配置文件中添加新节点 resolve
resolve: {
alias: {
'@': path.join(\_\_dirname, './src/)
}
}

**正式开始 vue：**
vue 有两大关键特点：数据驱动视图，双向数据绑定
数据驱动视图：数据的变化会自动导致页面的重新渲染
双向数据绑定：可以解决表单采集了数据自动获取，不再需要操作 dom

核心工作原理 MVVM
ViewModel 作为连接数据源 Model 和页面结构 View 的桥梁

使用 vue 的基本步骤：
1 导入 vue.js
2 创建 vm 实例对象(vue 对象)
使用 Vue()构造函数
3 在页面中声明将要被 vue 控制的 dom 区域
传入构造函数的参数是一个对象，设置对象的 el 属性，参数是选择器字符串，指定控制区域(包含其子元素)
设置对象的 data 属性，可以控制双向绑定，使用{{key}}把数据写到 html 标签中

vue 提供了六种类型的指令：
1 内容渲染指令
2 属性绑定指令
3 事件绑定指令
4 双向绑定指令
5 条件渲染指令
6 列表渲染指令

内容渲染指令 用于辅助渲染 dom 元素的文本内容，主要有三个指令：
v-text 添加到 html 标签的属性上，实际上就是自定义属性，特性是覆盖原有的标签内的原有内容
{{}} 插值表达式，可以防止覆盖原有的文本，最常用，里面也可以写简单运算式，函数调用等
v-html 内容可以有标签子元素等而不仅仅是普通文本，可以渲染出带标签的内容

属性绑定指令 用于动态绑定 html 元素的属性：
v-bind 把 v-bind 直接添加到要动态绑定的属性上 比如 v-bind:placeholder="tips" v-bind 也可以直接简写为:
在 v-bind 中如果进行字符串拼接在""的内容中还要再加一层''表示是字符串
p44

### 9.14

事件绑定指令 为 dom 绑定事件监听，函数定义到 vue 构造函数的 methods 属性里面
v-on 语法格式 v-on:click="function_name(args)"如果需要传参可以这样传，不需要传参可以不写()，v-on 可以直接被简写为@
事件处理中获取 data 的属性比如说函数要修改 data 中的 count，直接在函数中使用 vm.count 或者 this.count 即可
绑定事件的时候如果不传参数，绑定的处理函数中默认有事件对象 e，定义函数的时候添加参数 e，使用 e.target 就可以操作触发事件的对象
如果传递了参数 e 会被覆盖，可以使用内置变量$event 就是原生 dom 的事件对象，也传进去
事件修饰符：
在事件后添加.prevent 会去除默认的行为，@click.prevent="add"
.stop 阻止冒泡
.capture 捕获模式触发当前事件处理函数
.once 绑定的事件只触发一次
.self 只有当 event.target 是当前元素自身时触发事件处理函数
按键修饰符：一般用于监听键盘事件，比如监听 esc 按键事件 @keyup.esc="clearInput"

双向绑定指令 在不操作 dom 的情况下快速获取表单数据，这个属性双向绑定的是 value
v-model 也是 html 自定义属性，比如 input 标签里面 v-model="username"(相当于原生的 value 属性的自动更新)
之前使用的都是单向绑定，数据源的变化会自动导致页面的重新渲染，但是页面的变化不会导致数据源的变化
v-model 提供了双向绑定，页面的变化也会导致数据源的自动更新
v-model 也有修饰符：需求多可以连着写比如.number.lazy
.number 自动将输入值转化为数字
.trim 自动过滤用户输入的首尾空白字符
.lazy 在 change 时更新而不是 input 实时更新，失去焦点的时候同步到数据源
v-model 一般操作的对象有 input textarea select

条件渲染指令 按需控制 dom 的显示与隐藏
v-if html 自定义属性 v-if="bool" true 展示，false 隐藏 直接动态添加或删除元素 更经常使用
v-show html 自定义属性 v-show="bool" true 展示，false 隐藏 给对应元素动态添加或删除 display: none
和 v-if 配套的指令有 v-else-if 以及 v-else，v-else 后面就不跟条件了

列表渲染指令 辅助开发者基于数组循环来渲染列表结构
v-for 格式是 item in items, items 可以是数组也可以是对象，但是必须写在 data 里面，item 参数除了子元素，自身也可以访问
对于 items 是数组的情况还支持第二种(item, index) in items，使用这个 index 不需要 item.index 直接使用 index 就行
**使用了 v-for 要给 html 元素也绑定一个 key 属性，一般:key="item.id"(而不是 index)，key 只能是字符串或数字类型，必须有唯一性**

label 标签的 for 属性，一般 label 配合 checkbox 复选框操作，使用 for="复选框的 id"可以使点击 label 也能操作复选框

p64

### 9.15

过滤器(vue2 的功能，在 vue3 中删除)：常用于文本的格式化，用在插值表达式和 v-bind 属性绑定
过滤器函数使用|管道操作符使用，比如<p :id="rawID | deal">{{message | capitalize}}</p>
过滤器函数定义到 filters 节点里面，与 data，methods 平级的节点，过滤器函数一定要有返回值，参数的 val 就是管道符前面的值
在 filters 节点下定义的是私有过滤器，只能在定义的那个 vm 实例中执行
定义全局过滤器的方法是 Vue.filter('functionname', function() {...})
也可以定义传参的过滤器函数 Vue.filter('fn', function(arg, my_arg1, my_arg2) {...})调用的时候写 | fn(my_arg1, my_arg2)
全局和私有名字相同的情况下，按照就近原则调用，先调用自己的私有过滤器

侦听器：监视 data 数据的变化，数据变化就会调用
定义到 watch 节点(于 data 同级)，函数类侦听器，函数名就是要侦听的变量名，参数是 newVal 和 oldVal
如果要让侦听器刚进入页面立刻触发，需要将函数改为对象
还是写到 watch 节点里面，key 属性名还是要侦听的变量名，value 是一个对象
value 对象里面 handler 属性写侦听器函数，也可以直接写 handler(newVal, oldVal)
immdiate 属性，true / false 设置为 true 就可以立刻第一次也触发
deep 选项，true / false 解决如果侦听对象，对象属性改变不触发侦听器的问题，改为 true 对象属性的任何变化都会导致侦听器的触发
如果直接侦听一个对象的属性可以这么写 'user.info'(newVal, oldVal) {...}

计算属性：指通过一系列运算最终得到属性值，这个动态的属性值可以被模板结构或 methods 方法使用
计算属性定义到 computed 节点下，定义的时候定义成方法格式，最终返回一个字符串，传递给模板结构等
计算属性内部使用的是 data 节点下的数据，拼接出动态的属性字符串，定义的时候是方法，用的时候直接写计算属性名
可以很方便实现代码的复用，并且只要计算属性中的数据源变化计算属性就会自动重新求值

axios：专注于网络请求的库
调用 axios 方法得到的返回值是 promise 对象，then(res)中的形参不是服务器返回的真实数据，res.data 才是
当调用某个方法的返回值是 promise 对象的时候，方法的前面可以添加 await，await 只能用在被 async 修饰的方法中

**p76 涉及了 es6 的 promise 异步等，先跳转到 p226 学习新语法**

ES6 的模块化：ES6 的模块化标准是官方的标准
在 ES6 模块化之前已经有 AMD，CMD，CommonJS 几种模块化标准，但是通用性不强，AMD，CMD 适用于浏览器端(淘汰了)，CommonJS 适用于服务器端
ES6 定义：
每个 js 文件都是独立的模块
导入其他模块成员使用 import 关键字
向外共享模块成员使用 export 关键字
配置 node 使用 ES6 的模块化语法：需要 14.15.1 以上的 node 版本，在 package.json 根节点添加"type": "module"
ES6 的模块化主要包含三种用法：
1 默认导出和默认导入
默认导出 export default 默认导出的成员(用对象框起来) 每个模块中只能用一次
默认导入 import 接收名称 from '模块标识符'
2 按需导出和按需导入
按需导出 export 导出的成员 每个模块中可以多次
按需导入 import {要的成员名称} from '模块标识符' 相当于解构赋值，导出导入名称一定相同，可以使用 as 重命名，可以和默认一起使用
比如 import {s1, s2 as myName, add} from 'xxx'
3 直接导入并执行模块中的代码 (只想执行某个模块中的代码不想得到其向外共享的成员)
import 要导入执行的模块

Promise：解决回调地狱
Promise 是一个构造函数，new 出来的 Promise 实例代表了一个异步的操作
**Promise 的 Prototype 上包含一个 then 方法，每个 Promise 的实例都可以访问到 then 方法**
.then()方法就是用来预先指定成功和失败的回调函数 比如 p.then(result => {}, error => {})，成功函数必选，失败函数可选
如果上一个.then()方法 1 返回了一个新的 Promise 对象，那么可以通过下一个.then()处理，通过 then 链式调用解决回调地狱
**具体的流程大概是前一个 Promise 的 then 回调中返回下一个操作的 Promise，然后继续调用 then 重复操作**
通过 Promise 原型带有的.catch(err => {...})方法捕获错误，只要有错误直接进入.catch()，其捕获之前所有的错误
如果不希望 catch 提前终止回调链，可以将 catch 直接挂载到要捕获错误的 Promise 对象上
Promise.all()会发起并行的 Promise 异步操作，等所有异步操作全部结束才会执行下一步的.then 方法，类似于锁
Promise.all(promiseArr).then(([r1, r2, r3] => {... return promise})) 这里的 promiseArr 里面有很多的 promise 实例，并行
当前面是 Promise.all()时后面的 then 的回调也可以是一个对应数量的数组作为参数，如果少于就从前往后排
**Promise.all 提供了更简单的回调功能，但是更适合结构一样的**
Promise.race()参数和 all 一样，但是只要一堆 Promise 中有一个完成了会执行 then，那么 then 的回调参数也只需要写一个了
创建一个具体的异步操作:
const process = new Promise(function(resolve, reject) {...})，具体的异步操作定义到 function 内部
then 方法的两个参数就是 Promise 构造函数里的两个形参 resolve, reject

p243

### 9.16

async 和 await：整体上类似于提供一种简单的操作回调顺序的方法
ES8 中引入的新语法，用于简化 Prmise 操作，否则只能使用.then 链式调用的方法
在 Promise 对象前添加 await 关键字则从原来的 Promise 对象转为真实值，也就是使用 then 的参数，但是使用 await 外层的函数前面要添加 async
在 async 方法中，第一个 await 之前的代码会同步执行，await 之后的代码会异步执行(主线程结束后)

EventLoop：解决 js 是一个单线程语言的任务排队问题
为了防止某些任务耗时太长导致程序假死，js 把待执行任务分为两类：
同步任务：在主线程的排队任务，只有前一个执行完毕后一个才开始执行
异步任务：相对比较耗时，js 委托给宿主环境(浏览器/node)执行，异步任务执行完成后，通知 js 主线程执行异步任务的回调函数
当宿主环境把异步操作执行完毕后，把回调函数按照次序送到任务队列中，在主线程完成后回调函数依次执行
主线程从任务队列中读取异步任务的回调函数，放到执行栈中依次执行的这个过程是循环不断的，所以这种机制被称为 EventLoop

宏任务和微任务：
js 把异步任务进一步细分为宏任务和微任务
宏任务：
异步 ajax，定时器，文件操作，其他宏任务
微任务：
Promise.then .catch .finally / process.nextTick / 其他微任务
**Promise 的这个几个函数是微任务，但是本身 new Promise 是主线程的同步任务**
每当一个宏任务执行完毕后，都会检查是否有微任务，如果有就执行所有微任务再执行下一次宏任务

vue 从 p253 的 api 接口案例需要使用 mysql，可能需要回 node 学，预计把后面 node 的案例全部学完需要三天时间
从 node p57 继续

安装配置 MySQL：
对于开发人员只需要安装 MySQL Server 和 MySQL Workbench
MySQL Server：专门提供数据存储和服务的软件
MySQL WorkBench：可视化的 MySQL 管理工具，可以通过它方便的操作存储在 MySQL Server 的数据

SQL 语句：关键字对大小写不敏感
在 SQL 语句中-- 表示注释(两个杠一个空格)
选择数据：select 列名/_ from 表名 where...;
插入数据：insert into 表名 (列 1，列 2...) values (值 1, 值 2...)
修改数据：update 表名 set 列名 1=value1, 列名 2=value2 where 列名=...
删除数据：delete from 表名 where 列名=value;
and 和 or 替代 js 中的&&和||
排序子句：order by 列名 1 (desc), 列名 2 (desc) 默认升序，降序需要添加 desc 关键字，排序依据是先列名 1 再列名 2
count()用于返回查询结果的总数据条数比如 select count(_) from users where status=0;
使用 as 可以给查询出来的列设置别名 select count(\*) as total from users where status=0;
SQL 语句中有些数据段暂时不写可以使用?进行占位

在项目中操作 MySQL 的基本步骤：
1 安装操作 MySQL 数据库的第三方模块 mysql
2 通过 mysql 模块连接到 MySQL 数据库
import mysql from 'mysql';
使用 createPool 可以建立与数据库的连接
const db = mysql.createPool({
host: '127.0.0.1',
user: 'root',
password: 'admin123',
database: 'my_db_01'
可以选 port，默认是 3306 一般不动
})
3 通过 mysql 模块执行 SQL 语句
使用 db.query()指定要执行的 SQL 语句，通过回调拿到执行结果
查询数据 db.query('select 1', (err, results) => {...}) 如果执行的是 select 语句，执行的结果 results 是数组
插入数据 db.query('insert into users (username, password) values (?, ?)', ['jack', '888888'], (err, results) => {...})
执行插入语句的时候传入的参数数组按照次序填补前面?占位符的位置，可以通过检测 results.affectedRows === 1 看是否成功
简化的插入数据方法 db.query(sqlStr, user, callback) 这种情况下没有设置的元素按默认方法继续叠加
sqlStr = 'insert into users set ?' user = {username: '...', password: '...'}
更新数据 db.query('update users set username=?, password=? where id=?', ['mary', '234567', 1], callback)
简化的更新数据 db.query('update users set ? where id=?', [user, user.id], callback)
删除数据 db.query('delete from users where id=?', id, callback)
真实情况下可以使用标记删除的方法，修改 status 位防止误删除便于恢复

在 MySQL 中设置的 AI 自增属性是删除也会不变的，所以更新删除数据可以使用 id 作为行的判断依据，类似于 serial

p70

### 9.17

web 开发模式：
服务器渲染模式：服务器发送给客户端的 html 页面已经在服务器端通过字符串拼接动态生成，因此客户端不需要 ajax
优点：客户端耗时少，有利于 SEO 缺点：占用服务器资源，不利于前后端分离开发
前后端分离开发模式：后端只提供 api 接口，前端使用 ajax 调用接口
优点：分工明确，前端选择性高，用户体验好，服务器压力小 缺点：不利于 SEO，但是也可以使用 SSR 技术解决

身份认证：
服务器渲染模式使用 session 认证机制，前后端分离使用 jwt 认证机制

cookie 机制：
http 是无状态的协议，每次 http 请求是独立的，连续的多个请求没有直接关系，服务器不会主动保留每次 http 的请求状态
需要使用 cookie 突破 http 的无状态性，cookie 是存储在用户浏览器中的一段不超过 4kb 的字符串，由名称，值和其他几个可选属性组成
不同域名下的 cookie 各自独立，客户端发起请求的时候会自动把当前域名下的所有未过期 cookie 发送到服务器
cookie 的特性：自动发送，域名独立，过期时限，4kb 限制
客户端第一次访问服务器的时候服务器通过响应头将 cookie 发送给客户端，之后每一次访问服务器客户端都使用请求头将 cookie 发送给服务器
cookie 直接存储在浏览器，并且浏览器也提供 cookie 的 api，容易被伪造，cookie 并不具有安全性，不使用 cookie 存储重要数据

在 Express 中使用 session 中间件:
1 npm 安装 express-session
2 app.use(session({
secret: 'itheima', 这个地方一般类似于密钥
resave: false,
saveUninitialized: true
}))
3 中间件配置成功后可以使用 req.session 来访问和使用 session 对象
详见 9.12-9.18 mysqltest/app.js
清空 session 可以调用 req.session.destroy()，会清空当前用户的 session

session 的局限：
session 机制需要配合 cookie 才能实现，cookie 默认不支持跨域方法，涉及前后端跨域的时候需要很多额外配置

jwt(JSON Web Token)认证机制:
需要跨域的时候需要使用 jwt
jwt 类似于 cookie，生成加密的 token 字符串到发送给客户端而不是类似于 cookie 保留到服务器端
随后客户端再次发起请求的时候请求头中附带有 Authorization 字段，将 token 发给服务器，服务器将 token 还原成用户的信息对象
和 cookie 的主要区别：1 token 保存在客户端而不是服务器 2 有加密和还原的过程
jwt 字符串的三个组成部分 Header.Payload.Signature
Payload 才是用户的真实信息，Header 和 Signature 涉及安全的部分
jwt 字符串一般存储在浏览器的 localStorage 或者 sessionStorage，发送 jwt 时放在 http 请求头的 Authorization 字段，格式如下
`Authorization: Bearer <token>`

在 Express 中使用 jwt：
1 npm 安装 jsonwebtoken 和 express-jwt
jsonwebtoken 用于生成 jwt 字符串，express-jwt 中间件用于将 jwt 字符串解析还原成 json 对象
2 导入这两个包
新版的导入方法是 const {expressjwt: express_jwt} = require('express-jwt)
3 定义 secret 密钥，secret 密钥用于 jwt 的加密和解密过程
4 在用户登录成功后使用 jsonwebtoken 包提供的 sign()方法，将用户的信息(不要密码)加密成 jwt 字符串，通过 token 属性响应给客户端
token 属性对应的 jwt 使用 jsonwebtoken.sign()方法进行加密，有三个参数：
1 用户信息对象 2 加密的密钥 3 配置对象，可以配置 token 的有效期
5 将 jwt 字符串还原为 json 对象，使用到 express-jwt 中间件
app.use(express_jwt({secret: secretKey}).unless({path: [正则表达式]}))
**如果这里使用的是新版的 express-jwt，需要在 secret 后添加 algorithms: {'HS256'}**
unless 方法可以通过正则表达式匹配哪些接口不需要访问权限
6 使用 req.user 获取用户信息(**最新的官方已经改成了 req.auth**)

api 项目：
为了保证密码的安全性，实际使用中一般不把明文密码放入数据库中，而是把加密的密码放入数据库中
使用 bcrypt.js 可以对密码进行加密，加密后的密码不能逆向破解并且同一明文多次加密得到的结果也不同
p80

### 9.18

表单验证：前端为辅，后端为主，后端主要采用第三方数据验证模块
回顾 req 的三个子属性：(都是对象已经简化过)
1 req.query get 请求的查询字符串部分
2 req.params get 请求使用 url 动态参数时候获取动态参数用
3 req.body post 请求获取请求体用

node p83 大事件后端项目的大体基本实现，开始重新转向 vue，从 p253 开始

mysql 库中的 createPool 函数返回值 pool 提供.promise()方法，调用后可以允许使用 promise 的方式

async 和 await：
async 函数完全可以看作多个异步操作，包装成的一个 Promise 对象，而 await 命令就是内部 then 命令的语法糖
了解底层后会在这里补充

axios 的通常用法：
const {data: res} = await axios({
method: 'get/post',
url: ...
}) 直接使用 await 更简单获取 res 对象，然后结构赋值获取到 res.data

     axios.get(url, {
        params: {} 如果不需要传参数这个项可以省略
    }) 返回值Promise适合前面加await,返回值依然通过解构赋值获取
    
    axios.post(url, {要提交的参数}) 其他方面类似于axios.get()

vue-cli：
单页面应用程序：Single Page Application，一个 web 网站中只有唯一一个 html 页面
vue-cli：
是 Vue 的标准开发工具，简化了基于 webpack 创建工程化 Vue 项目的过程
vue-cli 是 npm 上的全局包，使用-g 参数安装 npm i -g @vue/cli
配置 vuecli 的一些选项：
Progressive Web App (PWA) support 渐进式 web 应用支持
Linter / Formatter 可以自动按照格式格式化代码
Unit/E2E Testing 用于软件测试

vue 项目下的文件构成：
src 文件夹内部：
assets 文件夹：存放项目中用到的静态资源文件，比如 css 样式表，图片资源
conponents 文件夹：程序员封装的，可复用的组件都放到这个位置
main.js：是项目的入口文件，整个项目的运行要先执行 main.js
App.vue：是项目的根组件，看到的结构就是源自 App.vue，这个文件定义了很多 ui 结构

vue 项目的运行流程：
通过 main.js 把 App.vue 渲染到 index.html 的指定区域
App.vue 用来编写待渲染的模板结构
index.html 需要预留一个 el 区域
main.js 把 App.vue 渲染到 index.html 所预留的区域
main.js 中 new Vue 后面跟的.$mount('选择器')跟直接写 el 效果是相同的，指定 vue 的代管区
render 函数会直接把 vue 的控制区直接替换

vue 组件：
组件化开发的思想是根据封装的思想把页面上可重用的 ui 结构封装成组件，从而方便项目的开发和维护
组件化开发：
vue 支持组件化开发，组件的后缀是.vue
vue 组件由三个部分：都是 html 标签的样式，三个标签平级
template 组件的模板结构
**必须只能有一个根节点**
script 组件的 js 行为 必须写 export default { data 函数数据源 } 导出数据
**vue 组件里面的 data 不能指向对象，应该是一个函数，这是跟之前的主要区别**
例如 data(){ return obj } return 的这个 obj 里面可以挂载数据
写函数的话跟之前一样使用 methods 节点，跟 data 平级的节点
style 组件的样式
**如果要使用 less 语法需要在 style 标签添加属性 lang="less"**
p89

### 9.19

main.js 中 render 函数渲染的是哪个 vue 组件，那个组件就称为根组件
根组件 App 使用其他组件，根据使用时候的嵌套关系可以称为父子组件等
在 vuecli 中@表示 src 目录会自动被配置

父子组件的使用：
1 在父组件中使用 import 语法导入需要的组件
2 使用 components 节点(跟 data 平级)注册组件
3 以标签的形式使用刚才注册的组件
通过 components 注册的是私有子组件，只能在注册的节点使用

    注册全局组件：都在main.js而不是App.vue
    1 在main.js使用import引入组件
    2 在main.js通过Vue.component()方法注册全局组件

组件的 props：
props 是组件的自定义属性，封装通用组件后使用 props 可以提高组件的复用性
在组件内部可以在跟 data 平级声明 props 节点，一个数组包着自定义属性名，props 中的数据可以直接渲染到页面上，跟 data 一样
使用的时候类似 html 标签添加属性比如<MyCount init="9"></MyCount>
在组件里面直接传的是字符串，比如上面是字符串 9，转数字可以使用:init="9"，v-bind 的方法
props 的属性是只读的，能修改但是强烈不建议，模拟修改可以把值先赋给 data 的数据，直接用 this.属性名就可以访问
在 data() return {...}里面 count: this.init
对象模式 props：
可以设置默认值比如 props:{init:{default: 0}}
设置数值的类型比如 props:{init:{type: Number}}，默认的类型是字符串，这个设置强行要求传进来的参数必须是指定的 type 类型
可以设置必填项属性 props:{init:{type: Number, required: true}} 不填必选项会报错

组件样式冲突：因为是单页面应用，一个组件的样式实际会写到全局生效
解决的原理是一个组件内的所有标签都添加用于标记的自定义属性，总的 css 文件最后综合属性选择器打包
解决方法是在组件的 style 标签添加 scoped 属性比如<style lang="less" scoped>
**样式穿透：在 css 选择器之前添加/deep/，用于父组件的样式穿透到子组件，主要是使用第三方库的时候如果需要修改第三方组件样式需要**

组件的生命周期大体：
vue 组件的模板结构最后会依赖于 vue 编译器变成 js 代码再插入 index.html(vue-template-compiler)
最后合并的组件其实是组件的实例，在写组件标签的时候实际上类似于 new，而组件类似于构造函数，组件的实例被合并
生命周期指的是一个组件从 创建 -> 运行 -> 销毁 的过程，生命周期函数会伴随生命周期自动运行，没写代码就空执行
生命周期函数直接放在 exports 里面的对象就可以比如 beforeCreate() {...}
创建过程的生命周期函数：(使用标签引入组件)
new Vue() -> beforeCreate -> created(组件在内存中创建完毕) -> beforeMount -> mounted(这个过程组件挂载到浏览器)
运行阶段和销毁阶段：
beforeUpdate -> updated
beforeDestroy -> destroyed
webpack 会使用 vue 编译器，从 main.js 开始，到 App.js 到其引入的其他组件，树状加载组件变成 js 代码最后送入 index.html

组件的生命周期细节：
组件的生命周期始于 new Vue()，随后初始化事件和生命周期函数，到 beforeCreate

    beforeCreate 后开始初始化props，data，methods等各种属性，随后进入created(此时组件的props/data/methods都已经成熟但是还没有模板结构)
    
    created 后进行判断是否有el选项，如果没有需要等到$mount()被调用，再判断有无template选项(不是模板结构)，接上下面的流程
    如果有el会继续判断有无template选项，如果无随后将el的虚拟dom结构转化为模板编译
    created 阶段经常使用ajax来获取数据等，获取数据的方法放在methods节点，然后可以在created里面调用然后赋值给data
    整体而言这个过程就是基于数据和模板在内存中编译生成html结构，结束后进入beforeMount
    
    beforeMount 的时候是将要把内存中编译好的html结构渲染到浏览器，此时浏览器中还没有相关组件的dom
    随后用内存中编译生成好的html结构替换el指定的dom元素，结束后进入mounted阶段
    
    mounted 阶段内存中的html已经渲染到了浏览器中，浏览器已经包含当前组件的dom结构，然后进入运行阶段
    
    beforeUpdate 由数据的变化触发(有变化才触发)，将要根据变化的数据重新渲染组件的模板结构，随后重新渲染进入updated
    
    updated 根据最新的数据已经完成了dom结构的重新渲染，已经是最新的数据
    
    beforeDestroy 准备销毁但是还没销毁，还在正常工作，销毁后进入destroyed
        这两个都不常用，常见的销毁是v-if选择性渲染属性
    destroyed 已经被销毁

组件之间的数据共享：
父子组件：
父组件向子组件共享数据需要使用自定义属性(其实就是父组件导入的时候使用 v-bind 用标签属性的方法给子组件的 props)
props 的值不要修改，还是拿到了就转到 data 属性去

        子组件向父组件共享数据需要使用自定义事件：
            使用自定义事件的步骤：
                1 子组件添加到方法里面内容是this.$emit('numChange', this.count) 让子元素触发numChange事件，传递的参数就是e事件对象
                2 父组件导入子组件的时候添加 @numChange = "getNewNumber" 给子元素添加了自定义的事件numChange
                3 父组件添加方法getNewNumber(val) {this.count = e}
            补充：
                实际上vue内部的事件也是vm.$emit('事件名称', {事件对象...target: 具体的dom元素})传递，$emit是用来触发事件的函数
    兄弟组件：
        在vue2版本中兄弟组件的数据共享使用EventBus.js，EventBus.js其实就是export一个空的vue实例，充当传递者，发送方和接收方都导入bus
        发送方使用bus.$emit('xxxevent', message)，接收方在created()使用bus.$on('xxxevent', message => {...})

p111

### 9.20

refs 引用：
可以在不使用原生 js 或者 jquery 的情况下获取 dom 元素或组件的引用
在每个 vue 组件实例上，都包含一个\$refs对象，里面存储对应的dom元素或者组件的引用，默认情况下组件的\$refs 指向一个空对象
**在模板中给每个标签添加自定义属性 ref="一个 id" 然后 refs 属性中就会自动添加 一个 id: 对应 dom 元素的引用 的键值对**
使用的时候 this.refs.id 即可，修改样式的话可以直接在后面继续添加.style.css 属性名
ref 除了可以引用 dom，还可以引用组件，使用方法就是父组件使用标签方法引入子组件的时候添加 ref="id"属性，然后 refs 里面的 id 就是子组件实例
**实际上这样父组件操作子组件会简单很多，比传统子组件向父组件共享数据使用 EventBus 方便**
$this.$nextTick(callback)这个函数的作用是让页面的 dom 重新渲染完毕再执行回调函数，适合需要等 dom 重新渲染的操作
虽然理论上可以使用 updated 来规避 dom 渲染的问题，但是实际上因为组件的任何变化都会导致 updated，并不合适

购物车案例：
在设置商品的勾选状态的时候要记得子组件 props 里面的 state 不是视图的值，仅仅是一个初始值，并且只读
真正视图中的值是 e.target.checked 或者设置 ref 更简单获取
eventBus 后缀不是.vue 而是.js
兄弟传值不仅仅只用于平级的关系，多层父子关系不方便转化的时候也可以直接使用兄弟传值
p145

### 9.21

动态组件：
vue 内置提供了 conponent 组件，把 component 以标签形式写进去类似于占位符
component 需要提供属性 is="真正要用的组件名"，可以传 data 里面的变量
在 component 切换的时候会销毁原组件新建新组件，导致原来组件的信息丢失
解决方法是 keep-alive，只要把 component 包在 keep-alive 标签即可，这种情况下未选取的元素被缓存在内存
keep-alive 有专门的生命周期函数：
组件被缓存：deactivated
组件被激活：activated 在组件第一次创建，既会执行 created 也会执行 activated
keep-alive 的 include 属性，值是字符串，多个组件之间用逗号分开，只有 include 的组件才被缓存
还有 exclude 属性，这两个属性不能同时使用，exclude 指定不缓存的组件
**组件的名称如果没有在 name 节点指定，则默认指的是注册 components 节点的属性名**

插槽：
插槽一般本身是为组件的封装者提供的能力，允许开发者在封装组件的时候把不确定的希望用户指定的部分定义为插槽
在组件中使用 slot 标签，用户使用的时候传递什么内容 slot 就换成什么
<u>用户传递直接在自定义组件标签内容里面写(innerHTML)，但是如果标签没有插槽，那么往标签的内容节点里面写是无效的</u>
**vue 规定每一个 slot 插槽都必须要有 name 名称属性，如果省略 name 属性则有默认的名称 default**
默认情况下，在使用组件的时候，提供的内容都会被填充到名字为 default 的插槽之中
**如果要指定放到哪个插槽，先用 template 标签包起来给 template 添加 v-slot:插槽名 然后里面写要填充的内容，最后 template 不被真实渲染**
**v-slot 的简写是# 所以指定 default 可以简写\#default 开发者在插槽中写的内容(innerHTML)称为后备内容，用户不指定就是后备内容**
插槽的进阶使用：
开发组件的时候 slot 除了 name 属性还可以添加自定义属性，用户使用的时候使用 #插槽名字="scope"可以获取
如果没有自定义属性，scope 是空对象，这种插槽称为作用域插槽，注意 scope 是整个插槽的所有属性的对象
比如仅仅使用插槽自带属性的 user，那么可以在 template 标签里面这么写#插槽名字="{ user }"实际上就是解构赋值

购物车项目重构：事件传递参数后事件对象参数 e 会被覆盖，需要使用\$event注册，自定义事件这个\$event 取决于传什么参数，不一定是对象，可能是普通数据类型

自定义指令：
自定义指令分为私有(限定组件内部)和全局两种
定义私有自定义指令：
在 directives 节点中声明私有自定义指令，用的时候是 v-指令名(v-color)
指令名(举例为 color): {...}里面是函数，函数参数 el 是对应的使用指令的元素，banding 是内置的参数
banding.value 是传入的参数，banding.expression 是写的东西比如"'red'"，此时 banding.value 是'red'
指令的内部函数：
bind(el, binding) {...} 刚一绑定就执行
update(el, binding) {...} 每次更新 dom 的时候调用
如果 bind 和 update 的内容相同可以换成函数定义的模式只需要写 color(el, bind) {...}
定义全局自定义指令：
在 main.js 里面写 Vue.directive('color', (el, binding) => {...})

ESLint：可以统一格式
在代码中打断点的方法，在要断的位置写 debugger，浏览器到这里会停
ESLint 的主要配置可以查官网，在.eslintrc.js 的 rules 节点可以修改配置

**markdown 的笔记也被插件格式化了，之后可能写个网站全部修改一下，只要内容还在问题不大**

--legacy-peer-deps 可以解决一些 npm 下载有误的问题，实际上是用旧的 node 下载方式

使用 axios 的新方法：(因为这种方案的复用性差，实际上也不经常使用)
    在 main.js 导入 axios，使用 Vue.prototype.axios = axios 把 axios 挂到 vue 原型
    使用的时候组件不再需要导入 axios，可以直接使用 this.axios.get()
    实际上挂载的一般命名为$http，然后使用this.$http.get()
    为了实现请求 url 的统一管理可以在挂载 axios 到 vue 之前，添加 axios.defaults.baseURL = '请求根路径'
    配置完毕后使用的时候只需要写域名后面的 url 部分比如 this.$http.get('api/get', ...)
    这个做法也不是全是好处，比如各个组件之间独立重新发 ajax 请求，不利于 api 接口的复用
    **实际上因为只有一个axios对象，也就只有一个baseURL选项导致要请求多个域名接口很不方便**
p175

### 9.22

前端路由的概念：路由实际上就是一种对应关系
对于 SPA 应用，不同组件和页面上的地址的对应关系就是路由
前端路由就是 Hash 地址与 组件 的对应关系，页面跳转的原理是 a 的锚链接，herf 元素绑定一个#id
井号以及后面的 hash 地址可以使用 location.hash 获得
hash 地址变化对应的事件是绑定到 window 上的 hashchange 事件

前端路由的工作方式：
工作步骤：
1 用户点击页面上的路由链接
2 导致 url 地址栏的 hash 值发生变化
3 前端路由监听了 hash 地址的变化
4 前端路由把当前 hash 地址对应的组件都渲染到浏览器

vue-router：vue-router 是 vue 官方提供的路由管理器
	安装和配置：实际上如果使用 cli 创建项目的话不需要手动安装配置
		1 安装 vue-router
		2 在项目中创建路由模块：
			在新的 js 文件导入 vue 和 vue-router 模块，Vue.use(VueRouter) / const router = new VueRouter() / export default router
			其中的 Vue.use() 是专门用来给 vue 装插件的函数
		3 在 main.js 导入，在 new Vue({render: ..., router: 路由实例对象})

vue-router 的使用：
    vue-router 提供了一个新的组件 router-view，作用就是给组件当占位符
    在 router 文件夹的 index.js 中，new VueRouter 的时候传入参数 { routes: [...] } 数组里面就是 hash 地址和组件的对应关系
    数组中写法：[ {path: '/home', component: 要展示的组件} ]，要展示的组件需要导入
    实际上原始的普通 a 链接也可以直接替换，使用 router-link 标签，其上有 to 属性，可以不用再写前面的#
    默认输入的域名对应/作为 hash 地址，如果想完成类似访问页面就进入首页这样的功能，可以使用路由重定向
    路由重定向 redirect 属性，在 routes 数组里面添加{path: '/', redirect: '/home'}

嵌套路由：通过路由实现组件的嵌套展示
    其实嵌套路由本身就是一种套娃，路由出来的组件里面继续嵌套子路由
    实现嵌套路由需要在路由组件中添加 router-link 选择路由的标签
    子路由的规则先到 routes 里面的父路由规则的对象，添加 children 属性，children 属性里面还是{path: ..., component: ...}
    子路由也可以添加重定向，子路由的重定向写在父路由比如 about 的路由规则添加 redirect: '/tab1'
    除了 redirect 属性还可以设定默认字符串，如果 children 数组里面哪一条 path 是空，这一条就是默认子路由

动态路由：
    动态路由指的是把 hash 地址中可变的部分定义为参数，提高路由规则的复用性，使用 url 动态参数加上:就可以了
    上述的例子比如{path: /movie/:id, component: Movie}，但是如果这么写 movie 中应该根据 id 的值反映出对应的页面
    获取 id 的方法是 movie 的 this.\$route.params.id 点击不同的 router-link 标签 id 属性就会跟着改变
    更理想的方法是直接在路由规则数组对象中添加props: true然后在Movie.vue声明对应的props就可以直接获得
    如果是查询字符串的参数不是hash地址，查询参数使用this.\$route.query 获得，获得的查询参数直接就是对象
    \$route 里面还有 fullPath 属性，里面有带 hash 地址和查询字符串的完整路径

this.\$route 是路由的参数对象，this.\$router 是路由的导航对象
声明式导航：点击链接导致组件的切换，比如使用 a 或者 router-link 标签
编程式导航：调用 api 实现导航，比如直接修改 location.herf

vue 项目的编程式导航：
vue-router 提供了三个常用的 api
    this.\$router.push('hash地址') 直接跳转到指定页面，增加一条历史记录，在页面内可以后退
    this.\$router.replace('hash 地址') 直接跳转到指定页面，替换一条历史记录
    this.\$router.go(数值 n) 数值 n 可以是正数也可以是负数，表示在历史记录前进后退
    对于 go 方法一般只前进一步或者后退一步，由此提供了.forward()和.back()
因为编程式导航一般只有一行代码，适合在行内绑定@click 函数，如果行内写就不要带 this

导航守卫：控制路由的访问权限
    比如在未登录的情况下不能访问后台主页，可以使用导航守卫判断有无token
    全局前置守卫：除了这个其实还有很多种
        在new VueRouter后，使用router.beforeEach(fn) 每次路由导航跳转前都触发fn
        fn守卫方法有三个形参，to, from, next 分别是将访问的路由信息对象，将离开的路由信息对象，next是函数，调用next()表示放行
        to和from参数的重点就在于其上的三个属性.fullPath .path .params
        next函数有三种调用方法 直接调用next() 强制跳转next('/login') 强制不允许跳转next(false)

练习路由使用的后台管理系统：
    做这个项目的时候路由守卫出了一些问题，在token还没有生成到localStorage的时候就去判断导致无法登录
    过一段时间尝试修改一下
p204

### 9.23
使用vue-cli创建项目之后，路由展示的组件放到views文件夹下而不是components

vant组件库：
    使用vant组件库，npm下载导入vant，可以全部导入，最后发布的时候再进行精简
    导入的语法：
        import vant from 'vant' import 'vant/lib/index.css' Vue.use('vant')
    vant组件可以实现大量的功能，包括路由跳转也可以直接使用Tabbar组件的路由模式
    如果需要统一修改vant主题的样式可以使用定制主题

实际使用axios的主要方案：
    封装request.js 里面导入axios const my_axios_id = axios.create({baseURL: '...'})
    不同的my_axios_id对应不同的axios对象，每个对象有自己的baseURL
    实际上是根据不同的服务器创建不同的axios对象，这些实例对象的方法完全相同.get .post等
    每个request.js最好只对应一个axios实例对象，有其他的最好新定义模块

ajax请求的接口复用：
    接口可以封装到单独的一个js文件
    使用axios的时候前面会带有一个await，实际上await后面就是一个Promise操作，可以把这个Promise抽取出来

如果props属性可以是多种类型 type: [Number, String]
如果props属性的类型是对象，必须使用函数类似于data() {return {...}}传递默认值

定制vant主题：
    import 'vant/lib/index.less' 注意这里是导入less文件而不是css
    一种方法是修改vue.config.js，直接覆盖变量，操作比较复杂并且需要重启打包的服务器，可以详见官网
    另一种方法是通过less文件覆盖，在vue.config.js中用绝对路径(可以在vue.config.js中使用__dirname)指明自己的less文件

开发常用的一个工具库：lodash

**vue2全部完结，明天开始vue3，由于课程重复可能3-4天就能看完，看完之后边做案例边走小程序**

p330

**开始学习markdown的使用**

简单重新学会了markdown，从明天开始在typora打开这个文件，前期的这些有空修改



### 9.24

**vue3提供的两种快速创建工程化SPA项目的方式：**

使用vite或者使用vue-cli

**vite：**

+ 仅支持vue3版本，不基于webpack，相对小巧，目前还正在完善

**vue-cli：**

+ 支持vue2和vue3，基于webpack，功能大而全，但是运行速度相对慢



**基于vite创建工程化的项目：**

代码步骤：

```
npm init vite-app 项目名称
cd 项目名称目录
npm install
npm run dev // 这个地方不是npm run serve
```

整体来讲vite创建的项目结构非常类似于vuecli创建的项目去除了webpack的有关部分

==在npm i 命令后要执行 npm i less -D，另外vite的项目是没有@代表src这个目录的==

src文件夹下的组成：

+ **assets** 用来存放所有的静态资源文件(css，font等)
+ **conponents** 放自定义组件
+ **App.vue** 项目的根组件
+ **index.css** 项目的全局样式文件
+ **main.js** 项目的打包入口文件

main.js的不同写法：

```javascript
// vue3的写法
import { createApp } from 'vue'
import App from './App.vue'

const spa_app = createApp(App)
spa_app.mount('#app')

// 回顾vue2的写法
import Vue from 'vue'
import App from './App.vue'

new Vue({
    router, // 如果有
    render: h => h(App)
}).$mount('#app')
```

另外还有一个区别是vue2的template里面还有一个根节点(一般是div)，在vue3中可以没有这个根节点(最后自动添加)

​	*不过用div包起来这个习惯也可以保留*

制作 todolist 案例的时候好像发现如果是props传递的是广义的对象，props属性是可以修改的，并且很好的解决了数据传递的问题

**vue3中自定义事件也有了变化，主要体现在传参使用的时候**

+   子组件使用跟data平级的emits指定有的事件`emits: ['add']`
+   子组件依然可以使用`this.$emit('add', this.taskname)`触发事件
+   父组件引入子组件的时候挂载事件处理函数`@add="onAddTask"`

​	实际上对比出来的区别就是vue2中子组件可以直接`this.emit('add', this.taskname)`不需要额外在`emits`数组中添加

一个今天做todolist出现的错误，push方法直接改变原数组，不需要更新返回值

另一个做todolist的经验，id用array.length的话可能不唯一，比如删除了过后id又重复了，这种情况下可以单独设置一个id变量

似乎vue3的v-model不仅限于表单元素，一会儿查看一下

>   在表单输入元素或组件上创建双向绑定  --Vue文档

**使用v-model绑定组件有什么要点**

​	在表单元素中，v-model默认绑定的是value属性和指定的数据，而组件中不一定有这个value属性

​	==常见的使用组件v-model的场景有父子共享数据同步==

​	所以就有以下的规则：

1.  组件默认绑定的是一个自定义属性 `modelValue` 对应的事件是 `updata:modelValue`本质原因是v-model其实就是语法糖，对应的事件往往被隐藏

2.  子组件可以有其他的自定义属性比如这么用

    ```javascript
    <MyComponent v-model:title="bookTitle"
    // 这个意思是子组件要有一个title的props属性，触发update:title事件导致更新
    // 因为update的函数是自动执行的，所以说其实就是 v-model:绑定的属性名="数据"
    ```

p414 之后大概3-4天刷完vue剩下的部分，逐渐理清vue2和vue3的区别

高程书看到了39页，明天先把括号匹配那个题做了，然后学vue3的同时推进js语言关



### 9.25

今天返校，不知道进展会不会顺利

**vue3中兄弟组件的传值**

​	相比起vue2中直接创建eventBus.js，里面就是一个空的vue实例来讲，vue3移除了事件总线，有一些区别

1.   使用第三方包 mitt 
2.   发送方给bus触发自定义事件，==接收方通过.on而不是.$on处理事件==

​	具体的代码如下：

```js
// 数据发送方
import bus from './eventBus.js'
bus.emit('eventName', data)

// eventBus 如果是vue2就直接new一个空的vue实例即可
import mitt from 'mitt'
const bus = mitt()
export default bus

// 数据接收方
import bus from './eventBus.js'
bus.on('eventName', (data) => {...})
```

**vue3中后代组件的传值**

​	在vue2中多级父子关系一般直接采用eventBus，而vue3提供了新方法

​	发送方使用provide，接收方使用inject，但是这里有限制 <u>必须是有多级父子的嵌套关系</u>

​	具体代码示例如下：

```js
// 在发送方跟data平级新增provide方法
provide() {
	return {
		color: this.color // 这个是data里面的color
	}
}

// 接收方跟data平级新增inject数组
inject: [
	'color' // 用的时候直接在template里面写color即可
]
```

​	有缺点，这样的inject不是响应式的，发送方数据变化不会导致接收方跟着变化，改成响应式代码如下

```js
import {computed} from 'vue'

// 在发送方跟data平级新增provide方法
provide() {
	return {
		color: computed(() => this.color) // 这个是data里面的color
	}
}

// 接收方跟data平级新增inject数组
inject: [
	'color' // 用的时候写 color.value
]
```

**vuex**

​	终极的组件之间数据共享方案，可以让组件数据共享变得高效清晰易于维护

​	vuex类似于给所有组件提供了一个公共的仓库，仓库提供共享数据的存取

**vue3全局配置axios 配置在main.js**

```js
axios.defaults.baseURL = 'http://api.com'
app.config.globalProperties.$http = axios
// 在vue2中第二行这么写 Vue.prototype.$http = axios
this.$http('url可以简写了', ...) // 用的时候这么写
```

​	学了vue2自然知道这种方法的复用性很一般，所以还是需要 const myAxios =  axios.create({baseURL: ...})

**记录之前ref引用缺失的点**

​	组件执行dom更新这是一个异步的操作，比如使用v-if新增一个元素，这个操作是异步的

​	意味着如果随后直接就使用ref获取这个新元素的引用得到的是undefined

​	为解决这个问题，让dom更新加载完成了再执行后续代码，需要使用 `this.$nextTick(callback)`

​	把这种操作放到回调里面去，等dom加载完毕才会执行回调，就解决了问题

**解决了9.22路由管理系统的问题**

​	不得不说实在很搞笑，`localStorage.getItem('token')`写成了直接的token，传递参数应该是字符串key

在vite项目中经常使用:root选择器，实际上就是html根元素选择器，在这里指定可以继承的样式很合适

**重新讲一下插槽的进阶使用**

​	只要是`slot`里面绑定了props数据的就是作用域插槽

```vue
<slot name="default" :info="obj"></slot> // 这是本身组件部分

<template #default="scope"> // 一般插槽的参数使用scope接收
	<p>{{scope.info}}</p>
</template>
// scope是一个插槽的大对象，里面会有插槽的全部自定义属性，但是如果没有自定义属性scope就是空对象
// 一般使用的时候可以使用解构赋值，改成这样
<template #default="{ info }">
	<p>{{info}}</p>
</template>
```

​	作用域插槽可以很方便的导入使用插槽的组件的数据，直接使用props传值即可

**vue3的router配置**

​	vue-router 3.x只能结合vue2使用 vue-router 4.x只能结合vue3使用 关键词vue3路由创建

​	配置流程：

```js
npm i vue-router@next -S // 意思是下载4.x版本最新的

// 创建router.js路由模块
import { createRouter, createWebHashHistory } from 'vue-router'

const router = createRouter({
	history: createWebHashHistory(),
	routes: [
		{ path: ..., conponent: ... },
		...
	]
})

export default router

// main.js导入router
import router from '...'
app.use(router)
```

**vue cli的使用 二**

​	补充使用vue ui来创建项目，整体操作类似于powershell中创建的流程

​	虽然创建过程并不方便，但是后续修改配置，安装新插件等适合使用vue ui

**vue组件库**

​	开发者可以打包.vue文件上传到npm供下载使用，vue组件相对bootstrap开箱即用

​	**element ui** 主要适用于PC端

​	使用方法：(如果是vue3版本使用ElementPlus，可以官网查询)

```js
// 这是对应vue2的
npm i element-ui -S

// element-ui可以全部引入或者按需引入

// 全部引入 main.js

import ElementUI from 'element-ui'
import 'element-ui/lib/theme-chalk/index.css'

Vue.use(ElementUI) //直接注册成插件

// 按需引入
npm i babel-plugin-component -D
// 第二步修改.babelrc配置文件
{
  "presets": [["es2015", { "modules": false }]],
  "plugins": [
    [
      "component",
      {
        "libraryName": "element-ui",
        "styleLibraryName": "theme-chalk"
      }
    ]
  ]
}
// 第三步可以在main.js使用按需引入
import { Button, Select } from 'element-ui'
Vue.use(Button)
Vue.use(Select)
```

**axios拦截器**

​	拦截器在每次发起ajax请求和得到响应的时候被触发 ==某种意义上来说就是一种前端的中间件==

​	配置请求拦截器(发到服务器之前要过一次请求拦截器)

```js
axios.interceptors.request.use(resolve, reject)
// resolve里面有一个config参数，里面有请求的信息，最后必须返回，另外reject(err)可以不写
```

​	配置响应拦截器(响应回客户端之前要过一次响应拦截器)

```js
axios.interceptors.response.use(resolve, reject)
// resolve里面有一个response参数，里面有响应的信息，也最后必须返回，同样reject(err)可以不写
```

**今天的算法题：20-有效的括号 1-两数之和**

p530



### 9.26

思考了一个有意思的项目：BetterWeChat

​	今天先来分析一下这个项目的大体结构，每个页面的组件名称等

vue动态添加dom元素：虽然可以但是用v-for和v-if一般够了，如果非要可以创建实例使用\$before \$after这种方法

**在准备做项目之前，先补一下git的知识：**

​	git记录的是文件的快照而不是文件的变化，svn使用文件变化，好处是节省磁盘空间，坏处是版本跳转必须一直走更新链，耗时

​	快照是在原有文件的基础上重新生成新的文件，类似于备份，如果文件没有修改，git不再重新存储文件而是存一个指针

​	git有三个区域，文件有三个状态：(实际上未跟踪也是一种状态)

+   工作区 处理工作的区域  已修改状态
+   暂存区 已完成的工作临时存放，等待提交  已暂存状态
+   git仓库 最终存放的区域  已提交状态

​	在C盘的.gitconfig文件中可以查看全局的git配置

​	或者也可以在终端输入`git config --list --global`，查看指定配置项`git config user.name`

​	终端中输入`git status`可以查看文件处于什么状态

​	使用`git add 文件名`就可以开始跟踪某个文件，添加到git管理，这个命令有三个功能

+   可以开始跟踪新文件
+   把已跟踪，且已修改的文件放到暂存区
+   把有冲突的文件标记为已解决

​	使用`git checkout -- 文件名`可以撤销修改回到git仓库的版本，这个操作危险性高

​	使用`git add .`添加全部的文件

​	使用`git reset HEAD 要移除的文件名`可以从暂存区移除对应的文件

​	使用`git commit -a -m 'message'`可以跳过暂存区，直接从工作区跳到git仓库，这种情况就不用git add了

​	移除文件：

```shell
git rm -f 文件名 // 从git仓库和工作区同时移除(下次提交的时候删除，不是立刻删)
git rm --cached 文件名 // 只从git仓库移除，工作区保留(直接进入不被跟踪的状态)
```

​	不需要git管理的文件可以在.gitignore中配置，里面的写法类似于正则表达式

​	使用`git log`可以查看全部的提交历史，后面跟上 -n 只会展示近期的 n 条提交历史

​	回退到提交版本：

```shell
git reflog --pretty=oneline // 查看命令操作的历史
git reset --hard <CommitID> // 根据提交的id回退到指定版本
```

git p90

**不通过后端cors或者jsonp解决跨域代理的问题**

​	原理如下：

+   把axios请求的根路径设置为vue项目的运行地址(自然也就不存在跨域问题)
+   vue项目发现没有请求的接口，请求转交给proxy代理
+   代理把请求根路径替换为devServer.proxy属性的值，发起真正的数据请求
+   代理把请求到的数据转发给axios

​	配置流程：*这个只在开发调试阶段使用*

1.   main.js调整axios的请求根路径(如果是axios.create的另说)
2.   项目根目录创建vue.config.js配置文件，然后这样写：

```js
module.exports = {
	// 这是开发阶段
	devServer: {
		proxy: '真实地址'
	}
}
```

p533 剩下的案例暂时不看了，vue基础相当于完结

写项目之前可能先把vuex学完，大概两天

**重中之重，js数据结构重学，有助于刷力扣**

开始看数据结构

​	js的数组封装极为优秀，但是常见的其它语言中数组经常需要封装使用(java的ArrayList)，原因如下：

+   常见语言数组不能存放不同类型数据，所以数组都是包装类
+   常见语言的数组容量不会自动改变，因此需要扩容的操作
+   常见语言的数组进行中间插入和删除操作的性能比较低

**栈**

​	在js中数组是最自由的线性数据结构，栈和队列都是增添了对元素插入和删除的限制，是==受限的线性结构==

​	之前用的已经很多了，不做过多记录

**队列**

​	使用shift和push就可以用数组模拟队列

​	因为插入队列需要对应数组的开始位置插入元素，后面的元素全部后移，效率不高

p18

**杂项**

```js
// 回顾 ES5 给对象添加方法
function Stack() {
	this.item = []
	// 添加方法有两种
  // 添加属性 (重点是给实例添加) 
	this.push = function() {}
  // 挂到原型 (重点是给类添加，省内存)
  Stack.prototype.push = function() {}
}
```



**今天的算法题总结 完成题目 88-合并两个有序数组 415-字符串相加**

​	==foreach循环是不能修改本身数组元素的，拿到的item是形参，修改不到真实值==，如果非要修改只能这样：

​	要在forEach里面改变数组，需要用array[index]的方法来改变数组本身，添加index参数，这样操作不如直接for

​	<u>大量ES6遍历数组的方法都不会改变原数组，要改原数组建议直接for</u>

​	另外重视数组中的splice方法，非常好用



### 9.27

**优先级队列**

​	队列的元素除了data还有priority，priority决定插入到队列的位置

​	实际上内置函数只有插入的时候需要判断插入的位置，其他并没有区别

**链表**

​	对比数组的好处

+   不需要连续内存空间
+   插入和删除快捷，导致扩容也成本很低

​	对比数组的缺点：访问任意位置的元素都需要从头或者尾开始，没有下标的优势

​	==一般情况下认为按着下标插入是插入后新下标对应插入的这个元素== 这个问题再继续考证一下

​		但是在splice方法中插入是放到新数组的对应指定下标

​	如果链表头不挂载数据的话，链表头跟第一个节点是等效的 `list.head = first_node`

数据结构 p27



**随便记点element ui的使用**

​	**1 布局**

​	使用layout控制布局，类似于flex，然后装容器，容器的内部可以分上下左右，内部还可以继续套容器

​	布局的时候先行后列，可以用空行充当 margin-top 的功能

​	row主要直接使用，可以用css调高度，内嵌div调样式，如果需要左右间距使用 `:gutter=20`这样的属性(实际上还是给col分左右)

```html
<el-row :gutter="20" type="flex" justify="..."></el-row>
```

​	col可以选择 `:span=24/12/8...`进行左右划分，一共24份，从左到右的偏移使用`:offset=6`单位跟`:span`一样的

```html
<el-col :span="18" :offset="6"></el-col>
```
​	**2 容器**	

​	容器对应的标签以及属性：

```html
容器本体 <el-container direction="vertical"> 子元素有<el-header>或者<el-footer>所有子元素会上下排列，否则左右排列
顶栏容器 <el-header height=...>
侧边栏容器 <el-aside width=...> // 侧边栏默认在左边我也不知道怎么简单方法调整到靠右
主要区域容器 <el-main>
底栏容器 <el-footer height=...>
container只能包含这四个元素或者自身，这四个元素的亲父元素也必须是container
复杂的样式可以嵌套container解决
```

​	**3 颜色，字体，边框**

​	颜色就是单纯列出了一些 \#FFFFFF 表示的推荐颜色，字体同样有推荐，用默认就行

​	边框的圆角化和阴影推荐都可以直接复制官方推荐

​	**4 图标**

​	官方推荐使用 i 标签代表图片，只需要给 i 添加类名即可

```html
<i class="el-icon-iconName"> // 要什么图标可以去官网查类名
```

​	**5 按钮**

​	按钮对应标签以及属性：

```html
<el-button type="什么主题风格" plain round circle disabled></el-button>
// 除了type有五个选项之外其他都是布尔选项，round表示圆角按钮，circle表示圆形按钮
// 如果按钮需要有文字或者图标，可以使用 icon 属性或者直接内嵌 i 标签
// 按钮的加载效果，只需要添加 loading 属性，按钮大小使用size属性，预设三种大小

<el-button-gruop>
	// 里面的el-button会以按钮组的形式出现
</el-button-gruop>
```



**Vue项目**

​	**el-row和el-col不要去设置宽度和高度，用内部元素撑开，布局不是容器**

**杂项**

+   console.log不会自动调用对象的toString方法，但是网页的alert方法会
+   如果前端和服务器不存在跨域问题可以考虑使用cookie(客户端)或者session(服务器端)记录状态

**今天的算法题总结 121-买卖股票的最佳时机 836-矩阵重叠**

​	不是每道题都可以使用暴力算法，买卖股票这道题会直接超时

​	设想了很多种方法，题的难度应该在于买的下标一定要小于卖的下标，从而引发顺序的问题

​	<u>但是实际上数组的循环本身就是按顺序来的，检索最便宜的购买价格，如果大就减了看利润是否替换，很顺畅的解法</u>

​	js求数组最大值的方法 `max_value = Math.max(...array)`使用剩余参数把 array 打散

​	矩阵重叠花了很长的时间，实际上不一定按着顶点考虑重叠，试着去考虑边，会轻松很多



不得不说element ui写得太费劲以至于明天需要花更多时间看



### 9.28

数据结构 p34

**element ui 继续看**

​	**受控组件**

+   只有表单元素才明确是不是受控组件
+   受控组件是直接被vue管理的，而非受控组件类似于原生的dom管理

​	**输入框**

​	`<el-input></el-input>`就是受控组件，并且如果不处理input事件并更新绑定值(或者干脆v-model也行) 会无法输入

​	输入框的标签和属性：

```html
<el-input placeholder="请输入密码" v-model="input" show-password></el-input>
// v-model必须写，不写不能正常使用
// Boolean属性：disabled clearable show-password
// 插入前后小图标：prefix-icon suffix-icon
// 如果换成textarea就添加 type="textarea" rows=...
```

​	**选择器**

```html
// 选择器的外层使用el-select，内层使用el-option，这个标签使用v-for渲染就实现了选择器内部的选项
// 举个例子
<el-select v-model="userType" placeholder="请选择登录身份" style="margin-bottom: 20px">
	<el-option v-for="item in userTypeOptions" :key="item.id" :label="item.label" :value="item.id">
	</el-option>
</el-select>
// 在el-select里面绑定的v-model="userType"，这个userType对应视图的值就是选中的el-option的value属性
```



​	**表单**

​	表单也是常见的表单组件拼出来的，相关的组件主要有两个`el-form`以及`el-form-item`

```html
// 最外层是el-form包起来，每一个表单域再使用el-form-item包起来
// 举个例子
<el-form ref="formRef" :model="form" label-width="80px" :rules="loginFormRules">
  <el-form-item label="活动名称" prop="activity"> // label是表单项展示出来的描述
    <el-input v-model="form.name"></el-input>
  </el-form-item>
</el-form>
// 在data里面添加规则
data() {
	return {
		loginFormRules: {
			(这个地方是规则的名字，规则使用prop传递给el-form-item)activity: [
				{required: true, message: '请输入活动名称', trigger: 'blur'}
			]
		}
	}
}

// 对于el-form，可以使用inline属性让表单域展现到一行
// 使用label-position调整描述文字的对齐方式
// 表单验证，比较复杂可以看文档
```

​	==一个表单就是一个系列，el-form添加model属性绑定data的对象，剩下的表单域绑定form对象的属性==

​	表单的验证总规则添加到el-form，分规则写到el-form-item，可以看上面的实际代码演示

​	通常给el-form一个ref属性，方便直接调用表单的方法，比如`resetFields / validate`

**通知类气泡消息提示**

​	element已经帮我们在Vue原型上挂载\$message属性，里面有一些弹框有关的方法可以直接使用

p32

**回顾一下Vue2的路由**

​	直接贴一个典型的 router.js 代码

```js
import Home from '@/components/Home.vue'
import Login from '@/components/Login.vue'
import Vue from 'vue'
import Router from 'vue-router'

Vue.use(Router)

const router = new Router({
  routes: [
    { path: '/', redirect: '/login' },
    { path: '/login', component: Login },
    { path: '/home', component: Home }
  ]
})

router.beforeEach((to, from, next) => {
  if (to.path === '/login') return next();
  const token = window.sessionStorage.getItem('token')
  if (!token) return next('login')
  next();
})

export default router

// 最后在main.js只需要很简单在创建vue对象的时候传参
import router from '.../router.js'
new Vue({
  router,
  render: h => h(App)
}).$mount('#app')
```



**杂项**

​	不是页面上的每个组件都要换成element ui，很多也可以自己写

​	在vue文件中使用sessionStorage这种window的属性，前面添加window对象`window.sessionStorage.setItem(key, value)`

​	回顾一下路由守卫的作用，卡路由访问权限可以用，比如/home只能登录了的用户才可以访问



**今天的算法题总结 70-爬楼梯 206-反转链表**

​	爬楼梯这个题用的是动态规划的方法，不同于递归，动态规划可以使用数组记录已经计算过的状态，递归每次都重新计算

​	这道题直接使用递归会超时，所以之前的计算结果应该存起来

​	想通了为什么动态规划使用dp数组可以比单纯的递归速度更快

```
比如说爬楼梯这道题，递归的公式是 f(n) = f(n-1) + f(n-2)
举个例子 f(5) = f(4) + f(3) = f(3) + f(2) + f(3)
显然从这里看如果不使用动态规划的dp数组，f(3)计算了两次，而动态规划只需要计算一次
```

找个闲时间整理一下格式



### 9.29

上午出门做了个志愿活动，今天从下午开始

**element ui**

​	**菜单布局**

​	使用的标签，属性以及使用的方法：

```html
// 两级菜单并且可以折叠
// 典型样例
<el-menu> // 菜单总体 text-color和active-text-color用来调整菜单文字和选中项目的文字
	<el-submenu> // 一级菜单 属性是el-submenu说明还有下级菜单
		<i class="el-icon-menu"></i>
		<span>一级菜单</span>
		<el-menu-item> // 二级菜单
			<i class="el-icon-menu"></i>
			<span slot="title">二级菜单</span>
		</el-menu-item>
	</el-submenu>
</el-menu>

// el-submenu的index属性需要不同，这个属性相当于子菜单的id，但是这个index属性只接受字符串参数
// el-menu-item也需要绑定index属性
// 每一级菜单的渲染都可以使用v-for，尤其是使用ajax获取数据的情况
```

p38

**杂项**

​	css属性 letter-spacing 单位可以使用em，调整字体间距用的

​	有时候遇到的GitHub Pages部署失败可以在部署页面重新点一下运行部署`Rerun jobs`



**今天的算法题总结 67-二进制求和 171-Excel表列序号**

​	这道题就是之前的字符串相加的简单版本，相当于重新熟悉一下代码，一遍就过

```js
// 字符转ascii码
String.fromCharCode(number) // 返回值就是对应的字符
// ascii码转字符
my_char.charCodeAt() // 返回值就是对应的ascii码
```

​	Excel表列序号就是写了个26进制转10进制，也非常简单

今天没看数据结构，把登录界面重构了一下，现在基本上看得过去了，明天开始管理员面板的构建



### 9.30

数据结构p39

找到了一个新的ES6课程，暂时不想做vue先看一下

**复盘ES6**

​	**let和const**

​		var的变量提升是把声明提升到最前面，但是赋值并没有被提前，所以之前的使用都是undefined

​		let和const都没有变量提升，限制于声明的作用域，不能重复声明

​		这俩还有个好处是不会污染全局变量，var声明的变量会直接挂到顶级作用域的属性(比如window)

​	**函数的默认参数，剩余参数和扩展运算符**

​		关于默认参数实际上es5并不是不行，只是不太方便

```js
// es5默认参数
function add(a, b) {
	a = a || 10; // 使用这种方法进行默认参数的传递
	b = b || 20;
	return a + b;
}

// es5关于不定函数参数
// 使用arguments获取实参，这个arguments是类数组，一般可以使用循环遍历这个数组
// 剩余参数是数组而arguments是伪数组，扩展运算符也是... 作用主要是展开数组
// 比如求数组的最大值
Math.max.apply(null, arr) // ES5
Math.max(...arr) // ES6
```

​	**箭头函数**

​		箭头函数本身自己没有this，箭头函数首先找箭头函数定义的作用域，这个定义的作用域的上层就是箭头函数的this

​		箭头函数中的this，始终指向函数声明时所在的作用域下的this值，因为箭头函数也没有自己的作用域链

​		<u>箭头函数没有arguments参数以及不能用来new对象</u>

​	**解构赋值**

​		这个可以混合剩余参数，解构对象的话剩余参数就是对象，解构数组的话剩余参数就是数组

​	**扩展的对象功能**

​		==这可能是今天最大的收获，本身ES6除了提供了同名属性简写以及函数简写之外，还提供了动态的属性名，例子如下==

```js
const name = 'jack';
const obj = {
	name, // 同名属性简写
	sayHi() {...}, // 函数简写
	[name + 'man']: 'Bojack' // 动态属性名，此时的属性名是 jackman
}
// 所以说 [symbol] 当属性名，是这样来用的

// 新方法 Object.is(one, another) 对比两个对象是否完全相等，比 === 更加准确
let result = Object.is(NaN, NaN) // 返回值是 true

// 新方法 Object.assign(target, obj1, obj2, ...) 把后面的所有属性合并到 target，可以浅拷贝
let newObj = Object.assign({}, obj1, obj2) // 返回值就是合并后的对象
```

​	**Symbol**

​		表示独一无二的值的原始数据类型，主要的用途是定义对象的私有变量，比如当属性名使用

​		如果是symbol定义的属性，取值的时候使用中括号比如`obj[s]`，不能使用`.属性名`

​		定义的时候属性名使用中括号包起来`let obj = {[s1]: 'jack'}`

​		symbol定义的属性不能使用传统的方法遍历出来(不属于对象的可枚举属性)

​		实在需要拿到symbol的属性名可以这样使用：

```js
// 第一种方法
let s = Object.getOwnPropertySymbols(obj);
console.log(s); // 返回值是一个由所有symbol属性名组成的数组
// 第二种方法
let m = Reflect.ownKeys(obj);
console.log(m); // 返回值也是一个由所有symbol属性名组成的数组
```

​	**Set 集合数据类型**

​		集合表示一个没有重复值的有序列表，使用`new Set()`声明，默认里面属性有`size`可以查看集合大小

​		部分内置方法

```js
// set是集合的一个实例
set.add(i) 传入的参数i可以是多种类型的值，添加重复元素不算
set.delete(i) 删除集合中的i
set.has(i) 返回布尔值集合中是否有i
set.forEach((val, key) => {...}) // 这个用的很少因为集合中val和key是相等的，意义不大
let set = new Set(oldArr) / let arr = [...set] // 数组和集合的相互转换，可以用来清除重复元素
```

​		set中的对象是不能释放的(设置对象是null后也不能释放)

​		解决方法是`new WeakSet()`这样对象就可以被释放了，但是weakset不能传入非对象参数，并且不能遍历，没有size属性

​	**Map 字典数据类型**

​		map是键值对的有序列表，并且<u>键和值都可以是任意类型</u>

​		map同样有set的方法但是要传入参数键和值，也有WeakMap类型

ES6 p12

**Vue 项目**

​	**设置单页面全屏的方法，main.js或者App.vue外源引入自己的css全局文件，内容如下：**

```css
html, 
body, 
#app { 
  height: 100%; 
  margin: 0; 
  padding: 0;
}
```



**今天的算法题总结 剑指offer22求链表倒数节点 剑指offer10斐波那契数列**

​	今天这俩都挺简单的，重新练习了一下数据结构和动态规划

CSS一生之敌，明天重新思考一下怎么排版布置并且排版的时候可以先把调试控制台关掉





### 10.1

**ES6**

​	**数组的新方法和新属性**

​	常用的新方法并不很多，使用扩展运算符可以简化很多，下列代码展示

```js
// from方法 把伪数组转为真正的数组
// ES5的方法
var arr = [].slice.call(arguments)
// ES6的方法
let arr = Array.from(arguments, callback) // callback可以处理每个元素
let arr2 = [...argument]
// 使用的场景除了arguments这种伪数组还有使用querySelectAll返回值也是链表伪数组

// of方法，把传入的参数混合到一个数组中
let arr = Array.of(arg1, arg2, arg3, ...)

// arr.copyWithin(0, 3) 把指定位置的数组成员复制覆盖到其他位置，这方法很少用，可以查文档

// find和findIndex
arr.find(callback) // 找出第一个符合条件的数组成员
arr.findIndex(callback) // 找出第一个符合条件的数组成员下标

// includes 类似于set中的has方法，indexOf可以替代这个方法
```

​	新增的属性与迭代器有关

```js
// 数组的内部属性
arr.entries() // 下标和值组成的数组的迭代器
arr.keys() // 数组下标的迭代器
arr.values() // 数组值的迭代器
// 这三个返回的都是迭代器，可以使用for of
```

​	**迭代器和生成器**

```js
// 获取迭代器的方法
const it = arr[Symbol.iterator]()
it.next() // 返回值是{value: ..., done: true/false}
// 迭代器是可以快速访问数据的接口，可以在任意位置遍历往后，不需要完全遍历

// 生成器，普遍跟迭代器相关
// 关键字是generator，使用yield关键字可以将函数的状态挂起，可以改变执行流，提供异步编程的方法
function * genFunc() {
	console.log('start');
	let x = yield '2';
	console.log(x);
	let y = yield '3'
}
const gen = genFunc()
// 返回值是一个生成器，一种特殊的迭代器，使用其原型上的next方法可以随着yield走
// 调用next每次返回都是{value: 当前yield的值, done: true/false}
console.log(gen.next())
console.log(gen.next())
// 这个gen.next(arg)也可以传递参数，这个arg会给上一个yield的参数，比如第二次next调用arg会传递给x
// 或者也可以说下一个next的参数是上一个yield的返回值，yield本身是没有返回值的
```

```js
// 生成器的经典使用场景是给不具备iterator属性的对象提供了遍历操作
// 下列代码示例
function * objGen(obj) {
	const props = Object.keys(obj);
	for(const prop of propKeys) {
		yield [prop, obj.prop];
	}
}

const person = {
	name: 'jack',
	age: 18
}
person[Symbol.iterator] = objGen;
// 这样person就是可迭代对象了
```

​	生成器可能还需要再看看

ES6 p16

今天先不推进项目进度，先重新调试练习一下CSS

**CSS重新训练**

​	重视顶线，中线，基线，底线四个文本排线，尤其是有图片的时候，使用vertical-align进行调整

​	line-height如果写的是%则相对的是自身的字体大小(%用来调居中并不合适)

​	margin和padding如果写%默认情况下都是参照父级宽度

​	<u>思路开阔，给一个元素留白，方法有很多种，不只是给其本身添加margin或padding，还可以给其上下的元素添加这两个属性</u>

​	用户状态展示可以参考9.26-10.2的CSS_train

**今天的算法题总结 283-移动零 860-柠檬水找零**

​	移动零这道题使用双下标的做法会更快，过段时间试试

​	柠檬水找零这道题属于很容易知道找一张5一张10比找三张5更加合理，但是如果这两个决定没有合不合理之分呢



### 10.2

**ES6**

​	**生成器的使用**

​	可以通过yield分段和next方法实现函数流程的控制，减少回调函数的使用

​	**Promise**

​		Promise对象相当于一个容器，内部保存一些未来才会结束的异步事件

​		各种异步操作都可以使用同样的方法进行处理，对象的状态不受外界的影响

​		在Promise对象中会存储其状态属性 pending resolved rejected 分别是进行中，成功，失败

​		创建一个Promise实例：

```js
// resolved和rejected本身也是函数
let pro = new Promise((resolved, rejected) => {
	// ...异步操作
	if(success) resolved(res.data)
	else rejected(res.error)
})

pro.then(val => {...}, err => {...}) // 对应resolved和rejected的函数，rejected的函数是可选的

// 为了实现Promise的参数自定，可以封装函数返回Promise对象
function timeOut(time) {
	return new Promise((resolved, rejected) => {
		setTimeout(() => {
			resolved('这就是成功的返回值');
			rejected('这就是失败的返回值');
		}, time)
	})
}
// 使用的时候
timeOut(1000).then(val => {...})
```

​	如果想要连续调用then方法实现链式编程，则必须then的返回值也是Promise对象

​	Promise的一些方法：

```js
// Promise.resolve(obj) 将现有的对象直接转化为Promise对象，仅处理resolved部分
// Promise.reject(obj) 将现有的对象直接转化为Promise对象，仅处理rejected部分

// Promise.all([Promise对象组成的数组]) 并行执行数组中的Promise，返回值也是Promise
// 在数组中Promise都成功的情况下才进入resolve，否则reject

// Promise.race([Promise对象组成的数组]) 可以用来设置请求的超时，请求完成和请求超时哪个先完成Promise就结束
// Promise.finally(callback) 一般放最后，resolved和rejected都会走finally的callback
```

​	**async和await**

​		async函数会返回Promise对象，本质上是生成器的语法糖，await和async配合使用

​		await后面一般是Promise对象，不是的话也会转化成Promise

​		如果async函数中有多个await，则then函数会等待所有的await指令都执行完毕才执行，并且then回调的参数就是async返回值

​		只要有一个await的Promise对象是rejected状态剩下的await都不会再执行

​		==理论上既然async函数的then方法最后会一次等所有await执行完毕，那写await有什么用呢==

​		==await可以强行让异步结束再继续往下，可以很简单控制同步异步同时存在的时候的线性流程，由于同步本来就自上而下，一般情况下await后面是异步操作，否则意义不大==

```js
async function f() {
	// 之前也还可以有很多await
	return await 'hello async'
}
// await后面的值会被自动转化为Promise对象变成async的返回值，可以使用then，catch等Promise的方法
```

​	**class**

​	可以像其他面向对象的语言一样创建对象，更加直观

```js
// 创建类
class Person{
	// 构造器函数会在实例化的时候立刻被调用
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}
	say() {
		console.log(this.name);
		return this.name;
	}
}

// 类的继承，使用extends
class Dog extends Animal {
	constructor(name, age, color) {
		super(name, age);
		this.color = color;
	}
	// 在这里面可以写自己的方法或者重写父类的方法
}
```

ES6视频部分完结

element p41

数据结构 p41

简单更新了一些页面细节，明天完善用户首页内容

**今天的算法题总结 53-最大子数组和119-杨辉三角II**

​	最大子数组和这道题其实挺绕的，过段时间可以再回味看看

​	杨辉三角可以使用动态规划双重循环做，理论上这个解法应该还行

不管怎么说CSS还是写的头大



### 10.3

作为休闲与调剂的学习，今天开始看看微信小程序

微信小程序p6



**今天的算法题总结 169-多数元素 704-二分查找**

​	多数元素想了那么久才想起应该先排序，二分查找最好使用left和right双指针



### 10.4

今天看到一篇知乎文章提问，既然await可以很简单的像同步一样操作异步，为什么不能把所有操作都自动添加await？

​	在单个函数或者代码块的内部，await是严格按自上而下执行，但是如果有其他函数的话，在两个await之间，可能有其他函数语句的执行，在没有共享变量等的时候并不存在什么问题，如果有共享变量，await之间可能真正执行了很多代码，流程不再被控制，所以不行

**数据结构**

**集合**

​	集合比较常见的实现方法是哈希表，这个地方讲的集合跟ES6默认提供的Set区别在于没有顺序，不能通过下标访问(ES6也不行)

p48

**杂项**

​	js的delete关键字可以用来删除对象的属性

​	使用`obj.hasOwnProperty(value)`可以检测obj对象是否有value属性，返回值是布尔值

​	`Object.keys(obj)`返回值是obj的属性组成的数组，同理`Object.values(obj)`获取obj的属性值组成的数组

**今天的算法题总结 344-反转字符串**

​	反转字符串虽然做出来了但是方法并不好，可以试试双指针



### 10.5

​	数据结构p55



### 10.7

这三天相当于休息了，今天最后这点时间看看数据结构，要不然力扣不好刷题，最好明后两天解决哈希表部分

**数据结构：**

​	**哈希表**

​	哈希表通常基于数组实现，相对于数组有如下的优势：

+   非常快速插入删除查找元素，无论多少个元素，插入删除都只需要接近常量的时间
+   相比树结构在速度和编码结构上都有优势

​	哈希表也有一些缺点：

+   哈希表中的数据没有顺序，不能以固定的方式(比如从大到小)遍历其中元素
+   哈希表的key不允许重复，不能放置相同的key存不同的元素

​	哈希表的结构就是数组，但是对下标值有一种变换，变换的操作是哈希函数

​	==核心是让内容和下标值产生一些联系，这个联系是hash函数实现的==

p61



### 10.8

**数据结构**

​	**哈希表**

​	**冲突**：冲突是两个不一样的值计算出的哈希值相等导致的

​	**解决冲突的两种方法**

1.   链地址法：每个数组位置都存储一个数组或者链表，到每个数组或者链表再线性查找
2.   开放地址法：主要工作方式是寻找空白的单元格添加重复的数据

​	**开放地址法又对应了三种方法**

+   线性探测 每次在index++的地方查找合适的位置放置，查找的时候如果查到是空位置就说明哈希表中没有这个元素
+   二次探测 每次跳步使用index+i^2等方法，防止连续的聚集
+   再哈希法 把已经得到的冲突的哈希值再经过另一个哈希函数计算出步长，原始哈希值加上步长才是真实下标

​		再哈希法的函数举例 `stepSize = const - (key % const)` 这个const一般是质数

​	**分析哈希化的效率**

​		装填因子：元素的数量 / 哈希表的长度，开放地址法的装填因子最大为1，而链地址法可以大于1

​		二次探测和再哈希法性能差不多，都比线性探测好，但是使用开放地址法最好装填因子小于1/2

​		链地址法的性能比较平均，不会受装填因子干扰太多，所以使用最多

​		优秀的哈希函数具有两个特点：快速计算和均匀分布

​	**哈希表的扩容**

​		虽然链地址法可以无限延伸，但是到后面会变得越来越臃肿，扩容伴随着整个哈希表的重组

​		一般情况下装填因子大于3/4的时候就进行扩容操作，缩容一般是装填因子小于1/4



​	**树**

​	树的好处是比如排序查找，二叉树可以自带二分查找的能力，查找速度非常快

​	**部分术语**

​		单个节点的度就是子节点的个数，树的度就是所有节点中最大的度

​		对于节点的层次，规定根节点的层次是1，树的深度就是节点的最大层次

​	**树的代码表示方法**

​		由于要兼顾除了二叉树的其他情况，一般采用<u>儿子兄弟表示法，即节点的数据结构分数据，子节点指针，兄弟节点指针三部分</u>

​		这种方法不仅使数组的表示变得简单通用，还实现了所有种类的树都可以转为二叉树

​	p81 二叉树

**综设网站**

​	得琢磨一下怎么搞一个弹出表单

**微信小程序**

​	**全局项目**

​	app.json全局配置文件主要有五个功能：

+   配置页面路径 有点类似于路由的操作
+   配置窗口表现 主要配置的是顶部的导航栏，状态栏等
+   配置导航标签 就是底部可以选的导航标签，实际应该类似于router-view
+   配置网络超时
+   配置debug模式

​	全局的app.wxss适合配置全局通用类名实现代码的复用

​	utils文件夹主要是存放工具类的函数，可以是外源引入的库，如果自己写的就要module.exports

​	**页面项目**

​	页面有五个文件，分别是js，wxml，wxss，wxs，json，其中js和wxml是必须的

​	书p32



**杂记**

​	js的自动判断是否是undefined或者null的机制

```js
// ?. 任意一个环节是undefined或者null都会终止并返回undefined或者null
object?.data?.person?.name 
// ?? 如果没有这个属性就自动选择后面的值
console.log(object.data.person.sex ?? '没这个') // 输出没这个
// ??= 如果这个属性是undefined或者null就设置属性为后面的值
object.person.addr ??= '默认地址'
```

​	解决使用比例布局到最右边不知道宽度高度写多少的问题：使用flex布局，自动填充到最尾部



**今天的算法题总结 21-合并两个有序链表 392-判断子序列**

​	判断子序列这道题可以使用双指针是更好的解法，有机会可以看看

最近略微有一点陷入不知道学什么的状态，倒是因为好多东西不想看，数据结构推进速度比预期快，估计一周内可以看完了

从今天学的来看微信小程序比vue2的网站开发还要简单一些



### 10.9

**数据结构**

​	**二叉树**

​		对于任意非空的二叉树，n0表示叶节点个数，n2表示度为2的非叶节点个数，满足 n0 = n2 + 1

​		完全二叉树是从最左边的叶节点数过去只缺右边的叶节点，完美二叉树就是全满

​		只有完全二叉树适合数组从上到下，从左到右的存储方式

​	**二叉搜索树**

​		二叉搜索树非空时候的三个限制：

+   非空左子树的所有键值小于其根节点的键值
+   非空右子树的所有键值大于其根节点的键值
+   左右子树本身也是二叉搜索树

​		二叉搜索树实现了二分查找的思想，查找的最大次数等于二叉搜索树的最大深度

​		二叉搜索树的三种遍历：

​		先序遍历：访问根节点，先序遍历左子树，先序遍历右子树

​		**二叉搜索树的删除操作 难点**

​		有如下几种情况：

​			1 就是根节点 最简单的情况，直接删除根就行了

​			2 是叶节点 次简单的情况，也是直接删除叶节点即可

​			3 是子节点，但是只有一个子树，直接指针指向下面的后续即可

​			4 是常规的子节点，最复杂

​		操作流程：先找到要删除的节点，然后分类进行删除操作

​		<u>第4种情况：</u>

​			<u>1 删除的是子节点的第一上级，把其下叶节点任意一个换到其位置即可</u>

​			<u>2 删除的子树有一定的层级规模，取左子树最大，右子树最小替换到当前的位置</u>

​		<u>相对一个节点，其左子树最大称为前驱，右子树最小称为后继</u>

​		==对于第四种情况最好先封装一个获取指定节点前驱或者后继的函数，然后在其基础上修改==

​		*实际的操作中，为了逃避删除操作，另一种方法是给每个节点添加 isDeleted 字段，但是并不好*

​	p100 平衡二叉树

**微信小程序**

​	**小程序的生命周期：**

​		小程序的生命周期分为<u>总体应用和单个页面的</u>

​			总体应用：onLaunch 小程序注册 -> onShow 小程序唤起前台展示 -> onHide 小程序前台隐藏 (-> onError 小程序出错)

​			单个页面：onLoad 页面注册 -> onShow 页面唤起前台展示 -> onReady 初次渲染完成 -> onHide 页面前台隐藏-> onUnload销毁

​	这些生命周期都对应着生命周期函数，直接在Page({...})函数中注册

​	onShow只是页面视图展示，页面本身还没完全准备妥当

​	具体的一些细节可以参见 https://www.cnblogs.com/bingcola/p/16499162.html

​	**小程序改变数据：**

​		==不能直接修改this.属性名==

​		改变数据使用setData函数，具体的使用方法如下

```js
// 比如一个view绑定了changeText函数，那么在Page({...})里面这么写
Page({
	data: {
		text: 'not yet'
	}
	changeText() {
		this.setData({
			text: 'change complete'
		})
	}
})
// setData的key属性可以复合，比如 arr[0].num: 20
```

​	**小程序的数据绑定**

​		小程序的数据绑定都使用`{{}}`无论是在wxml的innerHTML还是标签的内部属性

​		所有数据都使用`{{}}`可以省去vue的各种符号比如`: @`等

​	**小程序的条件渲染和列表渲染**

​		`wx-if`和`v-if`基本效果相同，如果wx-if要管理多个标签可以使用`block`标签框起来然后在block上添加wx-if

​		`wx-for`和`v-for`也基本相同，同样可以使用block框起来，比vue要有一个外层容器更加自由

​		<u>但是很离谱的是</u>`wx:key`<u>又是不写插值表达式里面直接写个字符串</u> `wx:key="someKey"` someKey就是wx-for的数组中的属性

​	**小程序的定义和使用模板**

​		这个模板有点类似于vue的conponent标签

```html
// 定义模板
<template name="myTemplate">
	<view>
		<text>{{index}} : {{msg}}</text>
    <text>Time : {{time}}</text>
	</view>
</template>

// 使用模板
<template is="myTemplate" data="itemsForTemplate"></template>
Page({
	data: {
		index: 0,
		msg: 'this is a message',
		time: '2022-10-9'
	}
})
```

​	**小程序WXML的引用**

​		`import`和`include`两种引用方式，都是使用标签的形式，添加src属性

​		import只引用template，为使用模板创建， 而include相当于直接将没有template的部分粘贴到include这个标签的位置

​	**WXS脚本语言**

​		就是直接使用wxs标签代替了原来有的script标签，在WXML文件的内部添加js代码

​	书p43 模块化

**杂记**

​	sort方法有些时候遇到稍大或者负数情况出错，原因是默认sort按照unicode排序，解决方法是传入比较函数

```js
arr.sort(function(a, b) {
  return a - b; // 升序
})
```

​	从这个片面有点看出了TypeScript限制类型不容易类型混乱的优势



**今天的算法题总结 876-链表的中间节点 1013-将数组分为和相等的三个部分**

​	数组链表类的题目都可以考虑快慢指针

等把树部分看完了开始看力扣的树部分题目



### 10.10

失眠 2:06

找了个nodejs的课看着玩

**Nodejs**

​	**Nodejs的底层**

​		**用户js代码 -> native modules 还是js -> builtin modules 胶水层，主要是C++ -> V8 LIbuv 第三方模块 底层**

​	**Reactor模式处理IO**

​		类似于回调实现单线程实现多线程的任务，单线程也导致Nodejs更适合IO密集型高并发请求

​		最好的IO应该是无需主动判断的非阻塞IO，通过回调函数通知而非一直轮询确认是否结束

​		IO的处理就是交给了Libuv，其实现了单线程异步IO

​		同步的代码执行完毕，异步代码就由Libuv处理

​	**事件驱动架构**

​		本质特点就是发布者广播消息，订阅者监听订阅的消息

​		Nodejs中使用on订阅事件，使用emit触发事件，使用这两个函数需要导入内置的events模块

​	**单线程**

​		<u>Nodejs通过单线程实现高并发：异步非阻塞IO配合事件回调通知</u>

​		单线程是指主线程是单线程，因为V8架构是只有一个主线程，但是Libuv库中有线程池，默认情况四个线程

​		单线程必须等待同步任务按顺序执行，所以很不适合CPU密集任务

上床 3:03

**继续Nodejs**

​	**Nodejs的全局对象**

​		在Nodejs中全局对象是`global`，根本作用就是作为全局变量的宿主

​		<u>默认情况下this和global不是一个东西，跟模块化实现有关</u>

​		==Nodejs常见全局变量==

​			`__filename` 正在执行脚本的绝对路径

​			`__dirname` 正在执行脚本的目录

​			`timer类函数` 执行顺序与事件循环的关系

​			`process` 提供与当前进程互动的接口

​			`require` 导入其他模块使用

​			`module export` 处理模块的导入导出

​	p10

**数据结构**

​	**平衡树**

​		二叉树插入数据的时候如果是有序的递增递减序列会导致树的深度非常大，不平衡，自然也就没有高效率

​		这种树称为非平衡树，极端情况下就是一个链表

​		好的二叉树应该是均匀分布的

​		平衡树的种类：AVL树和红黑树，其中AVL树性能不如红黑树

​	**红黑树 重难点**

​		**红黑树的特性：**

​			红黑树除了二叉搜索树的规则还有五个特性：<u>叶节点只可能是NIL空节点</u>

​				节点是红色或者黑色

​				根节点是黑色

​				每个叶节点都是黑色空节点(把所有节点都使用NIL空节点补齐)

​				每个红色节点的两个子节点都是黑色(从每个叶节点到根的所有路径上不能有两个连续的红色节点)

​				从任一节点到其所有叶节点的所有路径包含相同数目的黑色节点

​			这些规则保证了红黑树的关键特性：<u>从根到叶的最长路径不会超过最短路径的两倍</u>

​			最短路径全是黑节点，最长红黑交替，而所有路径的黑色节点数目相同，所以不会超过两倍

​		**红黑树的变色：**

​			在插入新节点后树可能不再平衡，通过换色 - 左旋转 - 右旋转的变换使树保持平衡

​			变色：<u>一般情况下规定新插入的节点是红色，插入红色有概率可以直接插入，好调整</u>

​		**红黑树的旋转**

​			左右旋转这两种变换有点复杂，旋转后不影响二叉树的结论

​		**红黑树的插入操作**

​			插入操作首先是最基础的二叉搜索树插入，然后再下分情况：

​			1 插入空树，新节点N位于树的根，没有父节点，直接插入后红转黑即可

​			2 新节点的父节点是黑色，因为新节点还是红色，只需要设置新节点的两个NIL空节点即可，没有问题

​			3 新节点的父节点是红色，且父节点的兄弟节点是红节点，祖节点是黑节点

​				处理方法：父兄转黑节点，祖转红节点，接下来往上都是递归解决方案

​			4 新节点是左儿子，新节点的父节点是红色，且父节点的兄弟节点是黑节点，祖节点是黑节点

​				处理方法：父转黑节点，祖转红节点，父节点和祖节点进行右旋转

​			5 新节点是右儿子，新节点的父节点是红色，且父节点的兄弟节点是黑节点，祖节点是黑节点

​				处理方法：父节点和祖节点进行左旋转，旋转后把父节点看作插入的新节点，变成了情况4

​		红黑树的删除操作更加复杂，以及代码之后有时间看看

​	p116 图

**综设网站**

​	vue的事件绑定的函数要写到methods节点里面，不像小程序是平级直接写在外面

​	使用component的时候，is属性不是字符串，而是组件的名字属性

**杂记**

​	原来要支持typescript只需要安装一个typescript的包而不是tsc，tsc已经过时废弃

​	npm的初始化命令是`npm init -y`

​	如果在ts文件中导入json需要在tsconfig.json中添加`"resolveJsonModule": true`



**今天的算法题总结 349-两个数组的交集 94-二叉树的中序遍历**

​	两个数组的交集这道题不动脑子的做法是两个数组都变成set然后set取交集

​	也可以使用以前经常用的longer和shorter，这样速度更快，排序对于这道题不一定是很好的解法

​	递归和迭代的区别：递归就是自己调用自己，迭代是用旧值推新值的过程(动态规划就是一种)

​	如果迭代实现中序遍历需要使用栈结构，实际上递归也间接实现了栈的使用

​	迭代的写法相对复杂，效率两者相当

经典焦虑



### 10.11

今天早上起来没有那么焦虑了

**Nodejs**

​	**process全局变量**

​		主要两个作用：获取进程信息，执行进程操作

```js
// 资源：cpu，内存
process.memoryUsage() // 返回内存的使用情况
process.cpuUsage() // 返回cpu的使用情况
// 运行环境：运行目录，node环境，cpu架构，用户环境，系统平台
process.cwd() // 当前代码的工作目录
process.version // 当前node版本
process.versions // 当前node，v8，libuv等版本
process.arch // 当前的cpu架构
process.env // 环境类
process.platform // 系统平台
// 运行状态 启动参数，PID，运行时间
process.argv // 启动时候传入的参数，是一个数组
process.pid // 进程号
process.uptime() // 运行时间，单位是秒
// 事件
process.on('exit', (code) => {
	... // 当前任务退出时会执行回调，参数是退出码，exit回调只能写同步代码
	// 另外还有其他事件类型比如beforeExit
})
// 标准输入输出，错误，跟文件的读写有一定的关系
process.stdout.write(data)
fs.createReadStream('文件路径').pipe(process.stdout)
```

​	p12

**综设网站**

​	感觉后续的ajax数据导入会是个大麻烦

​	综设这个网站其实已经搭了很大一部分。后续很多问题都会集中到前后端交互

​	*目前问题有查询会议面板中会议时间和会议室选择长度并不相等*

**数据结构**

​	**图**

​		图的重点是顶点和边，图结构的特点就是一组顶点一组边，边可以是有向的也可以是无向的

顶点的度就是其相连的边的数目，边可以有方向，权重类的属性

​		**图的表示**

​			顶点可以封装成节点，然后所有节点存储在数组或者链表中

​			主要问题是边的表示

​			<u>边使用邻接矩阵表示，实际上就是二维数组的表示方法，需要让顶点和数组的下标有对应关系</u>

​			邻接矩阵可以很好的实现有向图和权重图，但如果是一个稀疏图，邻接矩阵会有大量的0，并不合适

​	p122

**vue2转vue3**

​	**组合式api 基本数据类型和对象类型的属性的新的定义方式 vue3.2及以上**

​	属性和方法不一定需要分开写在data和methods，而且methods里面用属性反而不需要this

​	如果是基础数据类型要使用`refSomething.value`，不能直接调用

​	没有this的原因很大程度上也是因为vue3没有`new Vue().mount('render: h => h(App)')`这个过程而是`createApp(App)`

```vue
<script setup>
import { reactive, ref } from 'vue'
// 基本数据类型使用ref
const msg = ref('我是message')
const update = () => { msg.value = '我是修改后的msg' }
// 对象数据类型使用reactive
const objMsg = reactive({
	msg: '我是对象msg'
})
const updateObjMsg = () => {
	objMsg.msg = '我是修改的对象msg'
}
</script>
```

​	**vue3路由配置和使用**

​		路由创建和配置部分之前已经写过，直接搜索vue3路由创建即可

​		vue3路由使用

```js
// 需要使用路由的文件中
import { useRoute, useRouter} from 'vue-router'
const router = useRouter()
const route = useRoute()
// 路由路径
console.log(route.path)
// 路由跳转
router.push('home')
```

​	p4

**今天的算法题总结 35-搜索插入位置 104-二叉树的最大深度**

​	搜索插入位置这道题挺好的，复盘了二分查找的代码

​	二叉树的最大深度这道题可以引申出DFS和BFS，等把图部分看完了研究一下

离谱的是竟然感觉网站快要搭建完毕了，这个网站做完之后应该ajax部分也很熟悉了，然后开始ts和vue3

明天看看代理和反射是什么东西



### 10.12

**vue2转vue3**

​	**定义全局变量和方法**

​		全局变量和方法都是直接写到main.js里面

​		vue2 直接添加到vue原型 `Vue.prototype.Utils = Utils`Utils就是包括全局变量和方法的对象，使用`this.Utils.isEmpty()`

​		vue3 添加到app的属性 `app.config.globalProperties.Utils = Utils`，使用如下

```js
import { getCurrentInstance } from 'vue'
const { proxy } = getCurrentInstance()
proxy.Utils.isEmpty();
```

​	**侦听器watch的变化**

​		直接看vue3的使用，监听多个就多写几个watch方法

```js
import {ref, watch} from 'vue'
const msg = ref('123456')
watch(
	msg,
	(newValue, oldValue) => {
		...
	},
	{immediate: true, deep: true}
)
```

​	**父子组件调用 逻辑上这两个区别不大，写法有区别**

​		**vue2**

​			1 父组件向子组件传递参数使用prop属性

​			2 父组件调用子组件方法使用ref

```js
// 父组件中
<son ref="sonRef"></son>
// 调用子组件的方法，parentOpSon是子组件的方法
this.$refs.sonRef.parentOpSon('这个是父组件的参数')
```

​			3 子组件调用父组件方法，其实子组件无论是向父组件传递参数还是调用父组件方法都是子触发事件父处理事件

```js
// 子组件中
methods: {
	sonOpParent() {
		this.$emit('opParent', '我是子组件给的参数')
	}
}
// 父组件中
<son @opParent="parentMethod"></son>
methods: {
	parentMethod(e) {
		...
	}
}
```

​	**vue3**

​		1 父组件向子组件传递参数 主要就是定义props属性和vue2不同

```js
// 子组件
import { ref, defineProps } from 'vue'
const props = defineProps({
	msg: {
		type: String,
		default: ''
	}
})

// 父组件
<son :msg="'父组件给子组件传递参数'"></son>
```

​		2 父组件调用子组件的方法

​			子组件暴露自身方法，父组件创建子组件标签同名ref，使用ref.xxx调用子组件的方法

```js
// 子组件
import { ref, defineProps, defineExpose}
const parentOpSon = (parentMsg) => {
	...
}
// 子组件要暴露方法
defineExpose({
	parentOpSon
})

// 父组件
<son ref="sonRef"></son>

// 手动创建子组件的ref
const sonRef = ref();
const opSon = () => {
	sonRef.value.
}
```

​		3 子组件调用父组件方法

```js
// 子组件
const emit = defineEmits()
const opParent = () => {
	emit('opParent', '子组件传递给父组件的参数')
}

// 父组件
<son @opParent='parentMethod'></son>
const parentMethod = (e) => {
	...
}
```

​	**生命周期函数**

​		vue2省略

​		vue3

​			所有方法名前面添加了on比如`onMounted`

​			取消了beforeCreate和created，直接写的函数比如自己写的init函数就会在这个时间段调用，或者使用`setup()`代替

​			destroyed换成了onUnmounted，beforeDestroyed换成了onBeforeUnmount，效果相同

```js
const init = () => {
	console.log('我在beforeMount之前')
}
init()
onBeforeMount() {
	...
}
```

​	最后一部分vuex状态管理，过段时间看

**TypeScript**

​	ts的安装配置部分省略

​	**ts的类型限制**

​		ts可以限制类型，如果声明的时候不写，默认会等于赋值类型的变量的数据类型

​		<u>这些类型都要小写</u>

​		ts也不允许函数多传参数

```ts
let a: number = 100 // 这种写法实际上不常用
// 限制函数传参以及返回值是最有用的
function add(a: number, b: number): number {
	return a + b;
}

let b: 12; // 直接使用字面量限制类型，但是效果如同常量，所以也不是这么用的
// 可以实现简单的枚举类型，正式称为联合类型
let gender: 'male' | 'female';
// 不写就是any，跟js一样不推荐随便使用，any可以赋值给其他值导致其他值类型检查也消失
let some;
// 如果不清楚变量的类型可以这么写，unknown不能随便传值，解决上面的问题
// 实际上unknown类型就是类型安全的any，非要赋值的话使用typeof进行类型检查后可以
let something: unknown;

// 类型断言，手动告诉编译器实际类型，防止编译器报错，以下两种写法都行
s = e as string;
s = <string>e;

// void和never，主要是用来限制函数的返回值
function fn(): void {
	// 不写 / return / return null / return undefined
}
// never连undefined都不返回，适用于报错类函数，用的少
function fn2(): never {
	throw new Error('error');
}

// object，限制是一个对象，但是使用极少，因为对象种类太多，等于不限制
// 限制的应该不是是不是对象而是对象的属性结构类型，加?的是可选属性
let jack: {name: string, age: number, gender?: 'male' | 'female'};
// 如果限制是要有这个属性，其他属性不管
let mary: {name: string, [propName: string]: any};

// 限制函数类型
let func: (a: number, b: number) => number;
func = (a: number, b: number): number => a + b; // 这个函数必须匹配func的类型

// 限制数组类型
let arr: string[] // 限制这个是字符串类型的数组
let arr2: Array<number> // 效果相同

// 限制元组类型，本质就是长度固定的数组
let myTuple: [string, number];

// 限制枚举类型
// 先定义枚举类型
enum Gender {
	male: 0,
	female: 1
}
let gen: Gender;
gen = Gender.male;

// 给类型起别名，太长了不好写可以自己取名字
type myType = number | string | boolean;
let mytype: myType;
```

​	**编译选项**

​		自动编译修改后的文件

```
tsc xxx.ts -w // 表示watch侦听，自动监视变化就重新编译
```

​		想要一次性编译所有文件等自动化功能需要配置`tsconfig.json`文件，在终端输入`tsc --init`即可

```
// 完成上述操作后
tsc 编译所有文件
tsc -w 监视模式编译所有文件
```

​	**tsconfig.json的配置选项**

```json
{
  // ** 表示任意目录，* 表示任意文件
  // 要编译的文件目录
	"include": [
    "./src/**/*"
  ],
  // 不编译的文件目录 
  "exclude": [
    // 默认值是 node_modules, bower_components, jspm_packages
    "./src/no/**/*"
  ],
  "extends": "引入其他json的路径",
  "files": [
    "core.ts",
    "main.ts"
    // 直接列出所有要编译的文件的名字
  ],
  // 编译器的配置选项
  "compilerOptions": {
    "target": "es6", //指定编译出来的ES版本，默认情况转ES5
    "module": "es6", //指定模块化的规范
    "lib": [], //使用什么库，但是这个库如果是浏览器中一般不手动操作，默认就是浏览器环境
    "outDir": "./dist", //编译后文件所在目录
    "outFile": "./dist/app.js", //把代码合并成为一个文件，实现必须module属性是amd或system
    "allowJs": false, // 是否对js文件进行编译
    "checkJs": false, // 是否用ts规范检测js的语法
    "removeComments": true, //是否编译后移除注释
    "noEmit": false, //默认false，不生成默认的编译产生文件，所以默认会产生文件
    "noEmitOnError": false, //有错误的时候就不生成编译后的文件
    "alwaysStrict": false, //编译后的文件是否开启严格模式
    "noImplicitAny": false, //是否不允许隐式的any类型
    "noImplicitThis": false, //是否不允许不明确的this调用
    "strictNullHChecks": false, //是否严格检查空值，如果配置了会大幅使用?.等运算符，
    "strict": false, // 所有严格检查的总开关
  }
}
```

​	p10

**综设网站**

​	已经第二次掉坑了，输入框不设置v-model会不能输入，至少对于elementui如此

​	解决了对齐不对的问题，原因是有两层 el-form-item 重叠，margin也重复了

​	前端部分基本搭建完毕，明天开始使用express进行测试



**今天的算法题总结 191-位1的个数 100-相同的树**

​	位1的个数这道题可以用与的方法也可以直接转化成字符串处理

​	相同的树这道题挺练手适合双树遍历，并且练习了递归的额外退出条件

网站这周之前应该可以全部做完了，心情大好



### 10.13

**综设网站**

​	后端的get部分弄得差不多，假数据从前端写到了后端，后续数据弄到数据库去，得复盘一下axios的使用

​	promise也有一些遗忘，需要重新学习

​	发现有更合理的日期时间选择框，修改

**今天的算法题总结 226-反转二叉树 160-相交链表**

​	做久了算法题还挺有成就感，二叉树系列的题目大部分都可以递归变换遍历函数处理

​	相交链表这题做出来了但是方法并不好，另一种好点的是用双指针，让长表和短表对齐再比较，可以节省空间

今天整了一天综设网站了，后端和数据库都有了简单实践



### 10.14

失眠 1:10

**综设网站**

​	考虑失策，前端表单收集的时间数据应该和数据库的时间统一，要不然每次两边转换相当麻烦

​	对于上述的问题修改一下数据库，根据问题已经把数据库改好了

​	新问题，选14号会返回的是13号，每次都差一点，初步猜测时区不是中国

​	原因就是因为不是中国时区，用一些小技巧已经搞定

​	明天白天的任务是把用户表弄出来，然后添加判定添加会议是否合法的判断，如果学后端需要精进sql

上床 2:27

**综设网站**

​	不知道为什么发送请求服务器使用req.query接收不到参数

​	上面的问题解决了，是因为webpack自己没有刷新的原因，下次遇到这种不该有的问题可以刷新一下脚手架

​	<u>添加了async的生命周期函数，不一定会按照顺序执行，比如created添加了async，可能mounted先执行</u>

​	下一步给修改会议添加删除功能，并且实现数据库的update，然后新建用户表

**今天的算法题总结 459-重复的子字符串 257-二叉树的所有路径**

​	重复的子字符串可以考虑脑筋急转弯做法，二叉树的所有路径可以考虑BFS和DFS

​	明天还是看看数据结构

综设网站还有一些欠缺，还得大概两天吧



### 10.15

**数据结构**

​	**图**

​		除了邻接矩阵的表示方法，还有另一种是邻接表，邻接表本身可以使用数组，链表，哈希表等多种方式存储

​		邻接矩阵在有向图中计算出度(指向其他节点的数量)比较简单，入度比较困难

​		**BFS(基于队列)DFS(基于栈或者使用递归)**

​		为了记录顶点是否被访问过，使用三种颜色表示顶点状态，白色表示未访问，灰色表示访问过但是未探索，黑色表示访问且全探索

​	p128

**今天的算法题总结 54-螺旋矩阵 112-路径总和**

​	螺旋矩阵意外是个很好的方案，路径总和是新的二叉树递归题目

**综设网站**

​	由于数据库的触发器不太会使用，会议能否添加的判断加到后端执行

​	判断会议能否添加应该写到后端而不是前端，写错位置了，迁移一下

​	主要的功能已经基本实现了，还差一个用户表，可能完善的话还需要注册表，另外首页默认展示的会议最好有时间排序

​	做这个项目明显感觉数据库的操作还是比较重要的



### 10.16

**TypeScript**

​	webpack配置兼容IE可以添加`environment: { arrowFunction: false }`关闭箭头函数

​	**类**

​	在class里面定义属性的时候前面添加`static`可以定义为挂载到类上的静态属性

​	定义的属性前面加上`readonly`可以限制为只读属性

​	方法跟属性是一样的，也可以添加static

**代理和反射**

```js
// target是创建代理的目标对象，handler是目标代理配置对象
// handler是一个对象，里面可以返回很多事件方法，也被称为捕获器
// 不同的捕获器可以在对应时间拦截对对象的操作，并修改对应的行为
const proxy = new Proxy(target, handler)

// 由于捕获器种类非常多，有13种，如果每次都从头开始配置非常麻烦，js提供了反射Reflect
// Reflect提供了已支持的所有的捕获器方法，方法的内容就是默认的行为
// 所以不需要配置的情况下handler可以简写
handler: {
	get: Reflect.get
}
```



**Vue3和Vite**

​	**组合式API**

​	vue2的旧模式是选项式API，比如data，methods，props等，选项的属性会暴露到函数内部的this

​	组合式API侧重函数式的编程，组件的属性和方法可以直接写到一起

​	**响应式基础**

​		**reactive**

​		使用`reactive()`可以创建响应式的对象，本质是proxy，使用响应式的状态需要在`setup`中定义并返回，把响应式对象暴露

​		setup除了暴露使用`ref()`以及`reactive()`的响应式属性，还有响应式的函数，响应式的函数一般用于事件监听器

​		<u>如果是单文件组件，可以使用`<script setup></script>`这个语法糖</u>

​		响应式的状态更新不是完全同步的，如果把稳可以使用`nextTick(callback)`

​		响应式的状态默认是深层的，意味着对象内部属性的修改也会被响应到，<u>但是只能修改代理而不是原生数据</u>

​		<u>响应式对象的代理是不可以更换的，如果更换会导致响应性丢失</u>

​		**ref**

​		ref产生的原因是js没有对所有类型的数据都提供了引用的机制，简单数据类型使用ref.value就是其响应性数据

​		ref 被传递给函数或是从一般对象上被解构时，不会丢失响应性

​		ref在向上渲染到模板html时可以省略.value，这个过程会自动解包

​		**计算属性computed**

​		计算属性只针对响应式依赖改变才会跟着重新计算，意味着属性一定要是reactive或者ref里面的

​		**TodoList Demo**

​		所有的属性都可以装载到setup函数里面的state对象，然后方法调用state的数据，最后返回state以及新添加的函数

目前状态以一种简单的方式理解Vue3就是可以使用setup来定义属性和方法，同类型可以写在一起，维护性更好

使用setup语法糖的话，顶层的变量函数以及import进来的都可以直接在模板中使用，不需要return或者methods声明之类



**今天的算法题总结 101-对称二叉树 14-最长公共前缀**

​	对称二叉树这道题是非常有意思的二叉树递归题目，双变量递归，挺值得

​	最长公共前缀这个是属于非遍历不可的，尽量设置良好的退出条件就行



### 10.17

**Promise**

​	整个在Promise的代码可以同步执行，但是仅限于同步代码，在new Promise的时候被执行

​	Promise对象内部两个状态fulfilled和rejected可以供后续的then等方法判定

​	.catch方法本质上就是.then(null, reject => {...})  .finally方法类似于.then(f, f)不管Promise结果是什么都会执行

​	.finally并不一定放到最后执行，可以用于各种清除，但是.finally函数里面写返回值没什么意义

​	Promise链能执行的核心原因是.then方法返回的还是一个Promise，then函数中手动返回Promise可以构建异步行为链

​	为了能实现后续的操作(如果有)，异步行为应该都返回Promise

​	.catch可以有很多个，组成catch链，上一个处理不了的可以throw到下一个catch执行

**TypeScript**

​	也提供了抽象类，前面加个abstract即可，不能实例化，只能被继承，也可以写抽象方法

​	接口用于定义类的结构，类似于type类型，可以通过直接指定接口限定数据

​	接口中的所有属性都不能有真实的属性值，包括接口中的方法，所有方法都是抽象方法

​	比起抽象类就是用于继承，接口就是用于实现，接口本身就是对类的限制，提供规范

​	属性的默认值就是public，另外还有private和protected

​	get和set这样写，使用的时候也会自动操作

```js
get name() {
	return this._name
}

set name(newName) {
	return this._name = newName
}

// 使用，自动调用get和set，注意这个地方真实的属性名是前面带下划线的
person.name = 'zs'
let name = person.name
```

​	构造函数可以简写

```js
class some {
	constructor(public name: string, public age: number)
  // 这样的话属性也可以不用再声明
}
```

​	**泛型**

```
// 一般泛型的字母选用T-type K-key V-value E-enum
function func<T>(a: T): T {
	return a
}

// 泛型函数可以直接调用也可以指定泛型
let a: number = 0
let some1 = fn(a)
let some2 = fn<string>(a)

// 可以通过接口指定泛型的种类
Interface Inter {
	length: number
}
// 这个泛型里面至少要有length这个属性
function func2<T extends Inter>(a: T): T {
	return a.length
}
```

​	p22 剩下的部分是一个案例暂时不看，跟java差不多



**Vue3**

​	这段时间以来最硬的骨头，找了个新的项目演示视频，跟着做一下vue3项目

​	vue3的fragment特性可以支持在模板里面有多个根节点

​	vite配置的项目，入口文件是index.html而不是webpack的main.js

​	**ref全家桶**

​	除了最常见的`ref reactive`

​	另外本质上从源码来看ref如果不是基础数据类型，也会最终调用到reactive

```js
isRef() // 判断是否是ref对象，vue源码中使用比较多
shallowRef() // 浅层次的ref响应，不响应内部深层的内容
// 一般情况下为了不影响修改到shallowRef的深层，ref和shallowRef不一起写
triggerRef() // 触发强制更新，普通的ref()会自动调用这个函数
customRef() // 比较复杂，可以手动配置收集依赖和触发响应

toRef(target, attr) // 把某个数据转成ref类的，抓响应式对象的属性，只能修改响应式对象的值，非响应式视图不会改变
toRefs(target) // 把响应式对象的所有属性抓出来改成ref，可以使用解构赋值拿取
toRaw() // 把一个响应式的对象重新变成普通对象
```

​	p10



**Electron**

​	在electron的体系中，main.js控制主进程，主进程是运行在nodejs的实例，main.js负责生命周期，原生窗口展示，管理渲染进程等

​	其他的js文件可以是主进程导入的渲染器进程，负责展示内容，渲染进程都跑在网页中而不是nodejs

​	使用preload.js可以给渲染器挂载一些全局的属性或者方法





**今天的算法题总结 414-第三大的数 507-完美数**

​	今天这两道题都很简单

挺想学一下electron，想到快完工的综设网站还有点头大，明天有闲处理一下



### 10.18

失眠成为常态 1:25 看了点electron，写到下面去 上床 2:03

**Electron**

​	preload.js的作用是将不同类型的进程桥接在一起，它既可以操作dom也可以有一部分nodejs的系统api以及electron api

​	electron给每个打开的BrowserWindow生成一个独立的渲染器进程，渲染器无权直接访问require以及nodejs的api

​	官方文档对于preload.js的描述

​		预加载（preload）脚本包含了那些执行于渲染器进程中，且先于网页内容开始加载的代码 。 这些脚本虽运行于渲染器的环境中，却因能访问 Node.js API 而拥有了更多的权限

​	预加载脚本与渲染器共享一个window对象，可以使用contentBridge传递数据和方法，不能直接window.some = some因为上下文隔离

​	**进程间通信**

​		**渲染器进程到主进程 单向**

​		渲染器使用`ipcRenderer.send`发送消息(渲染器间接使用，这个函数变体在preload暴露出来)，主进程使用`ipcMain.on`接受消息

​		常见的使用场景是web内容调用主进程API

```js
// preload.js 省略引入过程
contentBridge.exposeInMainWorld('electronAPI', {
	setTitle: (title) => ipcRenderer.send('set-title', title)
})

// main.js event是一个IpcMainEvent结构，可以获取比如哪个渲染进程发来的信息
function handleSetTitle(event, title) {
	const webContents = event.sender
	const win = BrowserWindow.fromWebContents(webContents)
	win.setTitle(title)
}

ipcMain.on('set-title', handleSetTitle)

// renderer.js中只需要将set-title当成一种事件处理即可
```

​		**渲染器进程到主进程 双向**

​		渲染器使用`ipcRenderer.invoke`，主进程使用`ipcMain.handle`

​		`ipcRenderer.invoke`的返回值是一个Promise，因为要等待主进程的响应

​		常见的使用场景是渲染器进程调用主进程API并等待结果

```js
// preload.js 省略引入过程
contextBridge.exposeInMainWorld('electronAPI', {
	openFile: () => ipcRenderer.invoke('dialog:openFile')
})

// main.js
async function handleOpenFile() {
	const { canceled, filePaths } = await dialog.showOpenDialog()
  if (canceled) {
    return
  } else {
    return filePaths[0]
  }
}
ipcMain.on('dialog:openFile', handleOpenFile())

// renderer.js
btn.addEventListener('click', async () => {
  const filePath = await window.electronAPI.openFile()
  filePathElement.innerText = filePath
})
```

​		**主进程到渲染器进程**

​		主进程发送到渲染器进程的时候要指定是哪个渲染器接收消息，通过`WebContents`实例发送到渲染器进程，其内部有一个`send`方法

​		使用场景比如说应用上层的菜单等操作网页

```js
// main.js 使用webContents.send('事件名', 参数)发起事件
function createWindow() {
	const mainWindow = new BrowserWindow({
    webPreferences: {
      preload: path.join(__dirname, 'preload.js')
    }
  })

  const menu = Menu.buildFromTemplate([
    {
    	// 一级菜单
      label: app.name,
      // 子菜单
      submenu: [
        {
          click: () => mainWindow.webContents.send('update-counter', 1),
          label: 'Increment',
        },
        {
          click: () => mainWindow.webContents.send('update-counter', -1),
          label: 'Decrement',
        }
      ]
    }
  ])

  Menu.setApplicationMenu(menu)
  mainWindow.loadFile('index.html')
}

// preload.js 给渲染器函数注册限制过功能的ipcRenderer.on('监听的事件名', 操作或者其他)
// 这个地方写回调是可以方便渲染器函数自己操作，本质上也是有限制的暴露了ipcRenderer.on方法
contextBridge.exposeInMainWorld('electronAPI', {
	handleCounter: (callback) => ipcRenderer.on('update-counter', callback)
})

// renderer.js 通过window.electronAPI.handleCounter()传入自己的callback处理函数
// 这个函数隐形内部调用ipcRenderer.on监听了main.js发送过来的数据
const counter = document.getElementById('counter')

window.electronAPI.handleCounter((event, value) => {
  const oldValue = Number(counter.innerText)
  const newValue = oldValue + value
  counter.innerText = newValue
  // 如果要继续向main.js返回一些信息，使用以下代码，然后main.js监听即可
  event.sender.send('counter-value', newValue)
})
```

​		**渲染器到渲染器 无直接的方法，可以使用主进程代理**



**今天的算法题总结 342-4的幂 700-二叉搜索树中的搜索**

​	数字类型的题目可以考虑二进制的规律

​	留意二叉树题目的广度深度搜索

设想能不能用electron写一个可以自动检测复制粘贴然后查字典的呢



### 10.19

昨天想的这个electron应用的主要问题是我不知道该怎么截取鼠标选中事件，要不然就必须到剪切板去查找，等等再研究

**Vue3**

​	**计算属性computed**

```js
let total = ref(0)
total = computed<number>(() => {
	return ... // 算出来是total的值就行
})
```

​	**侦听器watch**

```js
// 侦听器可以一个函数侦听多个值
watch([message1, message2], (newVal, oldVal) => {
	// newVal和oldVal也会相应变成数组的形式
}, {deep: true})
// 如果监听的是reactive写不写deep效果相同
```

​	**高级侦听器watchEffect**

```js
// 非惰性，自动调用，如果有callback会先执行callback
let message = 'jack'
let stop = watchEffect((可选的callback) => {
	console.log(message) // message一改变就会被打印出来
}, {配置选项，可以上网查})
// 调用stop可以停止侦听
stop()
```

​	杂：vite创建的项目使用less只需要npm i less -D即可，less-loader是webpack的配置

​	**熟悉的组件传参**

​		父组件向子组件传参，setup语法糖的情况下不需要引入`defineProps`

​		另外在配合ts的情况下子组件可以这样设定props

```js
// 子组件中
type Prop = {
	title: string,
	data: number[]
}
defineProps<Prop>()
```

​		子组件向父组件传参，同样setup语法糖情况下不需要引入`defineEmits`

```js
// 子组件
const emit = defineEmits(['自定义的事件名']) // 获得的emit就是一个函数
emit('自定义的事件名', value) // 用这个函数触发事件
// 父组件
<Menu @自定义的事件名="func"></Menu>

// 但是直接这样使用拿到的是响应式数据，需要转化父组件才能拿到真实的值
// 所以子组件还要添加
defineExpose({
  title,
  list
})

// 对于整个props属性都有很大的变化，属性名和类型都已经由ts类型指定提供，如果还需要提供默认值需要这样写(ts写法)
withDefaults(defineProps<Props>(), {
  title: '我是默认值',
  list: () => [1, 2, 3] //为了防止引用数据类型直接引用，通过返回对象的方式
})
```

​	p16



**Electron**

​	已经通过main.js读取到了剪切板的内容，接下来是寻找一个合适的可以查单词的网络接口，调用

​	网络接口已经注册了，现在只需要调整系统托盘的功能以及修改更加自动化，比如自动侦听剪切板等

​	最基础的功能已经完成



**综设账本展示网页**

​	vite新建vue项目不是用之前的方式，`npm init vite-app 项目名`这个智能程度不够并且vue3的版本不新

​	用这个`npm create vite@latest`



**今天的算法题总结 0103面试题-URL化 54剑指offer-二叉搜索树的第k大节点**

​	部分这种简单的字符串数组题更像是练手字符串和数组的一些基本内置方法

​	这个二叉树实在是解释了递归的调用顺序问题，有些时候可以传入引用(包装类)防止值传递出现一些问题



### 10.20

**Vue3**

​	**组件**

​	全局组件

```js
// main.ts里面
import Card from './component/Card/Card.vue'
createApp(App).component('Card', Card).mount('#app')
```

​	局部组件就是在要使用的组件里面import，传统写法

​	递归组件，核心是组件里面也是组件，整体使用有点麻烦，可以查

​	动态组件 使用就是`<component :is="要用的组件名"></component>`

```js
// 在vue2中is通过组件名切换，vue3中通过组件实例切换
// markRaw是因为把组件做成响应式并没有什么意义
const tab = reactive<Com[]>([
	{name: 'A', comName: markRaw(A)},
	{name: 'B', comName: markRaw(B)},
])
```

​	p19



**综设数据展示网站**

​	vue3切忌直接修改ref和reactive变量，这样会导致响应性丢失，ref使用.value，reactive使用对应的属性方法

​	==如果想非要调整代码的执行顺序==

​		这个问题已经是老生常谈，如何良好的控制同步异步并行的代码线性走流程，方案是直接把同步代码放到then里面，强行加入到微任务队列(Promise的then，catch，finally都是微任务意味着就算Promise立刻被resolve也是异步执行)

```js
Promise.resolve()
	.then(() => alert('promise done')) // 实际上这个地方也可以写点异步操作
	.then(() => alert('code finish'))
// 这样代码的流程就被强行控制
```

​	==再来讲讲async和await==

​		async函数就是让返回值强行是一个resolve状态的Promise，简而言之就是包装，而await添加到一个Promise之前就是让js引擎等这个Promise出结果，然后以Promise的结果继续执行(一般也就是直接把resolve的结果抓出来，不进行Promise包装)，实际上暂停当前async函数的执行，让CPU去做其他事，基本上这个就是Promise.then的优雅写法

```js
// 把这段使用Promise的代码改成使用async和await的
function loadJson(url) {
  return fetch(url)
    .then(response => {
      if (response.status == 200) {
        return response.json();
      } else {
        throw new Error(response.status);
      }
    });
}

loadJson('https://javascript.info/no-such-user.json')
  .catch(alert); // Error: 404
  
// async和await模式
async function loadJson(url) {
	const response = await fetch(url)
  if(response.status == 200) {
		const json = await response.json()
  	return json
  } else {
		throw new Error
  }
}
```



**今天的算法题总结 9-回文数 155-最小栈**

​	忘记了`arr.reverse()`会改变原生数组而不是返回一个新的

​	最小栈这道题重新练习了从一个数组中找第几大/小的数这个流程，在数组只有1个元素的时候要设置max = second = 这个元素

​	另一种做法是直接做一个专门的最小值栈，最小值才能进栈



### 10.21

**Vue3**

​	**插槽的使用**

```vue
// 子组件提供插槽
<div>
	<slot name="header"></slot>
</div>

// 父组件使用子组件的时候填入插槽
<son>
	<template v-slot:header> // v-slot:可以简写为#
		<div>插入的内容</div>
	</v-slot>
</son>
```

​	**异步组件** 有点复杂，看看书

​	**Teleport**

​		可以用来传送子组件的位置，内置属性有to，填一个选择器

​	**keep-alive**

​		把组件写到keep-alive里面可以缓存组件的状态，缓存组件有两个新的生命周期

```vue
<keep-alive :max="10"> // max限制最大缓存组件的数目，遵循队列原则
	// 在keep-alive里面每次只能有一个组件被展示
	<A></A>
</keep-alive>

// A组件增加两个生命周期函数
onActivated(callback)
onDeactivated(callback)
```

​	p23



**会议室综设网站**

​	这个项目还有很多提升空间，可能主要做这个项目，唯一的缺点是vue2，关于管理员操作用户如何记录是一个问题，可能开新表



**今天的算法题 LC-141-环形链表 LC-62剑指offer-圆圈中最后剩下的数字**

​	检测已有元素的题目最好使用Set，这样元素的对比更加清晰

​	环形链表的双指针方法有点难理解，之后看看

​	圆圈中数字这道题还有点复杂，需要重新看看

明天重新看一眼深拷贝



### 10.22

**会议室综设网站**

​	添加登录校验功能，新增用户表，使用表中字段判断用户的权限

**Vue3**

​	**新增内置的transition组件**

​		可以使用这个功能给v-if，v-show和动态组件添加切换时的动画，实际上类似于简单的css3动画属性

```vue
// 模板中
<transition name="fade"> // 这个name属性是必须写的
	<div v-if="flag" class="box"></div>
</transition>

// style部分
<style>
.box {
	width: 200px;
	height: 200px;
}
// 这三个就是元素显示的起始状态，中间状态和结束状态
.fade-enter-from {
	width: 0;
	height: 0;
}
.fade-enter-active {
	transition: all 1.5s ease;
}
.fade-enter-to { // 其实这个属性一般是不写的，跟原生一样就行
	width: 200px;
	height: 200px;
}
// 与之对应元素的消失使用.fade-leave-from .fade-leave-active .fade-leave-to
</style>
```

​		实际上类名也可以自己定义，主要的作用是使用现成的图形库

​		`npm i animate.css`然后在组件里面`import animate.css`即可

```vue
// 可以自己给换个名
<transition enter-from-class="enter-from-this"></transition>

.enter-from-this {
	...
}

// 可以使用比如animate.css这样的动画库
<transition enter-from-class="animate__animated animate__bounce"></transition>

// 另外本身transition标签还有一些属性
// 比如duration控制动画化的时长单位是毫秒
<transition :duration="{enter: 50, leave: 500}"></transition> // 可以单独调整进出动画的时长
```

​		transition还有生命周期函数，使用这个可以用函数式的动画库gsap

```vue
<transiton @before-enter="enterFrom" @enter-cancelled="cancelEnter"></transition>
// 给enter前定一个生命周期函数，对应css的时间点就是enter-from-class
<script>
let enterFrom = (el, callback) => { //接受的参数el就是动画改变的元素，callback是当前生命周期执行完毕后的回调
	console.log('这就是生命周期函数')
}
let cancelEnter = (el, callback) => {console.log('过渡效果还没完被打断了')}
</script>

// appear属性，初始状态的动画 appear-from-class appear-active-class appear-to-class
<transition appear appear-from-class="..."></transition>
```

​	p27

**数据结构**

​	**广度优先搜索 BFS**

​		广度优先搜索步骤

​			1 创建队列

​			2 将顶点v标记为已经发现的，灰色，v进入队列

​			3 将v所有的未访问的邻接点(白色)，加入到队列中

​			4 将v标记为黑色

​	p130

有点劳累看不进去书，先看会儿react

**React**

​	**React的Hello World**

​	对于react来说babel除了传统的es6转es5之外，还可以将jsx转为js

```react
// 使用react实现一个hello react
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>

<body>
  <div id="test"></div>
  // 这三个文件的引入有严格的顺序
  <script type="text/javascript" src="./react/react.development.js"></script>
  <script type="text/javascript" src="./react/react-dom.development.js"></script>
  <script type="text/javascript" src="./react/babel.min.js"></script>
  <script type="text/babel"> // 这个地方要写babel类型
    // 创建虚拟dom，这是jsx的语法方式
    const VDOM = <h1>Hello React</h1>
    // 渲染虚拟dom到指定的位置
    ReactDOM.render(VDOM, document.getElementById('test'))
  </script>
</body>

</html>
// 如果上面的案例不使用jsx
// 内部是这样的，如果内部有嵌套元素会非常难写所以使用jsx
const VDOM = React.createElement('h1', {id: 'title'}, 'Hello React') // 三个属性是标签名，标签属性，innerHTML

// 并且jsx还支持非常类似原生html的写法
const VDOM = (
	<h1 id="title">
    	<span>Hello React</span>
  </h1>    
)
```

​	jsx主要是方便创建虚拟dom，纯js创建虚拟DOM基本上不使用

​	**虚拟DOM以及jsx语法**

​	虚拟DOM本质就是一般对象，真实DOM上有大量的属性，而虚拟DOM十分精简，没有过多的属性

```react
const myId = 'title'
const myData = 'Hello React'
const VDOM = (
  // html元素引入js使用{}包起来
  // 引入样式class换成className
  // 行内样式使用对象，写{{key: value}}双花括号不是插值表达式，外层表示是js，内层表示是对象，另外组合词汇改成小驼峰
  // jsx要求根标签只能有一个，这点类似于vue的template
  // 标签必须带自结束，自闭合
  // 标签的首字母如果小写字母开头就自动转html元素如果，如果html没有这个标签就报错，如果是大写字母开头认为是组件
	<h2 className="title" id={myId}>
  	<span style={{color: 'white'}}>{myData}</span>
  </h2>
)
```

​	jsx渲染数组类型 (类似于v-for的操作)

```react
const data = ['jack', 'sam', 'peter']
const VDOM = (
  <div>
  	<h3>写点名字</h3>
    <ul>
    	{data.map(item => {return <li key={index}>{item}</li>})} // 这个地方key写index并不合适
    </ul>
  </div>
)
```

​	**组件的定义和使用**

​		组件的概念是实现局部功能效果的代码以及资源的集合

​		组件有两种定义方式，函数式组件和类式组件

​		先讲讲函数式组件，适用于简单组件的定义

```react
<script type="text/babel">
  // 先创建函数式的组件
	function Demo() {
		return <h2>我是用函数定义的组件(更适合简单组件)</h2>
	}
  // 把组件渲染到页面
  ReactDOM.render(<Demo/>, document.getElementById('test'))
  // 上述语句的执行
  // React解析组件标签，找到MyComponent组件，发现组件是函数定义，随后调用函数，将返回的虚拟DOM转为真实DOM呈现
</script>
```

​		类式组件，适用于复杂组件

​		回顾类语法，子类如果写了构造器必须调用父类的`super()`方法，并且super要放在其他属性之前，在类中可以直接写赋值语句例如`a = 1`这样就是把`a`这个属性挂载到实例上

```react
<script>
	class MyComponent extends React.Component {
    // render的调用说明React隐式new了MyComponent的实例，render函数中的this也是一个实例
		render() { // 有没有构造器看这个组件的要求，但是render()必须有
			return (
      	<h2>我是用类定义的组件(更适合复杂组件)</h2>
      )
    }
  }
  ReactDOM.render(<MyComponent/>, document.getElementById('test'))
</script>
```

​	**组件实例的三大属性** -- 实例直接意味着是类式组件，因为函数式组件根本没有实例(最新版提供了hooks后可以使用)

​	**state属性** -- 相当于组件的状态

```react
<script type="text/babel">
	class Weather extends React.Component {
		constructor(props) {
    	super(props)
      // 构造器的初始化状态，设置state属性以及解决changeWeather实例方法的this指向
    	this.state = {
    		isHot: false
    	}
      this.changeWeather = this.changeWeather.bind(this) // 这个changeWeather作为属性
		}
  	render() { // 这个地方注意事件的变化，React把所有的原生重写了一份
  		return <h2 onClick={changeWeather}>今天天气很{this.state.isHot ? '炎热' : '凉爽'}</h2>
  	}
    changeWeather() { // 这个changeWeather在原型
      console.log('标题被点击了')
      // state不能直接修改，要使用setState，每次setState都会触发render重新调用
      this.setState({isHot = !isHot})
    }
  }
  ReactDOM.render(<Weather />, document.getElementById('test'))
</script>
```

​	接下来看看简写方式

```react
<script type="text/babel">
	class Weather extends React.Component {
    // 直接在类中赋值
    state = {
    		isHot: false
    }
  	render() { // 这个地方注意事件的变化，React把所有的原生重写了一份
  		return <h2 onClick={changeWeather}>今天天气很{this.state.isHot ? '炎热' : '凉爽'}</h2>
  	}
    // 自定义方法
    changeWeather = () => { // 挂载一个箭头函数到实例上
      console.log('标题被点击了')
      // state不能直接修改，要使用setState，每次setState都会触发render重新调用
      this.setState({isHot = !isHot})
    }
  }
  ReactDOM.render(<Weather />, document.getElementById('test'))
</script>
```





### 10.23

**React**

​	**props**

​	在使用组件的时候使用html传参的方法，传入的键值对会自动进入props属性

​	回顾一个浅拷贝对象的方法 `let person2 = {...person}` 没有实现迭代器的对象不能直接使用剩余运算符，但是套大括号可以

​	在react和babel的加持下允许直接使用...展开对象

​	如果要限制标签属性就必须引入prop-types.js文件，==props是只读的==

```react
const p = {name: 'jack', age: 20, gender: 'male'}
ReactDOM.render(<Person name="mary" age={19} gender="female"/>) // 大括号的地方是为了把字符串换成number类型
ReactDOM.render(<Person {...p}/>) // 这个地方的大括号仅仅是表示是js表达式

// 为了防止使用者传递错误的props属性，可以在定义组件的时候做一些限制
class Person extends React.Component {
  render() {
  	return (
    	<ul>
        <li>姓名：{name}</li>
        <li>年龄：{sex}</li>
        <li>性别：{age + 1}</li>
    	</ul>
    )
  }
  // 限制props的类型
  Person.propTypes = {
    name: PropTypes.string.isRequired,
    age: PropTypes.number,
    gender: PropTypes.string
    // 如果是函数写 PropTypes.func
  }
	Person.defaultProps = {
    age: 18,
    gender: '未知性别'
  }
}
```

​	props的简写方式

```react
class Person extends React.Component{
  // 直接使用静态属性，挂载到Person类
  static propTypes = {
    name: PropTypes.string.isRequired,
    age: PropTypes.number,
    gender: PropTypes.string
    // 如果是函数写 PropTypes.func
  }
  static defaultProps = {
    age: 18,
    gender: '未知性别'
  }
  render() {
  	return (
    	<ul>
        <li>姓名：{name}</li>
        <li>年龄：{sex}</li>
        <li>性别：{age + 1}</li>
    	</ul>
    )
  }
}
```

​	函数式组件使用props，但是老版的使用state和refs是不行的

```react
function Person(props) {
	const {name} = props
	return <li>姓名：{name}</li>
}
Person.propType = {...}
Person.defaultProps = {...}
```

​	**构造器**

​	React官方描述组件的构造器就是用来设定初始的state或者绑定事件处理函数，但是实际上通过类内直接赋值语句可以回避

​	如果写构造器就必须`super()`，super里面写不写props取决于是否希望在构造器中通过this访问props (大部分情况实际上是不需要的)

​	p27



**综合设计会议室以及一些杂记**

​	喜提重大问题，登录后通过eventBus传递id然后出现了数据修改但是视图一直不变的大问题

​	定位是User.vue的mounted生命周期函数，明天再看这个

​	vue2不能监视一个data里面定义的引用类型(对象或者数组)的增减属性

​	关于vue2的数据劫持，使用`Object.defineProperty()`vue2会定义一个新对象，完全仿制原来的对象，然后每个属性都提供get和set函数，进而导致每次对象属性的读取和修改都会被监管，但是这个同样导致增删属性不会被察觉

​	`Object.defineProperty()`这个代理的能力非常弱，只能支持get和set，不像vue3使用的proxy功能强大

​	所以vue2中引用数据类型的增添需要使用`Vue.set()`或者`this.$set()`，数组不受此规矩的限制是因为修改原数组方法都被重写了



**今天的算法题总结 783-二叉搜索树节点最小距离 111-二叉树的最小深度**

​	先提个杂记，昨天看了一个闭包的视频，其实就是外层变量加上一个函数使用外层变量，实在是太常见

​	对于递归函数的传参问题，除了我已经用了很长时间的包装类传参，实际上直接使用顶级层的闭包是更简单的

​	对于二叉树这道题，首先选择中序遍历，保证最自然的顺序，每次存储上一个prev值，恰恰prev不是目测的线性(这里掉坑)

​	找到一个好的BFS解决二叉树最小深度解法，这个题不适合全部遍历

```js
		// 使用bfs求二叉树的最小深度
    if(!root) return 0
    const q = [[root, 1]] // 右边数字1代表第一层级，后面的字母l则为结构出来的节点所在层级
    while(q.length) {
        const [n, l] = q.shift()
        // 只在叶子节点处返回层级，即为最小层级，算法结束
        if(!n.left && !n.right) {
            return l
        }
        if(n.left) q.push([n.left, l+1])
        if(n.right) q.push([n.right, l+1])
    }
```



### 10.24

**数据结构**

​	深度优先搜索，由于递归函数本来就是栈调用，不需要手动实现一个栈

​	**排序算法**

​	冒泡排序 交换和比较都是 O(n^2^)

```js
function bubbleSort(arr) {
  let length = arr.length
  for (let j = 0; j < length - 1; j++) {
    for (let i = 0; i < length - j; i++) {
      if (arr[i] > arr[i + 1]) {
        [arr[i], arr[i + 1]] = [arr[i + 1], arr[i]]
      }
    }
  }
}
```

​	选择排序 比较次数是 O(n^2^)，交换是O(n) 比冒泡排序有更好的效率

```js
function selectSort(arr) {
  let length = arr.length
  for (let j = 0; j < length - 1; j++) {
    let min = j
    for (let i = j + 1; i < length; i++) {
      if (arr[min] > arr[i]) {
        min = i
      }
    }
    [arr[j], arr[min]] = [arr[min], arr[j]]
  }
}
```

​	插入排序 相对于选择排序比较的次数减半，在三种简单排序中有最好的效果

```js
function insertSort(arr) {
  let length = arr.length
  for (let i = 1; i < length; i++) {
    let temp = arr[i]
    let j = i
    while (arr[j - 1] > temp && j > 0) {
      [arr[j], arr[j - 1]] = [arr[j - 1], arr[j]]
      j--
    }
    arr[j] = temp
  }
}
```

​	p145



**今天的算法题总结 09剑指offer-两个栈实现队列**

​	改天看这个题好解法



### 10.25

**数据结构**

​	**排序算法**

​	希尔排序 侧重于分组，分组是按间隔分，组内有序化然后不断缩小分组直到分组为1排序结束

​	希尔排序类似于插入排序的升级版，每个分组内执行的其实就是插入排序

```js
// 增量 gap 为 gap / 2 的情况
function shellSort(arr) {
  let length = arr.length
  let gap = Math.floor(length / 2)
  while (gap >= 1) {
    for (let i = gap; i < length; i++) {
      let temp = arr[i]
      let j = i
      while (arr[j - gap] > temp && j > gap - 1) {
        arr[j] = arr[j - gap]
        j -= gap
      }
      arr[j] = temp
    }
    gap = Math.floor(gap / 2)
  }
}
```

​	快速排序 普遍情况下比希尔排序有更好的效率，类似于冒泡排序的升级版，思维的重点是分而治之

​	冒泡排序中需要经过很多次交换才能在一次循环中将最大值放到正确位置，快速排序在一次循环中就可以找到元素的正确位置

​	p153

**React**

​	**refs和事件处理**

​	ref类似于vue中的ref属性，要操作dom的时候使用，组件内的标签通过定义ref可以标识自己，组件中通过`this.refs.refName`获取

```react
// 字符串形式的ref，由于效率问题，已经不再被官方推荐
class Demo extends React.Component {
  showData = () => {
    const { input1 } = this.refs
    alert(input1.value)
  }
  showData2 = () => {
    const { input2 } = this.refs
    alert(input2.value)
  }
  render() {
    return (
      <div>
        <input ref="input1" type="text" placeholder="点击按钮提示数据" />
        <button onClick={this.showData}>点击我显示左侧数据</button>
        <input ref="input2" type="text" placeholder="失去焦点提示数据" onBlur={this.showData2} />
      </div>
    )
  }
}
ReactDOM.render(<Demo />, document.getElementById('test'))

// 回调函数形式的ref (内联和类内)
	// 类内的形式因为不需要反复调用效率更高，但是整体无所谓，内联更方便
	saveInput2 = (currentNode) => {
    this.input2 = currentNode
  }
  render() {
    return (
      <div>
        {/*回调接受的参数就是当前DOM元素，使用的时候由于是直接挂载也不需要refs*/}
        {/*如果是像下面写的内联函数样式，更新过程中回调被调用两次，第一次传参null以清除旧的ref*/}
        <input ref={currentNode => this.input1 = currentNode} type="text" placeholder="点击按钮提示数据" />
        <button onClick={this.showData}>点击我显示左侧数据</button>
        <input ref={this.saveInput} type="text" placeholder="提示数据" onBlur={this.showData2} />
      </div>
    )
  }

// 使用React.createRef()，这个函数调用后返回一个容器，该容器可以存储被ref标记的节点
class Demo extends React.Component {
  // 先创建容器，注意每个容器只能存一个
  myRef = React.createRef()
  myRef2 = React.createRef()
  showData = () => {
    const input1 = this.myRef.current.value
    alert(input1.value)
  }
  showData2 = () => {
    const input2 = this.myRef2.current.value
    alert(input2.value)
  }
  render() {
    return (
      <div>
        <input ref={this.myRef} type="text" placeholder="点击按钮提示数据" />
        <button onClick={this.showData}>点击我显示左侧数据</button>
        <input ref={this.myRef2} type="text" placeholder="失去焦点提示数据" onBlur={this.showData2} />
      </div>
    )
  }
}
```

​	**事件**

​	react中事件通过委托的方式处理，意味着会冒泡到组件最外层元素，然后使用event.target得到发生事件的DOM元素对象

```react
  // 直接使用e.target即可
	showData2 = (event) => {
    alert(event.target.value)
  }
  render() {
    return (
      <div>
        <input ref={this.myRef} type="text" placeholder="点击按钮提示数据" />
        <button onClick={this.showData}>点击我显示左侧数据</button>
        <input type="text" placeholder="失去焦点提示数据" onBlur={this.showData2} />
      </div>
    )
  }
```

​	**数据双向绑定** - 实现类似于v-model的功能，实现这个功能的组件称为受控组件

```react
class Login extends React.Component {
  // 所谓受控组件主要是组件的状态动态维护到state里面，并且减少ref的使用
  state = {
    username: '',
    password: ''
  }
  handleSubmit = (e) => {
    e.preventDefault()
    const { username, password } = this.state
    alert(username, password)
  }
  saveUsername = (e) => {
    this.setState({ username: e.target.value })
  }
  savePassword = (e) => {
    this.setState({ password: e.target.password })
  }
  render() {
    return (
      <form action="" onSubmit={this.handleSubmit}>
        用户名 <input onChange={this.saveUsername} type="text" />
        密码 <input onChange={this.savePassword} type="password" />
        <button>登录</button>
      </form>
    )
  }
}
ReactDOM.render(<Login />, document.getElementById('test'))
```

​	p35



**今天的算法题总结 27-移除元素 844-比较含退格的字符串**

​	做数组，链表类型的题目要逐渐理解快慢指针的思想



### 10.26

**数据结构**

​	**快速排序**

​	要想快速排序简单可以先直接把结尾当成pivot

​	下面这两种算法除了有上述的特点之外，不基于原数组不能满足部分要求，并且空间复杂度高

```js
// 这个结构的快速排序最好理解但是操作不基于原数组，效率并不高
function quickSort(arr) {
  if (arr.length <= 1) return arr
  const midIndex = Math.floor(arr.length / 2)
  // 从原数组删除中位数并保留结果
  const middle = arr.splice(midIndex, 1)[0]
  const leftArr = [], rightArr = []
  for (let i = 0; i < arr.length; i++) {
    const current = arr[i]
    current > middle ? rightArr.push(current) : leftArr.push(current)
  }
  return quickSort(leftArr).concat(middle, quickSort(rightArr))
}

// 类似于上面的做法更简单的快速排序
function quickSort(array) {
  if(arr.length <= 1) return array
  let pivot = array[array.length - 1]
  let left = array.filter((v, i) => v <= pivot && i != array.length -1)
  let right = array.filter(v => v > pivot)
  return [...quickSort(left), pivot, ...quickSort(right)]
}
```

​	理想的快速排序，这个算法的pivot依然是取最后

```js
function quickSort(arr) {
  function quick(arr, left, right) {
    if (right - left <= 1) return
    let pivot = right
    let i = left
    let j = right - 1
    while (i < j) {
      while (arr[i] <= arr[pivot]) {
        i++
      }
      while (arr[j] > arr[pivot] && i < j) {
        j--
      }
      [arr[i], arr[j]] = [arr[j], arr[i]]
    }
    [arr[pivot], arr[i]] = [arr[i], arr[pivot]]
    quick(arr, left, i - 1)
    quick(arr, i + 1, right)
  }
  quick(arr, 0, arr.length - 1)
}
```



**Vue3**

​	**transition-group**

​	渲染整个列表，使用transition-group组件，里面是v-for

​	本身其他使用跟transition没什么区别，比如各种添加动画

```vue
<transition-group tag="section"> // 意味着外面还有一层section标签包起来
	<div v-for="item in list" :key="item.id">{{item}}</div>
</transition-group>
```

​	**依赖注入provide/inject**

​	提供了简便的从父组件向子组件传值的方法

```js
// 父组件
import {provide, ref} from 'vue'
const colorValue = ref('black')
provide('color', colorValue)

// 子组件
import {inject} from 'vue'
const color = inject('color')
```

​	p32



**今天的算法题总结 977-有序数组的平方 209-长度最小的子数组**

​	这两道题都是典型的双指针法，第二道题是滑动窗口



### 10.27

**Vue3**

​	**使用Mitt实现类似于Vue2中eventBus类似的效果**

​	`npm i mitt`

```js
// main.js
import mitt from 'mitt'
const mit = mitt()
app.config.globalProperties.$Bus = mit

// 发送组件
import {getCurrentInstance} from 'vue'
const instance = getCurrentInstance()、
// 其他地方调用这个emit即可
const emit = (e) => {
	instance.proxy.$Bus.emit('自定义事件', e)
}

// 接收组件
import {getCurrentInstance} from 'vue'
const instance = getCurrentInstance()
instance.proxy.$Bus.on('自定义事件', (e) => {

})
```

​	p34



**React**

​	**高阶函数以及函数柯里化**

```react
class Login extends React.Component {
  // 所谓受控组件主要是组件的状态动态维护到state里面，并且减少ref的使用
  state = {
    username: '',
    password: ''
  }
  handleSubmit = (e) => {
    e.preventDefault()
    const { username, password } = this.state
    alert(username, password)
  }
  // 这两个save函数有大量的重复
  /* saveUsername = (e) => {
    this.setState({ username: e.target.value })
  }
  savePassword = (e) => {
    this.setState({ password: e.target.password })
  } */
  
  // 高阶函数，所谓函数柯里化就是函数的返回值还是函数
  saveFormData = (dataType) => {
		return (e) => {
      this.setState({
        [dataType]: e.target.value
      })
    }
  }
  
  render() {
    // 各种on事件后跟的一定是一个js函数，不管是直接写函数还是返回值是一个函数，react会自动调用这个函数
    return (
      <form action="" onSubmit={this.handleSubmit}>
        用户名 <input onChange={this.saveFormData('username')} type="text" />
        密码 <input onChange={this.saveFormData('password')} type="password" />
        <button>登录</button>
      </form>
    )
  }
}
ReactDOM.render(<Login />, document.getElementById('test'))
```

​	实际上也可以不使用函数的柯里化，但是不能类似于vue获取到`$event`

```react
  saveFormData = (str, e) => {
		this.setState({
      str: e.target.value
    })
  }
  
  render() {
    // 各种on事件后跟的一定是一个js函数，不管是直接写函数还是返回值是一个函数，react会自动调用这个函数
    return (
      <form action="" onSubmit={this.handleSubmit}>
        用户名 <input onChange={(event) => {this.saveFormData('username', event)}} type="text" />
        密码 <input onChange={(event) => {this.saveFormData('password', event)}} type="password" />
        <button>登录</button>
      </form>
    )
  }
```

​	**组件的生命周期**

```react
// 删除组件的方法
ReactDOM.unmountComponentAtNode(document.getElementById('test'))

// 组件刚挂载的生命周期方法，相当于onMounted，写在和render同级的位置
componentDidMount() {
	...
}

// 组件卸载前，相当于beforeDestroy
componentWillUnmount()
```

​	p38



**关于Vue3响应式reactive不能解构赋值**

​	这个问题属于Proxy而不是vue，并且实在解构赋值的情况下如果内层又是一个对象依然可以保留响应式，但是如果被解构的已经是一个基础数据类型，解构的过程中就直接拿到了这个值(值传递)，这个值的获取已经跟对象底层的getter和setter没有关系，所以响应式会丢失，反观对象由于reactive会连续包装下去，对象依然在proxy里面，服从getter和setter



**今天的算法题总结 904-水果成篮**

​	大概理解了滑动窗口的概念



### 10.28

**React**

​	**旧版生命周期**

​	初次挂载： 构造器 -> componentWillMount -> render -> componentDidMount -> componentWillUnmount (如果有卸载组件这个操作)

​	以下三个是更新操作

​	setState：shouldComponentUpdate(默认返回值true) -> componentWillUpdate -> render -> componentDidUpdate

​	forceUpdate：componentWillUpdate -> render -> componentDidUpdate -> componentWillUnmount

​	父组件使用props：componentWillReceiveProps->shouldComponentUpdate->componentUpdate->render->componentDidUpdate

​	旧版的这个componentWillReceiveProps有一些坑，第一次传递的props不算，不会调用这个钩子函数，这个函数可以接受props参数

​	componentDidUpdate(preProps, preState)里面可以接受这两个参数，都是更新之前的数据

​	shouldComponentUpdate(nextProps, nextStates)同样是接受两个参数，都是新传来的数据

​	常见的钩子函数：

​		render：所有的渲染都要过一遍，重要性不言而喻

​		componentDidMount 开启定时器，发送网络请求，订阅消息

​		componentWillUnmount 关闭定时器，取消订阅消息

​	**新版生命周期**

​	废弃或者不再推荐使用

​		componentWillMount，componentWillUpdate 和 componentWillReceiveProps被改名，并且不再被推荐使用

​		如果一定要使用的话前面添加`UNSAFE_`前缀比如`UNSAFE_componentWillMount`

​		在异步渲染中React官方认为这三个钩子函数会有问题所以准备取消这三个生命周期

​	关于新增的两个

​		getDerivedStateFromProps: 写成静态方法，可以接收参数props和state，并且要求返回状态对象(state)或者null

​			上述方法的意义上是从Props得到派生的状态state，调用这个方法可以让state的值取决于props，使用极少

​			这个生命周期的位置对于初次挂载在constructor之后，三种更新时都第一个调用

​		getSnapshotBeforeUpdate(preProps, preState):

​			必须返回快照值或者null，这个钩子函数的功能是可以在组件更改前在DOM捕获一些信息(比如滚动的位置)，这个生命周期的任何返回值都会作为参数送给componentDidUpdate()

​			如果写了这个钩子函数，对应的componentDidUpdate(preProps, preState, snapshotValue)

​			这个生命周期的位置在更新时render->getSnapshotBeforeUpdate->真实更新DOM->componentDidUpdate

​	**DOM的diff算法**

​		这个解释了为什么react和vue的循环中key必须被绑定并且最好不要直接就是index

​	**React脚手架**

```shell
npm i -g create-react-app -g
create-react-app 项目名
```

​	p50



**今天的算法题总结 24-两两交换链表的节点 19-删除链表中的倒数第K个节点**

​	都是双指针法，顺便做链表题可以使用dummyHead虚链表头



### 10.29

**React**

​	**脚手架**

​	使用脚手架创建出的页面的index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8" />
  <!-- %PUBLIC_URL就表示public目录 -->
  <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
  <!-- 开启理想视口，用于移动端的适配 -->
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <!-- 用于配置浏览器页签 + 地址栏的颜色，仅限于部分安卓手机 -->
  <meta name="theme-color" content="#000000" />
  <meta name="description" content="Web site created using create-react-app" />
  <!-- 指定网页添加到手机主屏幕的图标 -->
  <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
  <!-- 应用加壳，可以通过这个技术直接转化为客户端应用 -->
  <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />

  <title>React App</title>
</head>

<body>
  <noscript>You need to enable JavaScript to run this app.</noscript>
  <div id="root"></div>

</body>

</html>
```

​	**实现样式的模块化**

```jsx
// 首先css文件改为.module.css比如Hello.module.css
// 案例中css就是 .title {color: blue} 等等样式

// 使用变量接收css文件
import Hello from './Hello.module.css'
export default class Hello extends React.Component {
	render() {
    {/*className更换格式*/}
		return <h2 className={Hello.title}>Hello React</h2>
	}
}
```

​	**React18 渲染的变化**

```react
// 17及以下版本
import ReactDOM from 'react-dom'
ReactDOM.render(组件, 挂载位置)
// 18及以上
import ReactDOM from 'react-dom/client'
const root = ReactDOM.createRoot(挂载位置)
root.render(组件)
```

​	p56



### 10.30

**React**

​	**子组件向父组件传递值**

​	不同于vue的触发事件，react中可以使用子元素调用父元素回调

```react
// 父组件
  handleAdd = (newName) => {
    const { todos } = this.state
    const newTodos = [...todos, { id: nanoid(), name: newName, done: false }]
    console.log(newTodos)
    this.setState({ todos: newTodos })
  }

// 子组件
  handleKeyUp = (e) => {
    const { keyCode, target } = e
    if (target.value.trim() === '') {
      return alert('输入不能为空')
    }
    if (keyCode === 13) {
      this.props.handleAdd(target.value) // 调用父组件的函数
      target.value = ''
    }
  }

  render() {
    return (
      <div className="todo-header">
        <input onKeyUp={this.handleKeyUp} type="text" placeholder="请输入你的任务名称，按回车键确认" />
      </div>
    )
  }
```

​	p61



**今天的算法题总结 242-有效的字母异位词 202-快乐数**

​	这里的哈希表用的很简单就是单纯用空间换取时间，并没有哈希化



### 10.31

**React**

​	**使用脚手架配置react前端代理**

​	不同于后端代理，前端代理使用一个同源的微型服务器，由于这个代理没有ajax引擎，从而绕开了同源策略，可以跨域

```json
// package.json中添加
"proxy": "http://localhost:端口号" // 这个地址是代理的目标，也就是真实服务器地址
```

```js
// react脚手架默认运行在3000端口，则给3000端口发送数据
// 这种情况下如果请求的是index.html这种public目录下有的就会直接被返回
axios.get('http://localhost:3000/students')
```

​	但是有些情况下，同一个页面可能请求不同的服务器地址，所以上述全局代理方式不够全面

​	**react脚手架配置代理总结 直接复制没有整理格式**

方法一

> 在package.json中追加如下配置

```json
"proxy":"http://localhost:5000"
```

说明：

1. 优点：配置简单，前端请求资源时可以不加任何前缀。
2. 缺点：不能配置多个代理。
3. 工作方式：上述方式配置代理，当请求了3000不存在的资源时，那么该请求会转发给5000 （优先匹配前端资源）



方法二

1. 第一步：创建代理配置文件

    ```
    在src下创建配置文件：src/setupProxy.js
    ```

2. 编写setupProxy.js配置具体代理规则 这个文件必须使用cjs规范：

    ```js
    const proxy = require('http-proxy-middleware')
    
    module.exports = function(app) {
      app.use(
        proxy('/api1', {  //api1是需要转发的请求(所有带有/api1前缀的请求都会转发给5000)
          target: 'http://localhost:5000', //配置转发目标地址(能返回数据的服务器地址)
          changeOrigin: true, //控制服务器接收到的请求头中host字段的值
          /*
          	changeOrigin设置为true时，服务器收到的请求头中的host为：localhost:5000
          	changeOrigin设置为false时，服务器收到的请求头中的host为：localhost:3000
          	changeOrigin默认值为false，但我们一般将changeOrigin值设为true
          */
          pathRewrite: {'^/api1': ''} //去除请求前缀，保证交给后台服务器的是正常请求地址(必须配置)
        }),
        proxy('/api2', { 
          target: 'http://localhost:5001',
          changeOrigin: true,
          pathRewrite: {'^/api2': ''}
        })
      )
    }
    ```

说明：

1. 优点：可以配置多个代理，可以灵活的控制请求是否走代理。
2. 缺点：配置繁琐，前端请求资源时必须加前缀。

​	p69



**今天的算法题总结 454-四数之和II 383-赎金信**

​	两数之和重新看了一下，使用哈希表的方法，其实也就是结果提前存起来

​	之所以感觉没有使用哈希表而只是把结果存起来，是因为map和set本身底层已经调用了哈希函数或者红黑树等结构

​	另外当元素数量有限且有规律的时候可以优先使用数组而不是map，这样速度更快



### 11.1

**React**

​	**任意组件之间的数据交互 - 消息订阅与发布机制**

​	先安装`npm i pubsub-js`

```js
import PubSub from 'pubsub-js'

// 消息发布方
PubSub.publish('消息名', data)

// 消息订阅接收方，其中回调的msg也是消息名，使用很少
let token = PubSub.subscribe('消息名', (msg, data) => {...})
// 取消订阅
PubSub.unsubscribe(token)
```

​	**原生的网络请求库fetch - 由于老版浏览器的兼容性问题使用并不是很多**

​	fetch同样也是Promise风格，替代最原生的xhr

​	fetch讲究关注分离，所以第一次调用promise返回的状态是是否响应成功(包括服务器的404等错误都算成功)而不是返回数据

​	第一次的resolve结果要使用其原型自带的`json()`方法拿到第二个promise，然后用await或者then解包就行

```js
fetch(`https://api.github.com/search/users?q=${keyWord}`).then(
  response => {
    console.log('服务器联系成功')
    return response.json()
  }
  // err => {
  //   console.log('联系服务器失败了', err.message)
  //   return new Promise(() => {})
  // }
).then(
  response => console.log(response)
  // err => console.log(err.message)
).catch(err => console.log(err.message))

// 更加精简的写法
try {
  const response = await fetch(`https://api.github.com/search/users?q=${keyWord}`)
  const data = await response.json()
} catch(err) {
  console.log('请求出错', err.message)
}
```

==Promise和async/await==

​	之前的理解是正确的，如果不想管reject的情况完全可以直接使用await，但是如果想处理，就使用try/catch包起来即可

​	**React前端路由**

​	前端路由依靠浏览器本身BOM的history属性，history有两种版本，h5版本直接操作history或者哈希history，没有使用h5的history

​	哈希这种模式兼容性好，使用的就是类似于之前a标签上面的锚点属性

​	p77

**今天的算法题总结 15-三数之和 541-反转字符串II 05剑指offer-替换空格 151-替换字符串中的单词**

​	实际上三数之和使用的还是双指针法，替换字符串中的单词这道题的解法还不够理想



### 11.2

**React**

​	**React前端路由**

​	使用的库是react-router-dom

​	最基本的路由使用

```react
// index.js 使用BrowserRouter或者HashRouter
import React from 'react';
import ReactDOM from 'react-dom/client';
import { BrowserRouter } from 'react-router-dom';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    {/*BrowserRouter和HashRouter是路由管理*/}
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>
);

//App.jsx 使用Link Route
import { Component } from 'react';
import { Link, Route } from 'react-router-dom';
import About from './components/about';
import Home from './components/home';


export default class App extends Component {
  render() {
    return (
      <div>
        <div className="row">
          <div className="col-xs-offset-2 col-xs-8">
            <div className="page-header"><h2>React Router Demo</h2></div>
          </div>
        </div>
        <div className="row">
          <div className="col-xs-2 col-xs-offset-2">
            <div className="list-group">
              {/*Link是路由链接*/}
              <Link className='list-group-item' to="/home">Home</Link>
              <Link className='list-group-item' to="/about">About</Link>
            </div>
          </div>
          <div className="col-xs-6">
            <div className="panel">
              <div className="panel-body">
                {/*Route是路由组件*/}
                <Route path="/home" component={Home}></Route>
                <Route path="/about" component={About}></Route>
              </div>
            </div>
          </div>
        </div>
      </div>
    );
  }
}
```

​	使用Route的路由组件会自带三个重要的props属性history location match

​	如果要选中路由的标签高亮可以使用NavLink，自动给选中的添加active类名，可以配置activeClassName修改自动添加的类名

​	实际使用中由于NavLink可能很多并且每个都需要写重复的activeClassName等属性，所以可以封装NavLink

```react
// NavLink/index.jsx
import { Component } from 'react'
import { NavLink } from 'react-router-dom'

export default class MyNavLink extends Component {
  render() {
    return (
      // 这个地方已经传递了包括children在内的很多属性
      <NavLink {...this.props}></NavLink>
    )
  }
}
```

​	**接收标签体内容，类似于插槽**

​		标签体内容就存放在props里面的children属性，所以说接收和传递标签体属性也可以使用children属性

```react
<NavLink className='list-group-item' to="/about" children="about"></NavLink>
```

​	**switch**

​		使用switch组件把Route组件包起来可以实现更好的Route效率，找到对应的就会停止不继续往下找

```react
<switch>
	<Route path="/home" component={Home}></Route>
  <Route path="/about" component={About}></Route>
</switch>
```

​	给Route添加`exact={true}`可以开启路由的精准匹配，默认是模糊匹配，但是一般情况下无问题不开启严格匹配，有时干预二级匹配

​	**Redirect组件**

​	一般位置写在最下面，所有路由都匹配不上就去redirect

```react
<switch>
	<Route path="/home" component={Home}></Route>
  <Route path="/about" component={About}></Route>
  <Redirect to="/home"></Redirect>
</switch>
```

​	**嵌套 / 多级路由**

​	整体而言相对比vue写的routes数组更加人性化，保证安全一般不写精确匹配exact

```react
// 上一个案例的home组件
import { Component } from 'react'
import { Route, Switch } from 'react-router-dom'
import MyNavLink from '../MyNavLink'
import Message from './Message'
import News from './News'

export default class home extends Component {
  render() {
    return (
      <div>
        <h3>home</h3>
        <div>
          <ul className="nav nav-tabs">
            <li>
              {/* <a className="list-group-item" href="./home-news.html">News</a> */}
              <MyNavLink to="/home/news">News</MyNavLink>
            </li>
            <li>
              {/* <a className="list-group-item" href="./home-message.html">Message</a> */}
              <MyNavLink to="/home/message">Message</MyNavLink>
            </li>
          </ul>
          <Switch>
            <Route path="/home/news" component={News}></Route>
            <Route path="/home/message" component={Message}></Route>
          </Switch>
        </div>
      </div>
    )
  }
}
```

​	**向路由组件传递参数 使用params参数**

​	普通组件可以直接在标签里面使用props传递参数，但是路由组件都是包在Route里面不能直接传递参数

```react
// params参数模式
<Link to={`/home/message/detail/${item.id}/${item.title}`}>{item.title}</Link>
<Route path="/home/message/detail/:id/:title" component={Detail}></Route>
// 随后Detail组件可以在props里面接收到参数
const { id, title } = this.props.match.params
```

​	p87

**今天的算法题总结 232-用栈实现队列 225-用队列实现栈**

​	栈实现队列两个一个管进一个管出，队列实现栈出栈的时候两个队列倒腾一下(或者可以直接一个队列实现，类似于环形)



### 11.4

**React**

​	**向路由组件传递参数**

​	**search参数**

```react
// 声明参数
<Link to={`/home/message/detail/?id=${item.id}&title=${item.title}`}>{item.title}</Link>
// 不需要声明接受的环节，直接写Route
<Route path="/home/message/detail" component={Detail}></Route>
// 包含?的query字符串会直接传递到this.props.location.search需要手动解开
this.props.location.search === '?id=1&title=消息1'
// 引入qs库自动解包，qs.stringify(obj)转为urlencoded格式，qs.parse(str)转为对象格式
import qs from 'qs'
const str = this.props.location.search
const obj = qs.parse(str) // 这一步之前手动把问号去掉
```

​	**state参数** 这个state是路由组件身上自带的不是组件三大特性

​	state传递参数地址栏不会展示，参数依赖于BOM本身的history，刷新可以保留，但清除缓存后会消失，默认state是undefined

​	==使用HashRouter的话刷新会导致路由的state参数丢失==

```react
// 声明参数
<Link to={{pathname: '/home/message/detail', state: {id: item.id, title: item.title}}}>{item.title}</Link>
// 不需要声明接受的环节，直接写Route
<Route path="/home/message/detail" component={Detail}></Route>
// 接受参数
this.props.location.state === {id: 1, title: '消息1'} || {}
const {id, title} = this.props.location.state
```

​	**push和replace**

​	可以给Link和NavLink标签开启replace模式，这样历史记录无法回退，默认是push

```react
<MyNavLink replace to="/home/message">Message</MyNavLink>
```

​	p91



### 11.5

**React**

​	**编程式路由导航**

​	可以解决有时候Link标签没有那么适用的情况，比如自动路由跳转

```react
// 本质上是使用this.props.histroy上面的五个方法
// 路由跳转的两个方法 push 和 replace
replaceShow = (id, title) => {
	this.props.history.replace(`/home/message/detail/${id}/${title}`)
}

searchShow = (id, title) => {
	this.props.history.push(`/home/message/detail?id=${id}&title=${title}`)
}

stateShow = (id, title) => {
	this.props.history.replace(`/home/message/detail`, {id, title})
}
// 控制历史记录回退和前进 go(n) goForward() goBack()
```

​	withRouter，让非路由组件也能使用编程式路由导航

```react
// 在非路由组件中
import {withRouter} from 'react-router-dom'
class Header extends Component {...}
export default withRouter(Header)
// withRouter加工后一般组件也会添加路由组件的props
```

​	**使用antd ui库**	

​		`npm i antd` 下载antd ui库

```react 
import {Button} from 'antd' // 按需引入组件
import 'antd/dist/antd.css' // 引入样式

export default class MyButton extends Component {
	render() {
		return (
    	<Button type="primarym"></Button> // 使用antd的组件
    )
  }
}
```

​		按需引入antd的样式

​		首先需要对脚手架的配置文件做修改，让webpack的配置文件暴露出来 `npm eject` 剩下的步骤很复杂直接看官网

​	**Redux**

​		Redux是专门做状态管理的js库，对于三大框架都可以使用但是一般与React配套

​		**Redux的核心三个元素：**

 	1. Action Creators 创建行为对象`{type: 'add_student', data: 1}`然后给Store
 	2. Store 接受行为对象，使用dispatch分发给对应的Reducer `(previousState, action)`，Reducer处理后组件通过`getState()`更新状态
 	3. Reducer 处理行为，接受参数是旧的state以及action，处理完毕之后返回给Store

​		<u>注意Redux仅仅维护数据，修改后需要手动更新页面视图</u>

​		`this.setState({})`就可以重新调用render函数，render不要手动调用

​		**跳过Action Creators的最简单例子**

```react
// index.js

import React from "react";
import ReactDOM from 'react-dom/client';
import App from "./App";
import store from "./redux/store";

store.subscribe(() => {
  const root = ReactDOM.createRoot(document.getElementById('root'))
  root.render(
    <React.StrictMode>
      <App />
    </React.StrictMode>
  )
})

// store.js

import { legacy_createStore as createStore } from "redux";
import countReducer from './count_reducer';
// 这个文件就是用于暴露store对象，整个应用只有一个store
export default createStore(countReducer)

// count_ reducer.js

// 创建一个为Count组件服务的Reducer，Reducer的本质就是一个函数
export default function countReducer(preState, action) {
  if (preState === undefined) preState = 0
  const { type, data } = action
  switch (type) {
    case 'increment':
      return preState + data
    case 'decrement':
      return preState - data
    // default这种情况对应于初始化
    default:
      return preState
  }
}

// Count的index.jsx

import { Component } from 'react'
// 引入store
import store from '../../redux/store'

export default class Count extends Component {
  state = {
    count: 0
  }

  // componentDidMount = () => {
  //   // 单个组件单位检测redux状态的变化，变化就调用render
  //   // subscribe函数会监听任何redux中的数据变化，只要变化就调用回调
  //   store.subscribe(() => {
  //     this.setState({})
  //   })
  // }

  increment = () => {
    const { value } = this.selectNumber
    // const { count } = this.state
    // this.setState({ count: parseInt(value) + parseInt(count) })
    store.dispatch({ type: 'increment', data: parseInt(value) })
  }

  decrement = () => {
    const { value } = this.selectNumber
    // const { count } = this.state
    // this.setState({ count: parseInt(count) - parseInt(value) })
    store.dispatch({ type: 'decrement', data: -parseInt(value) })
  }

  incrementIfOdd = () => {
    const { value } = this.selectNumber
    // const { count } = this.state
    const count = store.getState()
    if (count % 2 !== 0) {
      // this.setState({ count: parseInt(value) + parseInt(count) })
      store.dispatch({ type: 'increment', data: parseInt(value) })
    }
  }

  incrementAsync = () => {
    const { value } = this.selectNumber
    // const { count } = this.state
    setTimeout(() => {
      store.dispatch({ type: '', data: parseInt(value) })
    }, 500)
  }

  render() {
    return (
      <div>
        <h1>当前求和为 {store.getState()}</h1>
        <select ref={c => this.selectNumber = c}>
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
        </select>&nbsp;
        <button onClick={this.increment}> + </button>&nbsp;
        <button onClick={this.decrement}> - </button>&nbsp;
        <button onClick={this.incrementIfOdd}>当前求和为奇数 + 1</button>&nbsp;
        <button onClick={this.incrementAsync}>异步 + 1</button>&nbsp;
      </div>
    )
  }
}
```

​	p101



### 11.6

**React**

​	**Redux**

​		更加完整的Redux示例 增添了 constant.js 和 count_action.js

```react
// count_action.js
// 专门用于为count组件生成action
import { DECREMENT, INCREMENT } from "./constant"

export const createIncrementAction = (data) => ({ type: INCREMENT, data })
export const createDecrementAction = (data) => ({ type: DECREMENT, data })

// constant.js
// 定义action对象中type类型的常量值
export const INCREMENT = 'increment'
export const DECREMENT = 'decrement'

// count_reducer.js
// 创建一个为Count组件服务的Reducer，Reducer的本质就是一个函数
import { DECREMENT, INCREMENT } from "./constant"

export default function countReducer(preState, action) {
  if (preState === undefined) preState = 0
  const { type, data } = action
  switch (type) {
    case INCREMENT:
      return preState + data
    case DECREMENT:
      return preState - data
    // default这种情况对应于初始化
    default:
      return preState
  }
}

// count的index.jsx的修改部分
	increment = () => {
    const { value } = this.selectNumber
    // const { count } = this.state
    //   this.setState({ count: parseInt(value) + parseInt(count) })
    store.dispatch(createIncrementAction(parseInt(value)))
  }

  decrement = () => {
    const { value } = this.selectNumber
    // const { count } = this.state
    // this.setState({ count: parseInt(count) - parseInt(value) })
    store.dispatch(createDecrementAction(parseInt(value)))
  }

  incrementIfOdd = () => {
    const { value } = this.selectNumber
    // const { count } = this.state
    const count = parseInt(store.getState())
    if (count % 2 !== 0) {
      // this.setState({ count: parseInt(value) + parseInt(count) })
      store.dispatch(createIncrementAction(parseInt(value)))
    }
  }

  incrementAsync = () => {
    const { value } = this.selectNumber
    // const { count } = this.state
    setTimeout(() => {
      store.dispatch(createIncrementAction(parseInt(value)))
    }, 500)
  }
```

​		**异步Redux**

​		action不仅可以是对象，也可以是函数，对象类型的是同步action，函数类型的是异步action

​		异步action首先要`npm i redux-thunk`下载匹配的中间件，异步action的配置相对复杂，也可以组件内部直接异步逻辑

```react
// Count的index.js
	incrementAsync = () => {
    const { value } = this.selectNumber
    // const { count } = this.state
    // setTimeout(() => {
    //   store.dispatch(createIncrementAction(parseInt(value)))
    // }, 500)
    store.dispatch(createIncrementAsyncAction(parseInt(value), 500))
  }

// store.js
import { applyMiddleware, legacy_createStore as createStore } from "redux";
import thunk from 'redux-thunk';
import countReducer from './count_reducer';
// 这个文件就是用于暴露store对象，整个应用只有一个store
export default createStore(countReducer, applyMiddleware(thunk))

// count_action.js
// 专门用于为count组件生成action
import { DECREMENT, INCREMENT } from "./constant"

export const createIncrementAction = (data) => ({ type: INCREMENT, data })
export const createDecrementAction = (data) => ({ type: DECREMENT, data })
export const createIncrementAsyncAction = (data, ms) => {
  return (dispatch) => {
    setTimeout(() => {
      dispatch(createIncrementAction(data))
    }, ms)
  }
}
```

​	**react-redux**

​		react-redux是Facebook给react专门定做的，并不是直接用于替换redux而是提供了一种链接

​		react-redux的核心概念是容器组件和UI组件，只有容器组件和redux通信，UI组件通过props和容器组件通信

​	p105



11.7

**React**

​	**react-redux**

​		react-redux成功打散了react和redux，这两个通过中间人容器组件沟通，降低耦合性

​		react-redux的测试案例并没有跑通

​	p108



**今天的算法题总结 1047-删除字符串中的所有相邻重复项 150-逆波兰表达式求值**

​	检讨这三天没有做算法题，今天可以考虑多看几道

​	239-移动窗口的最大值有些情况没考虑到明天做



### 11.8

感觉昨天是很失败的一天，redux还是有一定的使用难度，redux部分先放一下，继续把react先看完

**React**

​	**React补充**

​		**setState**

​		setState是==异步==的操作，可以传入第二个参数是回调函数，在状态更新完毕且render也完毕后调用

​		另外setState(updater, callback)updater是一个函数，参数有state和props

​		其实本身对象式就是函数式的语法糖，如果想获取完更新的数据使用callback

```js
this.setState((state, props) => {
	// 比较适合更新
	return {count: state.count + 1}
}, callback)
```

​	p117

**今天的算法题总结 回溯专题 77-组合**

​	可能是对回溯不是非常懂，我感觉回溯更像是树形分层递归，可以画图理解



**11.9**

**React**

​	**React补充**

​		**lazyLoad 懒加载**

​		主要是处理路由组件，路由组件一般在没有点击的时候就已经被引入

```react
// index.jsx
import React, {Component, lazy, Suspense} from 'react'
// 不再写传统的引入路由组件的方式，更换为使用lazy函数的方式
const Home = lazy(() => import('./Home'))
const About = lazy(() => import('./About'))

// 在注册路由的地方用Suspense包起来，提供一个路由没加载过来的显示组件
<Susbense fallback={<h2>Loading...</h2>}>
	<Route path="/about" component={About}></Route>
	<Route path="/home" component={Home}></Route>
</Susbense>
```

​		**Hooks 从16.8版本新增的特性，可以在函数组件中使用state和其他的react特性**

​		函数式组件使用少的最主要原因就是没有this导致没有组件的三大特性，也没有自己的生命周期函数

​		Hooks让函数式组件拥有跟类一样的功能，并且新版本中函数式组件已经成为一种主流

​		**useState 给函数式组件提供了state**

```react
// Demo组件
function Demo() {
  // 这个语句的意思就是新建一个state是count，初始值0，新建一个setCount的方法
	const [count, setCount] = React.useState(0) // 返回值类似于元组，第一个元素是状态，第二个是更新状态的方法
  function add() {
    setCount(count + 1)
  }
  return (
  	<div>
    	<h2>当前求和为 {count}</h2>
      <button onClick={add}></button>
    </div>
  )
}
```

​		**useEffect 给函数式组件提供了生命周期函数**

```react
function Demo() {
  const [count, setCount] = React.useState(0)
  function add() {
    setCount(count + 1)
  }
  // 这个钩子可以捕获组件创建，更新等多个生命周期
  // 重点是第二个数组参数，表示监视，如果监视的state更新回调会再被触发，空数组表示不监视，不写第二个参数表示全部监视
  // 主要相当于componentDidMount (第二个参数空数组) / componentDidUpdate (第二个参数不写或者指定监视)
  // return里面的函数就实现了componentDidUnmount
	React.useEffect(() => {
		console.log('count改变了')
    return () => {/*这里面写componentWillUnmount的操作*/}
  }, [count])
}
```

​		**useRef 给函数式组件挂载ref**

​		整体非常类似于使用并不多的`React.createRef()`

```react
function Demo() {
	const myRef = React.useRef()
	function show() {
		console.log(myRef.value)
	}
	return (
		<div>
    	<input type="text" ref={myRef} />
    </div>
	)
}
```

​	p121



**今天的算法题总结 222-完全二叉树的节点个数 216-组合总和III 17-电话号码的字母组合**

​	对递归的理解不够深刻，迭代使用栈操作流程顺序非常费劲



### 11.10

**React**

​	**React补充**

​		**Fragment**

​		处理jsx语法外面必须有一个元素包起来干扰结构

```react
import React, {Component, Fragment} from 'react'
return (
	<Fragment>
  	<Demo/>
  </Fragment>
)
```

​		**Context**

​		适用于祖组件和后代组件之间通信

```react
// 祖级使用
const MyContext = React.createContext()
return (
	<MyContext.Provider value={username}>
  	<Demo/>
  </MyContext.Provider>
)
// 子级使用
// 类式组件
static contextType = MyContext
this.username // 就可以拿到username属性
// 类式组件和函数式组件
return (
	<div>
  	<h3>我是接收到的数据
    	<MyContext.Consumer>
      	{
          value => {
            return `我是${username}`
          }
        }
      </MyContext.Consumer>
    </h3>
  </div>
)
```

​	p123



**今天的算法题总结 39-组合总和 40-组合总和II**

​	组合总和II在去重上遇到了挺多麻烦



### 11.11

**React**

​	**React补充**

​		**PureComponent**

​		在子组件跟父组件没有关系的情况下，父组件render触发(setState)也会导致子组件的render调用，这实际上是不利于性能优化的

​		本质而言这是一个根深蒂固的问题，只要执行了setState()，即使不改变数据组件也会重新调用render，并且还会让子组件也render

​		<u>显然更好的做法应该是只有组件的state或者props改变了才重新render</u>

​		原因是我们写的组件都是继承自React.Component，而其中的shouldComponentUpdate总是返回true

​		解决方法：重写shouldComponentUpdate或者<u>直接继承PureComponent</u> (这个方法更加常用)

​		==PureComponent只进行数据的浅层比较，对象类在setState的时候传一个新的，解释了为什么每次setState数组经常使用扩展==

​		**Props的render属性，其实就是vue的插槽**

​		写组件的时候内容节点里面写的东西最后会出现在this.props.children属性里面，如果这样写除了手动调用还不能传递props

```react
// A的父组件
render() {
	return (
  	<A render={(props) => <B {...props}></B>}></A>
  )
}
// A组件
render() {
  const {props} = this.state
  return (
  	<div>
    	{this.props.render(props)}
    </div>
  )
}
```

​	p125

**今天的算法题总结 404-左叶子之和**



### 11.12

**React**

​	**React补充**

​		**错误边界 ErrorBoundary**

​		使用命令`npm build`后项目根目录生成build文件夹，然后`serve build`即可开启一个上线环境，前提是`npm i serve -g`

​		错误边界使用在容易出现错误的组件的父组件，类似于catch错误不导致整个页面报错

​		错误边界要正常使用需要整体环境处于build状态

```react
export default class Parent extends Component {
  state = {
    // 用于标识子组件是否产生错误
    hasError: ''
  }
  // Parent组件的任何子组件报错都会调用下面的函数
	static getDerivedStateFromError(error) {
		return {hasError:error}
  }
  // 下面这个函数一般用于统计错误的次数
  componentDidCatch() {
		console.log('渲染组件出错了')
  }
  render() {
		return (
    	<div>
      	{this.state.hasError ? <h2>当前网络不稳定请稍后再试</h2> : <Child></Child>}
      </div>
    )
  }
}
```

​	除了react-router6部分还没看，其他已经看完，接下来继续看ReactHooks

**ReactHooks**

​	**useContext**

​		主要是用于祖孙传递参数，方便一次跨越多个层级

```react
import React, {useState, createContext, useContext} from 'react'
const CountContext = createContext()
function Parent() {
  const [count, setCount] = useState(0)
	return (
		<div>
    	<CountContext.Provider value={count}>
      	<Son></Son>
      </CountContext.Provider>
    </div>
	)
}
function Son() {
	const count = useContext(CountContext)
  return (
  	<h2>{count}</h2>
  )
}
```

​		实际使用中一般createContext是在App组件，举例为组件层叠关系App -> C -> E -> F

```react
// App.js
import React from 'react'

import './App.css'

import ComponentC from './components/16ComponentC'

export const UserContext = React.createContext('')

export default const App = () => {
  return (
    <div className="App">
      <UserContext.Provider value={'我是给组件C的数据'}>
        <ComponentC />
      </UserContext.Provider>
    </div>
  )
}

// componentF.jsx
import React from 'react'

import { UserContext } from '../App'

function ComponentF() {
  return (
    <div>
      <UserContext.Consumer>
        {
          (value) => (
            <div>
             	我是App传过来的value {value}
            </div>
          )
        }
      </UserContext.Consumer>
    </div>
  )
}

export default ComponentF
```



### 11.13

​	**ReactHooks**

​		**useReducer**

​		这个配合useContext使用可以类似于Redux

```js
// 基本结构
const [value, dispatch] = useReducer((state, action) => {/*action对应state修改*/}, start)
// value就是可以使用的值，dispatch用于分发action
// state就是value的状态，start是初始值，state都通过action更改
```

​		下面的例子是一个最简单的useReducer演示

```react
// index.jsx
import { useReducer } from 'react'

function Count2() {
  const [count, dispatch] = useReducer((state, action) => {
    switch (action.type) {
      case 'add':
        return state + 1
      case 'sub':
        return state - 1
      default:
        return state
    }
  }, 0)
  return (
    <div>
      <h2>Count: {count}</h2>
      {/*dispatch分发的一般是一个action对象*/}
      <button onClick={() => dispatch({ type: 'add' })}>Increment</button>
      <button onClick={() => dispatch({ type: 'sub' })}>Decrement</button>
    </div>
  )
}

export default Count2
```

​		相对复杂的案例演示

```react
// color.jsx
import { createContext, useReducer } from "react";

export const ColorContext = createContext({})

export const UPDATE_COLOR = "UPDATE_COLOR"

const reducer = (state, action) => {
  switch (action.type) {
    case UPDATE_COLOR:
      return action.color
    default:
      return state
  }
}

export const Color = props => {
  const [color, dispatch] = useReducer(reducer, 'blue')
  return (
    <ColorContext.Provider value={{ color, dispatch }}>
      {props.children}
    </ColorContext.Provider>
  )
}

// ShowArea.jsx
import { useContext } from 'react'
import { ColorContext } from './color'
function ShowArea() {
  const { color } = useContext(ColorContext)
  return (
    <div style={{ color: color, marginBottom: '20px' }}>我是一段文字</div>
  )
}

export default ShowArea

//Buttons.jsx
import { useContext } from "react"
import { ColorContext, UPDATE_COLOR } from './color'
function Buttons() {
  const { dispatch } = useContext(ColorContext)
  return (
    <div>
      <button onClick={() => dispatch({ type: UPDATE_COLOR, color: 'red' })}>红色</button>
      <button onClick={() => dispatch({ type: UPDATE_COLOR, color: 'yellow' })}>黄色</button>
    </div>
  )
}

export default Buttons

//Example.js
import Buttons from "./Buttons";
import { Color } from "./color";
import ShowArea from "./ShowArea";

function Example() {
  return (
    <div>
      <Color>
        <ShowArea></ShowArea>
        <Buttons></Buttons>
      </Color>
    </div>
  )
}

export default Example
```

​	useMemo云里雾里 p10



### 11.14

今天准备做一个OneThing小型项目练手React 18分钟

需要学一下tailwind的css样式

**TailWind**

​	tailwind是一个原子化的css库，封装的是单独的每一种样式，而bootstrap主要是封装了组件，比如现成的按钮样式

​	29分钟



**今天的算法题总结 513-找树左下角的值 113-路径总和II 131-分割回文串**



### 11.15

**TailWind**

​	**添加组件的方法**

```css
// main.css
@tailwind base; // 给标签统一添加属性

@layer base {
  a {display: block;}
}

@tailwind components;
@tailwind utilities;

@layer components {
  .btn {
    @apply
		inline-block w-40 h-8 bg-green-400 text-center
  	text-white leading-8 rounded-md hover:bg-green-600
  }
}

@layer utilities {
  .btn3 {
    width: 300px;
    height: 200px;
    ...
  }
}
```

​	在tailwind中都是rem作为单位，1rem=16px

​	tailwind边看文档边试手，响应式设计很方便

​	**响应式设计重点**

​	内置五个分辨率断点 sm md lg xl 2xl 分别对应 640 768 1024 1280 1536

​	在有其他变体的情况下，响应式变体要放在最前面比如`lg:dark:hover:bg-white`



OneThing小项目做完了

**今天的算法题总结 93-复原IP地址**



### 11.17

昨天全天做页底插件部分，回顾CSS了



### 11.18

不知道CSS还有什么提升方法，这个真的挺麻烦的，换行出现的bug暂时先不管



### 11.19

虽然整体上来讲构思已经全面了很多，但是对于插件点击的变化还是做的不好，list-item组件的点击变化做的不好



### 11.20

displayInfo这个函数虽然整合度高但是内部还是应该拆分组件，因此直接把五种类型的组件拆开

拆组件所有样式直接毁于一旦，以后大段的复制代码都挪到其他地方防止剪切板被覆盖了，估计又要搞好久了

之前list-item的全部样式

```less
.list-item {
  // display: flex;
  width: 100%;
  box-sizing: border-box;
  border-bottom: 1px solid #dadce0;
  font-size: 14px;

  div {
    display: inline-block;
    height: 36px;
    line-height: 36px;
  }

  .name {
    width: 145px;
    font-weight: 700;
    padding-left: 10px;
  }

  .info {
    // flex: 1;

    span {
      display: inline-block;
    }

    div {
      box-sizing: border-box;
      display: inline-block;
    }

    .info-container {
      height: 100%;
      width: 100%;
    }

    .icon-container {
      margin-right: 5px;
    }

    .count-comment {
      margin-right: 30px;
    }

    .type-2,
    .type-4,
    .type-8 {
      // 添加边框颜色有问题
      height: 20px;
      line-height: 20px;
      // padding: 0 5px;
      text-align: center;
      vertical-align: baseline;
      // padding: 10px 0;
      // margin: 10px 0;
      border: 1px solid #dbdce0;
      border-radius: 7px;
    }

    .type-4,
    .type-8 {
      min-width: 170px;
      background-color: #81c995;
      border-color: transparent;
      border: 0;
      border-radius: 4px;
      margin-right: 8px;
    }


    .type-8 {
      border: 1px solid #188038;
    }

    // .info-str {
    //   // position: relative;
    //   // width: 9999px;
    //   // overflow: hidden;
    // }
  }

  .time {
    float: right;
    width: 210px;
    margin-right: 20px;
    text-align: right;

    .time-span {
      margin-right: 5px;
    }
  }
}
```

type4列表渲染中没有设置key，暂时使用index替代



### 11.21

今天上午基本收工了底部组件，近期需要提升使用CSS的技能，另外为后续的react项目做准备，最好再进阶使用TypeScript的能力

很久没有做算法了，并且还有一个问题是js底层还没有学好



**今天的算法题总结 78-子集**

​	大概明天再开始一天三道算法题吧
