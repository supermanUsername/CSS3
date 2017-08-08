# CSS3布局扩展 #

## flex布局 ##

CSS3 弹性盒子(Flexible Box 或 Flexbox)，是一种用于在页面上布置元素的布局模式，使得当页面布局必须适应不同的屏幕尺寸和不同的显示设备时，元素可预测地运行/列。对于许多应用程序，弹性盒子模型提供了对块模型的改进，因为它不使用浮动，flex容器的边缘也不会与其内容的边缘折叠。
 
**弹性盒模型，分老版与新版**
   -  老版本的我们通常称之为box
   - 新版本的我们通常称之为flex
 
**容器与项目**

容器为包裹器，项目为容器中元素。
 
**主轴 与 侧轴**

主轴为x轴，恻轴为y轴。
 
有了新版本后，为什么还需要老版本？（新版本比老版本要强大的很多）
    很多移动端浏览器内核版本都超低

----------


### 老版 ###

**容器设置display为-webkit-box**
开启display:-webkit-box，div一行排列

![](http://i.imgur.com/SqSWCVw.png)

**容器**

***容器的布局方向（改变主轴）***
- -webkit-box-orient: horizontal;
设定布局方向为水平方向。

![](http://i.imgur.com/m6r4wZl.png)

- -webkit-box-orient: vertical;
设定布局方向为垂直方向。

![](http://i.imgur.com/sGQfAwb.png)

***容器排列方向（改变主轴）***
- -webkit-box-direction: normal;
设定排列方向为正常方向。

![](http://i.imgur.com/b1VuAnN.png)

- -webkit-box-direction: reverse;
设定排列方向为相反方向。

![](http://i.imgur.com/zyW3brM.png)

***富裕空间的管理***

 富裕的空间的管理不会给项目区分配空间，它只是管理富裕空间的位置。
       
- 富裕空间的管理（主轴）

  -webkit-box-pack:start; 
富裕空间在右边。

![](http://i.imgur.com/6IMYi64.png)

  -webkit-box-pack:end;
富裕空间在左边。

![](http://i.imgur.com/S5Ut40a.png)

  -webkit-box-pack:center;
富裕空间在两边。

![](http://i.imgur.com/Mbi7JMP.png)

  -webkit-box-pack-justify;(box 没有的)
富裕空间在项目之间。

![](http://i.imgur.com/3KGRyWh.png)

-  富裕空间的管理（侧轴）      

  -webkit-box-align:start;
富裕空间在下边。

![](http://i.imgur.com/zXcX28Y.png)

  -weblit-box-align:end;
富裕空间在上边。

![](http://i.imgur.com/MJHf5uS.png)

  -webkit-box-align:center; 
富裕空间在两边。

![](http://i.imgur.com/LK3TEtN.png)

**项目**
 
***弹性空间的管理***
弹性空间的管理：将富裕空间按比例分配到各个项目上。
-webkit-box-flex: 1;

**等比分配**

![](http://i.imgur.com/Rv6vPgp.png)

**不等比分配**

![](http://i.imgur.com/qG0fl98.png)


----------


### 新版 ###

**容器设置display为flex**
开启display:flex，div一行排列。自动缩放，铺满整行。

![](http://i.imgur.com/HEZMK6r.png)

**容器**

***容器的布局方向***

- flex-direction: row;
设定布局方向为水平方向（行）。

![](http://i.imgur.com/IKprDg2.png)

- flex-direction: column;
设定布局方向为垂直方向（列）。

![](http://i.imgur.com/KZsonnd.png)

***容器排列方向***

- flex-direction:row-reverse;
设定排列方向为水平反方向。

![](http://i.imgur.com/BespgoY.png)

- flex-direction:column-reverse;
设定排列方向为垂直反方向。

![](http://i.imgur.com/NganQcF.png)

***富裕空间的管理***

- 更强大的富裕空间的管理（主轴）
 justify-content: flex-start;
富裕空间在主轴的正方向。

![](http://i.imgur.com/oiDUXtB.png)

 justify-content:flex-end;
富裕空间在主轴的反方向。

![](http://i.imgur.com/Pug5J0q.png)

 justify-content:center;
富裕空间在两边。

![](http://i.imgur.com/nt60n2y.png)

 justify-content:space-between;
富裕空间在项目之间。

![](http://i.imgur.com/kMSb4w8.png)

 justify-content:space-around;(box 没有的)
富裕空间在项目两边。

![](http://i.imgur.com/NGIh6kS.png)
           
- 更强大的富裕空间的管理（侧轴）
 align-items:flex-start;
富裕空间在侧轴的正方向。

![](http://i.imgur.com/FAbILRp.png)

 align-items:flex-end;
富裕空间在侧轴的反方向。

![](http://i.imgur.com/jqGxTUS.png)

 align-items:center;
富裕空间在两边。

![](http://i.imgur.com/CZA3ZCT.png)

 align-items:baseline;(box 没有的)
沿着基线对齐。

![](http://i.imgur.com/d2pPCLh.png)

 align-items: stretch;(box 没有的)
实现等高布局。

![](http://i.imgur.com/IK95OG2.png)

**项目**

***弹性空间的管理***
弹性空间的管理：将富裕空间按比例分配到各个项目上。
flex-grow: 1；

**等比分配**

![](http://i.imgur.com/BKyHmzm.png)

**不等比分配**

![](http://i.imgur.com/EewCxcC.png)

## 新版flex布局详解 ##

**弹性容器属性**
-     flex-direction
-     flex-wrap
-     flex-flow
-     justify-content
-     align-items
-     align-content

**弹性元素属性**
-     order
-     align-self
-     flex-grow
-     flex-shrink
-     flex-basis


----------

### 容器 ###

- **flex-wrap**

 flex-wrap 属性控制了容器为单行/列还是多行/列。并且定义了侧轴的方向，新行/列将沿侧轴方向堆砌。
 
 默认值：nowrap（不可继承）。
 
 *** 值***：nowrap | wrap | wrap-reverse 

 ![](http://i.imgur.com/KzWZ4VZ.png)

 ![](http://i.imgur.com/zqQ82Of.png)

 ![](http://i.imgur.com/QLOHfY1.png)

- **flex-flow**

 flex-flow 属性是设置“flex-direction”和“flex-wrap”的简写。
 
 默认值：row nowrap（不可继承）。

 控制主轴和侧轴的位置以及方向。

- **align-content**

 align-content 属性定义弹性容器的侧轴方向上有富裕空间时，如何排布每一行/列。当弹性容器只有一行/列时无作用。

 默认值：stretch（不可继承）。  
 
 *** 值***：
 flex-start
    所有行/列从侧轴起点开始填充。第一行/列的侧轴起点边和容器的侧轴起点边对齐。
    接下来的每一行/列紧跟前一行/列。

 flex-end
    所有弹性元素从侧轴末尾开始填充。最后一个弹性元素的侧轴终点和容器的侧轴终点对齐。
    同时所有后续元素与前一个对齐。

 center
    所有行/列朝向容器的中心填充。每行/列互相紧挨，相对于容器居中对齐。
    容器的侧轴起点边和第一行/列的距离相等于容器的侧轴终点边和最后一行/列的距离。

 space-between
    所有行/列在容器中平均分布。相邻两行/列间距相等。
    容器的侧轴起点边和终点边分别与第一行/列和最后一行/列的边对齐。

 space-around
    所有行/列在容器中平均分布，相邻两行/列间距相等。
    容器的侧轴起点边和终点边分别与第一行/列和最后一行/列的距离是相邻两行/列间距的一半。

 stretch
    拉伸所有行/列来填满剩余空间。剩余空间平均的分配给每一行/列。

----------

### 项目 ###

- **order**

 order 属性规定了弹性容器中的可伸缩项目在布局时的顺序。元素按照 order 属性的值的增序进行布局。拥有相同 order 属性值的元素按照它们在源代码中出现的顺序进行布局。
 
 默认值：0（不可继承）。

- **align-self**

 align-self 会对齐当前 flex 行中的 flex 元素，并覆盖 align-items 的值. 如果任何 flex 元素的侧轴方向 margin 值设置为 auto，则会忽略 align-self。
 
 默认值：auto（不可继承）
 
 ***值***：

 auto
    设置为父元素的 align-items 值，如果该元素没有父元素的话，就设置为 stretch。

 flex-start
    flex 元素会对齐到 cross-axis 的首端。

 flex-end
    flex 元素会对齐到 cross-axis 的尾端。

 center
    flex 元素会对齐到 cross-axis 的中间，如果该元素的 cross-size 的尺寸大于 flex 容器， 将在两个方向均等溢出。

 baseline
    所有的 flex 元素会沿着基线对齐。

  stretch
    flex 元素将会基于容器的宽和高，按照自身 margin box 的 cross-size 拉伸。

- **flex-shrink**

 flex-grow 属性定义弹性盒子项（flex item）的拉伸因子。

 flex-shrink 属性指定了 flex 元素的收缩规则  默认值为1。

- **flex-basis**

 flex-basis 指定了 flex 元素在主轴方向上的初始大小。
 
 默认值 ：auto（不可继承）
 
 注意：
    在flex简写属性中 flex-basis的默认值为0。
 
 flex-grow： 
   可用空间 = (容器大小 - 所有相邻项目flex-basis的总和)
   可扩展空间 = (可用空间/所有相邻项目flex-grow的总和)
   每项伸缩大小 = (伸缩基准值 + (可扩展空间 x flex-grow值))
 
 flex-shrink：
   每项flex收缩大小 = 伸展基准值 - (收缩比例 / 收缩比例总和 x 溢出的空间)-->并不是
   
   1.计算收缩因子与基准值乘的总和  
   2.计算收缩因数
              收缩因数=（项目的收缩因子*项目基准值）/第一步计算总和    
   3.移除空间的计算
              移除空间= 项目收缩因数 x 负溢出的空间   
 
- **flex**

 flex 是 flex-grow，flex-shrink，flex-basis 的简写属性
 
 默认值  ：
 flex-grow: 0（不可继承）
 flex-shrink: 1
 flex-basis: auto 
 
 值
 flex: none;//0 0 auto
 flex：1;
 
## 多列布局（分栏布局） ##

### 栏目宽度 ###

column-width指定每一栏的宽度（这是多列布局的第一种分法）。

### 栏目列数 ###

column-count指定要多少栏（这是多列布局的第二种分法）

### 栏目距离 ###

column-gap

### 栏目间隔线 ###

column-rule

## 响应式布局方案 ##

### 媒体类型 ###

-  all  ——  所有媒体
-  braille  —— 盲文触觉设备
-  embossed  —— 盲文打印机
-  print  ——  手持设备
-  projection  —— 打印预览
-  screen  ——  彩色屏幕
-  speech  —— “听觉”类似的媒体设备
-  tty  —— 不适用像素的设备
-  tv  —— 电视

### 媒体特性 ###

- min-width：分辨率宽度大于设置值的时候识别
- max-width：分辨率宽度小于设置值的时候识别
- orientation：portrait   ：竖屏
- orientation：landscape：横屏
- min-device-pixel-ratio：像素比

### 关键字 ###

- and  连接媒体特性
- not  排除指定媒体类型
- only 指定某种特定的媒体类型