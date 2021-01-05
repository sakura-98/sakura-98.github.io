---
title: Majorana
tags: physics
categories: QFT
mathjax: true
date: 2020-12-31
---

我发现自己连Majorana场的量子化都不会了，所以需要整理一下。顺便，新年快乐！

和[Klein-Gordon场](/2020/09/29/Klein-Gordon场量子化/)相似，先从运动方程计算（反）对易关系。他俩为

$$
(C^\mu\partial_\mu+m)\phi(x)=0,[\phi_a(x),\phi_b(y)]_\sigma=f_{ab}(x-y)
$$

<!--more-->

### 计算（反）对易关系

定义变换到动量空间为
$$
\phi(k)\equiv\int\mathrm d^4x\ e^{-ikx}\phi(x),f_{ab}(k)\equiv\int\mathrm d^4x\ e^{-ikx}f_{ab}(x)\tag{1.1}
$$

#### Lorentz变换寻找各点的关系

$$
f_{ab}(x)=[\phi_a(x),\phi_b(0)]=L(\Lambda)_{ac}L(\Lambda)_{bd}[\phi_c(\Lambda^{-1}x),\phi_d(\Lambda^{-1}0)]=L(\Lambda)_{ac}L(\Lambda)_{bd}f_{cd}(\Lambda^{-1}x)
$$

变换到动量空间，注意到$(\Lambda k)\cdot(\Lambda x)=k\cdot x$
$$
f_{ab}(\Lambda k)=L(\Lambda)_{ac}L(\Lambda)_{bd}\int\mathrm d^4x\ e^{-i(\Lambda k)x}f_{cd}(\Lambda^{-1}x)
=L(\Lambda)_{ac}L(\Lambda)_{bd}f_{cd}(k)\tag{1.2}
$$

这说明能通过Lorentz变换联系起来的两个点，值并不独立。

#### 根据运动方程寻找非零点

$$
0=(C^\mu\partial_\mu+m)\left[\phi(x),\phi(0)\right]_\sigma=(C^\mu\partial_\mu+m)f(x)=\int\frac{\mathrm d^4k}{(2\pi)^4}e^{ikx}(iC^\mu k_\mu+m)f(k)
$$

这说明只有$\det(iC^\mu k_\mu+m)=(k^2+m^2)^2\neq0$时才有非零值。因此只有两个独立值$f(\pm m,0,0,0)$

因为此时$k$没有空间分量，所以空间纯转动不会有任何影响，即由(1.2)式得$f_{ab}(k)=L(\Lambda)_{ac}L(\Lambda)_{bd}f_{cd}(k)$。

> 从运动方程可以推出
> $$
> 0=\left(C^\mu\frac{\partial}{\partial x^\mu}+m\right)L(\Lambda)\phi(\Lambda^{-1}x)=L(\Lambda)\left(L(\Lambda)^{-1}C^\mu(\Lambda^{-1})^\nu_\mu L(\Lambda)\partial_\nu+m\right)\phi(y)
> $$
> 对于无限小变换$\Lambda=1+\theta J^{ij},L(\Lambda)=1+\theta S^{ij}$，根据$L(\Lambda)^{-1}C^\mu(\Lambda^{-1})^\nu_\mu L(\Lambda)=C^\nu$保留一阶
> $$
> [C^\nu,S^{ij}]=C^\mu (J^{ij})^\nu_\mu=C^j\delta^{\nu i}-C^i\delta^{\nu j}\Rightarrow S^{ij}=\frac12 C^iC^j
> $$

$$
f_{ab}(k)=\left(\delta_{ac}+\theta\frac12(C^iC^j)_{ac}\right)\left(\delta_{bd}+\theta\frac12(C^iC^j)_{bd}\right)f_{cd}(k)\Rightarrow C^iC^jf+f(C^iC^j)^T=0
$$

解得
$$
f(k)=\left(\begin{array}{cccc}a11& a12& a13& a14\\
-a12& a11& a14& -a13\\
-a13& -a14& a11& a12\\
-a14& a13& -a12& a11
\end{array}\right)=a_{11}1-a_{12}C^5+a_{13}C^1C^2C^3-a_{14}C^0
$$

