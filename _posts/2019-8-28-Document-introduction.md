---
layout: post
title: 列表简介
date: 2019-8-28
excerpt: "列表是什么 this list is what?."
tags: [python]
comments: true
---

[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>

### 3.1 列表是什么 this list is what?

列表由一系列特定顺序的元素组成，例如0-9
在Python中，用方括号([])来表示列表，并用逗号来分隔其中的元素。这和C++有着区别，请留心。
{% highlight ruby %}
bicycles = ['one','two','three','four']
print(bicycles)

{% endhighlight %}
输出结果：['one','two','three','four'] 体会一下和C++的不同之处。


### 3.1.1 访问列表元素

{% highlight ruby %}

bicycles = ['one','two','three','four']
print(bicycles[0])

{% endhighlight %}
输出:one
此时不包含括号和引号。请留意。


{% highlight ruby %}

bicycles = ['one','two','three','four']
print(bicycles[0].title())

{% endhighlight %}

输出: One
细节便见语言的魅力之处。





请注意这里的元素顺序和C/C++一样，是从0开始的！
还有一个不同之处 
{% highlight ruby %}
print(bicycles[-1])
{% endhighlight %}
输出结果：three。
-1代表着列表元素的最后一个值，这和C/C++又有着不同。

### 3.13 使用列表中的各个值

{% highlight ruby %}
bicycles = ['one','two','three','four']
print(“the number is ” + bicycles[0].title() + ".........")
{% endhighlight %}
精妙

### 3.2 修改、添加和删除元素和C++一样，不再赘述。

### 3.2.2 在列表中添加元素
1.在列表末尾添加元素 .append('ducati')
{% highlight ruby %}

motorcycles = ['honda','yamaha','suzuki']
print(motorcycles)
motorcycle.append('ducati')
print(motorcycles)
{% endhighlight %}
输出结果是'honda','yamaha','suzuki，ducati'

另一种用法是可以先创建一个空列表，然后再用.append("")一个一个元素添加。
{% highlight ruby %}

motorcycles=[]
motorcycles.append("honda")
motorcycles.append("yamaha")
motorcycles.append("suzuki")
motorcycles.append("ducati)
print(motorcycles)
{% endhighlight %}
### 2.在列表中插入元素。 使用方法insert()
{% highlight ruby %}

motorcycles = ['honda','yamaha','suzuki']

motorcycles = [0,'ducati']
print(motorcycles)
{% endhighlight %}
输出结果为：['ducati','honda','yamaha','suzuki']

### 3.2.3从列表中删除元素
### 1.使用del语句删除元素
{% highlight ruby %}
motorcycles = ['honda','yamaha','suzuki']
del motorcycles[0]
print(motorcycles)

{% endhighlight %}
删除第一个元素，请自行证明。删除元素后不再以任何方式使用那个元素，请使用这种方法。

### 2.使用方法pop()删除元素
{% highlight ruby %}
nums = ['1','2','3','4']
poped_nums = nums.pop()
print(nums)//['1','2','3']
print(poped_nums)// 4
{% endhighlight %}
需要注意的是nums里面的4已经被删除，pop()删除最后一个元素的。
但是：请看下面

### 3.弹出列表中任何位置处的元素
{% highlight ruby %}
nums = ['1','2','3','4']
first_num = nums.pop(0)
print('the first_num is　'+ fist_nums)

{% endhighlight %}
此时删除的元素就是nums中的第一个了，删除后还要使用那个元素，请使用这种方法

### 4：根据值删除元素 方法remove()
{% highlight ruby %}
nums=['1','2','3']
print(nums)
nums.remove('2')
print(nums)
{% endhighlight %}
### 3.3 组织列表

### 3.3.1 使用方法sort()对列表进行永久性排序（按字母）
正序：
{% highlight ruby %}
nums = ['2','5','1','3']
nums.sort()
print(nums)
{% endhighlight %}
result: ['1','2','3','5']
倒序：
{% highlight ruby %}
nums.sort(reverse=True)
{% endhighlight %}
请读者自己实验，请注意True只能这个样子写，其他格式一律不正确。
此修改对列表是永久性的。

 

### 3.3.2 使用函数sorted()对列表进行临时排序（按字母）
{% highlight ruby %}

cars = ['bmw','audi','toyota','subaru']
print('here is the original list:')
print(cars)
print('\nhere is the sorted list:')
print(sorted(cars))
print('\nhere is the original list:')
print(cars)
{% endhighlight %}
注意：sorted()运行后对列表并没有更改。如果要反方向的输出可以使用reverse = True

### 3.3.3 倒着打印列表（按列表的排列）
{% highlight ruby %}

cars = ['bmw','audi','toyota','subaru']
print(cars)
cars.reverse()
print(cars)
{% endhighlight %}
此反转是永久有效的，如果想要反转回来，就再次使用cars.reverse();

### 3.34 确定列表的长度
{% highlight ruby %}

cars = ['bmw','audi','toyota','subaru']
len(cars)
{% endhighlight %}
注意这里没有用print,但是也能输出结果:4

### 3.4 使用列表时避免索引错误

假设你有一个包含三个元素的列表，却要求获取第四个元素，这时就会显示错误。
这和C/C++一样，不再赘述。

