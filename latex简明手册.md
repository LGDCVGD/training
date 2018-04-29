# latex公式简明教程

撰写数学公式。有时候投稿可能会要求Latex，这时候用Word+mathtype就没戏了

在web上撰写技术文档如果也需要公式，则可以使用markdown+mathjax方案。mathjax和latex语法基本类似

---

## 1 公式格式

### 1.1 行内公式

#### 语法

```
$公示内容$
```

#### 效果

如果有$y=x$则有$y=c$

> 因为显示在单行内，所以会压缩公式高度

---

### 1.2 独立公式

#### 语法

```
$$
公示内容
$$
```

#### 效果

定义：

$$
f(x)=ax+b
$$

> 公式不会自动换行，需要手动

---

### 1.3 换行公式

#### 语法

```
$$
\begin{公式类型}
f(t)=& 第一行\\
& 第二行
\end{公式类型}
$$
```

> 不同公式引擎支持的公式类型不同。常见的有`equation`, `matrix`, `gather`等，使用`\\`进行换行，使用`&`进行对齐

#### 效果

$$
\begin{matrix}
f(t)=& e^{-t}(\sin2t + 2\sin4t -\\
& {}- 0.4\sin2t\sin40t)
\end{matrix}
$$

> 例如我在vscode内使用的这个引擎就不支持`equation`，被迫使用`matrix`

---

### 1.4 公示编号

latex会自动对公式进行编号，有的渲染引擎则不会。对于latex，多行公式只需要1个编号时，使用`split`语法即可实现

```
$$
\begin{equation}
\begin{split}
多行公式内容
\end{split}
\end{equation}
$$
```

不自动编号的引擎，可以需要编号的行后边使用`\tag{编号}`手动编号。不过也不是所有的引擎都支持，具体方法请参考所使用引擎的文档

---

### 1.5 条件表达式/分段函数

#### 语法

```
$$
f(n) =
\begin{cases}
第一段, & \text{条件1} \\
第二段, & \text{条件2}
\end{cases}
$$
```

#### 效果

$$
f(n) =
\begin{cases}
n/2,  & \text{if $n$ is even} \\
3n+1, & \text{if $n$ is odd}
\end{cases}
$$

> 渲染器未必支持

---
---

## 2 公式内部符号

### 2.1 分组

使用`{}`将内容合为一部分
如`a_{xy}`就可以将xy都作为a的下标：$a_{xy}$


### 2.2 分式

使用`\frac {分子}{分母}`实现

$$\frac {1}{K+1}$$

### 2.3 根式

使用`\sqrt[次数]{内容}`实现

$$\sqrt[4]{x^2+y^2}$$

### 2.4 括号自适应

#### 语法

> {[()]}都可用

`\left[ ... \right]`

#### 无自适应效果

$$
[ \frac{e^x}{K+1} ]
$$

#### 自适应效果

$$
\left[ \frac{e^x}{K+1} \right]
$$

---
---

## 3 矩阵

### 3.1 点号

符号|语法|效果
--|---|--|--
横点|`\cdots`|$\cdots$
斜点|`\ddots`|$\ddots$
竖点|`\vdots`|$\vdots$

### 3.2 矩阵

#### 语法

```
$$
\left[
\begin{matrix}
   1 & \cdots & 3 \\
   4 & \ddots & \vdots \\
   7 & 8 & 9
\end{matrix}
\right]
$$
```

#### 效果

$$
\left[
\begin{matrix}
   1 & \cdots & 3 \\
   4 & \ddots & \vdots \\
   7 & 8 & 9
\end{matrix}
\right]
$$

增广矩阵什么的应该用不到吧，就不写了

---
---

## 4 特殊符号

### 4.1 字符

符号|语法|效果|备注
--|---|--|--
小写希腊字母|`\alpha`|$\alpha$|具体字符请自行查阅
大写希腊字母|`\Delta`|$\Delta$|自行查阅，有的不支持大写
无穷|`\infty`|$\infty$|

### 4.2 关系

符号|语法|效果
--|---|--
不等|`\ne`|$\ne$
恒等|`\equiv`|$\equiv$
约等|`\approx`|$\approx$
小于/大于等于号|`\le \ge`|$\le \ge$
分布|`\sim`|$\sim$
任意|`\forall`|$\forall$
存在|`\exists`|$\exists$
属于|`\in`|$\in$
不属于|`\notin`|$\notin$
子集|`\subseteq`|$\subseteq$
真子集|`\subset`|$\subset$

### 4.3 运算

符号|语法|效果|备注
--|---|--|--
并|`\cup`|$\cup$|
交|`\cap`|$\cap$|
非|`\neg`|$\neg$|
叉乘|`\times`|$\times$|
点乘|`\cdot`|$\cdot$|
星号|`\ast`|$\ast$|
正负|`\pm`|$\pm$|
累加|`\sum`|$\sum$|边界用上下标
累乘|`\prod`|$\prod$|同上
积分|`\int`|$\int$|同上
偏导|`\partial`|$\partial$|
对数|`\log`|$\log$|
极限|`\lim`|$\lim$|
梯度|`\nabla`|$\nabla$|

### 4.4 箭头

符号|语法|效果
--|---|--
右|`\to`|$\to$
左|`\gets`|$\gets$
充分|`\Rightarrow`|$\Rightarrow$
必要|`\Leftarrow`|$\Leftarrow$
充要|`\Leftrightarrow`|$\Leftrightarrow$

### 4.5 头顶

符号|语法|效果
--|---|--
帽子|`\hat 符号`|$\hat y$
横线|`\bar 符号`|$\bar a$
波浪|`\tilde 符号`|$\tilde y$
矢量|`\vec 符号`|$\vec x$
一阶导数|`\dot 符号`|$\dot x$
二阶导数|`\ddot 符号`|$\ddot x$

---
---

## 5 字体

字体|常用于|语法|效果
--|--|--|--
粗斜体|矩阵|`\bm 符号`|$\bm A$
正体|文本|`{\rm 符号}`|$\rm good$
花体|损失函数|`\mathcal 符号`|$\mathcal L$
空心正体|某些常用集合或函数|`\matchbb 符号`|$\mathbb E$
