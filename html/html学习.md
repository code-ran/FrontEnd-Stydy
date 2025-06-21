### HTML骨架标签

| 标签名            |    定义    | 说明                                                    |
| ----------------- | :--------: | :------------------------------------------------------ |
| `<html></html>`   |  HTML标签  | 页面中最大的标签，我们成为根标签                        |
| `<head></head>`   | 文档的头部 | 注意在head标签中我们必须要设置的标签是title             |
| `<title></title>` | 文档的标题 | 让页面拥有一个属于自己的网页标题                        |
| `<body></body>`   | 文档的主体 | 元素包含文档的所有内容，页面内容 基本都是放到body里面的 |

快速生成html骨架，ws中输入html:5即可。

#### body标签常用属性

##### bgcolor

设置整个网页的背景颜色。

##### background

设置整个网页的背景图片。

##### text

设置网页中的文本颜色。

##### leftmargin

网页的左边距。

##### rightmargin

网页右边距。

##### topmargin

网页上边距。

##### bottommargin

网页下边距。

### 段落和换行和标题标签

```html
<p></p>
<br />

<h1>标题标签</h1>
<h1>标题一共六级选,</h1>
<h2>文字加粗一行显。</h2>
<h3>由大到小依次减，</h3>
<h4>从重到轻随之变。</h4>
<h5>语法规范书写后，</h5>
<h6>具体效果刷新见。</h6>
......
```

### 文本格式化标签

```html
我是<strong>加粗</strong>的文字
我是<b>加粗</b>的文字
我是<em>倾斜</em>的文字
我是<i>倾斜</i>的文字
我是<del>删除线</del>
我是<s>删除线</s>
我是<ins>下划线</ins>
我是<u>下划线</u>
```

### div和span标签

```html
    <div>我是一个div标签我一个人单独占一行</div>
    <div>我是一个div标签我一个人单独占一行</div>
    <span>百度</span>
    <span>新浪</span>
    <span>搜狐</span>
```

![image-20250508223557042](D:\github\qianduan_learn\html\html学习.assets\image-20250508223557042.png)

### 图像标签

```html
   <h4> 图像标签的使用:</h4>
   <img src="img.jpg"/>
   <h4> alt 替换文本 图像显示不出来的时候用文字替换:</h4>
   <img src="img1.jpg" alt="测试"/>
   <h4> title 提示文本 鼠标放到图像上,提示的文字:</h4>
   <img src="img.jpg" title="思密达"  alt="测试"/>

   <h4> width 给图像设定宽度:</h4>
   <img src="img.jpg" alt="测试" title="思密达" width="500"/>
   <h4> height 给图像设定高度:</h4>
   <img src="img.jpg" alt="测试" title="思密达"  height="100"/>
   <h4> border 给图像设定边框:</h4>
   <img src="img.jpg" alt="测试" title="思密达"  width="500" border="15"/>
```

### 超链接标签

```html
<a href="http://www.baidu.com">百度a</a>
<a href="test1.html">个人页面</a>
<a href="http://www.baidu.com" target="_blank">百度a</a>
```

