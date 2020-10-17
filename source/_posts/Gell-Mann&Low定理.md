---
title: Gell-Mann&Low 定理
date: 2020-10-15
tags: physics
categories: QSP
mathjax: true
---

Gell-Mann Low 定理说的是，在绝热引入相互作用的方法下计算出的本征态就是相互作用系统的本征态。即系统的哈密顿量为
$$\hat H=\hat H_0+\hat H_I=\hat H_0+ge^{-\epsilon|t|}\hat H_1\tag{1}$$
非相互作用部分本征态$|\Phi\rangle$，则若
$$\lim_{\epsilon\rightarrow 0}\frac{\hat U_\epsilon(0,-\infty;g)|\Phi\rangle}{\langle\Phi|\hat U_\epsilon(0,-\infty;g)|\Phi\rangle}\equiv
\lim_{\epsilon\rightarrow 0}\frac{|\Psi^g(\epsilon)\rangle}{\langle\Phi|\Psi^g(\epsilon)\rangle}
=\frac{|\Psi^g\rangle}{\langle\Phi|\Psi^g\rangle}\tag{2}$$
注意到定义了$|\Psi^g(\epsilon)\rangle$，而且并没有说$|\Psi^g(\epsilon)\rangle\xrightarrow{\epsilon\rightarrow0}|\Psi^g\rangle$。那么有
$$\hat H(t=0)\frac{|\Psi^g\rangle}{\langle\Phi|\Psi^g\rangle}=E\frac{|\Psi^g\rangle}{\langle\Phi|\Psi^g\rangle}\tag{3}$$
<!--more-->
### 相互作用表象
波函数和算符分别为
$$|\Psi_I(t)\rangle\equiv e^{i\hat H_0t/\hbar}|\Psi_S(t)\rangle,\quad\hat O_I(t)\equiv e^{i\hat H_0t/\hbar}\hat O_Se^{-i\hat H_0t/\hbar}\tag{1.1}$$
因此波函数运动方程为
$$i\hbar\frac{\partial}{\partial t}|\Psi_I(t)\rangle=\hat H_I|\Psi_I(t)\rangle\tag{1.2}$$
算符运动方程为
$$i\hbar\frac{\partial}{\partial t}\hat O_I(t)=\left[\hat O_I(t),\hat H_0\right]\tag{1.3}$$
根据(1.1)可得时间演化算符$\hat U(t,t_0)$为
$$\hat U(t,t_0)=e^{i\hat H_0t/\hbar}e^{-i\hat H(t-t_0)/\hbar}e^{-i\hat H_0t_0/\hbar}\tag{1.4}$$
之所以不从(1.2)式出发，是因为$\hat H_I(t)$之间不一定对易，导致得不到简单的结果。但从(1.2)出发能得到时间演化算符的运动方程，通过迭代也能得到其表达式
$$i\hbar\frac{\partial}{\partial t}\hat U(t,t_0)=\hat H_I(t)\hat U(t,t_0)\tag{1.5}$$
当然，作为“算符”，它也应当满足(1.3)式，只不过用处不太大。

对(1.5)式积分，考虑到$\hat U(t_0,t_0)=\hat 1$
$$\hat U(t,t_0)=\hat 1+\frac{1}{i\hbar}\int_{t_0}^t\hat H_I(t_1)\hat U(t_1,t_0)\mathrm dt_1\tag{1.6}$$
继续迭代，最终得到
$$\hat U(t,t_0)=\sum_{n=0}^\infty\left(\frac{1}{i\hbar}\right)^n\frac{1}{n!}\int_{t_0}^t\mathrm dt_1\cdots\mathrm dt_n\ \hat T\left[\hat H_I(t_1)\cdots\hat H_I(t_n)\right]\tag{1.7}$$
其中引入编时算符$\hat T$使得各个$t_i$等价。
### 求解哈密顿量和时间演化的对易
这是证明过程中会遇到的一个问题，我们将其处理为引理。

