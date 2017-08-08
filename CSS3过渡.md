# CSS3过渡 #

定义：允许css的属性值在一定时间区间内平滑的过渡，在鼠标点击，鼠标滑过或对元素任何改变中触发，并圆滑地以动画改变css的属性值。

## 属性 ##

### transition-property属性。 ###
定义：设置对象中的参与过渡的属性。

语法：transition-property：none | all | property

参数说明：
- none： 没有属性改变。
- all : 默认值，所有属性都改变。
- property： 元素的属性名 color等。

### transition-duration属性。 ###
定义: 设置对象过渡的持续时间。

语法：transition-duration：time。

参数说明：规定完成过渡效果需要花费的时间，以秒或者毫秒计，默认值0。

### transition-timing-function属性。 ###
定义：设置对象中过渡的动画类型。

语法：只能使用一个属性值。

参数说明：
- linear:线性过渡（匀速）。
- ease:平滑过渡（0--慢--快--慢），默认值。
- ease-in:慢--快。
- ease-out:快--慢。
- ease-in-out:慢--快--慢。
- 贝塞尔曲线

### transition-delay属性。 ###
定义：设置对象延迟的过渡时间。

语法：transition-delay：time。

参数说明：指定秒或者毫秒数之前要等待切换效果的开始，默认是0。

### transition复合属性。 ###
定义：设置对象变换时的过渡。

语法：transition ： property  duration  timing-function   delay；

参数说明：时间顺序不能乱。