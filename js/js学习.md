### JavaScript概述

  js是一种运行在客户端（浏览器）的编程语言，可以实现人机交互效果。

 ![image-20250528053015603](D:\github\qianduan_learn\js\js学习.assets\image-20250528053015603.png)

常用在线文档： https://developer.mozilla.org/zh-CN/

JavaScript 程序不能独立运行，它需要被嵌入 HTML 中，然后浏览器才能执行 JavaScript 代码。通过 `script` 标签将 JavaScript 代码引入到 HTML 中。js位置在body标签中。

#### 引入方式

##### 内部方式

通过script标签包裹js代码

##### 外部方式

将js写在独立的以.js结尾的文件中，然后通过script标签的src属性进行引入

```html
<body>
  <!-- 外部形式：通过 script 的 src 属性引入独立的 .js 文件 -->
  <script src="demo.js"></script>
</body>
```

如果使用了外部引入的方式使用js,那么script标签内的其它js代码会被忽略

```html
<script src="demo.js">
    // 如下代码会失效
    let bts = document.querySelectorAll('button');
    for (let i = 0; i < bts.length; i++) {
        bts[i].addEventListener('click',function () {
            document.querySelector('.blue').className = ''
            this.className = 'blue'
        })
    }
</script>
```

#### 注释

##### 单行注释

```
//
```

##### 多行注释

```
/* */
```

#### 结束符

js中;代表结束，多数情况可省略。

### 输入和输出

##### 输出

###### document.write()

向body中输出内容，如果输出的内容是标签，也会被浏览器解析成网页元素。

input_output.js

```js
document.write('你好 世界!')
document.write('<h1>我是h1标题标签</h1>')
```

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
<script src="input_output.js"></script>
</body>
</html>
```

![image-20250528061901356](D:\github\qianduan_learn\js\js学习.assets\image-20250528061901356.png)

###### alert()

页面弹出警告对话框。

注意alert()优先级高于document.write()

```js
document.write('你好 世界!')
document.write('<h1>我是h1标题标签</h1>')

