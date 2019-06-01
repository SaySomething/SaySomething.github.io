---
title: Markdown语法总结
date: 2019-05-31 08:53:29
categories:
- 工具类知识
tags:
- Markdown
---

我认为Markdown语法算是html语言的一种语法糖，所以是兼容html语言的。
## 一.标题
##### 1. 两个= 或者两个- 对应1、2阶标题

    This is an H1(=最高阶标题)
    ==
    This is an H2(-第二阶标题)
    --
对应效果：
>This is an H1(=最高阶标题)
==
>This is an H2(-第二阶标题)
--

##### 2.在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶
```
# 这是 H1
## 这是 H2
###### 这是 H6
```
对应效果
># 这是 H1
>## 这是 H2
>###### 这是 H6

___
<br/>

## 二.区块引用 Blockquotes

##### 1.每行话前都加>

\> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
\> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.

对应的效果如下：
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.

##### 2.整个段落的第一句话前加>

\> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse id sem consectetuer libero luctus aqipiscing.

对应的效果如下：
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse id sem consectetuer libero luctus aqipiscing.

##### 3.区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的,注意中间加个>分割。
```
> This is the first level of quoting.
>
> > This is nested block quote.
>>>递减时中间加个>，如果不加的话，会一直保持最后的缩进
> 
>>This is nested block quote.
> Back to the first level.
```
> This is the first level of quoting.
>> This is nested block quote.
>>>递减时中间加个">"，如果不加的话，会一直保持最后的缩进
>
>>This is nested block quote.
> Back to the first level.

##### 4.引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：
```
> ### 这是一个标题。
> 1.  这是第一行列表项。
> 2.  这是第二行列表项。

> 给出一些例子代码：
> 
>    return shell_exec("echo $input | $markdown_script");  (最前边要有4个空格)
```
对应效果：
> ## 这是一个标题。
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。

> 给出一些例子代码：
> 
>     return shell_exec("echo $input | $markdown_script");

___
<br/>
## 三.列表

Markdown 支持有序列表和无序列表。
##### 1.无序列表使用星号、加号或是减号作为列表标记：
```
* Red    
- Green
+ Blue
```
>* Red
>- Green
>+ Blue

##### 2.有序列表则使用数字接着一个英文句点:
```
1. Bird   
2. McHale
3. Parish
```
>1.  Bird
>2.  McHale
>3.  Parish

你可以完全不用在意数字的正确性，建议第一个项目最好还是从 1. 开始。
____
<br/>

## 四.代码区块
##### 1.使用 `<pre>` 和 `<code>` 标签来把代码区块包起来
```
<pre> 代码块 </pre>
<code>单行代码</code>  
```
效果如下：
<pre> 代码块格式 </pre>
<code>单行代码格式</code>
##### 2.使用反引号“\`”包单行代码
  
    `单行代码格式`  
`单行代码格式` 

##### 3.代码区使用反引号 "\`" 的方式就是用 "\`\`" 将 "\`" 包起来。
```
A single backtick in a code span: `` ` ``
A backtick-delimited string in a code span: `` `foo` ``
```
转换成的效果如下：
>A single backtick in a code span: `` ` ``
>A backtick-delimited string in a code span: `` `foo` ``

##### 4.使用三个反引号"\`\`\`"包代码块，且前后的3个反引号各占一行。
    ```
    代码块
    ```
效果如下
```
代码块
```

##### 5.也可以只要简单地缩进 4 个空格或是 1 个制表符就可以。
```
    这是一个代码区块。
```
Markdown 转换成如下效果：

    这是一个代码区块。
且每行一阶的缩进（4 个空格或是 1 个制表符），都会被移除。一个代码区块会一直持续到没有缩进的那一行（或是文件结尾）。
##### 6.代码块内特殊字符不会起作用。
代码区块中，一般的 Markdown 语法不会被转换，像是星号便只是星号，这表示你可以很容易地以 Markdown 语法撰写 Markdown 语法相关的文件。
____
<br/>

## 五.分割线
你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：
\* \* \*

\*\*\*

\*\*\*\*\*

\- - -

\---------------
>---

___
<br/>

## 六.文字样式
##### 1.强调，Markdown 使用星号（\*）和底线（\_）作为标记强调字词的符号，效果如下：
```
*single asterisks斜体*    
_single underscores斜体(有的是下划线)_
**double asterisks粗体**
__double underscores粗体__
```
会转成：
> *single asterisks斜体*
> _single underscores斜体(有的是下划线)_
> **double asterisks粗体**
>__double underscores粗体__

你可以随便用你喜欢的样式，唯一的限制是，你用什么符号开启标签，就要用什么符号结束。

##### 2.强调也可以直接插在文字中间：

un\*\*frigging\*\*believable

>un**frigging**believable 

##### 3.文本两端增加\~\~可以作为删除线：
```
~~DeleteLine~~
```
转换的效果如下:
~~DeleteLine~~

##### 4.文本两端增加\=\=可以作为高亮(Hexo不支持)：
```
==高亮==
```
==高亮==
 
##### 5.上下标文字：
```
这是^上标文字 (Hexo不支持)
这是<sup>上标文字</sup>
这是<sub>下标文字</sub>
```
>这是^上标文字
这是<sup>上标文字</sup>
这是<sub>下标文字</sub>

___
<br/>

## 七.反斜杠

