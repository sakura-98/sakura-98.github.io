---
title: $\gamma$代数
tags: physics
categories: QFT
mathjax: true
date: 2020-12-24
---

在Dirac场中，$\gamma$矩阵起到很重要的作用，因此有必要考察它们的性质。

通常，选用以下16个矩阵为基
$$1,\gamma^\mu,\gamma_5\equiv i\gamma^0\gamma^1\gamma^2\gamma^3,i\gamma^5\gamma^\mu,\sigma^{\mu\nu}\equiv\frac i2\left[\gamma^\mu,\gamma^\nu\right]$$

本文先采用另一套记号计算，然后给出两套记号的关系，最后写出$\gamma$矩阵之间的关系。

<!--more-->

### C矩阵

#### 矩阵形式

$$
1=\left[\begin{array}{cccc}
+1 & 0 & 0 & 0 \\
0 & +1 & 0 & 0 \\
0 & 0 & +1 & 0 \\
0 & 0 & 0 & +1
\end{array}\right]
$$

$C^\mu$:
$$
\left[\begin{array}{cccc}
0 & 0 & 0 & -1 \\
0 & 0 & -1 & 0 \\
0 & +1 & 0 & 0 \\
+1 & 0 & 0 & 0
\end{array}\right],
\left[\begin{array}{cccc}
0 & +1 & 0 & 0 \\
+1 & 0 & 0 & 0 \\
0 & 0 & 0 & -1 \\
0 & 0 & -1 & 0
\end{array}\right],
\left[\begin{array}{cccc}
+1 & 0 & 0 & 0 \\
0 & -1 & 0 & 0 \\
0 & 0 & +1 & 0 \\
0 & 0 & 0 & -1
\end{array}\right],
\left[\begin{array}{cccc}
0 & 0 & 0 & -1 \\
0 & 0 & -1 & 0 \\
0 & -1 & 0 & 0 \\
-1 & 0 & 0 & 0
\end{array}\right]
$$

$$C^5\equiv C^0C^1C^2C^3=\left[\begin{array}{cccc}
0 & -1 & 0 & 0 \\
+1 & 0 & 0 & 0 \\
0 & 0 & 0 & -1 \\
0 & 0 & +1 & 0
\end{array}\right]$$

$C^5C^\mu$:
$$
\left[\begin{array}{cccc}
0 & 0 & +1 & 0 \\
0 & 0 & 0 & -1 \\
-1 & 0 & 0 & 0 \\
0 & +1 & 0 & 0
\end{array}\right],
\left[\begin{array}{cccc}
-1 & 0 & 0 & 0 \\
0 & +1 & 0 & 0 \\
0 & 0 & +1 & 0 \\
0 & 0 & 0 & -1
\end{array}\right],
\left[\begin{array}{cccc}
0 & +1 & 0 & 0 \\
+1 & 0 & 0 & 0 \\
0 & 0 & 0 & +1 \\
0 & 0 & +1 & 0
\end{array}\right],
\left[\begin{array}{cccc}
0 & 0 & +1 & 0 \\
0 & 0 & 0 & -1 \\
+1 & 0 & 0 & 0 \\
0 & -1 & 0 & 0
\end{array}\right]
$$

$\sigma^{\mu\nu}=\frac12\left[C^\mu,C^\nu\right]:$
$$
\mu=0:\left[\begin{array}{cccc}
0 & 0 & +1 & 0 \\
0 & 0 & 0 & +1 \\
+1 & 0 & 0 & 0 \\
0 & +1 & 0 & 0
\end{array}\right],
\left[\begin{array}{cccc}
0 & 0 & 0 & +1 \\
0 & 0 & -1 & 0 \\
0 & -1 & 0 & 0 \\
+1 & 0 & 0 & 0
\end{array}\right],
\left[\begin{array}{cccc}
+1 & 0 & 0 & 0 \\
0 & +1 & 0 & 0 \\
0 & 0 & -1 & 0 \\
0 & 0 & 0 & -1
\end{array}\right]
$$

