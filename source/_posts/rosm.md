---
title: ubunu16.04安装matlab2017a
date: 2017-03-27 16:23:52
tags: 
- matlab
- ros
categories:
- 工具
---
  ![](/images/Matlab.png)
 
1. 网上下载matlab2017a_linux文件，通常包含两个iso文件： R2017a_glnxa64_dvd1.iso  R2017a_glnxa64_dvd2.iso
2. 挂载到某个文件目录下，如home下建立一个matlab文件夹
   `sudo mount -t auto -o loop R2017a_glnxa64_dvd1.iso matlab/`
3. 运行安装文件   
   `sudo /home/song/matlab/install`
4. 按照 R2017a_glnxa64_dvd1 中readme.txt的步骤安装。
5. 在安装到提示插入DVD2时   
   `sudo mount -t auto -o loop R2017a_glnxa64_dvd2.iso matlab/`   
    
7. 运行 sudo matlab 载入.lic文件     
8. 链接相对路径      
 `cd  /usr/local/MATLAB/R2017a/bin`  
 `sudo chown song -R ~/.matlab`   
 `sudo ln -s /usr/local/MATLAB/R2017a/bin/matlab /usr/local/bin/matlab`
9. 添加快捷方式，图标即为本文的图标    
 `sudo gedit /usr/share/applications/Matlab.desktop`   
    输入   
   <code> [Desktop Entry]   
    Type=Application   
    Name=Matlab   
    GenericName=Matlab 2017a   
    Comment=Matlab:The Language of Technical Computing   
    Exec=sh /usr/local/MATLAB/R2017a/bin/matlab -desktop    
    Icon=/usr/local/MATLAB/Matlab.png   
    Terminal=false
    Categories=Development;Matlab;</code>      
1. 更改执行权限   
    `sudo chmod a+x Matlab.desktop`   
    搜索栏内便有了快捷方式
   
**Note:**如果没有找到安装包，可以通过留言或者邮件联系我。 ^_^


　　
　　