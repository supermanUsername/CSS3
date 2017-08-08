# CSS3背景与渐变 #

## CSS3背景 ##

### background-cilp ###

定义：指定背景的绘制区域
语法：background-cilp：border-box / padding-box / content-box

属性介绍：
- border-box：背景被裁剪到边框盒（从边框开始绘制背景图片）。
- padding-box：背景被裁剪到内边距框（从内边距开始绘制背景图片）。
- content-box：背景被裁剪到内容框。

### background-origin ###

定义：设置背景图像的原始起始位置。
语法：background-origin：border-box / padding-box / content-box(坐标原点与这三个有关系)。

**属性的介绍： **
- border-box：相对于边框来定位。
- padding-box：相对于内边距来定位。
- content-box：相对于内容框来定位。

注意点：background-position:定义背景图片的位置，水平与垂直方向上面的偏移量。

### background-size ###

定义：指定背景图像的大小。
语法：background-size：number / % / cover / contain。

**属性介绍：** 
- background-size： 宽度  高度（如果只写一个数值，第二个数值默认auto）。

- 百分比： 0% 100% 之间的任何值，此时的百分比参照于元素div的大小。

- cover：将背景图片等比缩放以填满整个容器，如果高度达到一定比例100%，宽度多出的会溢出，但是，具体那部分溢出取决于定位。

- contain：将背景图片等比缩放至某一边紧贴容器边缘为止，如果图片高度比较小，高度就会有空白区域出现。

### 多重背景图像background-image ###

定义：CSS3允许您为元素使用多个背景图片。
语法：background-image: url('1.jpg),url('2.jpg')  ...  使用逗号把图片分开。

注意：元素引入多个背景图片，前面图片会覆盖后面的图片。

### 背景图像的整合background ###

定义：可以在一个声明中设置所有的背景属性
语法：background：color  position  size  repeat origin  clip attachment image;     background: #abc  center  50% no-repeat  content-box  content-box  fixed url('1.jpg') ,url('2.jpg') ...

## CSS3渐变 ##

定义：可以在两个或者多个指定颜色之间显示平移的过渡。

### 线性渐变 ###

定义：是沿着一根轴线改变颜色，从起点到终点进行顺序渐变（从一边拉向另一边）。

语法：background:linear-gradient(方向，开始颜色，结束颜色)。

**方向分类：**

- 方向从上到下（默认）。
	兼容：
	background: -webkit-linear-gradient(red,blue);
	background: -moz-linear-gradient(red,blue);
	background: -o-linear-gradient(red,blue);
	background: linear-gradient(red,blue);

- 方向从左到右。
	兼容：
	background:-webkit-linear-gradient(left,red,blue);
	background: -moz-linear-gradient(right,red,blue);
	background: -o-linear-gradient(right,red,blue);
	background: linear-gradient(to right,red,blue);
	
	兼容描述：webkit内核，写开始点方向；moz和o内核，写结束点方向；标准：to 结束方向。

- 对角。
	兼容：
	background:-webkit-linear-gradient(left top,red,blue);
	background: -moz-linear-gradient(right bottom,red,blue);
	background: -o-linear-gradient(right bottom,red,blue);
	background: linear-gradient(to right bottom,red,blue);
	
	兼容描述：webkit --- (开始水平  开始垂直，red,blue)； moz 和 o ---  (结束水平  结束垂直，red,blue)；标准---（to  结束水平  结束垂直，red,blue）。

- 角度。
	语法：background: linear-gradient(角度,red,blue);
	
	角度说明：0deg 将创建一个从下到上的渐变，90deg将创建一个从左到右的渐变。

**颜色结点：默认每个颜色均匀分布**

background: linear-gradient(red 10%,blue 20%,green 30%,yellow 40%);

- 从0%到10%，为红色，从10%到20%为红色到蓝色的渐变，从20%到30%为蓝色到绿色的渐变，从30%到40%，为绿色到黄色的渐变。
background: linear-gradient(red 10%,blue);
- 从0%到10%，为红色，从10%到100%为红色到蓝色的渐变，最后如果不写具体数值，默认到100%。
background: linear-gradient(red,blue 30%);
- 从0%到30%，为红色到蓝色的渐变如果第一个不写，默认数值是 0%。
background:linear-gradient(rgba(255,0,0,0),rgba(255,0,0,1));
- 由透明色变为不透明色。

**重复渐变**

语法：
background:repeating-linear-gradient(90deg,red 0%,blue 20%);
或者background:repeating-linear-gradient(90deg,red 0%,blue 10%,red 20%);

注意：把元素的整体宽度看成100%。

### 径向渐变 ###

定义：从起点到终点，颜色从内向外进行圆形渐变。

语法：background:radial-gradient(形状尺寸，开始颜色，结束颜色)。

**形状分类：**

circle --- 圆形。

ellipse --- 椭圆形。

注意：当元素的高和宽一样时，参数无论设置谁，都是圆形。

**颜色结点：**

background: radial-gradient(circle,red 50% ,blue 70%);

注意：此时的百分比,指的是圆心到元素最远端的距离,即半径的距离。

**尺寸大小：**

- closest-side最近边。
	background: radial-gradient(closest-side circle,red , blue);

- farthest-side 最远边。
	background: radial-gradient(farthest-side circle,red , blue);

- closest-corner最近角。
	background: radial-gradient(closest-corner circle,red , blue);

- farthest-corner最远角。
	background: radial-gradient(farthest-corner circle,red , blue);

**重复渐变 **

background: repeating-radial-gradient(red 0%,blue 20%);

background: repeating-radial-gradient(red 0%,blue 10%,red 20%);

### IE渐变 ###

**语法：**

filter：progid:DXImageTransform.Microsoft.gradient(startColorstr='startcolor',endColorstr='endColor',GradientType=0)。

**GradientType 渐变的类型。**

0：从上到下。
1：从左到右。
2：由结束颜色到最深的黑渐变。