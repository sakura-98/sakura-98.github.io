---
title: CG系数
tags: physics
categories: AQM
mathjax: true
date: 2020-11-07
---
Clebsch-Gordon(CG)系数是角动量求和$(j_1+j_2=j)$过程中出现的系数，定义为
$$
\langle j_1m_1j_2m_2|j_1j_2;jm\rangle
$$
显然，完整的CG系数应当是$(2j_1+1)(2j_2+1)$维的矩阵。
<!--more-->
### 完备性

直积态的完备性是预先给定的，或者说通过和式左边两个角动量的完备性可以得到
$$\sum_{m_1,m_2}|j_1m_1j_2m_2\rangle\langle j_1m_1j_2m_2|=1\tag{1}$$
右边的正交性也有角动量理论给出，所以只需要维数正确，就有完备性关系。实际上

|$j$|$j_1+j_2$|$j_1+j_2-1$|$\cdots$|$j_1-j_2$|
|---|---|---|---|---|
|$m$|$2(j_1+j_2)+1$|$2(j_1+j_2)-1$|$\cdots$|$2(j_1-j_2)+1$|

所以总共有$(2j_1+1)(2j_2+1)$维，因此也是完备的
$$\sum_{j=|j_1-j_2|}^{j_1+j_2}\sum_{m=-j}^j|j_1j_2;jm\rangle\langle j_1j_2;jm|\tag{2}$$
所以可以利用CG系数可以将耦合态和直积态互相转换
$$|j_1j_2;jm\rangle=\sum_{m_1,m_2}|j_1m_1j_2m_2\rangle\langle j_1m_1j_2m_2|j_1j_2;jm\rangle\tag3$$
$$|j_1m_1j_2m_2\rangle=\sum_{j=|j_1-j_2|}^{j_1+j_2}\sum_{m=-j}^j|j_1j_2;jm\rangle\langle j_1j_2;jm|j_1m_1j_2m_2\rangle\tag4$$

### 递推关系

将角动量的升降算符作用在(3)上可以得到递推关系。具体而言，作用升算符
$$\begin{aligned}
&\sqrt{(j-m)(j+m+1)}|j_1j_2;j,m+1\rangle\\
=&\sum_{m_1,m_2}\sqrt{(j_1-m_1)(j_1+m_1+1)}|j_1,m_1+1,j_2m_2\rangle\langle j_1m_1j_2m_2|j_1j_2;jm\rangle\\
+&\sum_{m_1,m_2}\sqrt{(j_2-m_2)(j_2+m_2+1)}|j_1m_1j_2,m_2+1\rangle\langle j_1m_1j_2m_2|j_1j_2;jm\rangle\\
\end{aligned}$$
左乘$\langle j_1m_1j_2m_2|$得
$$\begin{aligned}
&\sqrt{(j-m)(j+m+1)}\langle j_1m_1j_2m_2|j_1j_2;j,m+1\rangle\\
=&\sqrt{(j_1-m_1+1)(j_1+m_1)}\langle j_1,m_1-1,j_2m_2|j_1j_2;jm\rangle\\
+&\sqrt{(j_2-m_2+1)(j_2+m_2)}\langle j_1m_1j_2,m_2-1|j_1j_2;jm\rangle\\
\end{aligned}\tag5$$
同理降算符可得
$$\begin{aligned}
&\sqrt{(j+m)(j-m+1)}\langle j_1m_1j_2m_2|j_1j_2;j,m-1\rangle\\
=&\sqrt{(j_1-m_1)(j_1+m_1+1)}\langle j_1,m_1+1,j_2m_2|j_1j_2;jm\rangle\\
+&\sqrt{(j_2-m_2)(j_2+m_2+1)}\langle j_1m_1j_2,m_2+1|j_1j_2;jm\rangle\\
\end{aligned}\tag6$$
> 从递推式看出，可以将CG系数全部设为实数。
> 对(4)再进行一次操作可知，CG系数构成的矩阵是对称的~~（没算过，有空补上）~~

### 计算方式

利用(3)可知得归一化条件
$$\sum_{m_1,m_2}\langle j_1m_1j_2m_2|j_1j_2;jm\rangle^2=1$$
特殊的，取$m=j$
$$\sum_{m_1}\langle j_1m_1j_2,j-m_1|j_1j_2;jj\rangle^2=1\tag7$$
一般程序为

1. 利用(5)取$m=j$计算$\langle j_1m_1j_2,j-m_1|j_1j_2;jj\rangle$，假设$m_1=j_1$时大于零
2. 利用(7)归一化
3. 利用(4)递推计算$m\neq j$的情况

