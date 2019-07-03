#笔记

##html页面骨架
+ 文档声明类型,表示告诉浏览器以html5的标准来解析页面
+ 介绍注释 注释是给程序员看的,方便维护代码,保证代码的可读性
+ `<html></html>`标签  网页的根节点(根标签),一个网页只能有一个根标签,其余所有内容都应该写在html标签内部
+ `lang='en'` html标签的属性 声明语言环境 默认 不用管
    * 标签的表现形式: <开始标签 附加属性>内容</结束标签>
    * 一般都是成对出现的
    * 标签可以添加属性 属性名="属性值"(key=value)(可以有多个属性,空格隔开)
+ `<head></head>`标签 给浏览器识别用的,辅助浏览器解析页面,并不会在页面当中显示
    * `<meta>`标签(设置网页的元数据) 
        * `charset=utf-8` 指定字符集编码utf-8(优化后的全球码)
        * 用于设置关键字 `<meta name="keywords" content="xxx" />`
        * 用于设置描述信息 `<meta name="description" content="xxxx" />`
    * `<title></title>`标签 设置页面标题,在浏览器头部tab当中显示
+ `<body></body>`标签  用于设置网页主体,网页中所展示的内容都在body标签中
    * 多个空格和 换行都会被当作一个处理

##常见标签
+ `<h1>~<h6>` 标题标签。在html中一共有6级标题。 h1 是最大的标题，一般在页面中只能出现一次。其他的无所谓。
+  `<p>` 段落标签
+  `<br/>` 换行标签
+  `<hr/>` 水平线换行标签
+  图片img标签`<img src="" alt="">`
    - src 图片路径
    - alt 图片未找到时,显示的内容
    - 图片格式 jpg,png,gif,svg,尽量使用大小合适的图片
+  相对路径
    - 同一级目录 直接引用
    - 下级目录
    - 上级目录 ../
    - 多层目录 ../../ (上一级的上一级)
+  绝对路径
    - 本地绝对路径 比如: `D:/01-html/dev/bf.png`
    - 网络路径 比如: `https://gss2.bdstatic.com/9fo3dSag_xI4khGkpoWK1HF6hhy/baike/w%3D268%3Bg%3D0/sign=586984b5572c11dfded1b8255b1c05ed/bd3eb13533fa828b9caedeb5fd1f4134960a5ad2.jpg`
+  `<a>` 超链接，可以跳转到其他页面
    - href 跳转的地址
    - target: _self 默认 当前页面跳转
    - target: _blank 新的窗口打开
+  列表标签
    - ul>li 无序列表
        * 开发常用
        * list-style:none  去掉前边默认的 圆点,自己实现样式
    - ol>li 有序列表
    - dl,dt,dd 自定义列表
+  字体标签
    - 斜体/加粗 `<em>` `<strong>` em标签用于表示一段内容中的着重点。strong标签用于表示一个内容的重要性
    - 斜体/加粗 `<i>` `<b>` 单纯的表示 斜体/加粗  没有语义化
    - 上标/下标 `<sup>` `<sub>` 比如: `5<sup>2<sup>`  ` H<sub>2</sub>O`
    - 下划线/删除线  `<ins>` `<del>`
+  转义字符
    - 空格    `&nbsp;`  `&#160;`
    - 小于号  `&lt;`    `&#60;`
    - 大于号  `&gt;`    `&#62;`
+   补充标签(没有任何样式)
    -   `<div></div>` 会自动换行,多用于布局
    -   `<span></span>` 不会自动换行,多用于照顾某些特殊字符

##html基本规范(语法规范)
+ html不区分大小写,但是尽量使用小写
+ html的注释不能嵌套(注释是给代码加说明,不能再页面中显示)
+ html的标签必须完整.  比如:`<p>` `</p>` `<p>` `<p>` `</p>`,明细不是成对的,及时浏览器能解析,但是是错误的! 
+ html标签是可以嵌套的.
+ 标签的属性必须加双引号.

##表格
+ `<table></table>`
    * align  left | center | right  表格的位置
    * border  表格边框 同时为td(单元格)生成边框
    * bgcolor 表格背景色
    * cellspacing 单元格与单元格之间的距离
    * cellpadding 文字和单元格之间的距离
