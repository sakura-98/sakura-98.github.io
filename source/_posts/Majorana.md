---
title: Majorana
tags: physics
categories: QFT
mathjax: true
date: 2020-11-27
---

Klein-Gordon场$\rightarrow$Majorana场$\rightarrow$自旋场、电磁场

todo:

1. 为什么对于任意满足$k_\mu k^\mu=-m^2$的4-矢量，根据Lorentz不变性可以得到一个解
2. 验证(3.10)(3.11)

<!--more-->

### 自由场理论

自由场应该满足两个条件：1. 时空平移不变性；2. Lorentz不变性。我们可以将复数场分解为两个实数场，所以可以限制自由场为实数。

#### Klein-Gordon场

从我们已知的Klein-Gordon场出发，我们可以写成线性方程组。定义
$$\varphi_1\equiv\varphi,\varphi_a\equiv\frac1m\partial^{a-2}\varphi,2\le a\le5\tag{1.1}$$

以上定义了五个新的“标量场”，以及四个方程（第一个除外）。第五个方程为Klein-Gordon方程
$$0=-\partial_\mu(m\varphi_{\mu+2})+m^2\varphi_1\Rightarrow
-\partial_0\varphi_2-\partial_1\varphi_3-\partial_2\varphi_4-\partial_3\varphi_5+m\varphi_1=0\tag{1.2}$$

将这五条**一阶偏微分方程**写成矩阵形式
$$(C^\mu\partial_\mu+m)\varphi=0\tag{1.3}$$

其中
$$
C^0=\left[\begin{array}{ccccc}
0 & -1 & 0 & 0 & 0 \\
1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
\end{array}\right],
C^1=\left[\begin{array}{ccccc}
0 & 0 & -1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
-1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
\end{array}\right],
C^2=\left[\begin{array}{ccccc}
0 & 0 & 0 & -1 & 0 \\
0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
-1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
\end{array}\right],
C^3=\left[\begin{array}{ccccc}
0 & 0 & 0 & 0 & -1 \\
0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 \\
-1 & 0 & 0 & 0 & 0 \\
\end{array}\right],
\varphi=\left[\begin{array}{c}
\varphi_1 \\\varphi_2 \\\varphi_3 \\\varphi_4 \\\varphi_5 \\
\end{array}\right],
$$

如果一个自由场理论有两个甚至多个质量参数，那么可以将其解耦为多个理论。所以我们可以假设只有一个质量参数

#### 对称性的限制

一般而言，对$\varphi=(\varphi_1,\cdots\varphi_N)^T$，自由场方程为$(C^\mu\partial_\mu+m)\varphi$，其中$C^0,C^1,C^2,C^3\in\mathbb R^{N\times N},m\ge0$。

根据时空平移对称性，$C^\mu$是常量。

根据Lorentz不变性，存在一个解为$\varphi(x)=ue^{ik\cdot(x-a)}+c.c$，进而$ue^{ik\cdot x}$也满足自由场方程（但不是解，因为不是实的），即
$$(ik_\mu C^\mu+m)u=0\Rightarrow\det(ik_\mu C^\mu+m)=0\tag{1.4}$$

此外，自由场可变换基底$\varphi=S\varphi'$，场方程化为$(S^{-1}C^\mu S\partial_\mu+m)\varphi'=0$，这说明相似变换联系着相同的场。

### Majorana自由场

而on-shell要求$k_1^2+k_2^2+k_3^2\ge m^2$有下界。但根据(1.4)可知$N=1$要求$k_\mu$形成一个平面，所以不可能。同理$N=3$也不可能。至于$N=2$，则要求
$$(if_1-m)(if_2-m)-i^2f_3f_4=-k_0^2+k_1^2+k_2^2+k_3^2+m^2\tag{2.1}$$

其中$f_j$均为$k_0,k_1,k_2,k_3$的一次齐次式。因为$m$没有一次项，所以
$$f_1+f_2=0\Rightarrow f_1^2+f_3f_4=-k_0^2+k_1^2+k_2^2+k_3^2\tag{2.2}$$

利用待定系数法，共有$4\times3=12$个待定系数和$10$条方程。

所谓的Majorana场为$N=4$，所以它不是Klein-Gordon场。$C^\mu$不唯一，至少可以用相似变换联系起来，一个特解为
$$
C^0=\left[\begin{array}{cccc}
0 & 0 & 0 & -1 \\
0 & 0 & -1 & 0 \\
0 & +1 & 0 & 0 \\
+1 & 0 & 0 & 0 \\
\end{array}\right],
C^1=\left[\begin{array}{cccc}
0 & +1 & 0 & 0 \\
+1 & 0 & 0 & 0 \\
0 & 0 & 0 & -1 \\
0 & 0 & -1 & 0 \\
\end{array}\right],
C^2=\left[\begin{array}{cccc}
+1 & 0 & 0 & 0 \\
0 & -1 & 0 & 0 \\
0 & 0 & +1 & 0 \\
0 & 0 & 0 & -1 \\
\end{array}\right],
C^3=\left[\begin{array}{cccc}
0 & 0 & 0 & -1 \\
0 & 0 & -1 & 0 \\
0 & -1 & 0 & 0 \\
-1 & 0 & 0 & 0 \\
\end{array}\right]
$$

