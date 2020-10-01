---
title: Klein-Gordon场量子化
tag: physics
categories: QFT
mathjax: true
date: 2020-09-29
---

Klein-Gordon方程为
$$\left(-\partial^2+\omega_0^2\right)\psi=0\tag{1}$$
在[之前的文章](/2020/09/25/标量场理论)中已经给出对易关系
$$[\phi(x),\phi(y)]=c_+\int\frac{\mathrm{d}^3\vec k}{(2\pi)^3}\frac1{2\omega_{\vec k}}\left[e^{-i\omega_{\vec k}t+i\vec k\cdot\vec x}-e^{i\omega_{\vec k}t+i\vec k\cdot\vec x}\right]\tag{2}$$
其中
$$\omega_{\vec k}=\sqrt{\vec k^2+\omega_0^2}\tag{3}$$

我们不加证明地认为
$$[\phi(x),\phi(y)]=c_+\mathrm{sign}(x^0-y^0)\left[i\omega_0\theta(\tau^2)\frac{J_1(\omega_0\tau)}{4\pi\tau}-\frac i{2\pi}\delta(\tau^2)\right]\tag{4}$$
其中$\tau=\sqrt{-(x-y)^2}$。我们将从此处继续完成Klein-Gordon场的量子化。
<!--more-->
### 计算$c_+$
因为场算符是厄米的，所以（第二个等号用到厄米性）
$$[\phi(x),\phi(y)]^*=[\phi^\dagger(y),\phi^\dagger(x)]=[\phi(y),\phi(x)]=-[\phi(x),\phi(y)]$$
最后一步仅仅用到对易子的定义。所以
$$C^*(x)=-C(x)$$
根据(4)可知$c_+\in\mathbb R$。又因为场算符可以任意伸缩，只需要伸缩量为实数以保持厄米性，所以可以另$c_+=\pm1$。

接下来要计算到底是哪一个，工具是利用哈密顿量有下界。首先我们有
$$[\phi(t,\vec x),\phi(t,\vec y)]\equiv 0\tag{5}$$
当$\vec x=\vec y$时是显然的，否则是因为类空。进一步可以计算
$$\begin{aligned}
&[\phi(t,\vec x),\dot\phi(t,\vec y)]\\
=&\lim_{\epsilon\rightarrow0}\left[\phi(t,\vec x),\frac1\epsilon(\phi(t+\epsilon,\vec y)-\phi(t,\vec y))\right]\\
=&\lim_{\epsilon\rightarrow0}\frac1\epsilon[\phi(t,\vec x),\phi(t+\epsilon,\vec y)]\\
=&\lim_{\epsilon\rightarrow0}\frac{c_+}\epsilon\mathrm{sign}(-\epsilon)\left[i\omega_0\theta(\epsilon^2-|\vec x-\vec y|^2)\frac{J_1(\omega_0\sqrt{\epsilon^2-|\vec x-\vec y|^2})}{4\pi\sqrt{\epsilon^2-|\vec x-\vec y|^2}}-\frac i{2\pi}\delta(\epsilon^2-|\vec x-\vec y|^2)\right]
\end{aligned}\tag{6}$$
当$\vec x-\vec y\neq\vec 0$时，只需$|\epsilon|<|\vec x-\vec y|$即可得到$\theta,\delta$函数均为$0$，所以$[\phi(t,\vec x),\dot\phi(t,\vec y)]\propto\delta(\vec x-\vec y)$。

