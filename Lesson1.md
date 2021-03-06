# 第一课：啥事编程语言

嗯，思考了很久，然后终于把心情安稳下来，可以专心和你一起学习这门Python语言。

一直不认为自己有能力写教程什么的，但借此机会，想做出第一次尝试。

现在写第一篇教程的时间是2020年10月7日凌晨两点钟。

我想把一些概念性的东西，复述成你可以浅显理解的知识，顺便也帮助回顾记忆理顺知识。

我不知道写起来会不会一本正经，但那样也觉得很尴尬，就当作给你唠嗑了。

那就从这里开始吧！

## 计算机的语言

正如世界上有汉语、英语、日语还有韩语一样，计算机世界也有很多种语言。

计算机语言有高级和低级之分。

首先，要知道计算机是由软件和硬件多层次组成的。

低级语言，指的是汇编语言、机器语言。这种语言，是写给计算机硬件看的，比如通过一条指令发送给CPU（中央处理器），让某一硬件比如寄存器等读或者写某一个数值。它又是一种符号语言，以固定的指令集，操作着计算机硬件。

高级语言，更高级在于，是人可以看懂和表达的。可是机器看不懂啊！

我们写程序，想用自己明白的语言，操作计算机，所以怎么让计算机理解程序去做我们想要的运算呢？

实际上，它们是有层次的，比如我们用高级语言中的C语言写了一个程序，计算机通过编译器，将高级语言转化为汇编语言，计算机这就能看懂我们要它做啥了，它进一步通过汇编器，将汇编语言转变成更简单原始的机器语言——硬件读不懂文字，它只能区分0和1构成的的二进制文件。

下面举一些例子：

比如机器语言

```
  4000b0:       b8 04 00 00 00
  4000b5:       bb 01 00 00 00
  4000ba:       b9 d4 00 60 00
  4000bf:       ba 0d 00 00 00
  4000c4:       cd 80
  4000c6:       b8 01 00 00 00
  4000cb:       bb 00 00 00 00
  4000d0:       cd 80
```

还有汇编语言

```asm
section .data
    hello:      db 'Hello World!', 10
    helloLen:   equ $-hello

section .text
    global _start

_start:
    mov eax, 4
    mov ebx, 1
    mov ecx, hello
    mov edx, helloLen
    int 80h

    mov eax, 1
    mov ebx, 0
    int 80h
```

然后是更高级的C语言

```c
#include <stdio.h>

int main(int argc, char** argv){
    printf("Hello!\n");
    return 0;
}
```

然后上面大概就是我想给你讲的关于计算机组成和计算机语言的小科普，帮助你了解什么是计算机语言。

如今编程语言大约有六百多种，最热门的语言分别是C、C++（又叫C艹、Cpp（Cplusplus））、Java、Python、VB、PHP等等

这些语言根据自身特性，在各种用途需要上，发挥着不同的特长。

比如C语言在计算机系统中充分发挥硬件性能，运行速度优良。C++在游戏开发等领域占据优势。

那么对于Python来说，它的长处在于它的简单优雅。

Python为我们提供了完善的基础功能库（你可以类比微信给你提供了支付的功能)

还有大量第三方库可供使用（类比微信给你提供滴滴打车功能）

所以这是一个功能强大，封装到位，简单便捷的语言。

这是你们学习Python的第一个重要理由，因为Python有很多数据处理的库可以供你使用，并且在数据可视化方面，提供了很好的接口，所以学Python是做数据分析的很好工具。

第二个理由就很简单了，就是因为它简单，适合初学者入门。

目前 Python 最新的版本为 3.9（太离谱了，前天还是3.8来着，10月5号刚更新）

顺便一提，Python主要分为2.x版本和3.x版本（就是2开头和3开头）

意思是说，2.x版本和3.x版本语法差距较大，在很多场景代码不兼容，而现在主流都已经采用3.x版本，所以我们学习的是Python3版本

对于编程来讲，首先要在你的电脑上准备好该语言的使用环境（即下载安装配置）

手把手演示下~~~

## 那我们开始准备环境。

### 准备环境

首先我们要先安装 Python 的运行环境。

#### 1. Windows

首先去下载 Python 的安装包，然后运行。

https://www.python.org/downloads/

![avatar](https://github.com/ShimizushimaKana/program-book-for-girlfriend/blob/master/picture/lesson1-1.png)

点击下载最新的3.9版本（注意 3点几都无所谓，只要是3开头，我们的语法规范都是相同的，只不过它经常会有小更新而已）

下载完成后打开这个安装包

一路“ Next ”到底就 OK 了

但是最后一个页面要注意！一定要勾选上 Add Python 3.9 to PATH

这一步意思是直接把Python环境配置在你的电脑环境变量中了，就不需要我们另外设置了。

![avatar](https://github.com/ShimizushimaKana/program-book-for-girlfriend/blob/master/picture/lesson1-2.png)

### 启动Python环境

1. Windows启动方法

不知道你会不会用你电脑的搜索功能啊，就是最低栏会有一个放大镜🔍一样的搜索功能。如果你的系统并没有显示，这个时候请用三个手指头敲击你的触摸板。

搜索框就被你给打开了。然后输入IDLE，如图所示，我们编写Python程序的初始工具就是它。

![avatar](https://github.com/ShimizushimaKana/program-book-for-girlfriend/blob/master/picture/lesson1-4.png)

打开之后

![avatar](https://github.com/ShimizushimaKana/program-book-for-girlfriend/blob/master/picture/lesson1-3.png)

### 书写你的第一个程序

现在你可以在屏幕上输入下面的内容：

```
print('I am always there for you~')
```

然后按键盘上的`回车键`执行这个程序。

自己试一下看它的输出和形式。

程序就是这个样子的了，print就是将后面这句话打印出来的意思，于是我们得到了我们想要的输出。

至此，如果顺利完成了这步，我们就已经完成环境配置了，可以开始正式上手了。

###但是我更推荐另一个编辑器，它叫做Pycharm

IDLE是Python自带的编程工具，它十分简便易用。

但是试想一下未来的场景，你需要做数据处理的脚本程序，篇幅很长，整个程序是从头到尾连贯的，而不是一行一行书写得到结果。

所以，我们需要一般要先编写一个后缀名为.py的Python脚本文件，再对该文件进行整体执行。

显然，编写一篇较长的程序文件在IDLE这种简易命令行中是不太方便的。

PyCharm是个功能更完备，适合我们做项目工程的编译工具。在此一定要介绍。至于Jupyter，我未使用过，不是很了解。

另外也没有必要使用Visual Studio Code，我们完全可以使用Pycharm这个Python语言集成环境一步到位。

PyCharm请在https://www.jetbrains.com/pycharm/download/#section=windows 这里下载。

我们选择右面的Community社区版。点击Download。

等待下载完成后，打开，进行安装。

一路“Next”，但你可以选择换一个磁盘，除非你的C盘空间真的很大（大于30GB)

该勾的全勾就可以了。

这里具体步骤，参考这篇十分详细的文档：https://cloud.tencent.com/developer/article/1482705

最后安装成功。

那么这个编译器该如何使用，在下一篇教程或者有时间我会手把手指导你的。

总之，到此，我们环境配置的工作基本结束了，我们已经可以开始模仿教程书上的示例代码自己进行尝试了~

最后附上两篇参考教程，也希望你有时间可以自行浏览阅读，都是很适合初学者阅读学习的。

廖雪峰Python3 教程：https://www.liaoxuefeng.com/wiki/1016959663602400

Python3 教程|菜鸟教程：https://www.runoob.com/python3/python3-tutorial.html


