# CSS3选择器 #

## 基本选择器 ##

### 子选择器 ###

定义：只能选择某元素的子元素。
语法：父元素>子元素。

### 相邻兄弟选择器 ###

定义：可以选择紧接着在另外一个元素后的元素，而且他们具有一个相同的父元素。
语法：元素 + 相邻兄弟元素。

### 通用兄弟选择器 ###

定义：选择某元素后边的所有兄弟元素，而且他们具有一个共同的父亲。
语法：元素 ~ 后面所有兄弟元素。

### 群组选择器（分组选择器） ###

定义：将具有相同样式的元素分组在一起，每个选择器之间用逗号 ， 隔开。
语法：元素1，元素2，元素3，.......

## 属性选择器 ##

### element[attribute] ###

定义：为带有attribute属性的元素设置样式。
语法：element[attribute]。

### element[attribute='value'] ###

定义：为attribute='value'属性的元素设置样式。
语法：element[attribute='value']。

### element[attribute~='value'] ###

定义：选择attribute属性包含单词value的元素,并设置样式。
语法：element[attribute~='value']。

### element[attribute^='value'] ###

定义：设置attribute属性值，以value开头的所有元素样式。
语法：element[attribute^='value']。

### element[attribute$='value'] ###

定义：设置attribute属性值，以value结尾的所有元素样式。
语法：element[attribute$='value']。

### element[attribute*='value'] ###

定义：设置attribute属性值，包含value的所有元素，并为其设置样式。
语法:element[attribute*='value']。

## 伪类选择器 ##

### 动态伪类 ###

定义：这些伪类并不存在于HTML中，只有当用户和网站交互的时候才能体现出来。

锚点伪类   :link  :visited。

用户行为伪类  :hover  :active  :focus。

### CSS3结构类：nth选择器 ###

** :first-child。 **
定义：选择属于其父元素的首个子元素的每个element元素，并为其设置样式。
语法：element:first-child。

**:last-child。**
定义：选择属于其父元素的最后一个子元素的每个element元素，并为其设置样式。
语法：element:last-child。

** :nth-child(n)。**
定义：选择某元素下第number个element元素（n是一个简单的表达式，不能用其他字幕代替，n从0开始计算）。
语法：element:nth-child(n)。

**:nth-child(odd) 。**
定义：可用于匹配下标是奇数的元素的关键字。
语法：element:nth-child(odd) 

**:nth-child(even)。 **
定义：可用于匹配下标是偶数的元素的关键字。
语法：element:nth-child(even)。

**:nth-last-child()。**
定义：匹配属于其元素的第n个元素的每个元素，从最后一个子元素开始计数。
语法：element:nth-last-child(n)。

** :nth-of-type()。**
定义：匹配属于父元素的特定类型的第n个子元素。
语法：element:nth-of-type(n)。

** :nth-last-of-type() **
定义：匹配属于父元素的特定类型的第n个子元素，从最后一个开始计数。
语法：element:nth-last-of-type(n)。

**:first-of-type。 **
定义：匹配属于其父元素的特定类型的首个子元素的每个元素。
语法：element：first-of-type。

**:last-of-type。**
定义：匹配属于其父元素的特定类型的最后一个子元素的每个元素。
语法：element：last-of-type。

** :only-child。**
定义：匹配属于其父元素的唯一子元素的每个元素。
语法：element:only-child。

** :only-of-type。**
定义：匹配属于其父元素特定类型的唯一子元素的每个元素。
语法：element :only-of-type。

**:empty。** 
定义：匹配没有子元素（包括文本节点）的每个元素。
语法：element :empty。

### 否定选择器  :not（：前有空格） ###

定义：匹配非元素或者选择器 的每个元素。
语法：父元素：not(子元素或者选择器)。

### 伪元素（也可以使用 ：） ###

** ::first-line。**
定义：对元素的第一行文本进行设置，只能用于块级元素。
语法:element::first-line。

**::first-letter。**
定义：用于向文本的首字母设置特殊样式，只能用于块级元素。
语法:element::first-letter。

**::before。**
定义：在元素的内容前面插入新内容，常与content配合使用。
语法:element::before。

**::after。**
定义：在元素的内容后面插入新内容，常与content配合使用。
语法:element::after。

**::selection。**
定义：用于设置浏览器中选中文本后的背景色与前景色。
语法:element::selection。

## CSS权重 ##

定义：当很多规则被应用到某一个元素上时，权重是一个决定哪种规则生效，或者是优先级的过程。

权重的等级与权值：行内样式（1000）> ID选择器（100）>类，属性选择器和伪类选择器（10）> 元素选择器和伪元素选择器（1）>通配符选择器（0）。

### CSS权重规则 ###

- 当多个选择器发生冲突时，会选择权重高的选择器来显示，权重越高越优先显示。

- 比较时需要将多个选择器的权重进行相加在进行比较，如果权重一样，后面的会覆盖前面的样式。

- 权重相加不可能超过他的最大数量级，例如无论多少个元素组成的选择器，都没有一个class选择器权重高。

- 可以在样式后边添加一个！important ，这样该样式将会拥有最大的优先级，其他样式都不能将其覆盖（注意：尽量不要使用！important）。