(6)式第一项中的$J_1(x)=\frac x2-\frac{x^3}{16}+o(x^5)$，所以对$\vec x$积分后领头阶为$\epsilon^3$，在趋于零的时候贡献为$0$。所以对$\vec x$全空间积分为
$$\begin{aligned}
\int[\phi(t,\vec x),\dot\phi(t,\vec y)]\mathrm{d}^3\vec x=&\lim_{\epsilon\rightarrow0}-\frac{ic_+}{2\pi\epsilon}\mathrm{sign}(-\epsilon)\int\mathrm{d}^3\vec x\ \delta(\epsilon^2-|\vec x-\vec y|^2)\\
=&\lim_{\epsilon\rightarrow0}-\frac{ic_+}{2\pi\epsilon}\mathrm{sign}(-\epsilon)\int_0^\infty 4\pi r^2\mathrm{d}r\delta(\epsilon^2-r^2)\\
=&\lim_{\epsilon\rightarrow0}-\frac{ic_+}{2\pi\epsilon}\mathrm{sign}(-\epsilon)\int_0^\infty 4\pi r^2\mathrm{d}r\frac{1}{2|\epsilon|}\delta(\epsilon-r)\\
=&ic_+
\end{aligned}$$
最后一步是注意到符号函数。因此
$$\left\{\begin{array}{l}
[\phi(t,\vec x),\dot\phi(t,\vec y)]=ic_+\delta(\vec x-\vec y)\\
[\phi(t,\vec x),\phi(t,\vec y)]=0
\end{array}\right.\tag{8}$$
根据Heisenberg绘景下的运动方程
$$i\dot\phi(x)=[\phi(x),\hat H]\Rightarrow i\ddot\phi(x)=[\dot\phi(x),\hat x]\tag{9}$$
再根据Klein-Gordon方程
$$(-\partial^2+\omega_0^2)\phi=0\Rightarrow[\dot\phi(x),\hat H]=i(\nabla^2\phi-\omega_0^2\phi)\tag{10}$$
利用(9)“推出”符号左边的等式猜测$\hat H$中有$\frac{1}{2c_+}\int\mathrm{d}^3\vec y\ \dot\phi^2(t,\vec y)$项，再利用(10)“推出”符号右边的等式猜测
$$\hat H=\frac{1}{2c_+}\int\mathrm{d}^3\vec x\left[\dot\phi^2+(\nabla\phi)^2+\omega_0^2\phi^2\right]\tag{11}$$
验证(10)式如下:
$$\begin{aligned}
&[\dot\phi(x),\hat H]=\frac1{2c_+}\int\mathrm{d}^3\vec y\ [\dot\phi(x),(\nabla_{\vec y}\phi(\vec y))^2+\omega_0^2\phi^2(\vec y)]\\
=&\frac1{2c_+}\int\mathrm{d}^3\vec y\ [\dot\phi(x),(\nabla_{\vec y}\phi(\vec y))^2]+\frac1{2c_+}\int\mathrm{d}^3\vec y\ [\dot\phi(x),\omega_0^2\phi^2(\vec y)]\\
=&\frac1{2c_+}\int\mathrm{d}^3\vec y\ [\dot\phi(x),(\nabla_{\vec y}\phi(\vec y))^2]+\frac1{c_+}\int\mathrm{d}^3\vec y\ [-ic_+\delta(\vec x-\vec y)]\omega^2_0\phi(\vec y)\\
=&\frac1{2c_+}\int\mathrm{d}^3\vec y\ [\dot\phi(x),(\nabla_{\vec y}\phi(\vec y))^2]-i\omega^2_0\phi(\vec x)\\
=&\frac1{2c_+}\int\mathrm{d}^3\vec y\ \nabla_{\vec y}\phi(\vec y)[\dot\phi(x),\nabla_{\vec y}\phi(\vec y)]\\
 &+\frac1{2c_+}\int\mathrm{d}^3\vec y\ [\dot\phi(x),\nabla_{\vec y}\phi(\vec y)]\nabla_{\vec y}\phi(\vec y)-i\omega_0^2\phi(\vec x)\\
=&\frac1{c_+}\int\mathrm{d}^3\vec y\ \nabla_{\vec y}\phi(\vec y)\nabla_{\vec y}[-ic_+\delta(\vec x-\vec y)]-i\omega_0^2\phi(\vec x)\\
=&-i\int\mathrm{d}^3\vec y\ \nabla_{\vec y}\phi(\vec y)\nabla_{\vec y}\delta(\vec x-\vec y)-i\omega_0^2\phi(\vec x)\\
=&i\int\mathrm{d}^3\vec y\ \delta(\vec x-\vec y)\nabla^2_{\vec y}\phi(\vec y)-i\omega_0^2\phi(\vec x)\\
=&i\nabla^2_{\vec x}\phi(\vec x)-i\omega_0^2\phi(\vec x)\\
\end{aligned}$$

根据哈密顿有有下界可知$c_+=1$，因为积分内明显是正定的。
> 还有一个小问题，这里没计算$[\dot\phi(t,\vec x),\dot\phi(t,\vec y)]$
> 不过可以将(11)式$\dot\phi\rightarrow\pi$认为是逻辑起点，正如大多数教材都从拉格朗日量出发。

### 哈密顿量的四矢量
(9)式写成四矢量的形式为下式的$0$分量
$$i\partial^\mu\phi(x)=[P^\mu,\phi(x)],i\partial^\mu\dot\phi(x)=[P^\mu,\dot\phi(x)]\tag{12}$$
猜测
$$\vec P=-\int\mathrm{d}^3\vec y\ \dot\phi(\vec y)\nabla_{\vec y}\phi(\vec y)\tag{13}$$
验证(12)左式
$$\begin{aligned}
&[P^\mathrm i,\phi(x)]=-\int\mathrm d^3\vec y\ [\dot\phi(\vec y),\phi(x)]\partial^\mathrm i_{\vec y}\phi(\vec y)\\
=&-\int\mathrm d^3\vec y\ [-i\delta(\vec x-\vec y)]\partial^\mathrm i_{\vec y}\phi(\vec y)\\
=&i\partial^\mathrm i\phi(\vec x)
\end{aligned}$$
### 二次量子化第一步：变换到动量空间
定义
$$\left\{\begin{aligned}
&\tilde\phi(k)=\int\mathrm d^4x\ e^{-ik\cdot x}\phi(x)\\
&\phi(x)=\int\frac{\mathrm d^4k}{(2\pi)^4}\ e^{ik\cdot x}\tilde\phi(k)\\
\end{aligned}\right.\tag{14}$$
则Klein-Gordon方程变为
$$(k^2+\omega_0^2)\tilde\phi(k)=0\tag{15}$$
厄米性条件变为
$$\tilde\phi^\dagger(k)=\int\mathrm d^4x\ e^{ik\cdot x}\phi^\dagger(x)=\tilde\phi(-k)\tag{16}$$
根据(15)式，满足Lorentz不变性的非平庸解为
$$\tilde\phi(k)=2\pi\delta(k^2+\omega_0^2)\left[a(\vec k)\theta(k^0)+a^\dagger(-\vec k)\theta(-k^0)\right]\tag{17}$$
> $$\begin{aligned}&[H,\tilde\phi(k)]=\int\mathrm d^4x\ e^{-ik\cdot x}[H,\phi(x)]\\
> =&\int\mathrm d^4x\ e^{-ik\cdot x}[-i\dot\phi(x)]\\
> =&-i\int\mathrm d^3\vec x\ e^{-i\vec k\cdot\vec x}\int\mathrm dt\ e^{i\omega_{\vec k}t}\dot\phi(x)\\
> =&i\int\mathrm d^3\vec x\ e^{-i\vec k\cdot\vec x}\int\mathrm{d}t\ i\omega_{\vec k}\phi(x)e^{i\omega_{\vec k}t}=-\omega_{\vec k}\tilde\phi(k)\end{aligned}$$
> 所以$H\tilde\phi(k)|E\rangle=(E-\omega_{\vec k})\tilde\phi(k)|E\rangle$，即$k^0=\omega_{\vec k}>0$处$\tilde\phi(k)$为湮灭算符，$k^0<0$处为产生算符

对易关系为
$$\begin{aligned}
&[\tilde\phi(k),\tilde\phi(l)]=\int\mathrm{d}^4x\mathrm{d}^4y\ e^{-ik\cdot x-il\cdot y}[\phi(x),\phi(y)]\\
=&\int\mathrm{d}^4x\mathrm{d}^4y\ e^{-ik\cdot x-il\cdot y}\int\frac{\mathrm{d}k'}{(2\pi)^4}\ e^{ik'\cdot(x-y)}2\pi\delta(k'^2+\omega_0^2)\mathrm{sign}(k'^0)\\
=&(2\pi)^4\int\mathrm{d}k'\ \delta(k'-k)\delta(k'+l)2\pi\delta(k'^2+\omega_0^2)\mathrm{sign}(k'^0)\\
=&(2\pi)^4\delta(k+l)2\pi\delta(k^2+\omega_0^2)\mathrm{sign}(k^0)\\
\end{aligned}\tag{18}$$

### 二次量子化：探索$a,a^\dagger$的物理意义