alert('告警提示窗')
```

![image-20250528062227777](D:\github\qianduan_learn\js\js学习.assets\image-20250528062227777.png)

###### console.log()

控制台输出，用于调试使用。

```js
console.log('调试日志')
```

![image-20250528062522280](D:\github\qianduan_learn\js\js学习.assets\image-20250528062522280.png)

##### 输入 

###### prompt()

优先级低于alert()高于document.write()

显示一个对话框，对话框中包含一条文字信息，用来提示用户输入文字

```js
prompt('请输入用户名')s
```

### 变量

变量是计算机中用来存储数据的“容器”。

#### 变量的使用

##### 声明

注意变量不允许重复声明

```
声明关键字 变量名
```

```js
let 变量名
```

声明多个变量

```js
let name = '张三' ,age = 27
```

##### 赋值

```js
let age = 27
或者
let age
age = 18
```

##### 变量命名规则

1. **只能是字母、数字、下划线、$**，**且不能能数字开头**
2. **字母区分大小写**，如 Age 和 age 是不同的变量
3. **js关键字不允许命名成变量**
4. 尽量保证变量具有一定的语义，见字知义
5. 驼峰命名法

##### 数组

声明语法

```js
let 数组名 = [元素1,元素2,元素3]
```

```js
let nums = [1,2,3]
```

取值语法

```
数组名[下标]
```

```js
let nums = [1,2,3]
console.log(nums[0])//1
```

获取数组的长度

```js
let nums = [1,2,3]
console.log(nums.length)
```

数组长度 = 最大索引 + 1

### 常量

使用const声明的变量称为常量。

声明语法

```
const 常量名  = 常量值
```

```js
const G = 9.8
console.log(G)
```

注意事项:

常量不允许重新赋值，声明的时候必须初始化。

### 数据类型

![image-20250528082947602](D:\github\qianduan_learn\js\js学习.assets\image-20250528082947602.png)

#### 基本数据类型

##### 数字类型(Number)

数学中的数字，整数、小数、正数、负数......

```js
let a = 1
let b = 1.1
let c = -1
```

##### 算数运算符

```
+（加）  -（减）  *（乘）  /（除）  %（取余）
```

先乘除取余，后加减，又小括号先算小括号里面的

##### 字符串类型(String)

通过单引号或者双引号或者反引号包裹的数据，推荐使用单引号。

```js
let str = '张三'
let str1 = "李四"
let str2 = `王五`
```

单引号或者双引号可以互相嵌套，但是不以自己嵌套自己。可以使用转义字符\输出单引号或者双引号。

字符串拼接使用:  +

**模版字符串**(es6新语法)

用于拼接字符串和变量

语法格式

```
`字符串1${变量名}字符串2`
```

```js
let age = 27
console.log(`年龄${age}了`)//27
console.log(`年龄${age + age}了`)//54
```

##### 布尔类型(boolean)

true/false

```js
let isCool = false
```

##### 未定义类型(undefined)

声明一个变量未赋值，那它就是undefined类型

注意:

```js
console.log(undefined + 1)//NAN 无穷大
```

##### 空类型(null)

代表一个无、空、或者值未知的特殊值

```js
let a = null
```

```js
console.log(null+1)//1
```

#### 引用数据类型

#### 检测变量的数据类型

使用typeof关键字

```js
let num = 10
console(type of num)//number
```

`null` 在内存中表示为全零(0x00)，因此它的类型标签也是 000，与对象相同，所以 `typeof` 返回 "object"。

```js
let a = null
console.log(typeof a)//object
```

### 类型装换

使用表单、prompt获取的数据默认都是字符串类型，此时不能直接进行简单运算。

需要进行合适的类型转换，以防bug。

#### 隐士转换

+号两边只要有一个是字符串，都会把另外一个转成字符串，除了+以外的算术运算符都会把致据转成数字类型。

**注意：**

+号作为正好解析可以转换成数字型

```js
console.log(+'123')//number类型123
```

#### 显示转换

转换成数字型

```js
let str ='123'
console.log(Number(str))//number类型
```

parseInt(数据)保留整数

```js
console.log(parseInt('12px'))//12
```

parseFloat(数据)保留小数

```js
console.log(parseFloat('12.14px'))//12.14
```

### 运算符

#### 算数运算符

```
+（加）  -（减）  *（乘）  /（除）  %（取余）
```

先乘除取余，后加减，又小括号先算小括号里面的

#### 赋值运算符

```js
=
+=
-=
*=
/=
%=
```

#### 一元运算符

```
正负号
```

#### 三元运算符

```js
const message = isMember ? '欢迎回来!' : '请注册!'
```

#### 比较运算符

```js 
==   左右两边的值是否相等
===  左右两边是否类型和值都相等
!==  左右两边是否不全等
```

**开发中推荐使用===**

NaN不等于任何值，包括它本身。

#### 逻辑运算符

```js
逻辑与 &&  两边都为真才是真
逻辑或 ||  两边有一个为真就是真
逻辑非 !   取反
```

#### 运算符优先级

![image-20250528203937202](D:\github\qianduan_learn\js\js学习.assets\image-20250528203937202.png)

### 语句

![image-20250528204341801](D:\github\qianduan_learn\js\js学习.assets\image-20250528204341801.png)

#### 分支语句

```js
if(){}
```

```js
if(){}else{}
```

```js
if(){}
else if(){}
else if(){}
else if(){}
......
else {}
```

```js
 switch (表达式) {
   case 值1:
     代码1
     break
   case 值2:
     代码2
     break
   ...
   default:
     代码n
 }
```

#### 循环语句

`continue`  中止本次循环，一般用于排除或者跳过某一个选项的时候

`break`   中止整个循环，一般用于结果已经得到, 后续的循环不需要的时候可以使用（提高效率） 

##### while循环

```js
while (条件表达式) {
   // 循环体    
}
```

##### for循环

```js
for(变量起始值;终止条件;变量变化量){
  //循环体
}
```

### 数组

属于对象类型。

#### 声明数组

```js
let classes = [];
```

```js
let classes = ['小明', '小刚', '小红', '小丽', '小米']
```

#### 获取数组的元素

```js
classes[0] - classes[4]
```

注意js的数组可以存放混合类型

```js
let mixin = [true, 1, false, 'hello']
```

#### 获取数组长度

```js
let mixin = [true, 1, false, 'hello']
console.log(mixin.length)
```

#### 常用操作数组（重点）

##### push

动态向数组的尾部添加一个元素

##### unshit

动态向数组头部添加一个元素

##### pop

删除最后一个元素

##### shift

删除第一个元素

##### splice

动态删除任意元素

##### reverse

反转元素

##### slice

浅拷贝数组

```js
    <script>
        let array = ['zhangsan',123,'aaa']
        console.log('array:',array);

        //尾部添加元素
        array.push('李四')
        console.log('push后array:',array);

        //动态像数组头部添加一个元素
        array.unshift('王五')
        console.log('unshift后array:',array);

        //删除最后一个元素
        array.pop();
        console.log('pop后array:',array);

        //删除第一个元素
        array.shift()
        console.log('shift后array:',array);

        //动态删除任意元素
        array.splice(1,1)//从索引为1的位置开始删除一个元素
        console.log('splice后array:',array);
    </script>
```

![image-20250529071021308](D:\github\qianduan_learn\js\js学习.assets\image-20250529071021308.png)