因为$\hat U$能表示为$\hat H_1$的函数，正如(1.7)所示，因此我们从这里开始计算。使用(1.3)
$$i\hbar\frac{\partial}{\partial t}\hat H_1(t)=[\hat H_1,\hat H_0]\tag{2.1}$$
因此$n$个$\hat H_1$的乘积有
$$[\hat H_1(t_1)\cdots\hat H_1(t_n),\hat H_0]=i\hbar\left(\frac{\partial}{\partial t_1}+\cdots+\frac{\partial}{\partial t_n}\right)\hat H_1(t_1)\cdots\hat H_1(t_n)\tag{2.2}$$
为了引入编时算符，我们能够证明（直接计算即可）
$$\sum_{j=1}^n\frac{\partial}{\partial t_j}\theta(t_{P(1)}-t_{P(2)})\cdots\theta(t_{P(n-1)}-t_{P(n)})=0\tag{2.3}$$
所以(2.2)式可直接套上编时算符，此时$t_1,\cdots t_n$完全等价，于是
$$[\hat T[\hat H_1(t_1)\cdots\hat H_1(t_n)],\hat H_0]=in\hbar\frac{\partial}{\partial t_1}\hat T[\hat H_1(t_1)\cdots\hat H_1(t_n)]\tag{2.4}$$
和(1)代回(1.7)得
$$\begin{aligned}[]
[\hat U(t,t_0),\hat H_0]&=\sum_{n=1}^\infty\left(\frac{1}{i\hbar}\right)^{n-1}\frac{g^n}{(n-1)!}\int_{t_0}^t\mathrm dt_1\cdots\mathrm dt_n\ e^{\epsilon(t_1+\cdots+t_n)}\\
&\times\frac{\partial}{\partial t_1}\hat T\left[\hat H_1(t_1)\cdots\hat H_1(t_n)\right]
\end{aligned}\tag{2.5}$$
### 正式证明
$$\left(\hat H_0-E_0\right)|\Psi^g(\epsilon)\rangle=\left(\hat H_0\hat U_\epsilon(0,-\infty;g)-\hat U_\epsilon(0,-\infty;g)E_0\right)|\Phi\rangle\tag{3.1}$$
注意到右边是一个对易子，因为$\hat H_0|\Phi\rangle=E_0|\Phi\rangle$。所以可将(2.5)代入
$$\begin{aligned}\left(\hat H_0-E_0\right)|\Psi^g(\epsilon)\rangle=&-\sum_{n=1}^\infty\left(\frac{1}{i\hbar}\right)^{n-1}\frac{g^n}{(n-1)!}\int_{t_0}^t\mathrm dt_1\cdots\mathrm dt_n\ e^{\epsilon(t_1+\cdots+t_n)}\\
&\times\frac{\partial}{\partial t_1}\hat T\left[\hat H_1(t_1)\cdots\hat H_1(t_n)\right]|\Phi\rangle
\end{aligned}\tag{3.2}$$
对$t_1$做分部积分，注意到积分下限有因子$e^{-\epsilon\infty}=0$，上限有$t_1=0>t_j$，所以为
$$\begin{aligned}
&-\hat H_1\sum_{n=1}^\infty\left(\frac{1}{i\hbar}\right)^{n-1}\frac{g^n}{(n-1)!}\int_{-\infty}^0\mathrm dt_2\cdots\mathrm dt_n\ e^{\epsilon(t_2+\cdots+t_n)}\hat T\left[\hat H_1(t_2)\cdots\hat H_1(t_n)\right]|\Phi\rangle\\
&+\epsilon\sum_{n=1}^\infty\left(\frac{1}{i\hbar}\right)^{n-1}\frac{g^n}{(n-1)!}\int_{-\infty}^0\mathrm dt_1\cdots\mathrm dt_n\ e^{\epsilon(t_1+\cdots+t_n)}\hat T\left[\hat H_1(t_1)\cdots\hat H_1(t_n)\right]|\Phi\rangle
\end{aligned}$$

对于第一项，可以重新编号$2\rightarrow1,3\rightarrow2,\cdots n\rightarrow(n-1)$得到$-g\hat H_1\hat U_\epsilon(0,-\infty;g)|\Phi\rangle$；

对于第二项，也可通过简单的算符与$\hat U_\epsilon(0,-\infty;g)$联系起来。两者结合得
$$\left(\hat H_0-E_0\right)|\Psi^g(\epsilon)\rangle=-g\hat H_1|\Psi^g(\epsilon)\rangle+\epsilon i\hbar g\frac{\partial}{\partial g}|\Psi^g(\epsilon)\rangle$$
移项后得到
$$\left(\hat H_0+g\hat H_1-E_0\right)|\Psi^g(\epsilon)\rangle=\epsilon i\hbar g\frac{\partial}{\partial g}|\Psi^g(\epsilon)\rangle\tag{3.3}$$
但是不能直接取极限$\epsilon\rightarrow 0$得到$|\Psi^g\rangle$是$\hat H=\hat H_0+\hat H_1$的本征态，因为

