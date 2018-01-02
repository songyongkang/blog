---
title: python程序的打包
date: 2016-04-15 11:20:54
tags: 
- python
categories:
- 工具
---

自己写了一个小脚本，但是想运行它的机器没有安装python，这才真正接触了python打包程序。
开始时想用Py2exe,操作比较简单，方便后来人参考。

[py2exe参考文档](http://www.py2exe.org/index.cgi/Tutorial)


1. 首先下载[Py2exe](http://sourceforge.net/projects/py2exe/files/py2exe/0.6.9/)
2. 编写python

```python
#!/usr/bin/python
print "hello world"
```
3. 编写setup脚本

```python
#!/usr/bin/python
from distutils.core import setup
import py2exe
setup(console=['hello.py']
```   
4. 打包程序,在命令窗口中键入：

```Python 
setup py2exe
```
5. 测试打包程序：
```cmd
C:\Users\dell\Desktop\hello\dist>hello.exe
hello world
```
证明程序可以正确运行。
此外，还有一个比较流行的插件就是: pyinstall:

1. 下载并解压：[PyInstaller]( http://www.pyinstaller.org/)
2. 去SourceForge 上面下载[扩展插件](http://sourceforge.net/projects/pywin32/?source=directory)
3. 然后编译Python 源码程序即可：
```cmd
pyinstall.py --console --onefile source.py
```