### 1常见标签
+ h1到h6标题标签 从大到小
+ p 段落标签
+ br 标签
+ span div
+ img 图片标签
+ a 超链接标签
    + target="_self" 默认,在本页面跳转
    + target = "_blank" 在新页面跳转
### 2列表标签
+ 无序列表
    + 定义 ul>li
    + 解释 ul=unorder list,li=list
+ 有序列表
    + 定义 ol>li
    + 解释 ol=order list, li=list
+ 自定义列表
    + 定义 dl>dt>dd
    + 解释 dl=define list, dt=define theme, dd=define data
### 3表格标签
+ 说明 table其实只是由each row 组成的
+ 定义 table>tr>td
+ 解释 tr=table row;td=table data
+ 提示 一般第一行或第一列一般标签为th=table head
### 4表单
+ 常见表单输入标签
    + type="text" 输入文本
    + type= "password" 输入密码
    + type = "button" 一个按钮
    + type = "image" 使用图片作为按钮
    + type = "radio" 单选项
    + type = "checkbox" 多选项
    + type = "submit" 提交
    + type = "reser" 重置
    + type = "file" 上传文件
    + type = "textarea" 文本域
+ 表单基本结构
```html
 <form action="">
        <fieldset>
        <!-- fieldset 是表单的整个输入空间 -->
            <legend>个人信息</legend>
            <!-- legend是表单的标题 -->
            用户名<br />
            <input type="text"><br />>
            密码<br />
            <input type="password"><br />>
        </fieldset>
    </form>
```
+ label标签为 input 元素定义标注 点击字就可以自动选中选项
```html
<form action="/action_page.php">
  <label for="male">Male</label>
  <input type="radio" name="gender" id="male" value="male"><br>
  <label for="female">Female</label>
  <input type="radio" name="gender" id="female" value="female"><br>
  <label for="other">Other</label>
  <input type="radio" name="gender" id="other" value="other"><br><br>
  <input type="submit" value="Submit">
</form>
```
+ 单选项 一定要写name and value
```html
<form action="/action_page.php">
<p>Please select your gender:</p>
  <input type="radio" name="gender" value="male"> Male<br>
  <input type="radio" name="gender" value="female"> Female<br>
  <input type="radio" name="gender" value="other"> Other<br>  

<p>Please select your age:</p>
  <input type="radio" name="age" value="30"> 0 - 30<br>
  <input type="radio" name="age" value="60"> 31 - 60<br>
  <input type="radio" name="age" value="100"> 61 - 100<br>  

  <input type="submit" value="Submit">
```
+ 多选项
```html
<form action="/action_page.php">
  <input type="checkbox" name="vehicle1" value="Bike"> I have a bike<br>
  <input type="checkbox" name="vehicle2" value="Car"> I have a car<br>
  <input type="checkbox" name="vehicle3" value="Boat" checked> I have a boat<br><br>
  <input type="submit" value="Submit">
</form>
```
