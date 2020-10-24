---
title: Heisenberg模型
tag: physics
categories: QSP
mathjax: true
date: 2020-10-05
---

根据北京大学shindou开设的《量子统计物理》第一次作业第二题整理。

Heisenberg模型是描述铁磁性的最简单的模型。考虑一个$N\times N\times N$，晶格常数为$a$的立方晶体，在每个格点上都有自旋算符$\hat{\vec s}_{\vec j}=(\hat s_{\vec j,x},\hat s_{\vec j,y},\hat s_{\vec j,z})$。哈密顿量为
$$\hat H=-J\sum_{\langle\vec i,\vec j\rangle}\hat{\vec s}_{\vec i}\cdot\hat{\vec s}_{\vec j}$$
其中$\langle\vec i,\vec j\rangle$表示近邻原子，相互作用$J>0$。
<!--more-->

### 基态$|full\rangle_z$

显然当所有格点上自旋均同向时能量最低，定义此时为基态$|full\rangle_z$。当然，要求它是哈密顿算符的本征态。
$$|full\rangle_z\equiv\prod_{\vec j}|s(s+1),s\rangle_{\vec j,z}\tag{1}$$
其中$|s(s+1),s\rangle_{\vec j,z}$是$\hat{\vec s}_{\vec j}^2,\hat s_{\vec j,z}$的共同本征态，本征值为$s(s+1),s$。为了证明它是哈密顿量的本征态，先计算$\hat{\vec s}_{\vec i}\cdot\hat{\vec s}_{\vec j}$（不要求近邻）作用其上的结果。
定义升降算符
$$\left\{\begin{aligned}
\hat s_{\vec j,+}&=\hat s_{\vec j,x}+i\hat s_{\vec j,y}\\
\hat s_{\vec j,-}&=\hat s_{\vec j,x}-i\hat s_{\vec j,y}\\
\end{aligned}\right.\tag{2}$$
略去下标$\vec j$，容易证明$[\hat s_z,\hat s_+]=i\hat s_j+\hat s_x=\hat s_+,[\hat s_z,\hat s_-]=-\hat s_-$，因此物理意义为升降算符。这样的话
$$\begin{aligned}
&\hat{\vec s}_{\vec i}\cdot\hat{\vec s}_{\vec j}=\hat s_{\vec i,x}\hat s_{\vec j,x}+\hat s_{\vec i,y}\hat s_{\vec j,y}+\hat s_{\vec i,z}\hat s_{\vec j,z}\\
=&\frac14\left(\hat s_{\vec i,+}+\hat s_{\vec i,-}\right)\left(\hat s_{\vec j,+}+\hat s_{\vec j,-}\right)
-\frac14\left(\hat s_{\vec i,+}-\hat s_{\vec i,-}\right)\left(\hat s_{\vec j,+}-\hat s_{\vec j,-}\right)+\hat s_{\vec i,z}\hat s_{\vec j,z}\\
=&\frac12\left(\hat s_{\vec i,+}\hat s_{\vec j,-}+\hat s_{\vec i,-}\hat s_{\vec j,+}\right)+\hat s_{\vec i,z}\hat s_{\vec j,z}\\
\end{aligned}\tag3$$
根据升降算符的性质$\hat s_{\vec i,+}|s(s+1),s\rangle_{\vec i,z}=0$，所以
$$\hat{\vec s}_{\vec i}\cdot\hat{\vec s}_{\vec j}|full\rangle=\hat s_{\vec i,z}\hat s_{\vec j,z}|full\rangle=s^2|full\rangle$$
对所有近邻自旋求和得
$$\hat H|full\rangle=-3JN^3s^2|full\rangle\tag4$$

### 较低激发态-准玻色子

使用Holstein-Primakoff变换，玻色子$[\hat b,\hat b^\dagger]=1$
$$\left\{\begin{aligned}
&\hat s_z=s-\hat b^\dagger\hat b\\
&\hat s_+=\sqrt{2s}\left(1-\frac{\hat b^\dagger\hat b}{2s}\right)^{1/2}\hat b\\
&\hat s_-=\sqrt{2s}\hat b^\dagger\left(1-\frac{\hat b^\dagger\hat b}{2s}\right)^{1/2}\\
\end{aligned}\right.\tag5$$
验证对易关系
$$\left\{\begin{aligned}
&[\hat s_x,\hat s_y]=i\hat s_z\\
&[\hat s_z,\hat s_x]=i\hat s_y\\
&[\hat s_z,\hat s_y]=-i\hat s_x\\
\end{aligned}\right.\Leftrightarrow
\left\{\begin{aligned}
&[\hat s_+,\hat s_-]=2\hat s_z\\
&[\hat s_z,\hat s_+]=\hat s_+\\
&[\hat s_z,\hat s_-]=-\hat s_-\\
\end{aligned}\right.
\tag6$$
右边三项都是极其容易证明的。
考虑$\hat b^\dagger\hat b$的本征态$|n\rangle$，则根据(5)式得
$$\left\{\begin{aligned}
&\hat s_z|n\rangle=(s-n)|n\rangle\\
&\hat s_+|n\rangle=\sqrt{2s}\left(1-\frac{\hat b^\dagger\hat b}{2s}\right)^{1/2}\sqrt n|n-1\rangle=\sqrt{(2s-n+1)n}|n-1\rangle\\
&\hat s_-|n\rangle=\sqrt{2s}\hat b^\dagger\left(1-\frac{n}{2s}\right)^{1/2}|n\rangle=\sqrt{(2s-n)(n+1)}|n+1\rangle\\
\end{aligned}\right.\tag7$$

### 大s展开

将(5)代入(3)得到用$\hat b,\hat b^\dagger$表示的哈密顿量，当$s\gg n$时可只保留$\frac1s$低阶项。顺便可定义$M=s-n$代替$n$，但在此处用不到
$$\begin{aligned}
&\hat H=-J\sum_{\langle\vec i,\vec j\rangle}\hat{\vec s}_{\vec i}\cdot\hat{\vec s}_{\vec j}\\
=&-J\sum_{\langle\vec i,\vec j\rangle}\left[\frac12\left(\hat s_{\vec i,+}\hat s_{\vec j,-}+\hat s_{\vec i,-}\hat s_{\vec j,+}\right)+\hat s_{\vec i,z}\hat s_{\vec j,z}\right]\\
\approx&-J\sum_{\langle\vec i,\vec j\rangle}\left[s\left(\hat b_{\vec i}\hat b^\dagger_{\vec j}+\hat b^\dagger_{\vec i}\hat b_{\vec j}\right)+\left(s-\hat b^\dagger_{\vec i}\hat b_{\vec i}\right)\left(s-\hat b^\dagger_{\vec j}\hat b_{\vec j}\right)\right]\\
\approx&-Js\sum_{\langle\vec i,\vec j\rangle}\left(\hat b_{\vec i}\hat b^\dagger_{\vec j}+\hat b^\dagger_{\vec i}\hat b_{\vec j}-\hat b^\dagger_{\vec i}\hat b_{\vec i}-\hat b^\dagger_{\vec j}\hat b_{\vec j}\right)-J\sum_{\langle\vec i,\vec j\rangle}s^2\\
\end{aligned}\tag8$$
第二项实际上就是基态能量$E_0-3JN^3s^2$正如(4)式；第一项为了方便起见展开写，最终为
$$\hat H=-Js\sum_{\vec i}\sum_{\nu=x,y,z}\left(\hat b_{\vec i}\hat b^\dagger_{\vec i+\vec e_\nu}+\hat b^\dagger_{\vec i}\hat b_{\vec i+\vec e_\nu}-\hat b^\dagger_{\vec i}\hat b_{\vec i}-\hat b^\dagger_{\vec i+\vec e_\nu}\hat b_{\vec i+\vec e_\nu}\right)+E_0\tag9$$

### 对角化

一般而言，二次型通过傅里叶变换就能做到对角化，也就是说，定义
$$\tilde b_{\vec k}=\sum_{\vec i}\frac1{\sqrt{N^3}}\hat b_{\vec i}e^{-i\vec k\cdot\vec i}\tag{10}$$
因为格点有限，所以$\vec k$也是分立的，即用三个整数$k_x,k_y,k_z$描述
$$\vec k=\frac{2\pi}{Na}(k_x,k_y,k_z)\tag{11}$$
容易验证逆变换为
$$\hat b_{\vec i}=\sum_{\vec k}\frac1{\sqrt{N^3}}\tilde b_{\vec k}e^{i\vec k\cdot\vec i}\tag{12}$$
以及对易关系
$$\left[\tilde b_{\vec k},\tilde b^\dagger_{\vec k'}\right]=\sum_{\vec i,\vec j}\frac1{N^3}[\hat b_{\vec i},\hat b_{\vec j}^\dagger]e^{-i\vec k\cdot\vec i+i\vec k'\cdot\vec j}=\sum_{\vec i}\frac1{N^3}e^{-i(\vec k-\vec k')\cdot\vec i}=\delta_{\vec k,\vec k'}\tag{13}$$
$$\left[\tilde b_{\vec k},\tilde b_{\vec k'}\right]=\left[\tilde b^\dagger_{\vec k},\tilde b^\dagger_{\vec k'}\right]=0$$
将(12)代入(9)即可，但在此之前先计算
$$\begin{aligned}
&\sum_{\vec i}\hat b^\dagger_{\vec i}\hat b_{\vec i+\vec j}=\sum_{\vec i}\sum_{\vec k,\vec k'}\frac1{N^3}\tilde b_{\vec k}^\dagger e^{i\vec k\cdot\vec i}\tilde b_{\vec k'}e^{-i\vec k'\cdot(\vec i+\vec j)}\\
=&\sum_{\vec i}\sum_{\vec k,\vec k'}\frac1{N^3}\tilde b_{\vec k}^\dagger\tilde b_{\vec k'}e^{i(\vec k-\vec k')\cdot\vec i}e^{-i\vec k'\cdot\vec j}\\
=&\sum_{\vec k,\vec k'}\tilde b_{\vec k}^\dagger\tilde b_{\vec k'}\delta(\vec k-\vec k')e^{-i\vec k'\cdot\vec j}=\sum_{\vec k}\tilde b_{\vec k}^\dagger\tilde b_{\vec k}e^{-i\vec k\cdot\vec j}\\
\end{aligned}\tag{14}$$
所以(9)为
$$\hat H=-Js\sum_{\vec k}\tilde b^\dagger_{\vec k}\tilde b_{\vec k}\sum_{\nu=x,y,z}\left(e^{i\vec k\cdot\vec e_\nu}+e^{-i\vec k\cdot\vec e_\nu}-2\right)+E_0\tag{15}$$
即
$$\begin{aligned}
&\hat H=\sum_{\vec k}\hbar\omega_{\vec k}\tilde b^\dagger_{\vec k}\tilde b_{\vec k}+E_0\\
&\hbar\omega_{\vec k}=4Js\left[\sin^2\frac{\vec k\cdot\vec e_x}2+\sin^2\frac{\vec k\cdot\vec e_y}2+\sin^2\frac{\vec k\cdot\vec e_z}2\right]
\end{aligned}\tag{16}$$

### 热容

当然，为了要和实验对比，我们计算定容热容$C_V$，一般过程为
$$Z\rightarrow F\rightarrow U\rightarrow C_V$$
配分函数$Z$:
$$\begin{aligned}
&Z=Tr\left[e^{-\beta\hat H}\right]=e^{-\beta E_0}Tr\left[\prod_{\vec k}e^{-\beta\hbar\omega_{\vec k}\tilde b^\dagger_{\vec k}\tilde b_{\vec k}}\right]\\
=&e^{-\beta E_0}\prod_{\vec k}\sum_{n_{\vec k}}e^{-\beta\hbar\omega_{\vec k}n_{\vec k}}=e^{-\beta E_0}\prod_{\vec k}\frac1{1-e^{-\beta\hbar\omega_{\vec k}}}\\
\end{aligned}$$
自由能
$$F=-k_BT\ln Z=E_0+\sum_{\vec k}k_BT\ln\left(1-e^{-\hbar\omega_{\vec k}/k_BT}\right)$$
内能
$$U=F+TS=F-T\frac{\partial F}{\partial T}=E_0+\sum_{\vec k}\frac{\hbar\omega_{\vec k}}{e^{\hbar\omega_{\vec k}/k_BT}-1}$$
其实这也正是Bose-Einstein分布的内能公式。而偏导是因为$F=F(V,T)$，体积的信息包含在$\vec k$中，正如(11)(16)式
进而定容内能为
$$C_V=\frac{\partial U}{\partial T}=\sum_{\vec k}\left(\frac{\hbar\omega_{\vec k}}{e^{\hbar\omega_{\vec k}/k_BT}-1}\right)^2\frac{e^{\hbar\omega_{\vec k}/k_BT}}{k_BT^2}\tag{17}$$
低温极限根据(16)式可得$\omega_{\vec k}=\rho_s|\vec k|^2$，根据(11)式
$$\sum_{\vec k}=\left(\frac{Na}{2\pi}\right)^3\int_{|\vec k|<2\pi/a}\mathrm{d}^3\vec k$$
因此(17)近似为
$$\begin{aligned}
&C_V=\frac{\partial U}{\partial T}=\sum_{\vec k}\left(\frac{\hbar\omega_{\vec k}}{e^{\hbar\omega_{\vec k^2/k_BT}}-1}\right)^2\frac{e^{\hbar\omega_{\vec k}/k_BT}}{k_BT^2}\\
\approx&\left(\frac{Na}{2\pi}\right)^3\int_0^{\pi/a}4\pi k^2\mathrm{d}k\ \left(\frac{\hbar\rho_s k^2}{e^{\hbar\rho_s k^2/k_BT}-1}\right)^2\frac{e^{\hbar\rho_s k^2/k_BT}}{k_BT^2}\\
=&\left(\frac{Na}{2\pi}\right)^3\int_0^{\sqrt{\frac{\hbar\rho_s\pi} {k_BTa}}}4\pi\left(\frac{k_BT}{\hbar\rho_s}\right)^{3/2} \frac{\sqrt u}2\mathrm{d}u\ \left(\frac{k_BTu}{e^u-1}\right)^2\frac{e^u}{k_BT^2}\\
\approx&\frac{(Na)^3}{4\pi^2}\left(\frac{k_B}{\hbar\rho_s}\right)^{3/2}\int_0^\infty \frac{u^{5/2}e^u}{(e^u-1)^2}\mathrm{d}u\ k_BT^{3/2}
\end{aligned}$$
所以低温下热容和温度$3/2$次方成正比。