因此可以自己写代码计算（🚩)

### 和$\mathscr D$矩阵的关系

$$\begin{aligned}
\mathscr D^{j}_{mm'}&=\langle jm|U|jm'\rangle=\langle jm|U_1U_2|jm'\rangle\\
&=\sum_{m_1m_2}\langle jm|j_1m_1j_2m_2\rangle\langle j_1m_1j_2m_2|U_1U_2|jm'\rangle\\
&=\sum_{m_1m_2}\langle jm|j_1m_1j_2m_2\rangle\left(\langle j_1m_1|U_1\otimes\langle j_2m_2|U_2\right)|jm'\rangle\\
&=\sum_{m_1m_2}\sum_{m_1'm_2'}\langle jm|j_1m_1j_2m_2\rangle\left(\mathscr D^{j_1}_{m_1m_1'} \mathscr D^{j_2}_{m_2m_2'}\right)\langle j_1m_1'j_2m_2'|jm'\rangle\\
\end{aligned}\tag9$$
其中第三个等号是对任意可能的$j_1j_2$固定后求和。我们并没有假定对于任意$j_1j_2$答案都是一样，但是从结果上来看确实如此。
$$\begin{aligned}
&\mathscr D^{j_1}_{m_1m_1'}\mathscr D^{j_2}_{m_2m_2'}=\langle j_1m_1|U_1|j_1m_1'\rangle\langle j_2m_2|U_2|j_2m_2'\rangle\\
=&\langle j_1m_1j_2m_2|U_1U_2|j_1m_1'j_2m_2'\rangle\\
=&\langle j_1m_1j_2m_2|U|j_1m_1'j_2m_2'\rangle\\
=&\sum_{jm}\sum_{j'm'}\langle j_1m_1j_2m_2|jm\rangle\langle jm|U|j'm'\rangle\langle j'm'|j_1m_1'j_2m_2'\rangle\\
=&\sum_{jmm'}\langle j_1m_1j_2m_2|jm\rangle \mathscr D^{j}_{mm'}\langle jm'|j_1m_1'j_2m_2'\rangle\\
\end{aligned}\tag{10}$$

### 和球谐函数的关系

球谐函数有如下性质
$$Y_{lm}(\theta,\phi)=\langle\hat n|lm\rangle=\langle\hat z|U|lm\rangle=\sum_{m'}\langle \hat z|lm'\rangle \mathscr D^l_{m'm}$$
其中$U$为欧拉角$\alpha=\theta,\beta=\phi,\gamma=0$的转动的算符。利用$Y_{lm}(0,0)=\sqrt{\frac{2l+1}{4\pi}}\delta_{m0}$可得
$$Y_{lm}(\theta,\phi)=\sqrt{\frac{2l+1}{4\pi}}\mathscr D_{0m}^l$$
因此(10)取$m_1=m_2=0$（进而$m=0$）可得
$$\begin{aligned}
&Y_{l_1m_1}(\theta,\phi)Y_{l_2m_2}(\theta,\phi)=\sqrt{\frac{2l_1+1}{4\pi}}\sqrt{\frac{2l_2+1}{4\pi}}\mathscr D_{0m_1}^{l_1}\mathscr D_{0m_2}^{l_2}\\
=&\sqrt{\frac{2l_1+1}{4\pi}}\sqrt{\frac{2l_2+1}{4\pi}}\sum_{lm}\langle l_10l_20|l0\rangle\mathscr D^l_{0m}\langle lm|l_1m_1l_2m_2\rangle\\
=&\sum_{lm}\sqrt{\frac{(2l_1+1)(2l_2+1)}{4\pi(2l+1)}}Y_l^m(\theta,\phi)\langle l_10l_20|l0\rangle\langle lm|l_1m_1l_2m_2\rangle\\
\end{aligned}$$
其中第二行的$|l_1l_2;lm\rangle$和第三行的$|l0;lm\rangle$均为$|lm\rangle$。第三行中插入完备性关系，只不过这个完备性$(2l+1)$项中只有一项有效。
进一步可得三个球谐函数的积分
$$\int\mathrm d\Omega\ Y^*_{l_3m_3}Y_{l_1m_1}Y_{l_2m_2}=\sqrt{\frac{(2l_1+1)(2l_2+1)}{4\pi(2l_3+1)}}\langle l_30|l_10l_20\rangle\langle l_1m_1l_2m_2|lm\rangle$$
