# 使用SassC和Libsass编译Sass
由于某些代码在sass 3.4.21编译下会报错,而使用SassC+Libsass来进行编译则有可能通过并得到正确的结果,故纪录下如何安装SassC+Libsass.
* [Sassmeister](http://www.sassmeister.com/) - Sass官方在线编译器(编译器版本可自选)
###### 本文是基于Windows版本下的安装,其他平台请参考如下地址:
* [Compile Sass with SassC and Libsass Guide](http://mattferderer.com/compile-sass-with-sassc-and-libsass/)


# STEP-1 Git Libsass and SassC
# Step 1 - Git Libsass and SassC

先安装Git版本控制器:

[Download Git](https://git-scm.com/)

然后在命令提示符输入
```sh
git clone https://github.com/hcatlin/sassc.git
git clone https://github.com/hcatlin/libsass.git
```
# Step 2 – Compile SassC
在编译SassC之前,我们需要把Libsass library与SassC链接在一起.
用文本编辑器打开Sassc目录下的Makefile,在文件最上方添加上
```sh
export SASS_LIBSASS_PATH = libsass的路径名
```
*在输入路径的时候,发现绝对路径(如:"C:\Program Files\Git\libsass")并不能被正确识别,需要这样写
"../libsass" (sassc文件夹需要与libsass文件夹处于同一目录下).*

接下来还需要安装MinGW用来编译SassC:

[MinGw Installer](http://sourceforge.net/projects/mingw/files/)

上述只是一个MinGw安装管理器,还需要在里面选择MinGw32-base一级mingw32-gcc-g++,选上mark for installtion然后Apply Changes.

安装完MinGw之后应该可以在安装目录下面的/bin下面找到mingw32-mark,将其改名为mark并添加到系统变量PATH中.

用命令提示符进入sassc目录下面,使用mark命令来编译sassc.

等待编译完成,就可以在sassc/bin目录下看到sassc.exe了,同样将其添加进系统变量PAHT中,输入
```sh
sassc -v
```
查看sassc版本号.

输入
```sh
sassc -h
```
查看具体命令.

 ----- 01.25.2016













