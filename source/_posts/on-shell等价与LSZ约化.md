---
title: on-shell等价与LSZ约化
date: 2020-10-13
tags: physics
categories: QFT
mathjax: true
---
 LSZ约化公式是属于量子场论中十分重要的公式。它是考虑相互作用以后求解场的演化性质，将散射振幅和关联函数联系起来。
<!--more-->

### on-shell等价函数

设$m$是**相互作用**标量场$\phi$中单粒子的静质量。若有两个函数$\psi_1(x),\psi_2(x)$，它们的傅里叶变换$\tilde\psi_i(k)\equiv\int e^{-ik\cdot x}\psi_i(x)\mathrm dx$在on-shell条件$l^2+m^2=0$满足时均有
$$\tilde\psi_1(l)=\tilde\psi_2(l)$$
可以计算
$$\begin{aligned}
\int\mathrm d^4x\ \psi(x)\phi(x)|0\rangle=&\int\mathrm d^4x\frac{\mathrm d^4k}{(2\pi)^4}\frac{\mathrm d^4l}{(2\pi)^4}e^{-i(k-l)\cdot x}\tilde\psi(k)\tilde\phi(-l)|0\rangle\\
=&\int\frac{\mathrm d^4k}{(2\pi)^4}\frac{\mathrm d^4l}{(2\pi)^4}(2\pi)^4\delta(k-l)\tilde\psi(k)\tilde\phi(-l)|0\rangle\\
=&\int\frac{\mathrm d^4k}{(2\pi)^4}\tilde\psi(k)\tilde\phi(-k)|0\rangle\\
\end{aligned}$$
因为不满足on-shell条件时$\tilde\phi(-k)|0\rangle=0$，所以
$$\int\mathrm d^4x\ \psi_1(x)\phi(x)|0\rangle=\int\mathrm d^4x\ \psi_2(x)\phi(x)|0\rangle\tag{1}$$

假设$F(x)$具有相对论性波函数的形式
$$F(x)=\int\frac{\mathrm d^3\vec l}{(2\pi)^3}\ f(\vec l)e^{-i\omega_{\vec l}t+i\vec l\cdot x}\tag2$$
我们想要证明，对于所有的$T$，$F(x)g(t-T)$都是on-shell等价的。这是因为
$$\begin{aligned}
&\int\mathrm d^4x\ e^{-ik\cdot x}F(x)g(t-T)\\
=&\int\mathrm d^4x\frac{\mathrm d^3\vec l}{(2\pi)^3}\frac{\mathrm d\omega}{2\pi}\ e^{ik\cdot x}f(\vec l)e^{-i\omega_{\vec l}t+i\vec l\cdot x}\tilde g(\omega)e^{-i\omega (t-T)}\\
=&\int\frac{\mathrm d^3\vec l}{(2\pi)^3}\frac{\mathrm d\omega}{2\pi}\ f(\vec l)\tilde g(\omega)(2\pi)\delta(k^0-\omega_{\vec l}-\omega)(2\pi)^3\delta(-\vec k+\vec l)e^{i\omega T}\\
=&f(\vec k)\tilde g(k^0-\omega_{\vec k})e^{i(k^0-\omega_{\vec k})T}\\
\end{aligned}\tag3$$
on-shell意味着$k^0=\omega_{\vec k}$，因此(3)式与$T$无关。

### 入态$|in\rangle$与出态$|out\rangle$

入态指的是$t\rightarrow-\infty$时有确定的、可分辨的轨迹和粒子数，$t\rightarrow+\infty$时粒子数、轨迹均不确定；
出态指的是$t\rightarrow+\infty$时有确定的、可分辨的轨迹和粒子数，$t\rightarrow-\infty$时粒子数、轨迹均不确定。
**我们要求出态和入态的所有粒子动量均不一样**，不然的话可以不考虑不散射的粒子。

