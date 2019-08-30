---
layout: post
title: 初学MFC框架
date: 2019-7-22
excerpt: "MFC的框架分为窗口的定制、窗口类的注册、窗口的创建、窗口的显示、消息的循环与处理。以下是初学之时的代码，注释在旁边奉上：."
tags: [MFC]
comments: true
---

[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>


MFC的框架分为窗口的定制、窗口类的注册、窗口的创建、窗口的显示、消息的循环与处理。以下是初学之时的代码，注释在旁边：


{% highlight ruby %}

 #include<windows.h>

LRESULT CALLBACK WndProc(HWND,UINT,WPARAM,LPARAM);

int WINAPI WinMain(

HINSTANCE hinstance,　　//当前应用程序实例的句柄
HINSTANCE hPrevInstance,//系统中前一个应用程序实例的句柄
PSTR szCmdLine,　　　　//指向本程序命令行的指针
int nCmdShow)　　　　　 //决定应用程序窗口显示方式的标志
{
HWND hwnd;　　　　//定义窗口的句柄
MSG msg;
WNDCLASS wc;
wc.style=0;　　　　　　　　//窗口样式，一般设置为0；
wc.lpfnWndProc=WndProc;  //指向窗口函数的指针；
wc.cbClsExtra=0;　　　　　//预留的扩展成员,一般设置为0;
wc.cbWndExtra=0;　　　　 //预留的扩展成员,一般设置为0;
wc.hInstance=hinstance;      //与窗口类关联的应用程序实例句柄
wc.hIcon=LoadIcon(NULL, IDI_WINLOGO);　　　　　　　　//窗口图标句柄
wc.hCursor=LoadCursor(NULL,IDC_ARROW);　　　　　　//窗口光标句柄
wc.hbrBackground=(HBRUSH)(COLOR_WINDOW+1);　　//窗口背景颜色刷句柄
wc.lpszMenuName=NULL;　　　　　　 //窗口菜单资源名
wc.lpszClassName = "MyMFC";　　　　//本窗口类名

RegisterClass(&wc);


hwnd=CreateWindow(
TEXT("MyMFC"),　　　　　　　　//窗口类的名称
TEXT("This is my first MFC!"),　　//窗口实例的标题
WS_OVERLAPPEDWINDOW,　　//窗口风格
CW_USEDEFAULT,　　　　　　　//窗口左上角位置坐标值X

CW_USEDEFAULT,　　　　　　//窗口左上角位置坐标值Y
CW_USEDEFAULT,　　　　　　//窗口的宽度
CW_USEDEFAULT,　　　　　　//窗口的高度
NULL,　　　　　　　　　　　　//父窗口的句柄
NULL,　　　　　　　　　　　　//主菜单的句柄
hinstance,　　　　　　　　　　//应用程序实例句柄
NULL　　　　　　　　　　　　//该值通常为NULL
);

 

//窗口的显示

ShowWindow(hwnd,nCmdShow);　　//窗口的句柄.....窗口的显示方式
UpdateWindow(hwnd);　　　　　　//窗口的句柄

 

//消息循环
while(GetMessage(&msg,NULL,0,0)){
TranslateMessage(&msg);　　//调用解释键盘消息API函数
DispatchMessage(&msg);　　//调用消息发送API函数将消息发送给系统
}

return msg.wParam;


}
LRESULT CALLBACK WndProc(HWND hwnd,　　　　//派送消息的窗口句柄
UINT message,　　　　　　　　//系统传递来的消息标识
WPARAM wParam,　　　　　　//消息的附加参数(32位)

LPARAM lparam　　　　　　　//　消息的附加参数(32位)
)
{
switch(message)
{
case WM_LBUTTONDOWN:
MessageBeep(0);

retur 0;
case WM_DESTROY:
PostQuitMessage(0);　　　　//调用关闭主窗口函数
return 0;

}
return DefWindowProc(hwnd,message,wParam,lparam);
}
{% endhighlight %}