---
html:
  embed_local_images: true
  embed_svg: true
  offline: true
  toc:  undefined

print_background:  false
export_on_save:
  html: false
data:  2019/ 1/ 29
updated: 2019/ 2/ 17
---

# 环境

1. python版本：3.7
2. win10
3. matplotlib：3.0.2
4. pycharm 18.2.4

> 读完数据之后，又想要显示一下，所以网上搜了搜看到了matplotlib，操作简单，和matlab使用相似，所以决定一试。在此记录。

# 简单入门

## 安装matplotlib库

``` bash
>>> pip install matplotlib
```

## 引用模块

``` python
import matplotlib.pyplot as plt
```

## 简单绘制——plot(轴域)

``` python
plt.plot([1,2,3,4],[2,3,4,5],"-") # x坐标为 第一个数组， y坐标为第二个数组 一一对应，最后一个参数表示使用实线
plt.ylabel('y')
plt.xlabel("x") # x，y轴上的标签

plt.show() # 输出的一步，否则前面都白写
```

![matplotlib_learning_1](https://i.loli.net/2019/01/30/5c511a6bc4f29.png)

坐标域是自动生成的，当然我们可以自行设置。

``` python
# 之后所加都要加在show之前。
plt.axis([0,6,0,6]) # 前两位是x轴，后两位是y轴
```
![matplotlib_learning_2](https://i.loli.net/2019/01/30/5c511b4e6ae91.png)




## 组合绘制——figure(图形)

> 处理多个图形和轴域

![matplot——figure](https://i.loli.net/2019/02/17/5c691323e5da1.png)

``` python
>>> plt.figure(1) # 创建图形
>>> plt.subplot(211) #创建 子图 （两行 一列 的第一个 子图）
>>> plt.plot([1, 2, 3]) # 绘制当前图
>>> plt.subplot(212) # 第一个图形的第二个子图
>>> plt.plot([4, 5, 6])
```

这里的figure()命令是可选的，因为默认情况下将创建figure(1)，如果不手动指定任何轴域，则默认创建subplot(111)。
subplot()命令指定numrows，numcols，fignum，其中fignum的范围是从1到numrows * numcols。
如果numrows * numcols <10，则subplot命令中的逗号是可选的。 因此，子图subplot(211)与subplot(2, 1, 1)相同。
你可以创建任意数量的子图和轴域。 如果要手动放置轴域，即不在矩形网格上，请使用axes()命令，该命令允许你将axes([left, bottom, width, height])指定为位置，其中所有值都使用小数（0 到 1）坐标。

## 处理文字——修饰

> text()命令可用于在任意位置添加文本，xlabel()，ylabel()和title()用于在指定的位置添加文本

![matplotlib_learning_4_text](https://i.loli.net/2019/02/17/5c6920904eecb.png)

``` python
plt.xlabel('x') # x轴 命名
plt.ylabel('y') # y轴 命名
plt.title('title') # 标题
plt.text(1, 2, r'$\mu=100,\ \sigma=15$') # 自定义位置 文字
```
### 在文本中使用数学表达式

matplotlib在任何文本表达式中接受 TeX 方程表达式。 例如，要在标题中写入表达式，可以编写一个由美元符号包围的 TeX 表达式：

``` python
plt.title(r'$\sigma_i=15$')
```

标题字符串之前的r很重要 - 它表示该字符串是一个原始字符串，而不是将反斜杠作为 python 转义处理。 matplotlib有一个内置的 TeX 表达式解析器和布局引擎，并且自带了自己的数学字体 - 详细信息请参阅编写数学表达式。



# 支持原创
## 码文不易，希望支持，谢谢->**[支持原创](http://blog.csdn.net/qq923132714/article/details/79399145)**
![微信支付](https://raw.githubusercontent.com/923132714/my_picture/master/blog/support/weixin.png)![微信支付](https://raw.githubusercontent.com/923132714/my_picture/master/blog/support/支付宝.png)
## 再次感谢，大家对本人的支持。