利用$(iC^\mu k_\mu+m)f=0$可得每列都应该是$(1,0,0,\mp i)(0,1,\mp i,0)$的线性组合，所以
$$
f(\pm m,0,0,0)=A(1\mp iC^0)+B(1\pm iC^0)C^5=\left(\begin{array}{cccc}
A& -B& \pm iB& \pm iA\\
B& A& \pm iA& \mp iB\\
\mp iB& \mp iA& A& -B\\
\mp iA& \pm iB& B& A
\end{array}\right)
$$

#### 共轭、反演

$$
\begin{aligned}
f^*_{ab}(k)=&\left[\int\mathrm d^4x\ e^{-ikx}[\phi_a(x),\phi_b(0)]_\sigma\right]^*=\int\mathrm d^4x\ e^{ikx}[\phi_a(x),\phi_b(0)]_\sigma\left(=f_{ab}(-k)\right)\\
=&\int\mathrm d^4(-y)\ e^{-iky}[\phi_a(-y)\phi_b(0)-\sigma\phi_b(0)\phi_a(-y)]\\
=&\int\mathrm d^4y\ e^{-iky}(-\sigma)[\phi_b(0)\phi_a(-y)-\sigma\phi_a(-y)\phi_b(0)]\\
=&\int\mathrm d^4y\ e^{-iky}(-\sigma)f_{ba}(y)=-\sigma f_{ba}(k)
\end{aligned}\tag{1.4}
$$

因为共轭等于负宗量，所以$A,B\in\R$
$$
f(\pm m,0,0,0)=\left(\begin{array}{cccc}
A& -B& \pm iB& \pm iA\\
B& A& \pm iA& \mp iB\\
\mp iB& \mp iA& A& -B\\
\mp iA& \pm iB& B& A
\end{array}\right),f^\dagger=\left(\begin{array}{cccc}
A& B& \pm iB& \pm iA\\
-B& A& \pm iA& \mp iB\\
\mp iB& \mp iA& A& B\\
\mp iA& \pm iB& -B& A
\end{array}\right)
$$

所以$B=0,\sigma=-1$。因此
$$
f(k_0,0,0,0)=2\pi\delta(k^2+m^2)\left[\beta\theta(k_0)(1-iC^0)+\alpha\theta(-k_0)(1+iC^0)\right]
$$

#### 具体表达式，因果律

进而一般地，根据$f_{ab}(\Lambda k)=L(\Lambda)_{ac}L(\Lambda)_{bd}f_{cd}(k)$得
$$
f(k)=2\pi\delta(k^2+m^2)\left[\alpha\theta(k^0)L(\Lambda)(1+iC^0)L(\Lambda)^T+\beta\theta(-k^0)L(\Lambda)(1-iC^0)L(\Lambda)^T\right]
$$
其中$L(1+\theta K^{0i})=1+\frac\theta4[C^0,C^i]$. 若考虑$(k,0,0,0)\stackrel\Lambda\rightarrow(k^0,k^1,0,0)$，则boost为
$$
\Lambda=\lim_{\theta_0\rightarrow0}\left(\begin{array}{cc}1 & \theta_0 \\\theta_0 & 1\end{array}\right)^{\theta/\theta_0}=\left(\begin{array}{cc}\cosh\theta & \sinh\theta \\\sinh\theta & \cosh\theta\end{array}\right),L=\left(\begin{array}{cccc}
\cosh\frac\theta2&0&-\sinh\frac\theta2&0\\
0&\cosh\frac\theta2&0&-\sinh\frac\theta2\\
-\sinh\frac\theta2&0&\cosh\frac\theta2&0\\
0&-\sinh\frac\theta2&0&\cosh\frac\theta2
\end{array}\right)=\sqrt{\frac{k^0+k}{2k}}-\frac{k^1}{\sqrt{2k(k^0+k)}}C^0C^1
$$
此时为
$$
\begin{aligned}
f(k)=&2\pi\delta(k^2+m^2)\left\{\left[\alpha\theta(k^0)+\beta\theta(-k^0)\right]LL^T+\left[\alpha\theta(k^0)-\beta\theta(-k^0)\right]LiC^0L^T\right\}\\
=&2\pi\delta(k^2+m^2)\left\{\frac1{k}\left[\alpha\theta(k^0)+\beta\theta(-k^0)\right](k^0-k^1C^0C^1)+i\left[\alpha\theta(k^0)-\beta\theta(-k^0)\right]C^0\right\}\\
=&2\pi\delta(k^2+m^2)\left\{\frac1{k}\left[\alpha\theta(k^0)+\beta\theta(-k^0)\right](-k^0C^0+k^1C^1)C^0+i\left[\alpha\theta(k^0)-\beta\theta(-k^0)\right]C^0\right\}\\
\end{aligned}
$$

