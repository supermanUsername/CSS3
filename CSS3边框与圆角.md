# CSS3边框与圆角 #

## CSS3圆角border-radius ##

定义：可以为元素添加圆角边框。

### 指定每一个圆角 ###
- 四个值：左上角   右上角   右下角   左下角。
- 三个值：左上角    右上角和左下角    右下角。
- 两个值：左上角和右下角  右上角和左下角。
- 一个值：4个角都生效。

### 圆形与椭圆 ###

一旦使用百分比，参照的是元素本身的高度与宽度。

当拿50%时， 宽 等于 高  ，圆形宽 。不等于 高，，椭圆形。

### 属性： ###
- border-top-left-radius   左上角。
- border-top-right-radius  右上角。
- border-bottom-right-radius  右下角。
- border-bottom-left-radius  左下角。

### 兼容性： ###
- chrome：  -webkit-border-radius。
- firefox:  -moz-border-radius。
- IE:		 -ms-border-radius。
- opera:    -o-border-radius。
- 正常：    -order-radius。

## 盒阴影box-shadow ##

定义：可以控制一个或多个下拉阴影的框。

语法：box-shadow: 水平方向的偏移量  垂直方向的偏移量  模糊程度  扩展程度  颜色  是否具有内阴影。

### 属性名的介绍 ###

**移量：**

把元素左上角（0，0）作为基准点，找水平方向和垂直方向的偏移量。

水平： 正值 --- 右   ，负值 --- 左。

垂直： 正值 --- 下   ， 负值 --- 上。

**模糊程度： **

边界模糊，但是边界线未动。

由边界线向外模糊多少像素。

**扩展程度：**

盒子阴影，上下左右都向外扩展多少像素。

** 是否具有内阴影： **

inset(默认没有，也就是默认是外阴影)。

加上inset,把元素本身的位置先里挤。

内阴影可为负值，但是模糊不可以。