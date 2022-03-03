# ** Basic HTML and HTML5。**



- 标题标签 h1-h6
- 段落: p
- 注释 <!— —>
- HTML5的语义化， main header , footer nav, video, article, section 作用： 让HTML更易读，便于开发者维护； 有助于搜索引擎和无障碍访问



- 图片 <img src=“图片地址” alt=“图片描述”/ > alt增加网站的可访问性
- 





- 链接跳转 <a href=“url”>点我跳转</a>
- \1. 内部跳转
- \2. 跳转到网页
- tartget 控制是否打开新的页面

- 可以把其他元素嵌套进入a元素里面，让他们变成一个链接



### 列表元素

- 无序列表 ul
- 有序列表 ol
- 列表项 li

### 表单元素

##### input

- type控制表单类型

- - radio 单选框 （name相同表示一组）

    这里有两个 `radio` 单选框。 当用户提交表单时，如果 `indoor` 选项被选中，表单数据会包含：`indoor-outdoor=indoor`。 也就是所选项的 `name` 和 `value` 属性值。如果没有指明 `value` 属性值，则会使用默认值做为表单数据提交，也就是 `on`。这样的表单数据看起来不够直观，因此最好将 `value` 属性值设置为一些有意义的内容。

    ```html
    <label for="indoor">
      	<input id="indoor" type="radio" name="indoor-outdoor"> Indoor
    </label>
    <label for="outdoor">
      	<input id="outdoor" type="radio" name="indoor-outdoor"> Outdoor
    </label>
    ```

    

  - checkbox
  - Checked 默认选项

```html
<label>
</label>
```



- Placeholder 占位符，提示输入
- required

```html
<input type="text" placeholder="cat photo URL" required/>
```

![image-20220302213931985](/Users/bobtang/Library/Application Support/typora-user-images/image-20220302213931985.png)

#### button

```js
<button type="submit">Submit</button>
```



#### label



#### div

`div` 元素也叫内容划分元素，是一个包裹其他元素的**通用容器**

##### 文档类型声明

 `<!DOCTYPE html>` 对应的就是 HTML5。

##### 网页的整体结构

`html` 的结构主要分为两大部分：`head` 和 `body`。 网页的描述应放入 `head` 标签， 网页的内容（向用户展示的）则应放入 `body` 标签

##### head

- link
- meta
- title
- Style



# Basic CSS

##### 制定CSS样式的方法

- 行内样式

- style标签内部 + 选择器来指定

- 类选择器的声明 (具有可重用性，可以重复使用)

  - ```js
    .blue-text {
      color:blue;
    }
    ```

- 元素选择器

- id 选择器 `id` 属性应是唯一的。 尽管浏览器并非必须执行这条规范，但这是广泛认可的最佳实践。 因此，请不要给多个元素设置相同的 `id`。

- 属性选择器

```css
[type=radio] {
  margin:20px 0px 20px 0px;
}
```





##### 关于文字显示

- font-size

- font-family

  - 自定义字体 这里通过css引用

  ```js
  <link href="https://fonts.googleapis.com/css?family=Lobster" />
  ```

  - 文字优雅的降级 从左往右匹配，如果没有安装该字体则降级

  ```js
  h2 {
      font-family: Lobster, monospace;
    }
  ```



##### 边框

- border
- Border-radius 像素 或者 百分比(自身的宽度)



#### 背景

- Backgrou-color



##### 盒模型基础

合并书写，四个值的时候：顺时针转： 上，右，下，左

- padding
  - Padding-top
  - Padding-right
  - padding-bottom
  - Padding-left
- margin 控制元素边框与其他元素之间的border距离
  - maring-top
  - margin-right
  - margin-bottom
  - margin-left

```js
添加负值，子元素填满父元素内容
```



- border



##### CSS的单位；绝对单位和相对单位

绝对单位会接近屏幕上的世界测量值，不过不同的屏幕分辨率会存在差异，可能造成误差。

绝对单位

- px 

相对单位

- em  依赖父元素的font-size
- rem

