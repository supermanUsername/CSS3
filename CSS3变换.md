# CSS3变换 #

定义：让一个元素在一个坐标系统中变形，这个属性包含一系列的变形函数，可以移动，旋转，缩放元素。

语法：transform：none
默认值是none。

## 2d变换 ##

### rotate()旋转 ###

定义：通过指定一个角度参数，对元素指定一个2D的旋转。

语法：transform：rotate(angle)       单位deg。

参数说明：angle指旋转角度，正数表示顺时针旋转，负数表示逆时针旋转。

### translate()平移 ###

定义：根据X轴和Y轴的位置给定参数，使当前元素位置移动。

**translateX()  仅水平方向移动。**
语法：transform：translateX()   单位px。

**translateY()  仅垂直方向移动。 **
语法：transform：translateY()   单位px。

**translate(x,y)  水平方向和垂直方向同时移动。**
语法：transform：translate( X, Y)   单位px。

**注意**：如果只写一个参数，第二个默认是0，也就是只设置了水平方向上的位移。

### scale()缩放 ###

定义：设置元素的缩放程度。

**scaleX() 仅水平方向缩放。**
语法：transform：scaleX()  没有单位。

**scaleY() 仅垂直方向缩放。**
语法：transform：scaleY()  没有单位。

**scale(x,y) 使元素和水平方向同时缩放。**
语法：transform：scale(x,y)  没有单位。

### skew()扭曲/倾斜 ###
定义：设置元素的倾斜状态。

**skewX()  仅使元素在水平方向上扭曲变形 **
语法：transform：skewX()  单位deg正值 ----逆时针。 

**skewY()  仅使元素在垂直方向上扭曲变形 **
语法：transform：skewY()  单位deg正值 ----顺时针。

**skew()  使元素在水平方向和垂直方向上扭曲变形 ** 
语法：transform：skew(x,y)  单位deg。

**注意**：0deg与180deg  效果一样

## 3d变换 ##

### rotate()旋转 ###

**rotateZ()。**(等价于rotate(angle))
定义：指对象在Z轴上的旋转角度。

语法：transform:rotateZ() 没有单位。

**rotate3d()。**
定义：指对象在Z轴的3D旋转角度。

语法：transform:rotate 3d(x,y,z,angle) 没有单位。

参数说明：前三个参数分别表示旋转的方向，第4个参数表示旋转的角度，参数不允许省略。前三个参数只有0-1之间的数字，代表需旋转的程度。

### translate()平移 ###

**translateZ()。**
定义：指对象在Z轴上面的平移

语法：transform：translateZ()  单位px。

**translate3d()。 **
定义：指对象的3d位移。

语法：transform:translate3d(x,y,z)  参数不允许省略，单位px。

### scale()缩放 ###

**scaleZ()。**
定义：指定对象的Z轴缩放。

语法：transform：scaleZ() 没有单位。

**scale3d()。**
定义：指定对象的3D缩放。

语法：transform：scale3d（x,y,z）  参数缺一不可， 没有单位。

## 变换基点。 ##
定义：元素变换的基准点。

语法： transform-origin：水平方向 垂直方向。
 
### 参数说明： ###
left  top   左上角   ----四个角均可以。
25%  top 。
50px  50px。

### 默认值： ###
rotate    几何中心点。
skew  几何中心点。
scale  几何中心点。
translate  本身。


### transform-style ###

这个属性指定了子元素如何在空间中展示，只有两个属性值：flat（默认）和preserve-3d。

          flat 表示所有子元素在2D平面呈现，
          preserve-3d 表示所有子元素在3D平面呈现。
 
如果被扁平化，则子元素不会独立的存在于三维空间。

因为该属性不会被（自动）继承，所以必须为元素所有非叶子后代节点设置该属性。

### backface-visibility ###

backface-visibility属性用来设置，是否显示元素的背面，默认是显示的。

backface-visibility: keyword;

keyword有两个值，hidden和visible，默认值是visible。

### 景深（perspective） ###

景深（英语：Depth of field, DOF）景深是指相机对焦点前后相对清晰的成像范围。在光学中，尤其是录影或是摄影，是一个描述在空间中，可以清楚成像的距离范围。虽然透镜只能够将光聚 到某一固定的距离，远离此点则会逐渐模糊，但是在某一段特定的距离内，影像模糊的程度是肉眼无法察觉的，这段距离称之为景深。当焦点设在超焦距处时，景深 会从超焦距的一半延伸到无限远，对一个固定的光圈值来说，这是最大的景深。

简单的理解，景深就是我们的肉眼距离显示器的距离，景深越大，元素离我们越远，效果就不好，在我们CSS3中，perspective用于激活一个3D空间，属性值就是景深大小（默认none无景深）。

应用景深的元素称为“舞台元素”，舞台元素的所有后代元素都会受影响，（如果后代元素中也添加了perspective属性，效果会叠加而不是覆盖）。

**transform: perspective(depth);**
depth的默认值是none，可以设置为一个长度值，这个长度是沿着Z轴距离坐标原点的距离。1000px被认为是个正常值若使用perspective()函数，那么他必须被放置在transform属性的首位，如果放在其他函数之后，则会被忽略。
 
**perspective: depth;**
    同perspective()函数一样，depth的默认值是none，可以设置为一个长度值，这个长度是沿着Z轴距离坐标原点的距离。他们唯一的区别是，perspective属性是被用于元素的子元素，而不是元素本身；就是说，为某个元素设置perspective属性后，是对这个元素的子元素起作用，而不是这个元素本身。
 
**perspective-origin;**
    同perspective属性，也是设置在父元素上，对后代元素起作用。 这个属性来设置你在X, Y轴坐标确定的那个点来看这个元素，Z轴是被perspective属性设置的。

### 灭点 ###

指的是立体图形各条边的延伸线所产生的相交点。透视点的消失点。

景深越大,灭点越远,元素的变形越小。
景深越小,灭点越近,元素的变形越大。