+ `<tr></tr>`  表格的每一行
    * align  left | center | right  文字对齐方式 
    * bgcolor  当前行的背景色
+ `<th></th>` 
+ `<td></td>` 
    * colspan  单元格所占据的列
    * rowspan  单元格所占据的行
+ 课程表

##表单 
+ `<form>` 用于包括输入框,提交数据
	- action 提交的地址,暂时不用理解
	- method 提交数据的方法 get/post,如果不写,默认是get方式.
+ `<input>` 表单输入框,根据tpye的类型,表现不同的形式
	- type: text  必须 单行文本输入框
	- name: 当前表单的名称  目前必须要有,因为提交的时候后台程序需要通过name属性获取表单的内容.
	- value: xx  当前表单的内容.value是提交的结果.如果设置了vlaue,则是当前表单的默认值.
+ `<input>`: type:password  密码输入框
+ `<input>`: type:radio  单选
	- name 必须要有,这里表明当前的单选输入框为一组
	- value 必须要有,因为单选按钮提交的结果是value的值. value一般采用数字编码的形式表示.
	- checked  默认选中
+ `<input>`: type:checkbox  多选
	- name 同radio
	- value 同radio
	- checked  默认选中
+ `<select>`  option  下拉框
	- name 属性需要设置
	- value 每个option都要设置value
	- selected 默认选中
+ `<input>`: type:file  上传
	- 当选中的时候 ,实际文件并没有被上传上来
	- multiple 可以实现多选
+ `<textarea>` 多行文本输入框
	- cols /rows  文本框的宽度和高度
	- name值需要设置,value指的是标签内部的内容
+ `<input>` type:submit 提交按钮
	- value 按钮显示的内容
	- 点击后表单被提交到 form.action 配置的地址
+ `<label>` 用于包括输入框的头部和输入框 使之称为一体。多用于单选和多选。
+ readonly 只读属性，输入框内容不能更改。
+ disabled 禁用  表单的值再提交时会被舍弃。
+ `<fieldset>` `<legend>` 可以实现表单的分组。
+ get提交
	- 参数被放到地址提交
	- 不安全
	- 地址栏拼接的参数长度有限,一般是<4k
	- 一般用于获取数据
+ post提交
	- 地址栏不显示提交内容,再请求体显示
	- 相对安全
	- 提交的数据量没有上限
	- 一般用于提交保存数据

##CSS书写位置
-   行内样式 `<p style="color: red; font-size: 24px;">这是一个p标签</p>`
-   内部样式 `<style>p{color: red;font-size: 24px;}</style>`
-   外部引入 `<link rel="stylesheet" href="style.css">`
-   区别
    -   行内样式 严重耦合 用的很少
    -   内部样式 测试使用 当前页面的样式只能当前页面使用
    -   外部样式 上线使用 多个页面可以复用样式

##CSS选择器
-   简单选择器
    -   标签选择器
    -   id 选择器
    -   class 选择器
-   复杂选择器
    -   交集选择器
    -   并集选择器
    -   后代选择器
    -   通配符

##CSS权重问题
-   行内样式 > id 选择器 > class 选择器 >标签选择器
-   复杂选择器权重计算 - 行内样式 1000 - id 选择器 100 - class 选择器 10 - 标签选择器 1 - 通配符/继承属性 0
-   如果两个选择器是一样的,遵循就近原则
-   如果写了相同的选择器, 希望某个选择器权重更高,添加 class 即可

##CSS单位
-   px 像素单位
-   em 基于当前字体的倍数： text-indent: 2em;
-   颜色 - 预定义颜色： blue yellow pink purple red 等 - 十六进制： 每两位表示一种颜色的深度 分别表示 red green blue; 比如： #ff00ff