可以验证
$$\det(ik_\mu C^\mu+m)=(k^2+m^2)^2\tag{2.3}$$

当然，可以显式地写为
$$\left\{\begin{aligned}
-\partial_0\varphi_4+\partial_1\varphi_2+\partial_2\varphi_1-\partial_3\varphi_4+m\varphi_1=0\\
-\partial_0\varphi_3+\partial_1\varphi_1-\partial_2\varphi_2-\partial_3\varphi_3+m\varphi_2=0\\
+\partial_0\varphi_2-\partial_1\varphi_4+\partial_2\varphi_3-\partial_3\varphi_2+m\varphi_3=0\\
+\partial_0\varphi_1-\partial_1\varphi_3-\partial_2\varphi_4-\partial_3\varphi_1+m\varphi_4=0\\
\end{aligned}\right.\tag{2.4}$$

容易验证这些矩阵满足反对易关系
$$\frac12\{C^\mu,C^\nu\}=g^{\mu\nu}\tag{2.5}$$

最后，我们说明，Majorana场的每个组成部分都是Klein-Gordon场
$$0=(C^\nu\partial_\nu+m)(C^\mu\partial_\mu-m)\varphi=(C^\nu C^\mu\partial_\mu\partial_\nu-m^2)\varphi\tag{2.6}$$

将指标交换不改变结果，因此
$$0=\left(\frac12\{C^\nu,C^\mu\}\partial_\mu\partial_\nu-m^2\right)\varphi=(\partial_\mu\partial^\mu-m^2)\varphi\tag{2.6}$$

### Majorana场的Lorentz变换

在标量场中，Lorentz变换为对坐标做逆变换。但在多分量的自由场中，还需要对分量之间做变换，只是这个变换我们尚未知晓
$$\varphi(x)\rightarrow\bar\varphi(x)=L(\Lambda)\varphi(\Lambda^{-1}x)\tag{3.1}$$

#### 无穷小变换

无穷小变换可写为
$$L(1+\theta)=1+\frac i2\theta_{\mu\nu}S^{\mu\nu}\tag{3.2}$$

回忆标量场时利用保内积证明
$$g_{\mu\nu}\Lambda^\mu_{\ \rho}\Lambda^\nu_{\ \sigma}=g_{\rho\sigma}\Rightarrow0=g_{\rho\nu}\theta^\nu_{\ \sigma}+g_{\mu\sigma}\theta^\mu_{\ \rho}=\theta_{\rho\sigma}+\theta_{\sigma\rho}\tag{3.3}$$

因此$S$的”对称“部分无贡献，即可假设$S^{\mu\nu}=-S^{\nu\mu}$。所以有六个独立分量$S^{01},S^{02},S^{03},S^{12},S^{23},S^{13}$

> 需要注意的是，这里要求$S$反对称，但不要求$S^{\mu\nu}\in\mathbb R^{4\times 4}$反对称

#### 变换的表示

注意到$L(\Lambda)$的表示空间是自由场的多分量
$$(C^\mu\partial_\mu+m)\bar\varphi(x)=L(\Lambda)\left[(\Lambda^{-1})^\mu_{\ \nu}L^{-1}(\Lambda)C^\nu L(\Lambda)\frac{\partial}{\partial y^\mu}+m\right]\varphi(y)\tag{3.4}$$

这说明
$$L^{-1}(\Lambda)C^\nu L(\Lambda)=C^\mu\Leftrightarrow L^{-1}(\Lambda)C^\nu L(\Lambda)=\Lambda^\nu_{\ \mu}C^\mu\tag{3.5}$$

#### 生成元

(3.2)代入(3.5)得
$$-\frac i2\theta_{\rho\sigma}\left[S^{\rho\sigma},C^\nu\right]=\theta^\nu_{\ \mu}C^\mu=g^{\nu\rho}\theta_{\rho\sigma}C^\sigma\tag{3.6}$$

既然对所有无穷小都成立，所以
$$\frac12\left[C^\nu,iS^{\rho\sigma}\right]=g^{\nu\rho}C^\sigma\tag{3.7}$$

利用$S^{\rho\sigma}=-S^{\sigma\rho}$得
$$\left[C^\nu,iS^{\rho\sigma}\right]=g^{\nu\rho}C^\sigma-g^{\nu\sigma}C^\rho\tag{3.7}$$

假设$S_1^{\rho\sigma},S_2^{\rho\sigma}$都是(3.7)的解，那么它们的差$X$满足
$$\left[C^\nu,X\right]=0\tag{3.8}$$

$C^2$给出$X_{12}=X_{14}=X_{21}=X_{23}=X_{32}=X_{34}=X_{41}=X_{43}=0$；再利用$C^0\pm C^3$给出其他四个非对角元也为零，以及$X_{11}=X_{44},X_{22}=X_{33}$；最后根据$C^2$给出$X_{11}=X_{22}$。综上所述，$X=\xi\mathbb1$，因此可以再给一个限制使得不确定性消失
$$\mathrm{Tr}S^{\rho\sigma}=0\tag{3.9}$$

> 利用(2.5)检验下式
> $$\begin{aligned}\left[C^\mu,\left[C^\rho,C^\gamma\right]\right]
> =&-\left[C^\rho,\left[C^\gamma,C^\mu\right]\right]-\left[C^\gamma,\left[C^\mu,C^\rho\right]\right]\\
> \end{aligned}$$

可以证明（但没证过）

$$S^{\rho\sigma}=-\frac i4[C^\rho,C^\sigma]\tag{3.10}$$
$$[S^{\mu\nu},S^{\rho\sigma}]=i\left[g^{\mu\rho}S^{\nu\sigma}-(\mu\leftrightarrow\sigma)\right]-(\rho\leftrightarrow\sigma)\tag{3.11}$$

### 自旋

转动算符为$U(\Lambda)$
$$U(\Lambda^{-1})\varphi(x)U(\Lambda)=L(\Lambda)\varphi(\Lambda^{-1}x)\tag{4.1}$$

同样考虑无穷小变换$\Lambda=1+\theta$，注意希腊字母代表0-3，英文字母代表1-4
$$\left(1-\frac i2\theta_{\mu\nu}M^{\mu\nu}\right)\varphi_a(x)\left(1+\frac i2\theta_{\mu\nu}M^{\mu\nu}\right)=\left(1+\frac i2\theta_{\mu\nu}S^{\mu\nu}\right)^b_{a}\varphi_b(x+\theta x)\tag{4.2}$$

与经典对应可知，$M$为角动量，具体而言，$M^{ij}=\epsilon_{ijk}J_k$，进而可以定义$M^{0i}=K_i$。至于其他分量，和之前的讨论一样我们可以假设$M^{ab}=-M^{ba}$。展开到一阶
$$-\frac i2\theta_{\mu\nu}\left[M^{\mu\nu},\varphi_a(x)\right]=\theta_{\mu\nu}x^\mu\partial^\nu\varphi_a(x)+\frac i2\theta_{\mu\nu}\left(S^{\mu\nu}\right)^b_a\varphi_b(x)\tag{4.3}$$

注意到$\theta_{\mu\nu}=-\theta_{\mu\nu}$，通过指标对换可以写得更加对称
$$\left[\varphi_a(x),M^{\mu\nu}\right]=\frac1i\left(x^\mu\partial^\nu-x^\nu\partial^\mu\right)\varphi_a(x)+\left(S^{\mu\nu}\right)^b_a\varphi_b(x)\tag{4.3}$$

---

特殊地，我们考虑特殊情况
$$\left[\varphi_a(x),J_3\right]=\frac1i\left(x^1\partial^2-x^2\partial^1\right)\varphi_a(x)+\left(S^{12}\right)^b_a\varphi_b(x)\tag{4.3}$$

利用(3.10)
$$\left\{\begin{aligned}
&\left[\varphi_1(x),J_3\right]=\frac1i\left(x^1\partial^2-x^2\partial^1\right)\varphi_1(x)+\frac i2\varphi_2(x)\\
&\left[\varphi_2(x),J_3\right]=\frac1i\left(x^1\partial^2-x^2\partial^1\right)\varphi_2(x)-\frac i2\varphi_1(x)\\
&\left[\varphi_3(x),J_3\right]=\frac1i\left(x^1\partial^2-x^2\partial^1\right)\varphi_3(x)-\frac i2\varphi_4(x)\\
&\left[\varphi_4(x),J_3\right]=\frac1i\left(x^1\partial^2-x^2\partial^1\right)\varphi_4(x)+\frac i2\varphi_3(x)\\
\end{aligned}\right.\tag{4.4}$$

对于固定的零分量，可以定义
$$O_1(t)=\int\mathrm d^3\bm x\ [\varphi_1(x)+i\varphi_2(x)]\Rightarrow[O_1(t),J_3]=\frac12O_1(t)\tag{4.5}$$

所以升降算符每次升降为$1/2$，即自旋1/2

### 左/右手旋量
