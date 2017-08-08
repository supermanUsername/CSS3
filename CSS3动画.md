# CSS3动画 #

定义：使元素从一种样式逐渐变化到另外一种样式的效果。

## 原理 ##

**视觉暂留原理**：人类具有”视觉暂留“的特征，人的眼睛在看到一幅画或一个物体后，在0.34s 内不会消失。
**
动画原理**：通过把人物的表情，动物变化等动作，分解成许多动作瞬间的画幅，利用视觉原理，在一幅画还没消失前播放下一副画，就会给人造成一种流畅的视觉变化效果。

## @keyframes ##
**定义**：keyframes关键帧，用来决定动画变化的关键位置。

**注意**：keyframes 控制关键位置，并不是所有的位置。

**语法**：

	@keyframes  animationname{
		keyframes-selector{
			cssStyles;
		}
	}

**参数说明**：
animationname：必写项，定义动画的名称。

keyframes-selector：必写项，动画持续时间的百分比。

0% - 100%之间， 或者使用form和to关键字也可以设置，form代表0%，to代表100%。

## animation属性 ##

### animation-name属性。 ###

**定义**：设置对象所应用的动画名称。

**语法**：animation-name：keyframename  |   none。

**参数说明：**

keyframename：指定要绑定到选择器的关键帧的名称。

### animation-duration属性。 ###

**定义**：设置对象动画的持续时间。

**语法**：animation-duration：time。

**参数说明**：指定对象播放完成需要花费的时间，默认值是0。

### animation-timing-function属性。 ###

**定义**：设置对象动画的过渡类型。

**参数说明**：

- linear:线性过渡（匀速）。
- ease:平滑过渡（0--慢--快--慢），默认值。
- ease-in:慢--快。
- ease-out:快--慢。
- ease-in-out:慢--快--慢。
- 贝塞尔曲线。

### animation-delay属性。 ###

**定义**：设置动画的延迟时间。

**语法**：animation-delay：time。

**参数说明**：可选值，定义动画开始前等待的时间，以秒或者毫秒数计数，默认值是0。

### animation-iteration-count属性 。###

**定义**：设置对象动画的循环次数。

**语法**：animation-iteration-count ： infinite | number

**参数说明**：

number为数字，其默认值是1。

infinite：无限循环次数。

### animation-direction属性。 ###

**定义**：设置对象动画是否反向运动。

**语法**：animation-direction：normal , reverse , alternate , alternate-reverse。

**参数说明**：

normal : 正常方向。

reverse :反向运动。

alternate ： 先正常运动在反向运动，并持续交替运行， 需要配合循环属性使用。

alternate-reverse ： 先反向运动在正常运动，并持续交替运行， 需要配合循环属性使用。

### animation-play-state属性。 ###

**定义**：指定对象是否正在运行或已暂停。

**语法**：animation-play-state：paused | running

**参数说明**：

paused ： 指定暂停动画。

running : 默认值，制定正在运行的动画。

### animation复合属性。 ###

**定义**：设置对象所应用的动画特效。

**语法**：animation ： name duration timing-function delay interation-count direction  play-state	。