先考虑入态，设
$$
C_\alpha=\int\mathrm d^4x_\alpha\ u_\alpha(x_\alpha)\phi_\alpha(x_\alpha)=\int\frac{\mathrm d^4k}{(2\pi)^4}\ \tilde u(k)\tilde\phi(-k)\tag4
$$
其中$\alpha$标记粒子，$u_\alpha$为一个小窗。这个小窗时间方向为$g_\alpha(t-T_-),T_-\rightarrow-\infty$，空间（动量）方向为$f_\alpha(\mathbf k_\alpha)$——所以当$|T_-|$足够大时，只需每个粒子的$\mathbf p_\alpha$不相等，就能将它们完全分开。这样，
$$
u_\alpha(x)=g_\alpha(t-T_-)\int\frac{\mathrm d^3\mathbf k}{(2\pi)^3}\ f_\alpha(\mathbf k_\alpha)e^{-i\omega_{\mathbf k}t+i\mathbf{k\cdot x}}\tag{5}
$$
显然这是$F(x)g(t-T)$的形式，因此on-shell等价，之后会用到该结论。
可以变换到$k$空间，为
$$
\tilde u_\alpha(k)=\tilde g(k^0-\omega_{\mathbf k})f_\alpha(\mathbf k)e^{i(k^0-\omega_\mathbf k)T_-}
\tag6
$$
因此(4)中只有$k=(\omega_\mathbf k,\mathbf k)$附近的值被提取出来，即为产生算符。
> 一个极端的取法是$\delta$函数
> $$g_\alpha(t-T_-)=\delta(t_\alpha-T_-),f_\alpha(\mathbf k_\alpha)=(2\pi)^32\omega_\mathbf k\delta^3(\mathbf{k-p}_\alpha)$$