有些单位长度选项是**相对视窗**大小来改变值的， 这种设定符合响应式网页设计的原则。



#### CSS中的继承

- body里面的元素继承相关属性 font-family和background-color

```js
<style>
  body {
    background-color: black;
    color:green;
    font-family:monospace;
  }

</style>
<body>
  <h1>Hello World</h1>
</body>
```

- **class选择器的样式高于继承样式。**

- 在class属性中，类名的排列顺序没有关系的。但是，在 `<style>` 标签里面声明的 `class` 顺序十分重要，**之后的声明会覆盖之前的声明。** 第二个声明的优先级始终高于第一个声明。 由于 `.blue-text` 是在后面声明的，所以它的样式会覆盖 `.pink-text` 里的样式。

- ID选择器的优先级高于class选择器.  无论在 `pink-text` class 之前或者之后声明，`id` 选择器的优先级总是高于 class 选择器
- **内联样式的优先级高于 ID 选择器**证明了行内样式会覆盖 `style` 标签里面所有的 CSS 声明。
- important优先级最高

```js
.pink-text {
    color: pink !important;
  }
```

#### 颜色

**十六进制表示颜色**

- Hex 十六进制表示，在CSS中我们使用6个十六进制的数字代表颜色。RGB

- 创建 1600 万种不同颜色。

- `0` 是十六进制里面最小的数字，表示没有颜色。

  `F` 是十六进制里面最大的数字，有最高的亮度。

- 缩写 这样，颜色的数量减少到了大约 4000 种。 且在浏览器里 `#FF0000` 和 `#F00` 是完全相同的颜色。

- https://www.freecodecamp.org/news/rgb-color-html-and-css-guide/#whatisthergbcolormodel

**RGB模型**

- Rgb 数值表示0-255 颜色的亮度

```js
rgb(0,0,0) 表示黑色
rgb(255,255,255)表示白色
```





##### CSS变量

```css
/*定义css变量 */
--penguin-skin:gray;

/* 使用css变量*/
.test-var {
  /* 过渡到black,当定义的变量不起作用的时候*/
  background-color:var(--penguin-skin,black)
}
```



##### 浏览器降级提高兼容性

- 浏览器会自动忽视不能识别或者不支持的属性

```css
<style>
  :root {
    --red-color: red;
  }
  .red-box {
    // 通过在使用变量之前提供能够支持的颜色，达到优雅降级的目的。
    background:red;
    background: var(--red-color);
    height: 200px;
    width:200px;
  }
</style>
<div class="red-box"></div>
```



#### 继承CSS的变量

`:root` 是一个伪类选择器，它是一个能够匹配文档根元素的选择器，通常指的是 `html` 元素。 我们在 `:root` 里创建变量在全局都可用，即在任何选择器里都生效。当你在 `:root` 里创建变量时，这些变量的作用域是整个页面。

```css
:root {
    /* 只修改这一行下面的代码 */
    --penguin-belly:pink;
    /* 只修改这一行上面的代码 */
  }
```



##### 媒体查询 media query

