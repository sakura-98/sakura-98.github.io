---
title: Ising
tags: physics
categories: QSP
mathjax: true
date: 2021-01-27
---

Ising模型是最简单的磁性结构模型，哈密顿量为
$$
H=-\mu B\sum_i S_i+J\sum_{\langle i,j\rangle}S_iS_j
$$
其中$S_i=\pm1$，进而配分函数为
$$
Z=\sum_{\{S_i\}}e^{-\beta H(S_1,\cdots,S_N)}
$$
<!--more-->

### 一维精确解

配分函数可以写为
$$
Z=\sum_{\{S_i\}}\prod_{i=1}^Ne^{\beta(\mu BS_i-JS_iS_{i+1})}
$$
其中$S_{N+1}=S_1$，即周期性边界条件。定义一个矩阵$T$使得（相当于给出所有矩阵元）
$$
\langle S|T|S'\rangle=e^{\beta(\mu BS-JSS')}
$$
则配分函数实际为
$$
Z=\sum_{\{S_i\}}\langle S_1|T|S_2\rangle\langle S_2|T|S_3\rangle\cdots\langle S_{N-1}|T|S_N\rangle\langle S_N|T|S_1\rangle=\sum_{S_1}\langle S_1|T^N|S_1\rangle=tr\left[T^N\right]
$$
事实上利用$T$的矩阵形式可以得到
$$
Z=\lambda_+^N+\lambda_-^N
$$
其中$\lambda_\pm$为以下一元二次方程的解
$$
(\lambda-e^{\beta(\mu B-J)})(\lambda-e^{\beta(-\mu B-J)})=e^{2\beta J}\Leftrightarrow\lambda^2-2\lambda e^{-\beta J}\cosh\beta\mu B-2\sinh2\beta J=0
$$

解得
$$
\lambda_\pm=e^{-\beta J}\cosh\beta\mu B\pm\sqrt{e^{-2\beta J}\cosh^2\beta\mu B+2\sinh2\beta J}
$$
**无磁场或弱磁场下**
$$
\lambda_\pm\approx (e^{-\beta J}\pm e^{\beta J})+\frac12e^{-2\beta J}(e^{\beta J}\pm e^{-\beta J})(\beta\mu B)^2+\mathcal O(B^4)
$$
所以
$$
Z=\lambda_+^N+\lambda_-^N\approx (2\cosh\beta J)^N+(-2\sinh\beta J)^N
$$
低温极限和高温极限下
$$
Z=\left\{\begin{array}{ll}
2e^{NJ/k_BT}&,N\ is\ even\\
2Ne^{(N-2)J/k_BT}&,N\ is\ odd
\end{array}\right.,\quad Z=1+\frac{NJ^2}{2k_B^2T^2}
$$

#### 热容

低温：
$$
F=-k_BT\ln Z=-k_BT\ln 2-NJ,\quad F=-k_BT\ln(2N)-(N-2)J
$$
当$N$是偶数时（奇数也类似）
$$
S=-\frac{\partial F}{\partial T}=k_B\ln 2\Rightarrow U=F+TS=-NJ\Rightarrow C_V=0
$$
高温：
$$
F=-k_BT\ln\left(1+\frac{NJ^2}{2k_B^2T^2}\right)\Rightarrow S=-\frac FT-\frac{k_BT}{1+\frac{NJ^2}{2k_B^2T^2}}\frac{NJ^2}{k_B^2T^3}=-\frac FT-\frac{Nk_BJ^2}{k_B^2T^2+\frac12 NJ^2}
$$
所以热容为
$$
C_V=\frac{2NJ^2}{k_BT^3}
$$

#### 平均磁矩

$$
\langle\sigma_1\rangle=\frac1Z\sum_{\{S_i\}}S_1\langle S_1|T|S_2\rangle\cdots=\frac1Z\sum_{\{S_i\}}\langle S_1|\sigma_zT|S_2\rangle\langle S_2|T|S_3\rangle\cdots=\frac1Ztr(\sigma_zT^N)
$$

在弱磁场下“可以”算得
$$
\langle\sigma_1\rangle=\frac1Ze^{-2\beta J}\left[(2\cosh\beta J)^N-(-2\sinh\beta J)^N\right]\beta\mu B+\mathcal O(B^3)
$$
因此磁化率
$$
\chi=\mu\beta e^{-2\beta J}\frac{(2\cosh\beta J)^N-(-2\sinh\beta J)^N}{(2\cosh\beta J)^N+(-2\sinh\beta J)^N}
$$

高温下
$$
\chi\approx\frac{\mu}{k_BT}e^{-2J/k_BT}
$$
低温下
$$
\chi\approx\left\{\begin{array}{cc}
&N\ is\ even\\
&N\ is\ odd
\end{array}\right.
$$