由于$\delta$函数的存在，要求$k=\pm m$，即
$$
f(k)=2\pi\delta(k^2+m^2)\left\{\frac1{m}\left[\alpha\theta(k^0)-\beta\theta(-k^0)\right](-k^0C^0+k^1C^1)C^0+i\left[\alpha\theta(k^0)-\beta\theta(-k^0)\right]C^0\right\}
$$
提出公因子，容易推广到其他boost，最终为
$$
f(k)=2\pi\delta(k^2+m^2)\frac{\alpha\theta(k^0)-\beta\theta(-k^0)}{m}(k\!\!\!\backslash+im)C^0\tag{1.5}
$$
那么变换回坐标空间
$$
\begin{aligned}
f(x)=&\int\frac{\mathrm d^4k}{(2\pi)^3}e^{ikx}\delta(k^2+m^2)\frac{\alpha\theta(k^0)-\beta\theta(-k^0)}{m}(k\!\!\!\backslash+im)C^0\\
=&\int\frac{\mathrm d^3\vec k}{(2\pi)^32\omega_{\vec k}}e^{-i\omega_{\vec k}t}e^{i\vec k\cdot\vec x}\frac{\alpha}{m}(-\omega_{\vec k}C^0+k^iC^i+im)C^0\\
-&\int\frac{\mathrm d^3\vec k}{(2\pi)^32\omega_{\vec k}}e^{i\omega_{\vec k}t}e^{i\vec k\cdot\vec x}\frac{\beta}{m}(\omega_{\vec k}C^0+k^iC^i+im)C^0\\
\end{aligned}
$$
类空时$f(x)\equiv0$，所以不妨计算如下式子，第二项把$\vec k\rightarrow -\vec k$
$$
\begin{aligned}
f(0,\vec x)+f(0,-\vec x)=&\int\frac{e^{i\vec k\cdot\vec x}\mathrm d^3\vec k}{(2\pi)^3\omega_{\vec k}m}\left[\alpha(\omega_{\vec k}+imC^0)-\beta(-\omega_{\vec k}+imC^0)\right]\\
=&\frac{\alpha+\beta}m\delta^3(\vec x)+i(\alpha-\beta)\int\frac{e^{i\vec k\cdot\vec x}\mathrm d^3\vec k}{(2\pi)^3\omega_{\vec k}}C^0\\
\end{aligned}
$$

第二项和$\vec x$有关，所以要求$\alpha=\beta$，进而
$$
f(k)=\frac\alpha m(2\pi)\delta(k^2+m^2)\mathrm{sgn}(k^0)(k\!\!\!\backslash+im)C^0\tag{1.6}
$$

#### 尚待解决的问题

1. $\alpha$现在只知道是实数，通过波函数的伸缩可以自由变大变小，但尚未知道其正负性
2. 从动量空间变换回坐标空间。具体表达式要用到很怪的数理技巧，下节计算等时情形

这两个问题都将在下一节中（部分）解决

### 等时特例

$$
f(0,\vec x)=\int\frac{\mathrm d^4k}{(2\pi)^4}e^{ikx}f(k)
=\frac\alpha m\int\frac{\mathrm d^3\vec k}{(2\pi)^32\omega_{\vec k}}e^{i\vec k\cdot\vec x}(-2\omega_{\vec k}C^0)C^0=\frac\alpha m\delta^3(\vec x)
$$

