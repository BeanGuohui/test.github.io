---
layout: post
title: 变量和简单数据类型(Python编程 从入门到实践)
date: 2019-8-27
excerpt: "使用方法修改字符串的大小"
tags: [python]
comments: true
---

[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>

### 2.3.1使用方法修改字符串的大小
{% highlight ruby %}

name = "ada lovelace"
print(name.title())
{% endhighlight %}

title以首字母大写的方式输出。
{% highlight ruby %}
bicycles = ['one','two','three','four']

name = "ada lovelace"
print(name.upper())	//以全部为大写的格式输出
print(name.lower())	//以全部为小写的格式输出
{% endhighlight %}

### 2.3.2合并字符串

{% highlight ruby %}

first_name="Mr."
last_name="Bean!"
full_name=first_name + last_name
print(full_name.upper())
print(full_name.lower())
print(full_name.title())

{% endhighlight %}

### 2.3.3使用制表符或换行符来添加空白
{% highlight ruby %}

print("\nlanguage\tPython!")
{% endhighlight %}

### 2.3.4删除空白
删除结尾的空白 restrip()
{% highlight ruby %}

>>>favorite_language = "python "
>>>favorite
‘python ’
>>>favorite_language.rstrip()
‘python’
>>favorite_language
'python '
{% endhighlight %}

在使用方法rstrip()的时候，只是在输出的时候去掉字符串最后面的空格，变量的内容不变；
想要改变这一现象可以myname=myname.rstrip

删除开头的空白 lstrip()

此方法的使用方式和上述中的restrip()一致。


### 2.3.5单引号和双引号之间的差错
此类容和C++的用法注意点一致。

### 2.3.6 print 语句

print相较于printf简单了许多。此处不再赘述。

### 2.4 数字

需要注意的一点在于：python使用两个乘号代表乘方运算，其余的不再赘述。

### 2.4.3 使用函数str()避免类型错误
{% highlight ruby %}

age = 23
message = "Happy " + age + "rd Birthday!"
print(message)
{% endhighlight %}
此时运行程序会出错，因为python无法判断age是什么类型的参数，int or string？
so,you should add this str(),this mains that age is string;
如下所示
{% highlight ruby %}

age = 23
message = "Happy " + str(age) + "rd Birthday!"
print(message)
{% endhighlight %}
### 2.4.4 python中的这个数除法

这里需要注意了，在python2中3/2=1，注意这里不是四舍五入，而是直接删除小数，要留下小数请用3.0/2 or 3/2.0 or 3.0/2.0
在pythin3中3/2=1.5

### 2.5 注释

"#",这个东西将直接有着 "//" 的功能


### 2.6 重头戏，python之禅

请在CMD中敲击import this (python之禅)
{% highlight ruby %}

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!

{% endhighlight %}
翻译

美 优于 丑

明确 优于 隐晦

简单 优于 复杂

复杂 也好过 繁复

扁平 优于 嵌套

稀疏 优于 拥挤

可读性很重要

固然代码实用与否 比洁癖更重要，

我们以为的特例也往往没有特殊到必须打破上述规则的程度

除非刻意地静默，

否则不要无故忽视异常

如果遇到模棱两可的逻辑，请不要自作聪明地瞎猜。

应该提供一种，且最好只提供一种，一目了然的解决方案

当然这是没法一蹴而就的，除非你是荷兰人

固然，立刻着手 好过 永远不做。

然而，永远不做 也好过 不审慎思考一撸袖子就莽着干

如果你的实现很难解释，它就一定不是个好主意

即使你的实现简单到爆，它也有可能是个好办法

命名空间大法好，不搞不是地球人！

 内容和书本上的有所纂改，但是大致一样，都是总结，有问题请留言！！！