$$
\mu=1:\left[\begin{array}{cccc}
0 & -1 & 0 & 0 \\
+1 & 0 & 0 & 0 \\
0 & 0 & 0 & +1 \\
0 & 0 & -1 & 0
\end{array}\right],
\left[\begin{array}{cccc}
0 & 0 & -1 & 0 \\
0 & 0 & 0 & -1 \\
+1 & 0 & 0 & 0 \\
0 & +1 & 0 & 0
\end{array}\right]
$$

$$
\mu=2:\left[\begin{array}{cccc}
0 & 0 & 0 & -1 \\
0 & 0 & +1 & 0 \\
0 & -1 & 0 & 0 \\
+1 & 0 & 0 & 0
\end{array}\right]
$$

#### 线性无关性、完备性

根据第一个非零元素的列坐标和对称性分为八类

| 列坐标 | 0 | 1 | 2 | 3 |
| :---: |:---:|:---:|:---:|:---:|
|  对称 | $1,C^2,C^5C^1,\sigma^{03}$|$C^1,C^5C^2$|$C^5C^3,\sigma^{01}$|$C^3,\sigma^{02}$|
|  反称 | |$C^5,\sigma^{12}$|$C^5C^0,\sigma^{13}$|$C^0,\sigma^{23}$|

因此很容易看出这16个矩阵构成一组线性无关的完备基。

#### 反对易关系

排列顺序$1,C^5,C^\mu,C^5C^\mu,\sigma^{\mu\nu}$，逐个计算。有下划线的为直接代入矩阵形式，否则可以根据已有信息计算出来

单位矩阵和任意矩阵的反对易关系是平凡的
$$\{1,1\}=2,\{1,C^5\}=2C^5,\{1,C^\mu\}=2C^\mu,\{1,C^5C^\mu\}=2C^6C^\mu,\{1,\sigma^{\mu\nu}\}=2\sigma^{\mu\nu}$$

一个个计算过来可得，$C^5$和其他矩阵的反对易关系为
$$\underline{\{C^5,C^5\}=-2},\underline{\{C^5,C^\mu\}=0},\{C^5,C^5C^\mu\}=0,
\underline{\{C^5,\sigma^{\mu\nu}\}=2\epsilon_{\mu\nu\rho\sigma}\sigma^{\rho\sigma}}$$

$C^\mu$之间的反对易关系是简单的，或者说，正是取合适的基使得满足如下简单的关系
$$\underline{\{C^\mu,C^\nu\}=2g^{\mu\nu}=\mathrm{diag}\{-1,1,1,1\}}$$
此外还有
$$\{C^\mu,C^5C^\nu\}=-2\epsilon_{\mu\nu\rho\sigma}\sigma^{\rho\sigma},
\{C^\mu,\sigma^{\nu\rho}\}=2\epsilon_{\mu\nu\rho\sigma}C^5C^\sigma$$

最后一式为将$C_5^{-1}=-C^5$左乘之，再利用$\{C^5,\sigma^{\mu\nu}\}=2\epsilon_{\mu\nu\rho\sigma}\sigma^{\rho\sigma}$即可

最后还有三类反对易关系
$$\{C^5C^\mu,C^5C^\nu\}=2g^{\mu\nu},\{C^5C^\mu,\sigma^{\nu\rho}\}=0,\{\sigma^{\mu\nu},\sigma^{\rho\sigma}\}=-2\epsilon_{\mu\nu\rho\sigma}C^5$$

#### 对易关系

单位矩阵和任意矩阵对易，即
$$\left[1,C^\mu\right]=\left[1,C^5\right]=\left[1,C^5C^\mu\right]=\left[1,\sigma^{\mu\nu}\right]=0$$

$C^\mu$之间对易关系根据定义即可得到（假设前者指标小于后者：若相等，则显然为0；若大于，则仅差一个负号）
$$\left[C^\mu,C^\nu\right]=2\sigma^{\mu\nu}$$

#### 总结

比较常用的为
$$\{C^\mu,C^\nu\}=2g^{\mu\nu},\{C^5,C^\mu\}=0,\{C^5,C^5\}=-2$$

||$C^0$|$C^i$|$C^5$|
|:---:|:---:|:---:|:---:|
|对易|||
|反对易|||

### 两套记号

### $\gamma$矩阵