也就是说
$$
\{\phi_a(t,\vec x),\phi_b(t,\vec y)\}=\frac\alpha m\delta^3(\vec x-\vec y)\delta_{ab}
$$
因为场算符（波函数）是厄米的，所以其平方应当非负，即$\alpha>0$。通过伸缩我们可以要求
$$
\{\phi_a(t,\vec x),\phi_b(t,\vec y)\}=\delta^3(\vec x-\vec y)\delta_{ab}\tag2
$$

### 4-动量

#### 积木

哈密顿量应当满足
$$
\left[P_\mu,\phi_a(t,\vec x)\right]=i\partial_\mu\phi_a(t,\vec x)\tag{3.1}
$$
我们能用的“积木”为(2)式及其导数
$$
\begin{aligned}
&\int\mathrm d^3\vec y\ [\phi_i(t,\vec y)\phi_j(t,\vec y),\phi_a(t,\vec x)]
=\int\mathrm d^3\vec y\ \left(\phi_i\phi_j\phi_a-\phi_a\phi_i\phi_j\right)\\
=&\int\mathrm d^3\vec y\left(\phi_i\phi_j\phi_a-\delta_{ia}\delta^3(\vec x-\vec y)\phi_j+\phi_i\phi_a\phi_j\right)
=\int\mathrm d^3\vec y\left(-\delta_{ia}\delta^3(\vec x-\vec y)\phi_j+\phi_i\delta_{aj}\delta^3(\vec x-\vec y)\right)\\
=&\delta_{ja}\phi_i(t,\vec x)-\delta_{ia}\phi_j(t,\vec x)
\end{aligned}\tag{3.2}
$$

$$
\begin{aligned}
&\int\mathrm d^3\vec y\ [\phi_i(t,\vec y)\partial_k\phi_j(t,\vec y),\phi_a(t,\vec x)]=\int\mathrm d^3\vec y\ (\phi_i(\partial_k\phi_j)\phi_a-\phi_a\phi_i(\partial_k\phi_j))\\
=&\int\mathrm d^3\vec y\ (\phi_i\partial_k(\phi_j\phi_a)-(\delta_{ai}\delta^3(\vec x-\vec y)-\phi_i\phi_a)\partial_k\phi_j)\\
=&\int\mathrm d\vec y\ (\phi_i\partial_k(\phi_j\phi_a+\phi_a\phi_j)-\delta_{ai}\delta^3(\vec x-\vec y)\partial_k\phi_j)\\
=&\int\mathrm d^3\vec y\ \phi_i\partial_k(\delta_{ja}\delta^3(\vec y-\vec x))-\delta_{ai}\partial_k\phi_j(t,\vec x)\\
=&-\int\mathrm d^3\vec y\ \delta_{ja}\delta^3(\vec y-\vec x)\partial_k\phi_i-\delta_{ai}\partial_k\phi_j(t,\vec x)
=-\delta_{aj}\partial_k\phi_i(t,\vec x)-\delta_{ai}\partial_k\phi_j(t,\vec x)
\end{aligned}\tag{3.3}
$$

#### 动量

(3.1)告诉我们$[P_k,\phi_a(t,\vec x)]=i\partial_k\phi_a(t,\vec x)$，利用(3.3)得到
$$
P_k=-\frac i2\sum_{i=1}^4\int\mathrm d^3\vec y\ \phi_i(t,\vec y)\partial_k\phi_i(t,\vec y)
$$

#### 哈密顿量

(3.1)告诉我们$-[H,\phi_a(t,\vec x)]=i\partial_0\phi_a(t,x)$，再利用运动方程
$$
[H,\phi_a(t,\vec x)]=-i\partial_0\phi_a(t,\vec x)=-i(C^0C^k\partial_k+C^0m)\phi_a(t,\vec x)
$$
利用(3.3)凑出第一项，利用(3.2)凑出第二项
$$
H=\int\mathrm d^3\vec y\left\{\frac i2\phi^T(t,\vec y)C^0C^k\partial_k\phi(t,\vec y)+\frac i2\phi^T(t,\vec y)C^0m\phi(t,\vec y)\right\}=\frac i2\int\mathrm d^3\vec y\ \phi^TC^0(C^k\partial_k+m)\phi
$$