##CSS常用属性
| 属性名称         | 属性作用           | 值                                                                                 |
| ---------------- | ------------------ | ---------------------------------------------------------------------------------- |
| width / height   | 宽高(块状单位有效) | px 百分比 em 等                                                                    |
| background-color | 背景颜色           | color                                                                              |
| cololr           | 字体颜色           | color                                                                              |
| font-size        | 字体大小           | px em 等                                                                           |
| text-align       | 文字对齐方式       | center left right                                                                  |
| text-indent      | 首行缩进           | px em 等                                                                           |
| font-family      | 字体               | 微软雅黑 Microsoft YaHei、黑体 SimHei、Arial 等                                    |
| font-weight      | 字体加粗           | 100-900.加粗 700-900/ bolder lighter normal                                        |
| font-style       | 字体样式           | Italic 斜体 / normal 正常                                                          |
| line-height      | 行高               | 单位： px /倍数 / 百分比 ;- 设置文字的行间距- 单行文字垂直居中 ：行高=父类盒子高度 |
| font             | 字体缩写           | `font:italic bolder 20px/1.2 'Arial','Microsoft YaHei'                             |

##背景图片
| 属性名称              | 属性作用           | 值                                                          |
| --------------------- | ------------------ | ----------------------------------------------------------- |
| background-color      | 背景图片颜色       | color                                                       |
| background-image      | 背景图片           | url(‘1.png’);                                               |
| background-repeat     | 平铺方式           | repeat 、 no-repeat 、 repeat-x 、 repeat-y                 |
| background-position   | 图片位置           | left、 right、 top、 bottom、 center                        |
| background-attachment | 背景滚动           | scroll、fixed (注意：基于 body 的定位）                     |
| background            | 简写（顺序不能错） | background: green url(1.jpg) no-repeat center center fixed; |

##标签的表现形式
+ 块状标签  独占一行，宽高有效。 比如： div   p  h1~h6  form  table   hr  br  ul>li   ol>li dl>dt/dd 
+ 行内块标签  可以同一行显示，宽高有效。  比如: input select  img   button 
+ 行内标签  可以同一行显示，但是宽高无效， margin-top/margin-bottom 无效。。  比如： a   span   strong  del ins  em  i  b  等字体标签

##盒子模型
+ CSS处理网页时，它认为每个元素都包含在一个不可见的盒子里。包含内容区域、 padding（内边距） 、 border（边框）、margin（盒子与盒子的距离）
+ 所有的页面的元素都可以看成是一个盒子，占据一定的页面空间
+ padding
	- padding:10px 20px 30px 40px 这样会设置元素的上、右、下、左四个方向的内边距。
	- padding:10px 20px 30px; 分别指定上、左右、下四个方向的内边距
	- padding:10px 20px; 分别指定上下、左右四个方向的内边距
	- padding:10px;同时指定上左右下四个方向的内边距
	- 同时在css中还提供了padding-top、padding-left、padding-right、padding-bottom分别用来指定四个方向的内边距。
+ margin
	- 用法和padding类似，同样也提供了四个方向的margin-top/right/bottom/left。
	- margin: xxx auto;可以使元素居中。
	- 嵌套崩塌：两个盒子发生嵌套的时候，给子类设置maring会给父类造成一种崩塌现象，子类的margin-top没有效果，而直接作用到父类。
	- 解决方案：  1. 父类  overflow: hidden ; 2. 父类 设置极小的padding
	- 重叠： 如果垂直两个块状元素同时设置了margin-bottom和margin-top,那么这两个值将会发生重叠,不会累加，哪个值大用哪个。
	- margin-top/margin-bottom 对于行内元素无效。
+ border
	- 可以在元素周围创建边框，边框是元素可见框的最外部。
	- border:1px solid red 分别指定了边框的宽度、颜色和样式,是一种缩写： border-widht:  border-style border-color
	- border-style: none (默认)  /  dashed(虚线) / dotted（点）  / solid(实线)  /  double(双实线)
	- 可以单独设置某一条边框： border-right: 20px solid blue;
+ 影响盒子大小的因素
	- border
	- padding  特殊：继承的盒子在父盒子宽度范围内，padding值不会影响该盒子大小。
+ display 我们可以通过修改display来修改元素的性质。
	- block：设置元素为块元素
	- inline：设置元素为行内元素
	- inline-block：设置元素为行内块元素
	- none：隐藏元素
	- 转换的必要性：比如可以把a标签转换为块状元素，进而实现一个按钮的样式。
+ visibility 和display不同，使用visibility隐藏一个元素，隐藏后其在文档中所占的位置会依然保持，不会被其他元素覆盖。
+ overflow 相关标签里面的内容超出了样式的宽度和高度时如何处理
	- visible：默认值
	- scroll：添加滚动条
	- auto：根据需要添加滚动条
	- hidden：隐藏超出盒子的内容

##文档流
+ 块状标签独占一行
+ 行内元素可以同一行显示，如果不够会自动换行
+ 自上而下的展示

##浮动
> 浮动指的是使元素脱离原来的文本流，在父元素中浮动起来。
+ 浮动使用float属性。
+ 可选值：
	– none：不浮动
	– left：向左浮动
	– right：向右浮动
+ 块级元素和行内元素都可以浮动，当一个行内元素浮动以后将会自动变为一个块级元素.
+ 当一个块级元素浮动以后，宽度会默认被内容撑开，所以当漂浮一个块级元素时我们都会为其指定一个宽度。
###浮动的表现形式
+ 当一个元素浮动以后，其下方的元素会上移。元素中的内容将会围绕在元素的周围。
+ 浮动会使元素完全脱离文本流，也就是不再在文档中在占用位置。
+ 元素设置浮动以后，会一直向上漂浮直到遇到父元素的边界或者其他浮动元素。
+ 元素浮动以后即完全脱离文档流，这时不会再影响父元素的高度。也就是浮动元素不会撑开父元素。
+ 浮动元素默认会变为块元素，即使设置display:inline以后其依然是个块元素。
###浮动的影响
+ 如果子类元素设置了浮动，而父类元素没有设置高度，或者高度比子类元素小，那么子类元素脱离了文档流，就无法把父类盒子撑开。那么整个文档的结构将受到破快。
+ 清除浮动的影响： 
    - 严格计算父类盒子高度
    - clear: left/right/both  不允许当前元素的left/right/both有浮动元素。
	- 在浮动元素的最后面追加一个空的div,设置clear:both即可清除浮动的影响。
+ 因为浮动会对文档流造成影响，所以能用流式布局 就不要使用浮动。
+ 补充：1.display：inline-block 标签的换行符会被显示为空格  2.float:right  会改变标签的前后顺序。

##定位
> 通过postion属性可以实现元素的定位。元素定位之后，需要通过设置left和top值对元素定位。
+ position属性可以把一个元素放置到网页中的任何位置。
+ 可选值：
	– static
	– relative
	– absolute
	– fixed
+ static 默认
+ relative 相对定位。 相对元素本身的位置定位。
	- 每个元素在页面的文档流中都有一个自然位置。相对于这个位置对元素进行移动就称为相对定位。周围的元素完全不受此影响。
	- 当开启了相对定位以后，可以使用top、right、bottom、left四个属性对元素进行定位。
	- 如果不设置元素的偏移量，元素位置不会发生改变。
	- 相对定位不会使元素脱离文本流。元素在文本流中的位置不会改变。
	- 相对定位不会改变元素原来的特性。
	- 相对定位会使元素的层级提升，使元素可以覆盖文本流中的元素。
+ absolute 绝对定位指使元素相对于html元素或离他最近的祖先定位元素进行定位。
	- 当开启了绝对定位以后，可以使用top、right、bottom、left四个属性对元素进行定位。
	- 绝对定位会使元素完全脱离文本流。
	- 绝对定位的块元素的宽度会被其内容撑开。
	- 绝对定位会使行内元素变成块元素。
	- 一般使用绝对定位时会同时为其父元素指定一个相对定位，以确保元素可以相对于父元素进行定位。
+ fixed 固定定位。元素会被锁定在屏幕的某个位置上，当访问者滚动网页时，固定元素会在屏幕上保持不动。
	- 固定定位不占据原来的位置，会脱标。
	- 给元素设置固定定位之后，元素位置从浏览器左上角出发。
	- 可以将行内元素转换为行内块元素。
+ z-index 当元素开启定位以后就可以设置z-index这个属性。默认是0.值越大，越靠上。
	- z-index可以指定一个整数作为参数，值越大元素显示的优先级越高，也就是z-index值较大的元素会显示在网页的最上层。

##规避脱标流 
>经验： 一般布局采用标准流，如果布局实现不了用浮动。定位一般用于解决小范围的某个标签的位置。
+ 能用标准流（没有脱标）解决就不用浮动
+ 解决不了就考虑有浮动（页面布局类型，“不完全脱标”）
+ 浮动解决不了用定位（小图标，完全脱标，不影响内容）