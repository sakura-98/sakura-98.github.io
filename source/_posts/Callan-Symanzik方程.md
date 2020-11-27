---
title: Callan-Symanzik方程
tags: physics
categories: QFT
mathjax: true
date: 2020-11-26
---

费曼图的积分中经常会出现发散，重整化的思想为将发散项根据有限个实验数值或理论假设替代为有限。不同的替代方案从物理上来讲应该是等价的。它们之间由Callan-Symanzik方程相连接。

本文仍然以六维时空的$\varphi^3$理论为例。

<!--more-->

### on-shell方案与$\mu$-方案

我们在[一种正规化方案](/2020/11/14/一种正规化方案/)中计算过自能和三点顶角为
$$\Pi(k^2)=\frac\alpha2\left[\int_0^1\mathrm dx\ D\ln D+c_1+c_2k^2\right]$$
$$V_3(k_1,k_2,k_3)=g\left[1-\frac\alpha2\left(\int\mathrm dF_3\ \ln D_3+c_3\right)\right]$$

其中
$$D=x(1-x)k^2+\omega_0^2,\quad D_3=x_1x_2k_3^2+x_2x_3k_1^2+x_3x_1k_2^2+\omega_0^2$$

当时取的是**on-shell方案**，即$\Pi(-\omega_0^2)=\Pi'(-\omega_0^2)=0,V_3(0,0,0)=g$，结果为
$$\Pi(k^2)=\frac\alpha{12}\left[(k^2+4\omega_0^2)^{3/2}\frac{2\mathrm{arcsinh}\frac{\sqrt{k^2}}{2m}}{\sqrt{k^2}}+(3-2\pi\sqrt3)\omega_0^2+(3-\pi\sqrt3)k^2\right]$$
$$V_3(k_1,k_2,k_3)=g\left[1-\frac\alpha2\int\mathrm dF_3\ \ln \frac{D_3}{\omega_0^2}\right]$$

