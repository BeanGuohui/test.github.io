---
layout: post
title: MFC简单划线
date: 2019-08-16
excerpt: "简易画图."
tags: [MFC]
comments: true
---

[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>

 在电脑中绘图，我们首先需要思考的事情是电脑会怎么做。

 首先，当鼠标左键点下去的那一时刻，屏幕会扑捉到用户点击的坐标，此时用户不松开鼠标左键在屏幕上面移动就形成了线，当用户松开鼠标，系统会扑捉到用户松开鼠标的坐标点，此时代表划线结束。

 步骤：

1）创建项目：文件——新建——项目——MFC应用程序

<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816110726757-1399722526.jpg"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816110726757-1399722526.jpg"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>
 



 

 点击确定

 

<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816110804885-986349348.png"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816110804885-986349348.png"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>
 

点击下一步，这一步有两个需要改变的地方

 
<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816110912430-1616895132.jpg"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816110912430-1616895132.jpg"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>


 

之后点击完成，如果不小心点成下一步的话也没有关系，后面的一直下一步，或者点击完成就好！创建成功！！！

 

2）工作：

 

<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816111735296-973612497.png"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816111735296-973612497.png"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>

 

 

 在旁边的工具栏里面，默认打开的是类视图，选择类视图

 

<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816112018692-1746966001.png"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816112018692-1746966001.png"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>
 

 

 
点击下方的1箭头所指的“属性”，再找到2箭头所指的WM_LBUTTONDOWN,点击右边的空行，会出现如图所示，点击<Add>OnLButtonDown

 
<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816112416920-78982049.png"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816112416920-78982049.png"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>



之后就会出现如图所示的样子

<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816121241730-1017869784.png"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816121241730-1017869784.png"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>
 

接下来要做的就是测试一下我们的鼠标按下是不是真的有效

所以在里面添加代码： MessageBox(TEXT("这是框架！"));//这句话的意思是弹出一个对话框，里面的内容为“这是框架！”


<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816121241730-1017869784.png"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816121241730-1017869784.png"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>

 

 按F5键运行，事实上能够运行出来，但是当按下鼠标左键的时候却没有任何的反应，那么这是为什么呢？

 

接下来我们以同样的方法在类视图中选择


<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816121522380-1856383709.png"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816121522380-1856383709.png"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>

CLineationView,这个类的意思是视图类，以同样的方法添加函数WM_ONBULLTONDOWN;

之后再在里面天价代码：MessageBox(TEXT("视图类！"))；//以对话框的样式弹出“视图类！”；

之后按F5键，得到如图所示的东东：
<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816121933699-1889180479.png"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816121933699-1889180479.png"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>


 

这说明一个什么样的问题呢？就像盖房子一样，首先要有框架，之后添上砖头，再涂上水泥和颜料。

而我们第一次添加的CMainFrame就是在框架里面写东西，现在的CLineationView就是在外面涂刷的白漆上面写东西。试问你认为能在哪里看到这个消息呢，是看到砖头里面，还是白漆上面呢？(This my view,so this is possible wrong!)

接下来我们要做什么？那就是删除掉框架里面刚刚写的东西！

你想一行一行删除？不，不用这么麻烦，

 鼠标放在CMainFrame上面， 右键点击类向导 找到方法 然后选择你要删除的函数 删除就可以了；（目前我知道的是这种方法，如果你有更方便的可以交流一下）

 

接下来就要开始完成最终的部分了：

首先注释掉你在view视图类里面的messagebox函数；

接着写

在view类的名字上面左键， 添加，添加函数，类型：CPoint，变量名：m_ptOrigin，私有成员。创建之后系统会自动生成初始化的数据的代码，之后： 

 

HDC hdc;
hdc = ::GetDC(m_hWnd);
MoveToEx(hdc, m_ptOrigin.x, m_ptOrigin.y, NULL);
LineTo(hdc, point.x, point.y);

 

::ReleaseDC(m_hWnd, hdc);//释放hdc


<figure>
	<a href="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816172946912-495837990.png"><img src="https://img2018.cnblogs.com/blog/1680878/201908/1680878-20190816172946912-495837990.png"></a>
	<figcaption><a href="" title=""></a>.</figcaption>
</figure>
 

 HDC是绘图的一个类型，getdc是得到当前多要绘图窗口的句柄，之后呢movetoex就是鼠标左键不断移动的新的一个地址，也就是画线两点中的起始点。你可以注释掉这句话再运行就会明白了。

而下面的lineto就是划线了，它会把两点连接起来画一条直线。最后的releasedc就是释放掉hdc，避免内存泄漏。

自己动手试一下吧，你将会发现新的问题哦！！！！