Markdown 可以利用反斜杠来插入一些在语法中有其它意义的符号，比如：
\\* literal asterisks \\\*
转换成的效果如下(*只是展示没有转成斜体的语法)：
>\*literal asterisks\*

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：
```
\ 反斜线;  ` 反引号;  * 星号;  _ 底线;  {} 花括号;  [] 方括号;  () 括弧;
# 井字号;  + 加号;  - 减号;  . 英文句点;  ! 惊叹号;
```
___


## 八.表格

表格的样式最重要的就是第二行的占位符。
```
文本类型 | 文本类型| 文本类型
:-----|:------:|-----:
居左文本 | 居中文本 | 居右文本
```
>文本类型 | 文本类型| 文本类型
>:-----|:------:|-----:
>居左文本 | 居中文本 | 居右文本

___
<br/>

## 九.超链接
Markdown 支持两种形式的链接语法： 行内式和参考式两种形式。不管是哪一种，链接文字都是用 [方括号] 来标记。
##### 1.行内式的链接。
```
这是 [百度](http://baidu.com/ "百度") 的链接，这也是[百度](http://baidu.com/) 链接.
```
转换成的效果如下：
>这是 [百度](http://baidu.com/ "百度") 的链接，这也是[百度](http://baidu.com/) 链接.

##### 2.可使用相对路径链接到相同主机的资源。
See my [本地资源名]\(/相对路径/) page for details.

转化成的效果如下: 
>See my [本地资源名](/相对路径/) page for details.

##### 3.参考式链接,需要链接内容配合。
```
This is [百度][百度ID] reference-style link. 
This is [百度] [百度IDI] reference-style link.( 两个方括号之间加个空格键也可以)

（链接内容，通过ID链接，链接内容会隐藏）
[百度ID]: http://baidu.com/  "百度Title"
[百度IDI]: http://baidu.com/  
```
转换成的效果如下：
>This is [百度][百度ID] reference-style link. 
This is [百度] [百度IDI] reference-style link.( 两个方括号之间加个空格键也可以)

[百度ID]: http://baidu.com/  "百度Title"
[百度IDI]: http://baidu.com/

____
<br/>

## 十.图片
Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： 行内式和参考式。

##### 1.行内式的图片语法：
```
![图片下方文字](图片地址 "图片title") 

![bloakChain](https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/
u=702257389,1274025419&fm=27&gp=0.jpg)
```
>![图片下方文字](图片地址 "图片title") 
![bloakChain](https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/
u=702257389,1274025419&fm=27&gp=0.jpg)

图片title可有可无。有些语法图片下方文字不展示。

##### 2.参考式的图片语法：
```
![bloakChain][imageId]

[imageId]: https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/
u=702257389,1274025419&fm=27&gp=0.jpg "区块链"
```
>![bloakChain][imageId]

[imageId]: https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=702257389,1274025419&fm=27&gp=0.jpg "区块链"

到目前为止， Markdown 还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的 `<img>` 标签。

____
<br/>

## 十一.脚注和注释（Hexo 不支持）
##### 1.使用`[^]`定义脚注，示例如下：
```
脚注[^1]为什么在上边？
[^1]: 因为这个注释会在文章的最后出现
```
脚注[^1]为什么在上边？
[^1]: 因为这个注释会在文章的最后出现

##### 2.注释只在文本编辑时出现：
```
<!--注释-->
```
右侧使用了注释，但你看不见：<!--注释-->

<br/>

## 十二.Markdown中常用的Html标签
##### 1.字体
```
<font face="微软雅黑" color="red" size="6">字体及字体颜色和大小</font>
<font color="#0000ff">字体颜色</font>
```
效果如下：
<font face="微软雅黑" color="red" size="6">字体及字体颜色和大小</font>
<font color="#0000ff">字体颜色</font>

##### 2.换行符
```
第一行
第二行 <br/>
使用换行符号\<br>后
```
第一行
第二行 <br/>
使用换行符号`<br>`后
##### 3.文本对齐方式
```
<p align="left">居左文本</p>
<p align="center">居中文本</p>
<p align="right">居右文本</p>
```
<p align="left">居左文本</p>
<p align="center">居中文本</p>
<p align="right">居右文本</p>
##### 4.下划线
```
<u>下划线文本</u>
```
<u>下划线文本</u>
<br/>
___

## 十三.任务列表
任务列表的内容支持其他格式的markdown语法
```
- [ ] 未选中的选项 [百度链接](http://baidu.com)，__强调__
- [x] 选中的选项 
```
效果如下：
- [ ] 未选中的选项 [百度链接](http://baidu.com)，**强调**
- [x] 选中的选项 

## 十四.自动链接和目录
##### 1.自动链接
Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用方括号包起来， 就会自动把它转成链接。例如：

```
网址： <http://example.com/>
邮箱:  <address@example.com>
```
Markdown 会转为：
网址：<http://example.com/>
邮箱:   <address@example.com>

##### 2.目录
	[TOC]
	
使用TOC会自动生成目录(简书/Hexo暂不支持)
____

## 十五.流程图(Hexo 不支持)

	```flow
	st=>start: Start:>https://www.jpjbp.com/
	io=>inputoutput: verification
	op=>operation: Your Operation
	cond=>condition: Yes or No?
	sub=>subroutine: Your Subroutine
	e=>end
	st->io->op->cond
	cond(yes)->e
	cond(no)->sub->io
	&```
	
更多的流程图语言请参考：[Markdown流程图语言](http://flowchart.js.org)

转换的效果如下：
```flow
st=>start: Start:>https://www.jpjbp.com/
io=>inputoutput: verification
op=>operation: Your Operation
cond=>condition: Yes or No?
sub=>subroutine: Your Subroutine
e=>end
st->io->op->cond
cond(yes)->e
cond(no)->sub->io
&```

