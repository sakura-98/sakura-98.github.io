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
### 对角化
### 热容