1. 我们并不知道$|\Psi^g(\epsilon)\rangle$随$g$的变化关系
2. 我们并不知道$|\Psi^g(\epsilon\rightarrow0)\rangle$是否就是$|\Psi^g\rangle$
3. 倘若右边为零，说明相互作用不会改变本征能量，只会改变本征矢，这是荒谬的

受Gell-Mann&Low定理的条件(2)启发，我们去凑相应的形式，计算
$$\begin{aligned}
&\frac{\partial}{\partial g}|\Psi^g(\epsilon)\rangle=\frac{\partial}{\partial g}\left[\langle\Phi|\Psi^g(\epsilon)\rangle\frac{|\Psi^g(\epsilon)\rangle}{\langle\Phi|\Psi^g(\epsilon)\rangle}\right]\\
=&\langle\Phi|\Psi^g(\epsilon)\rangle\frac{\partial}{\partial g}\left[\frac{|\Psi^g(\epsilon)\rangle}{\langle\Phi|\Psi^g(\epsilon)\rangle}\right]+\frac{\partial}{\partial g}\left[\langle\Phi|\Psi^g(\epsilon)\rangle\right]\frac{|\Psi^g(\epsilon)\rangle}{\langle\Phi|\Psi^g(\epsilon)\rangle}\\
\end{aligned}\tag{3.4}$$
代入(3.3)得
$$\begin{aligned}
&\left(\hat H_0+g\hat H_1-E_0\right)\frac{|\Psi^g(\epsilon)\rangle}{\langle\Phi|\Psi^g(\epsilon)\rangle}\\
=&i\epsilon\hbar g\frac{\partial}{\partial g}\left[\frac{|\Psi^g(\epsilon)\rangle}{\langle\Phi|\Psi^g(\epsilon)\rangle}\right]\\
+&i\epsilon\hbar g\frac{\partial}{\partial g}\ln\left[\langle\Phi|\Psi^g(\epsilon)\rangle\right]\frac{|\Psi^g(\epsilon)\rangle}{\langle\Phi|\Psi^g(\epsilon)\rangle}
\end{aligned}\tag{3.5}$$
利用(2)可知，上式取$\epsilon\rightarrow0$时，第一项的括号内为常数，所以可以使用极限公式$\lim AB=\lim A\times\lim B$得到值$0$。第二项要能取极限是有要求的，即$\lim_{\epsilon\rightarrow0}i\epsilon\hbar g\frac{\partial}{\partial g}\ln\left[\langle\Phi|\Psi^g(\epsilon)\rangle\right]$极限存在，设为$\Delta E^g$。假设满足要求（具体见补充说明），则上式为
$$\left(\hat H_0+g\hat H_1-E_0\right)\frac{|\Psi^g\rangle}{\langle\Phi|\Psi^g\rangle}
=\lim_{\epsilon\rightarrow0}\left\{i\epsilon\hbar g\frac{\partial}{\partial g}\ln\left[\langle\Phi|\Psi^g(\epsilon)\rangle\right]\right\}\frac{|\Psi^g\rangle}{\langle\Phi|\Psi^g\rangle}
\tag{3.6}$$
因此令$g=1$即得到
$$\hat H(t=0)\frac{|\Psi\rangle}{\langle\Phi|\Psi\rangle}=(E_0+\Delta E)\frac{|\Psi\rangle}{\langle\Phi|\Psi\rangle}$$
即得证。
### 补充说明
利用(1.7)式
$$\hat U(-\infty,0)=\sum_{n=0}^\infty\left(\frac{g}{i\hbar}\right)^n\frac{1}{n!}\int_{-\infty}^0e^{\epsilon t_1}\mathrm dt_1\cdots e^{\epsilon t_n}\mathrm dt_n\ \hat H_1^n\tag{4.1}=\exp\left(\frac{g\hat H_1}{i\hbar\epsilon}\right)$$
所以$\langle\Phi|\Psi^g(\epsilon)\rangle=\langle\Phi|\exp(-i\frac g{\hbar\epsilon}\hat H_1)|\Phi\rangle=A^g\exp(i\epsilon^{-1}\alpha^g)$，所以
$$
\lim_{\epsilon\rightarrow0}i\epsilon\hbar g\frac{\partial}{\partial g}\ln\left[\langle\Phi|\Psi^g(\epsilon)\rangle\right]=\hbar g\frac{\partial\alpha^g}{\partial g}
$$
因此证明中(3.6)式成立