因此，单粒子被限制在$(T_-,\mathbf x(t=0)+\mathbf p_\alpha T_-)$附近，单粒子态为$C_\alpha|0\rangle$。而且各个粒子时间几乎相等，空间互不重叠，所以是类空的，因此所有的粒子算符对易
$$|in\rangle=C_1C_2\cdots C_n|0\rangle\tag7$$
同理定义出态，直接写出
$$\left\{\begin{aligned}
&D_{\alpha'}=\int\mathrm d^4x'_{\alpha'}\ u'_{\alpha'}(x'_{\alpha'})\phi(x'_{\alpha'})\\
&u'_{\alpha'}(x)=g'_{\alpha'}(t-T_+)\int\frac{\mathrm d^3\mathbf k}{(2\pi)^3}\ f'_{\alpha'}(\mathbf k)e^{-i\omega_{\mathbf k}t+i\mathbf{k\cdot x}}\\
&T_+\rightarrow+\infty\\
&|out\rangle=D_1D_2\cdots D_{n'}|0\rangle
\end{aligned}\right.\tag8$$
因此两者的内积——转移振幅为
$$\langle out|in\rangle=\langle0|\hat T[D_1^\dagger\cdots D_{n'}^\dagger C_1\cdots C_n]|0\rangle\tag9$$
编时算符在此其实没有作用，因为出态之间对易，末态之间也对易，出态和末态本身已经编时。

### LSZ约化公式

定义
$$\overline C_\alpha=\int\mathrm d^4x_\alpha \bar u_\alpha(x_\alpha)\phi(x_\alpha),
\bar u_\alpha(x_\alpha)=g_\alpha(t_\alpha-T_+)\int\frac{\mathrm d^3\mathbf k}{(2\pi)^3}\ f_\alpha(\mathbf k_\alpha)e^{ik\cdot x}
$$
可以证明，$C_\alpha\rightarrow\overline C_\alpha$后，(9)的右边变成零，这是因为编时算符要求它移到所有$C$算符左方，类空性质（因为动量均不相等）允许它移到所有$D$算符左方。因此会出现$\langle 0|\overline C_\alpha$。因为$\bar u_\alpha$和$\bar u$ on-shell 等价，所以同(6)可知提取出了产生部分，即$\overline C_\alpha$为产生算符。于是(9)可以改写为
$$\langle out|in\rangle=\langle0|\hat T[(\overline D_1-D_1)^\dagger\cdots (\overline D_{n'}-D_{n'})^\dagger (C_1-\overline C_1)\cdots (C_n-\overline C_n)]|0\rangle\tag{10}$$
略去下标，计算 $C-\overline C$，首先将时间变换到频率
$$
\begin{aligned}
&C-\overline C=\int\mathrm d^4 x\int\frac{\mathrm d\nu}{2\pi}\tilde g(\nu)\left(e^{-i\nu(t-T_-)}-e^{i\nu (t-T_+)}\right)\int\frac{\mathrm d^3\mathbf k}{(2\pi)^3}f(\mathbf k)e^{ik\cdot x}\phi(x)\\
&=\int\frac{\mathrm d^4x\mathrm d\nu\mathrm d^3\mathbf k}{(2\pi)^4}\tilde g(\nu)\left(e^{i\nu T_-}-e^{-i\nu T_+}\right)f(\mathbf k)e^{-i(\omega_\mathbf k+\nu)t+i\mathbf{k\cdot x}}\phi(x)
\end{aligned}
$$
我们知道Klein-Gordon场无相互作用，因此若$\phi$满足$(-\partial^2+m^2)\phi=0$，上式应当为$0$；而对于又相互作用的场则为有限值。方便起见，先作用在指数项上，变为
$$
\int\frac{\mathrm d^4x\mathrm d\nu\mathrm d^3\mathbf k}{(2\pi)^4}\tilde g(\nu)\frac{e^{i\nu T_-}-e^{-i\nu T_+}}{-2\omega_\mathbf k\nu-\nu^2}f(\mathbf k)(-\partial^2+m^2)\left[e^{-i(\omega_\mathbf k+\nu)t+i\mathbf{k\cdot x}}\right]\phi(x)
$$
其中用到了$\omega_\mathbf k^2=m^2+\mathbf k^2$。利用分部积分可以将偏导挪到$\phi$上
$$
\int\frac{\mathrm d^4x\mathrm d\nu\mathrm d^3\mathbf k}{(2\pi)^4}\tilde g(\nu)\frac{e^{i\nu T_-}-e^{-i\nu T_+}}{-2\omega_\mathbf k\nu-\nu^2}f(\mathbf k)e^{-i(\omega_\mathbf k+\nu)t+i\mathbf{k\cdot x}}(-\partial^2+m^2)\phi(x)
$$
由于$|T_\pm|\rightarrow\infty$，所以对于任何变化“缓慢”的函数$f(\nu)$，$0\notin[a,b]$，都有$\int_a^bf(\nu)e^{i\nu T_\pm}\mathrm d\nu=0$。而对于$0\in[a,b]$，因为有效的只有$0$附近的值，所以可以将$\nu^2$项丢弃
$$
\int_{-\infty}^\infty\frac{e^{i\nu T}}{\nu}\mathrm d\nu=i\int_{\nu=-\infty}^\infty\frac{\sin\nu T}{\nu T}\mathrm d(\nu T)=i\pi\mathrm{sign}(T)
$$
因此
$$
C-\overline C=\int\mathrm d^4x\tilde{dk}\ ie^{ik\cdot x}\tilde g(0)f(\mathbf k)(\partial^2-m^2)\phi(x)\tag{11}
$$
取$\tilde g(0)=1$，则
$$\begin{aligned}
&\langle out|in\rangle=i^{n+n'}\\
\times&\int\tilde{\mathrm dp_1}f_1(\mathbf p_1)\cdots\int\tilde{\mathrm dp_n}f_n(\mathbf p_n)\\
\times&\int\tilde{\mathrm dp'_1}f'_1(\mathbf p'_1)\cdots\int\tilde{\mathrm dp'_{n'}}f'_{n'}(\mathbf p'_{n'})\\
\times&\int\mathrm d^4x_1(m^2-\partial^2_1)\cdots\int\mathrm d^4x_n(m^2-\partial^2_n)\\
\times&\int\mathrm d^4x'_1(m^2-\partial'^2_1)\cdots\int\mathrm d^4x'_{n'}(m^2-\partial'^2_{n'})\\
\times&\langle0|\hat T[\phi(x_1')\cdots\phi'(x_{n'})]|0\rangle
\end{aligned}\tag{12}$$