### 波函数

我们希望将波函数以4-动量的本征态展开

$$
0=(iC^\mu k_\mu+m)u(\vec k)
$$

因为$\det(iC^\mu k_\mu+m)=(k^2+m^2)^2$，所以有两个特解$u_+(\vec k),u_-(\vec k)$。考虑到$k^0=\pm\omega_{\vec k}$，对于一个3-动量存在四个特解，剩下两个可以根据下式直接写出为$u_\pm^*(-\vec k)$。
$$
0=\left[(iC^\mu k_\mu+m)u(\vec k)\right]^*=(-iC^\mu k_\mu+m)u^*(\vec k)=(iC^\mu k_\mu+m)u^*(-\vec k)
$$
利用厄米性可推出$\phi^*(p)=\phi(-p)$，则波函数可以写为
$$
\phi(p)=2\pi\delta(p^2+m^2)\sum_{s=\pm}(b(\vec p)u_s(\vec p)\theta(p^0)+b^\dagger(\vec p)u_s^*(\vec p)\theta(-p^0))
$$
变换回坐标空间
$$
\phi(x)=\int\frac{\mathrm d^4p}{(2\pi)^4}e^{ikx}\phi(p)=\sum_{s=\pm}\int\tilde{dp}\left[b(\vec p)u_s(\vec p)e^{ipx}+b^\dagger(\vec p)u^*_s(\vec p)e^{-ipx}\right]
$$

#### $u,b$的性质

当$\vec k=\vec 0$时， $k_0=\mp m$，取正半支为$(1-iC^0)u(\vec 0)=0$，我们希望它是角动量$z$分量的本征态，即$\frac i4\left[C^1,C^2\right]$的本征态
$$
u_+(\vec 0)=(1,-i,1,i)^T,u_-(\vec 0)=(1,i,-1,i)^T
$$
诚然，我们可以通过变换$u(\vec k)=L(\Lambda)u(\vec 0)L(\Lambda)^T$

#### 重新审查4-动量

$$
\begin{aligned}
H=&\frac i2\int\mathrm d^3\vec y\ \phi^TC^0(C^k\partial_k+m)\phi\\
=&\frac i2\int\mathrm d^3\vec y\ \sum_{s=\pm}\int\tilde{dp}\left[b(\vec p)u^T_s(\vec p)e^{ipy}+b^\dagger(-\vec p)u^T_s(-\vec p)e^{-ipy}\right]\times\\
&C^0(C^k\partial_k+m)\sum_{s'=\pm}\int\tilde{dp'}\left[b(\vec p')u_{s'}(\vec p')e^{ip'y}+b^\dagger(-\vec p')u_{s'}(-\vec p')e^{-ip'y}\right]\\
=&\frac i2\int\mathrm d^3\vec y\ \sum_{s=\pm}\int\tilde{dp}\left[b(\vec p)u^T_s(\vec p)e^{ipy}+b^\dagger(-\vec p)u^T_s(-\vec p)e^{-ipy}\right]\times\\
&C^0\sum_{s'=\pm}\int\tilde{dp'}\left[(iC^kp'_k+m)b(\vec p')u_{s'}(\vec p')e^{ip'y}+(-iC^kp'_k+m)b^\dagger(-\vec p')u_{s'}(-\vec p')e^{-ip'y}\right]\\
=&\frac i2\sum_{s,s'=\pm}\int\frac{\tilde{dp}}{2\omega_{\vec p}}\left[b(\vec p)u_s^T(\vec p)C^0(-iC^kp_k+m)u_{s'}(-\vec p)\left(b(-\vec p)+b^\dagger(-\vec p)\right)\right]\\
+&\frac i2\sum_{s,s'=\pm}\int\frac{\tilde{dp}}{2\omega_{\vec p}}\left[b^\dagger(-\vec p)u_s^T(-\vec p)C^0(iC^kp_k+m)u_{s'}(\vec p)\left(b(\vec p)+b^\dagger(\vec p)\right)\right]\\
\end{aligned}
$$

