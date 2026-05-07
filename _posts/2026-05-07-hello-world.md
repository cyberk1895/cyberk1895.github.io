---
layout: post
title: "Hello World！"
tags: [Blog, Jekyll, Notes, Markdown]
---

Hello World！这是我的第一篇文章，后续将分享代码、科研、工程和读书笔记等内容

## 代码块

Jekyll 使用 Rouge 做语法高亮，适合记录真实代码：

```cpp
#include "fvCFD.H"

int main(int argc, char *argv[])
{

    #include "setRootCase.H"

	// OpenFOAM screen output is very similar to rudimentary C++ with its std::cout, std::nl and std::endl
	// being replaced with Foam::Info, Foam::nl, and Foam::endl. 
    Info << "Hello World, I'm an OpenFOAM program!" << nl << endl;

    Info<< "End\n" << endl;

    return 0;
}
```

```cpp
#include <iostream>
int main()
{
    std::cout << "Hello world!" << std::endl;
    return 0;
}
```

## 表格

| 场景 | 建议 |
| --- | --- |
| 短笔记 | 直接写成一篇 post |
| 未完成内容 | 放入 `_drafts` |
| 长文档 | 按主题拆成多篇文章 |

## 命令

```bash
ls
```

## 中文
中文测试

## English
English test

## 数学公式
$f(x) = x^2 + 2x + 1$

$$\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$$

<br>

$$
    \begin{align}
    f(x) &= ax^2 + bx + c \\
    f'(x)  &= 2ax + b \\
    f''(x)  &= 2a
    \end{align}
    $$

## 图片

![waving-robot]({{ site.baseurl }}/assets/images/waving-robot.png)

## gif动图

![jim-carrey]({{ site.baseurl }}/assets/images/jim-carrey-typing-on-keyboard.gif)





本地预览确认无误后，再提交到 GitHub 仓库。
