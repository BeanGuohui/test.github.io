---
layout: post
title: MFC里面的一些实例应用
date: 2019-8-07
excerpt: "下面这个函数作用是读取键盘输入的按键是什么，例如：输入“x”，屏幕会弹出消息对话框“x”"
tags: [MFC]
comments: true
---

[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>

## 下面这个函数作用是读取键盘输入的按键是什么，例如：输入“x”，屏幕会弹出消息对话框“x”

{% highlight ruby %}

void CMy01MFCtestView::OnChar(UINT nChar, UINT nRepCnt, UINT nFlags)
{

TCHAR ch = (TCHAR)nChar;

CString str;

str.Format(TEXT("%c"), ch);

MessageBox(str);

CView::OnChar(nChar, nRepCnt, nFlags);
}
{% endhighlight %}
 

## 这个是当鼠标左键在窗口点击的时候，会弹出消息对话框显示鼠标左键点击的窗口的坐标值。

{% highlight ruby %}

void CMy01MFCtestView::OnLButtonDown(UINT nFlags, CPoint point)
{

CString str;

str.Format(TEXT("x=%d,y=%d"), point.x, point.y);

MessageBox(str);

CView::OnLButtonDown(nFlags, point);
}
{% endhighlight %}