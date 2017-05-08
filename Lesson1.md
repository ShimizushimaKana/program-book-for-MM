# 第一课：让电脑说我爱你

嗯，咳。

原谅我这么一本正经，事实上我也觉得很尴尬。

想了很久，还是打算写这样一份教程。

你应该知道，你的男朋友（或者说是未来的老公）是个程序员，还是最笨的那种。

想了好久，还是决定要教你学着怎么写程序。

那就从这里开始吧！

## 计算机的语言

正如世界上有汉语、英语、日语还有韩语一样，计算机世界也有很多种语言。

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

先别说看不懂，我其实也没指望你能看懂。

我们要说的，是一门名叫 Python 的语言。

目前 Python 最新的版本为 3.5

## 废话少说，我们开始。

### 准备环境

首先我们要先安装 Python 的运行环境。

#### 1. Windows

首先去下载 Python 的安装包，然后运行。

一路“ Next ”到底就 OK 了，不会有捆绑软件的。

#### 2. OSX  
[TODO]

苹果的 OSX 是自带一个 Python 环境的，但并不是最新的版本。

#### 3. Linux
几乎所有的 Linux 发行版都会自带 Python ，如果需要，可以使用如下命令：

Ubuntu/Debian:
```bash
$ sudo apt-get install python3
```

Fedora:

最新版本的 Fedora 已经自带 Python 3

事实上，一个**称职**的男朋友应该提前为你准备好一切了。

### 启动Python环境

1. Windows启动方法
[Windows启动方法]

2. Linux 和 OSX

### 书写你的第一个程序

现在你可以在屏幕上输入下面的内容：

```python
print('I Love you~')
```

然后保存，按键盘上的`F5`执行这个程序。

看到了什么？

这里的`print()`是一个**函数**，作用是将括号内的内容显示到屏幕上。

记得吧，写作文的时候，某个人说的话要用引号括起来，在这里也是，“I Love you~”也要用引号括起来，不然的话，电脑就该犯迷糊了：

```
  File "Lesson1.py", line 3  
    print(I Love you~)  
               ^  
SyntaxError: invalid syntax
```

上面这个例子就是这样，如果不用引号将“I Love you~”括起来的话，程序就会报错，并指出出错的语句。

上面的“I Love you~”我们称为**字符串**，顺带说一句，在Python中，使用单引号（'）和双引号（"）效果是一样的。

### 让我们把程序升级一下

上面的程序只是能让计算机说一句固定的话，如果想让他说不同的话，就得修改这个程序，总之还是很麻烦吧？

下面我们将程序升级一下。

```python
name = input('想对谁说呢？')  # 输入语句
print('I Love you~', name)
```

上面程序中的`name`我们称为**变量**；后面的`=`可不是数学中的“等于”，我们称为**赋值号**，作用是将右边的值传递给左边的变量；后面的`input()`函数，作用是给出一个提示信息（就是括号里面的那个字符串），然后等待键盘输入，将键盘输入作为它的一返回值。所以这一条语句的意思是，将键盘输入的内容赋值给name这个变量。

关于变量，这里要说一下起名的规则：

1. 只允许字母，数字，下划线（_）
2. 数字不能作为变量名的第一个字符
3. 不能其他的变量、函数（如print、input、open）、关键字（如while、if、True、False）重名

然后你会看到，在`print()`函数里面，我将name放到了“I Love you~”的后面，用一个逗号（,）分隔，这样计算机会按顺序将这两个内容输出到屏幕上，并在这两个字符串之间添加空格。

还有一个东西你应该也注意到了，就是`#`号。以这个符号开头的内容我们称为**注释**。注释是给人看的，计算机会忽略掉注释的内容。一般我们会将注释加在一条语句的后面，或者单独占用一行。

当然，这个地方其实还有很多种方法。

```python
print('I Love you~' + name)  # 拼合字符串，这个比较常用
print('I Love you~{0}'.format(name))  # 使用字符串的format()方法，将{0}替换
print('I Love you~{who}'.format(who=name))  # 使用字符串的format方法，将{who}替换
```

有一点要注意，以上3种方法，不会在字符串之间添加空格。

好了，第一课就讲到这里了，让我们完成一个作业吧

* 让计算机说“xx喜欢xx”