所谓的 **$\mu$-方案**指的是
$$\left\{\begin{aligned}&\Pi(\mu^2)=\Pi'(\mu^2)=0\\ &V_3(k_1,k_2,k_3)=g,\quad k_1^2=k_2^2=k_3^2=\mu^2\end{aligned}\right.$$

解得
$$\Pi(k^2)=\frac\alpha2\left[-\frac16(k^2-\mu^2)+\int_0^1\mathrm dx\ D\ln \frac D{x(1-x)\mu^2+\omega_0^2}\right]\tag1$$
$$V_3(k_1,k_2,k_3)=g\left[1-\frac\alpha2\int\mathrm dF_3\ \ln \frac{D_3}{(x_1x_2+x_2x_3+x_3x_1)\mu^2+\omega_0^2}\right]\tag2$$

假设此时的拉氏量为
$$\mathcal L=-\frac12\partial_\mu\varphi\partial^\mu\varphi-\frac12\omega_0^2\varphi^2+\frac g{3!}\varphi^3\tag3$$

其中$\omega_0,g$都是$\mu$的函数，他们的限制为物理质量$m$和。

### 物理质量

物理质量为传播子的极点，而传播子为
$$\hat{\mathbf\Delta}(k)=\frac1{k^2+\omega_0^2-\Pi(k^2)}$$

所以物理质量$m$满足如下方程
$$-m^2+\omega_0^2-\frac\alpha2\left[\frac16(m^2+\mu^2)+\int_0^1\mathrm dx\ (-{x(1-x)m^2+\omega_0^2})\ln \frac {-x(1-x)m^2+\omega_0^2}{x(1-x)\mu^2+\omega_0^2}\right]=0$$

也可理解为关于$\omega_0,\mu$的隐函数。

### 波函数

二阶关联函数为传播子，三阶关联函数除了传播子外还有一个顶点
$$\langle T\varphi\varphi\rangle=\Delta,\quad\langle T\varphi\varphi\varphi\rangle=\Delta\Delta\Delta V_3$$

所以可以得到三阶顶点的量纲，更一般地还能得到高阶顶点的量纲
$$V_3\propto\varphi^{-3}\rightarrow V_n\propto\varphi^{-n}$$

### Callan-Symanzik方程

假设方案$\mu\rightarrow\mu(1+\epsilon)$时波函数也改变了一个小量
$$\left.\varphi(x)\right|_{\mu(1+\epsilon)}=(1-\gamma_\varphi\epsilon)\left.\varphi(x)\right|_\mu$$

根据上一小节，可以得到传播子和顶点的变换关系
$$\left.\mathbf\Delta(k)^{-1}\right|_{\mu(1+\epsilon)}=(1+2\gamma_\varphi\epsilon)\left.\mathbf\Delta(k)^{-1}\right|_\mu\tag5$$
$$\left.V_3\right|_{\mu(1+\epsilon)}=(1+3\gamma_\varphi\epsilon)\left.V_3\right|_\mu\tag6$$

(4)可以得到微分方程
$$\mu\epsilon\frac{\mathrm d}{\mathrm d\mu}\mathbf\Delta(k)^{-1}=2\gamma_\varphi\epsilon\mathbf\Delta(k)^{-1}$$

在(3)式的讨论中可知，按链式法则展开
$$\left(\frac{\partial}{\partial\ln\mu}
+\frac{\mathrm d\alpha}{\mathrm d\ln\mu}\frac{\partial}{\partial\alpha}
+\frac{\mathrm d\omega_0}{\mathrm d\ln\mu}\frac{\partial}{\partial\omega_0}
-2\gamma_\varphi\right)\mathbf\Delta(k)^{-1}=0\tag7$$

同理
$$\left(\frac{\partial}{\partial\ln\mu}
+\frac{\mathrm d\alpha}{\mathrm d\ln\mu}\frac{\partial}{\partial\alpha}
+\frac{\mathrm d\omega_0}{\mathrm d\ln\mu}\frac{\partial}{\partial\omega_0}
-3\gamma_\varphi\right)V_3=0\tag8$$

### 参数

先给出结论
$$\left\{\begin{aligned}
&\gamma_\varphi=\frac14f\left(\frac{\omega_0}\mu\right)\alpha+\mathcal O(\alpha^2)\\
&\gamma_{\omega_0}\equiv\frac{\mathrm d\omega_0}{\mathrm d\ln\mu}=\frac14\left(1+\frac{\mu^2}{\omega_0^2}\right)f\left(\frac{\omega_0}{\mu}\right)\alpha\\
&\gamma_\alpha\equiv\frac{\mathrm d\alpha}{\mathrm d\ln\mu}=\left(\frac32f\left(\frac{\omega_0}{\mu}\right)-2h\left(\frac{\omega_0}{\mu}\right)\right)\alpha^2+\mathcal O(\alpha^3)
\end{aligned}\right.$$
其中
$$\left\{\begin{aligned}
f(\xi)&=\frac13-2\xi^2+\frac{8\xi^4}{\sqrt{1+4\xi^2}}\mathrm{arcsinh}\frac1{2\xi}\\
h(\xi)&=\int\mathrm dF_3\frac{x_1x_2+x_2x_3+x_3x_1}{x_1x_2+x_2x_3+x_3x_1+\xi^2}
\end{aligned}\right.$$

可以看到，$\mu\gg\omega_0$时
$$f(\xi)\rightarrow\frac13-2\xi^2,\quad h(\xi)\rightarrow 1-4.68781\xi^2$$

所以根据第三条方程，耦合常数$\alpha$可解为
$$\alpha=\alpha_0\left/\left[1+\frac32\alpha_0\ln\frac\mu{\mu_0}\right]\right.$$

当$\mu$趋于无穷时，耦合常数趋于零，即所谓的渐近自由。

此外，$\gamma_\varphi=\frac1{12}\alpha+\mathcal O(\alpha^2)$

### 参数的计算过程

利用微扰计算，方便起见，记$\xi=\omega_0/\mu$。

利用(1)取$k^2=\mu^2$得,
$$\left\{\begin{aligned}
&\frac{\partial}{\partial\mu}\left.\Pi(k^2)\right|_{k^2=\mu^2}=\frac\alpha2\left[\frac\mu3-\int_0^1\ 2x(1-x)\mu\right]=0\\
&\frac{\partial}{\partial\alpha}\left.\Pi(k^2)\right|_{k^2=\mu^2}=\frac{\partial}{\partial\omega_0}\left.\Pi(k^2)\right|_{k^2=\mu^2}=0\\
\end{aligned}\right.$$

代入(7)得到
$$2\omega_0\gamma_{\omega_0}-2\gamma_\varphi(\mu^2+\omega_0^2)=0\tag{*.1}$$

同理利用(2)取$k_1^2=k_2^2=k_3^2=\mu^2$得
$$\left\{\begin{aligned}
&\frac{\partial}{\partial\mu}\left. V_3(k_j^2)\right|_{k_j^2=\mu^2}=g\alpha\int\mathrm dF_3\ \frac{(x_1x_2+x_2x_3+x_3x_2)\mu}{(x_1x_2+x_2x_3+x_3x_2)\mu^2+\omega_0^2}=g\alpha h(\xi)/\mu\\
&\frac{\partial}{\partial\alpha}\left. V_3(k_j^2)\right|_{k^2_j=\mu^2}=\frac{\partial}{\partial\omega_0}\left. V_3(k_j^2)\right|_{k_j^2=\mu^2}=0\\
\end{aligned}\right.$$

代入(8)得到
$$\alpha h(\xi)-3\gamma_\varphi=0\tag{*.2}$$

最后(1)取$k^2=0$
$$\Pi(0)=\frac\alpha2\left[\frac16\mu^2+\omega_0^2\int_0^1\mathrm dx\ \ln\frac{\omega_0^2}{x(1-x)\mu^2+\omega_0^2}\right]$$

$$\left\{\begin{aligned}
\frac{\partial}{\partial\mu}\left.\Pi(k^2)\right|_{k^2=0}&=\frac\alpha2\left[\frac\mu3-\omega_0^2\int_0^1\mathrm dx\ \frac{2x(1-x)\mu}{x(1-x)\mu^2+\omega_0^2}\right]=\frac\alpha2\mu f(\xi)\\
\frac{\partial}{\partial\alpha}\left.\Pi(k^2)\right|_{k^2=0}&=\frac12\left[\frac16\mu^2+\omega_0^2\int_0^1\mathrm dx\ \ln\frac{\omega_0^2}{x(1-x)\mu^2+\omega_0^2}\right]\\
&=\\
\frac{\partial}{\partial\omega_0}\left.\Pi(k^2)\right|_{k^2=0}&=\alpha\omega_0\int_0^1\mathrm dx\left[\ln\frac{\omega_0^2}{x(1-x)\mu^2+\omega_0^2}+\frac{x(1-x)\mu^2}{x(1-x)\mu^2+\omega_0^2}\right]\\
\end{aligned}\right.$$
