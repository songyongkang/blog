---
title: Sublime Text 3设为Markdown编辑器
date: 2016-04-13 18:20:54
tags: 
- sublime
categories:
- 工具
---
  ![](/images/sublime.jpg)

Sublime Text 3作为一个优秀的文本编辑器，拥有很多的扩展插件。我们可以利用这些插件为Sublime Text 增加扩展的功能。
Sublime Text支持大量插件，如何找到并管理这些插件就成了一个问题，Package Control正是为了解决这个问题而出现的，利用它我们可以很方便的浏览、安装和卸载Sublime Text中的插件。

进入Package Control的官网，里面有详细的安装教程。Package Control支持Sublime Text 2和3，本文只给出3的安装流程：

使用“Ctrl + ` ”打开Sublime Text控制台。
将下面的代码粘贴到控制台里：
```
import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by) ```
等待Package Control安装完成。之后使用Ctrl + Shift + P打开命令板，输入PC应出现Package Control：
Package Control安装成功

成功安装Package Control之后，我们就可以方便的安装使用Sublime Text的各种插件：

使用Package Control安装插件
    使用组合键 CTRL SHIFT P (Windows, Linux) 或者 CMD SHIFT P .
在输入框键入想要安装的包（MarkdownEditing)，并回车。自动安装完成后重启即可。