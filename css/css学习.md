## CSS学习

### CSS基础选择器

#### 标签选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>基础选择器之标签选择器</title>
    <style>
    /* 标签选择器 : 写上标签名 */
    p {
        color: green;
    }
    div {
        color: pink;
    }
    </style>
</head>
<body>
    <p>男生</p>
    <div>女生</div>
</body>
</html>
```

#### 类选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>基础选择器之类选择器</title>
    <style>
        /* 类选择器口诀: 样式点定义  结构类(class)调用  一个或多个 开发最常用*/
      .red {
          color: red;
      }
      .star-sing {
        color: green;
      }
      .memeda {  
         color: pink;
      }
        .font35 {
            font-size: 35px;
        }
    </style>
</head>
<body>
    <ul>
        //多类选择器使用
        <li class="red font35">冰雨</li>
        <li>李香兰</li>
        <li class="memeda">生僻字</li>
        <li class="star-sing">江南style</li>
    </ul>
</body>
</html>
```

#### id选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    #d1 {
        color: green;
        font-size: 14px;
    }
</style>
<body>
    <div id="d1">你好世界</div>
</body>
</html>
```

#### 通配符选择器

```html
    <style>
     /**对所有的标签设置红色 **/
     * {
         color: red;
     }
    </style>
```

### 字体属性

#### 设置字体

```html
    <style>
     h1 {
         font-family: 'Microsoft YaHei';
     }
    </style>
```

#### 设置字体大小

```html
    <style>
        body {
            font-size: 16px;
        }
    </style>
```

#### 设置字体粗细

```html
    <style>
       .bold {
           /* font-weight: bold; */
           /* 这个700 的后面不要跟单位  等价于 bold 都是加粗的效果 */
           /* 实际开发中,我们跟提倡使用数字 表示加粗或者变细 */
           font-weight: 700;    
       }
       h2 {
           font-weight: 400;   
           /* font-weight: normal;    */
       }
    </style>
```

#### 设置字体文字样式

```html
    <style>
      p {
          /*倾斜 */
          font-style: italic;
      }
      em {
          /* 让倾斜的字体不倾斜   就是赶紧脉动回来 */
          font-style: normal;
      }
    </style>
```



### 文本属性

#### 文本颜色

```html
    <style>
       div {
           /* color: deeppink; */
           /* color: #cc00ff; */
           color: rgb(255, 0, 255);
       }
```

#### 文本对齐方式

```html
    <style>
        h1 {
            /* 本质是让h1盒子里面的文字水平居中对齐 */
            /* text-align: center; */
            text-align: right;
        }
    </style>
```

#### 文本缩进

```html
    <style>
        p {
            font-size: 24px;
            /* 文本的第一行首行缩进 多少距离  */
            /* text-indent: 20px; */
            /* 如果此时写了2em 则是缩进当前元素 2个文字大小的距离  */
            text-indent: 2em;  
        }
    </style>
```

#### 文本行间距

```html
    <style>
       div {
           line-height: 26px;
       }
    </style>
```

#### 文本装饰

```html
    <style>
       div {
           /* 下划线 */
           /* text-decoration: underline;   */
         /* 删除线 */
           text-decoration: line-through;
           /* 上划线 */
           text-decoration: overline;

       }
       a {
           /* 取消a默认的下划线 */
           text-decoration: none;
           color: #333;
       }
    </style>
```

### CSS引入方式

#### 内部样式表

在head标签中编写style标签

```html
    <style>
            div {
                color: pink;
            }
     </style>
```

#### 行内样式表

直接在标签上编写style内容

```html
 <p style="color: pink; font-size: 20px;">给我一个粉红的回忆</p>
