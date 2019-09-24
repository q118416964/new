### 1 兄弟选择器
+ 相邻兄弟选择器
    + 标签之间用`+`连接
    + 注意:只能链接到下一个兄弟标签上
+ 所有兄弟选择器
    + 标签之间用`~`链接
    + 注意:链接到这个元素之后所有标签
### 2 属性选择器
+ `div[attr]`
+ `div[attr=mydemo]`
+ `div[attr*=mydemo]`  //任意位置
+ `div[attr^=mydemo]`  //开始位置
+ `div[attr$=demos]`  //结束位置
### 3 结构伪类选择器
+ 注意:这是标签父元素的第几个元素
+ 结构
    + `E:first-child`第一个子元素
    + `E:last-child`最后一个子元素
    + `E:nth-child(n)` 第n个子元素
    + `E:nth-last-child(n)` 同E:nth-child(n) 相似，只是倒着计算
+ 例子
    + 偶数
        + `E:nth-child(2n)`
        + `E:nth-child(even)`
    + 奇数
        + `E:nth-child(2n-1)`
        + `E:nth-child(odd)`
    + 选中前五个 `E:nth-child(-1n+5)`
    + 选中后五个 `E:nth-last-child(-1n+5)`
### 4 伪元素选择器
+ 结构 `E::before、E::after`
+ 注意 
    + `content:"";`一定要写
    + `display:block`一定要写
### 5 伪标签选择器
+ `E::first-letter`文本的第一个字母或字
+ `E::first-line` 文本第一行
+ `E::selection` 可改变选中文本的样式
### 6 颜色
+ 关于颜色这一块我们经常会遇到半透明,我们该如何选择
    + 一般元素透明用opacity:05;
    + 遮罩层rgba背景透明;
    + 制作三角的时候用transparent;
+ 不让背景色扩充到边框
    + background-clip:border-box;
### 7 css3盒子模型
+ 格式 `box-sizing:border-box;`
+ 注意 此时设置`height`和`width`是包含了内容区高度以及内边距和边框;
+ 格式 `box-sizing:content-box` 默认
+ 注意 此时设置`height`和`width`只是设置的内容区的高度




