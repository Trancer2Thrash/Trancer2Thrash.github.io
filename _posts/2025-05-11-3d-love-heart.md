---
layout: post
title: "3D爱心特效"
date: 2025-05-11 20:00:00 +0800
categories: 博客 技术
---

## 用数学表达爱

在这篇文章中，我想分享如何使用Python和数学公式创建一个漂亮的3D爱心图形，来源自`https://sun0225sun.github.io/Awesome-Love-Code/`

## 3D爱心效果展示

下面是我们用Python生成的3D爱心图形：

![3D爱心图形](/assets/images/3d_heart.png)

*使用Python和matplotlib创建的3D爱心*

## 实现原理

这个3D爱心是通过一个隐函数绘制的，数学表达式如下：

$$(x^2 + \frac{9}{4}y^2 + z^2 - 1)^3 - x^2z^3 - \frac{9}{80}y^2z^3 = 0$$

这个方程描述了一个类似心形的三维曲面。

## Python实现代码

我使用了Python的matplotlib和NumPy库来实现这个效果。以下是关键代码：

```python
import matplotlib.pyplot as plt
import numpy as np

def heart_3d(x, y, z):
    return (x**2 + (9/4)*y**2 + z**2 - 1)**3 - x**2*z**3 - (9/80)*y**2*z**3

def plot_implicit(fn, bbox=(-1.5, 1.5)):
    xmin, xmax, ymin, ymax, zmin, zmax = bbox * 3
    fig = plt.figure()
    ax = fig.add_subplot(111, projection='3d')
    
    # 设置网格
    A = np.linspace(xmin, xmax, 100)
    B = np.linspace(xmin, xmax, 40)
    A1, A2 = np.meshgrid(A, A)
    
    # 在不同平面绘制轮廓
    for z in B:
        X, Y = A1, A2
        Z = fn(X, Y, z)
        ax.contour(X, Y, Z + z, [z], zdir='z', colors=('red',))
        
    # 设置视图限制
    ax.set_zlim3d(zmin, zmax)
    ax.set_xlim3d(xmin, xmax)
    ax.set_ylim3d(ymin, ymax)
    
    plt.title("3D爱心")
    plt.show()
```


## 自定义你的3D爱心

你可以通过以下方式自定义你的3D爱心效果：

1. **改变颜色** - 修改`colors`参数来改变爱心的颜色
2. **调整视角** - 使用`ax.view_init(elev, azim)`来设置不同的视角
3. **增加动画效果** - 使用matplotlib的动画功能让爱心旋转

## 在自己的博客中使用

如果你也想在自己的博客中添加这样的效果，你可以：

1. 安装所需的Python库：`pip install matplotlib numpy`
2. 复制上面的代码并运行
3. 将生成的图片保存并添加到你的博客中

