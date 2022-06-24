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

块级元素的水平居中显示，设置width以及margin设置为auto，或者margin设置为auto并且text-align: center
行内元素和行内块元素的水平居中显示，父元素设置为text-align: center;
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

盒子的重叠情况：未指定优先级的情况下，后来者居上，可以通过z-index指定优先级，只有定位的盒子才会有index属性

**解决了昨天的问题** 通过父盒子设置相对定位，子盒子绝对定位设置right: 0;解决了问题，但是为什么没有浮动到最右未解决

添加绝对定位的盒子不能通过margin: 0 auto;实现水平居中
绝对定位盒子居中的方法：先用top，left等50%，然后通过margin设置为负值，本盒子宽度的一半

添加了定位的行内元素会自动变成行内块元素
浮动的元素不会压住标准流元素的文字部分，但是绝对定位会

**修改总体的属性然后专门修改局部要注意选择器的优先级**
