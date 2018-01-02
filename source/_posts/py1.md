---
title: python的GUI编程(tkinter)
date: 2016-04-15 11:20:54
tags: 
- python
categories:
- 工具
---
<h4 align = "center">Tkinter是什么</h4>
[Tkinter模块](https://wiki.python.org/moin/TkInter/)是Python内置的标准GUI工具包接口.因为python是跨平台的，所以Tk和Tkinter可以较好地运行在绝大多数平台上面。Tk8.0的后续版本甚至可以实现本地窗口风格,它属于Tcl/Tk的GUI工具组。Tcl/Tk是由John Ousterhout发展的书写和图形设备。

Tcl(工具命令语言)是个宏语言，用于简化shell下复杂程序的开发，Tk工具包是和Tcl一起开发的， 目的是为了简化用户接口的设计过程。
<h4 align = "center">Tkinter怎么用</h4>
Tk工具包由许多不同的小部件，如一个按钮、一个滚动条等。通过Tk提供的这些小部件，我们就可快速地进行GUI开发。
下面是一个小的例子：
使用Tkinter创建一个GUI应用程序是一件容易的事。所有你需要做的是执行以下步骤:


- 导入Tkinter模块.

- 创建GUI应用程序的主窗口.

- 添加上述部件之一或更多的GUI应用程序.

- 进入主事件循环的由用户触发每个事件响应.
``` python
#!/usr/bin/python
import Tkinter  #导入模块
top = Tkinter.Tk()  #创建主窗口
label = Tkinter.Label(top,text='Hello World') #创建label标签
label.pack()  #pack（）用来管理和显示组件
Tkinter.mainloop() #进入主循环

```
三，Tkinter的几何管理器。
在进行GUI编程时，放好每个组件的是很繁琐的，不仅要调整自身大小，还要
整和其他组件的相对位置。Tk提供了三个管理器来帮助我们：Pack  Grid  Place
1. pack
Pack使用很简单，就是w.pack(option)。常用的option有：
Side 表示把组件放到哪一边，TOP（上），BOTTOM（下），LEFT，RIGHT
Padx和pady  表示parcel的每一个边和组件的预留空间。
Ipadx和ipady，表示组件的每一个边和他包含的内容之间的预留空间。
Anchor表示在parcel放置组件的方式，缺省时CENTER。
2. grid
使用方法和pack类似。
3. place
精确的摆放一个组件的位置，一般不太用。
 
关于这个三个的详细使用和算法可以参考相关资料
``` python
#!/usr/bin/python
from tkinter import *  #引入模块
#resize函数是用来改变文字大小的，当进度条改变时调用
def resize(ev=None):
label.config(font='Helvetica -%d bold' % scale.get())
#config函数就是通过设置组件的参数来改变组件的，这里改变的是font字体大小
top=Tk()   #主窗口
top.geometry('600x400')  #设置了主窗口的初始大小600x400
label=Label(top,text='Hello Timesong!',font='Helvetica -12 bold')  #设置标签字体的初始大小
label.pack(fill=Y,expand=1)
#scale创建进度条，设置
scale=Scale(top,from_=10,to=40,orient=HORIZONTAL,command=resize)
scale.set(12)  #设置起始位置
scale.pack(fill=X,expand=1)
quit = Button(top,text='QUIT',command=top.quit,activeforeground='white',
activebackground='red')
quit.pack()
mainloop()
```
运行结果如下：
![](/images/gui.png)