```

#### 外部样式表

在head标签中引入css样式的内容

```html
<link rel="stylesheet" href="style.css">
```



### Emmet语法

Emmeti语法的前身是Zen coding,它使用缩写来提高html/css的编写速度，Vscode内部已经集成该语法。

![image-20250622011450179](D:\github\FrontEnd-Stydy\css\css学习.assets\image-20250622011450179.png)

### vscode保存自动格式化

![image-20250622012104794](D:\github\FrontEnd-Stydy\css\css学习.assets\image-20250622012104794.png)

### 复合选择器

复合选择器可以更准确、更高的选择目标元素（标签）。复合选择器是由两个或多个基础选择器，通过不同的方式组合而成的。

常用的复合选择器包括：后代选择器、子选择器、并集选择器、伪类选择器等等

#### 后代选择器

```html

    <style>
        /* 我想要把ol里面的小li选出来改为pink */

        ol li {
            color: pink;
        }

        /* 中国 山东 济南 蓝翔 */
        ol li a {
            color: red;
        }

        .nav li a {
            color: yellow;
        }
    </style>
```

#### 子元素选择器

```html
    <style>
        .nav>a {
            color: red;
        }
    </style>
```

#### 并集选择器

```html
    <style>
        div,
        p,
        .pig li {
            color: pink;
        }

        /* 约定的语法规范,我们并集选择器喜欢竖着写 */
        /* 一定要注意,最后一个选择器 不需要加逗号 */
    </style>
```

#### 链接伪类选择器(编写顺序固定)

1.选择所有未被访问的链接(a:link)

2.选择所有已被访问的链接( a:visited)

3.选择鼠标指针位于其上的链接(a:hover)

4.选择鼠标按下未弹起的链接(a:active)

```html
    <style>
        /* 1.未访问的链接 a:link  把没有点击过的(访问过的)链接选出来 */
        a:link {
            color: #333;
            text-decoration: none;
        }

        /*2. a:visited 选择点击过的(访问过的)链接 */
        a:visited {
            color: orange;
        }

        /*3. a:hover 选择鼠标经过的那个链接 */
        a:hover {
            color: skyblue;
        }

        /* 4. a:active 选择的是我们鼠标正在按下还没有弹起鼠标的那个链接 */
        a:active {
            color: green;
        }
    </style>
```

#### focus选择器

```html
    <style>
        /* // 把获得光标的input表单元素选取出来 */
        input:focus {
            background-color: pink;
            color: red;
        }
    </style>
```



### HTML元素显示类型

#### 块元素

```
特点：
（1）独占一行。
（2）高度，宽度、外边距及内边距都可以控制。
（3）宽度默认是容器（父级完度）的100%。
（4）是一个容器及盒子，里面可以放行内或者块级元素
```

常见块元素:

```html
<h1>~<h6>、<p>、<div>、<ul>、<ol>、<i>等
```

注意p标签里不能放div

#### 行内元素

```
特点：
(1)相邻行内元素在一行上，一行可以显示多个。 
(2)高、宽直接设置是无效的。
(3)默认宽度就是它本身内容的宽度。
(4)行内元素只能容纳文本或其他行内元素。
```

常见的行内元素：

```html
<a>、<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<span>等
```

注意：链接里面不能再放链接，链接里面可以再放块元素

#### 行内块元素

在行内元素中有几个特殊的标签一<img/>、<iput/>、<td>,它们同时具有块元素和行内元素的特点。有些资料称它们为行内块元素。

```
特点：
(1)和相邻行内元素（行内块）在一行上，但是他们之间会有空白缝隙。一行可以显示多个（行内元素特点）。
(2)默认宽度就是它本身内容的宽度（行内元素特点）。
(3)高度，行高、外边距以及内边距都可以控制（块级元素特点）。
```

### 元素显示模式转换

#### 行内元素转换为块元素

```html
display: block;
```

```html
例子:
        a {
            width: 150px;
            height: 50px;
            background-color: pink;
            /* 把行内元素 a 转换为 块级元素 */
            display: block;
        }
```

#### 块元素转换为行内元素

```html
display: inline;
```

```html
        div {
            width: 300px;
            height: 100px;
            background-color: purple;
            /* 把 div 块级元素转换为行内元素 */
            display: inline;
        }
```

#### 转换为行内块元素

```
 display: inline-block;
```

```
        span {
            width: 300px;
            height: 30px;
            background-color: skyblue;
            display: inline-block;
        }
```

