---
layout: post
title: 折腾Jekyll之Liquid
date: 2017-07-22 16:09:00 +08:00
tags: [Jekyll]
---

# 写在开始

因为最近在折腾`GitHub Pages`,所以顺便看了一下`Jekyll`.这里主要说一下`Liquid`这个语言.

# 关于Jekyll

官网上如是说:

> Jekyll 是一个简单的博客形态的静态站点生产机器。它有一个模版目录，其中包含原始文本格式的文档，通过一个转换器（如 Markdown）和我们的 Liquid 渲染器转化成一个完整的可发布的静态网站，你可以发布在任何你喜爱的服务器上。Jekyll 也可以运行在 GitHub Page 上，也就是说，你可以使用 GitHub 的服务来搭建你的项目页面、博客或者网站，而且是完全免费的。

看这架势这个东西似乎是依仗着`GitHub Pages`才火起来的,不过真的说是用的话其实还是挺好用的.

# 关于Liquid

这是一个模板语言,按照我的理解的话就是一个写在HTML里面预编译的一个语言,然后个人感觉就是动态性比PHP差一点,其他的感觉和PHP那一类的语言差不多,不过PHP的代码是写在`<php></php>`里面的,而这个Liquid是写在哪里都行的.然后就是这个Liquid语言是在你加载页面之前就已经执行完的了,而不是像PHP那样子的当你加载页面的时候执行PHP生成HTML网页.整体来说就是这样吧.

# 基本语法

Liquid的语句都是包在双花括号或者花括号百分号中的.
然后下面是一些常见的标记

> assign - 赋值给某个变量Assigns some value to a variable

> capture - 可将文本捕获到变量中的块标签 Block tag that captures text into a variable

> case - Block tag, its the standard case...when block

> comment - Block tag, comments out the text in the block

> cycle - Cycle is usually used within a loop to alternate between values, like colors or DOM classes.

> for - For loop

> if - Standard if/else block

> include - Includes another template; useful for partials

> raw - temporarily disable tag processing to avoid syntax conflicts.

> unless - Mirror of if statement

其实我并不知道几个,知道一个`include`是导入东西用的,可以直接导入一个HTML文档,然后`if`是一个条件判断,`for`是一个循环,都是类似于Python风格的语句(可能是因为是Ruby的Jekyl的原因).

然后是一些标准过滤器:

> date - 格式化日期 (syntax reference)

> capitalize - 将输入句子中的单词大写

> downcase - 将输入字符串转为小写

> upcase - 将输入字符串转为大写

> first - 获取传递的数组中的第一个元素get
the first element of the passed in array

> last - 获取传递的数组中的最后一个元素

> join - join elements of the array with certain character between them

> sort - 数组元素排序

> map - map/collect an array on a given property

> size - 返回字符串或者数组的大小

> escape - 转义字符串

> escape_once - 返回转义版的html，并且不影响已存在的转义实体(escaped entities)

> strip_html - 剔除字符串中的html(strip html from string)

> strip_newlines - 剔除字符串中所有的换行符(\\n)

> newline_to_br - 将字符串中换行符替换成html断行(<br>)

> replace - replace each occurrence e.g. barbar #=> 'barbar'

> replace_first - replace the first occurrence e.g. foobar #=> 'foobar'

> remove - remove each occurrence e.g. barbar #=> 'barbar'

> remove_first - remove the first occurrence e.g. bar #=> 'bar'

> truncate - 将字符串截断为x个字符

> truncatewords - 将字符串截断为x个字(主要用来处理多字符的字，比如CKJ的字符集)

> prepend - 向前追加一个字符串 例如: foobar #=> 'foobar'

> append - 向后追加一个字符串 e.g. foobar #=> 'foobar'

> minus - 减subtraction e.g. 2 #=> 2

> plus - 加addition e.g. 2 #=> '11', 2 #=> 2

> times - 乘multiplication e.g 20 #=> 20

> divided_by - 除division e.g. 5 #=> 5

> split - 以给定的模式分隔字符串 e.g. ab #=> ['a','b']

> modulo - 求余remainder, e.g. 1 #=> 1

这些就当作API文档放在这里吧,也就是现用现查了.

然后就是一些规则,所有的语句都在双花括号和花括号和百分号里面,而且每一个这个里面只有一个语句,这个设定很奇怪,但是应该是当做标记吧.

还有一个就是`for`后面带着`endfor`,`if`后面带着`endif`,`else if`性质的语句写作`elsif`,需要写的基本语法应该就这些了吧,`when`没搞懂,应该类似于kotlin里面的那个when,但是估计我也用不着太多,所以就不看了.

# 写在最后
这个篇主要是写一些API,应该是说这些东西我也就用一点,更多的时候我会倾向于用Coffee来解决这些问题.
