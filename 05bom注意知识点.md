<!--
 * @Description: In User Settings Edit
 * @Author: your name
 * @Date: 2019-10-19 10:26:12
 * @LastEditTime: 2019-10-21 09:22:51
 * @LastEditors: Please set LastEditors
 -->
### 1 offset家族
+ offsetWidth 和 offsetHeight 检测盒子自身宽高
    + `offset宽/高  =  盒子自身的宽/高(width/height) + padding +border`
+ offsetLeft 和 offsetTop 检测距离有定位的父盒子的左/上的距离
    + 如果父级都没有定位则以 `body` 为准, `offsetLeft` 从父亲的 `padding` 开始算,父亲的 `border` 不算
+ offsetTop/Left 和style.top/left 区别
    + 最大区别在于 `offsetTop/Left` 可以返回没有定位盒子的距离左侧的位置。而 `style.top/left` 不可以
    + `offsetTop/Left` 返回的是整数，而 `style.top/left` 返回的是字符串，除了数字外还带有单位：`px`,小数点后一位
    + `offsetTop/Left` 只读，而 `style.top/left` 可读写。
    + `obj.style.xxx` 只能获取行内样式
+ offsetParent (检测父系盒子中带有定位的父盒子的节点)
    + 如果当前元素的父级元素没有进行 CSS 定位(absolute,relative,fixed) `offsetParent` 为 `body`
    + 如果当前元素的父级元素中有 CSS 定位 `offsetParent` 取最近的那个父级元素。
### 2 事件对象 Event
+ 定义:每一次点击屏幕中的元素都会触发事件对象event
+ event.target 在屏幕上点击什么元素就会得到什么对象
+ event.currentTarget 绑定事件的目标元素
+ event.pageX/Y 获取鼠标点击的相对于页面的位置
+ event.clientX/Y 获取鼠标点击的相对于可视区域的位置
+ event.offsetX/Y 表示鼠标点击位置相对于出发事件的对象的位置
+ event.type 事件的类型
+ event.key 键盘按键码
+ event.button 鼠标点击的按键
### 3 阻止冒泡和默认事件
+ 阻止冒泡 `event.stopPropagation()`
+ 阻止默认事件 `event.preventDefault()`
### 4 事件委托
+ 由于事件的冒泡机制,可以使用事件委托的方式给元素添加事件,多用于ul监听事件更改li的情景
+ closest Element.closest()` 方法用来获取：匹配特定选择器且离当前元素最近的祖先元素（也可以是当前元素本身）。如果匹配不到，则返回 `null`。 换句话说，方法 closest 在元素中检查每个父类。如果与选择器匹配，则停止搜索并返回祖先。IE不支持此方法
```html
<article>
    <div class="div1">Here is div-01
        <div class="div2">Here is div-02
            <div class="div3">Here is div-03</div>
        </div>
    </div>
</article>

<script>
    var div3 = document.querySelector('.div3');

    div3.onclick = function() {
        console.log(div3.closest('.div2'))          //返回div2
        console.log(div3.closest('div div'))        //返回自身
        console.log(div3.closest('article div'))    //返回自身
        console.log(div3.closest('article>div'))    //返回第一个div
    }

</script>
```
+ 我们还可以使用事件委托**声明式**地通过特定属性和类为元素添加“行为”。
```html
add: <input type="button" value="1" data-counter>
add1: <input type="button" value="2" data-counter>

<script>
  document.addEventListener('click', function(event) {

    if (event.target.dataset.counter != undefined) { // if the attribute exists...
      event.target.value++;
    }

  });
</script>
```
### 5 scroll家族
+ scrollWidth/scrollHeight 检测盒子的宽高 内容+padding
    + 内容未溢出   设定的内容宽高 + padding
    + 内容溢出,并且未设置 overflow属性  内容宽高 + 左/上padding
    + 内容溢出,并且设置了 overflow 属性   内容宽高 + 左/上下padding
+ scrollTop/scrollLeft 可读写
    + 前提是目标元素有滚动条
    + 监听页面滚动
```html
<script>
    // onsroll事件,
    document.onscroll = function () {
        console.log(sct())
    }

    function sct() {
        return document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop;
    }

    function scl() {
        return document.documentElement.scrollLeft || window.pageXoffset || document.body.scrollLeft;
    }
</script>
```
+ window滚动的方法
    + `window.scroll(x,y)`是让window滚动条滚动到那个x,y坐标。//x是水平坐标，y是垂直坐标

### 6 client家族
+ `window.getComputedStyle(element, [pseudoElt]).styleName`	返回的是一个带单位的字符串
+ document.documentElement.clientWidth/clientHeight  获取浏览器可视区域的宽高
+ clientTop/clientLeft (只读) 表示内容区域的左上角相对于整个元素左上角的位置,也就是边框