```html
<style>
  :root {
    --penguin-size: 300px;
    --penguin-skin: gray;
    --penguin-belly: white;
    --penguin-beak: orange;
  }

  @media (max-width: 350px) {
    :root {
      /* 只修改这一行下面的代码 */
      --penguin-size:200px;
      --penguin-skin:black;
      /* 只修改这一行上面的代码 */
    }
  }

  .penguin {
    position: relative;
    margin: auto;
    display: block;
    margin-top: 5%;
    width: var(--penguin-size, 300px);
    height: var(--penguin-size, 300px);
  }

  .right-cheek {
    top: 15%;
    left: 35%;
    background: var(--penguin-belly, white);
    width: 60%;
    height: 70%;
    border-radius: 70% 70% 60% 60%;
  }

  .left-cheek {
    top: 15%;
    left: 5%;
    background: var(--penguin-belly, white);
    width: 60%;
    height: 70%;
    border-radius: 70% 70% 60% 60%;
  }

  .belly {
    top: 60%;
    left: 2.5%;
    background: var(--penguin-belly, white);
    width: 95%;
    height: 100%;
    border-radius: 120% 120% 100% 100%;
  }

  .penguin-top {
    top: 10%;
    left: 25%;
    background: var(--penguin-skin, gray);
    width: 50%;
    height: 45%;
    border-radius: 70% 70% 60% 60%;
  }

  .penguin-bottom {
    top: 40%;
    left: 23.5%;
    background: var(--penguin-skin, gray);
    width: 53%;
    height: 45%;
    border-radius: 70% 70% 100% 100%;
  }

  .right-hand {
    top: 5%;
    left: 25%;
    background: var(--penguin-skin, black);
    width: 30%;
    height: 60%;
    border-radius: 30% 30% 120% 30%;
    transform: rotate(130deg);
    z-index: -1;
    animation-duration: 3s;
    animation-name: wave;
    animation-iteration-count: infinite;
    transform-origin:0% 0%;
    animation-timing-function: linear;
  }

  @keyframes wave {
      10% {
        transform: rotate(110deg);
      }
      20% {
        transform: rotate(130deg);
      }
      30% {
        transform: rotate(110deg);
      }
      40% {
        transform: rotate(130deg);
      }
    }

  .left-hand {
    top: 0%;
    left: 75%;
    background: var(--penguin-skin, gray);
    width: 30%;
    height: 60%;
    border-radius: 30% 30% 30% 120%;
    transform: rotate(-45deg);
    z-index: -1;
  }

  .right-feet {
    top: 85%;
    left: 60%;
    background: var(--penguin-beak, orange);
    width: 15%;
    height: 30%;
    border-radius: 50% 50% 50% 50%;
    transform: rotate(-80deg);
    z-index: -2222;
  }

  .left-feet {
    top: 85%;
    left: 25%;
    background: var(--penguin-beak, orange);
    width: 15%;
    height: 30%;
    border-radius: 50% 50% 50% 50%;
    transform: rotate(80deg);
    z-index: -2222;
  }

  .right-eye {
    top: 45%;
    left: 60%;
    background: black;
    width: 15%;
    height: 17%;
    border-radius: 50%;
  }

  .left-eye {
    top: 45%;
    left: 25%;
    background: black;
    width: 15%;
    height: 17%;
    border-radius: 50%;
  }

  .sparkle {
    top: 25%;
    left:-23%;
    background: white;
    width: 150%;
    height: 100%;
    border-radius: 50%;
  }

  .blush-right {
    top: 65%;
    left: 15%;
    background: pink;
    width: 15%;
    height: 10%;
    border-radius: 50%;
  }

  .blush-left {
    top: 65%;
    left: 70%;
    background: pink;
    width: 15%;
    height: 10%;
    border-radius: 50%;
  }

  .beak-top {
    top: 60%;
    left: 40%;
    background: var(--penguin-beak, orange);
    width: 20%;
    height: 10%;
    border-radius: 50%;
  }

  .beak-bottom {
    top: 65%;
    left: 42%;
    background: var(--penguin-beak, orange);
    width: 16%;
    height: 10%;
    border-radius: 50%;
  }

  body {
    background:#c6faf1;
  }

  .penguin * {
    position: absolute;
  }
</style>
<div class="penguin">
  <div class="penguin-bottom">
    <div class="right-hand"></div>
    <div class="left-hand"></div>
    <div class="right-feet"></div>
    <div class="left-feet"></div>
  </div>
  <div class="penguin-top">
    <div class="right-cheek"></div>
    <div class="left-cheek"></div>
    <div class="belly"></div>
    <div class="right-eye">
      <div class="sparkle"></div>
    </div>
    <div class="left-eye">
      <div class="sparkle"></div>
    </div>
    <div class="blush-right"></div>
    <div class="blush-left"></div>
    <div class="beak-top"></div>
    <div class="beak-bottom"></div>
  </div>
</div>
```





# 应用视觉设计

