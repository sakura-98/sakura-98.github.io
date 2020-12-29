---
title: QED单圈重整化
tags: physics
categories: QFT
mathjax: true
date: 2020-11-14
---

这篇将会写比较长时间吧。一来因为计算量确实不小，二来……算了，也不要二来了。

高维球的体积和表面积公式直接给出吧。

| $d$   |0| 1    | 2    | 3    | 4    |$\cdots$|$d$|
| :-: | :-:|:-: | :-: | :-: | :-: |:-:|:-:|
| $V^d$ |   $1$|$2$   | $\pi$ | $\frac{4\pi}3$ | $\frac{\pi^2}4$ ||$\pi^{d/2}/\Gamma\left(\frac d2+1\right)$|
| $S^d$ | $0$ | $2$ | $2\pi$ | $4\pi$ |$2\pi^2$||$2\pi^{d/2}/\Gamma\left(\frac d2\right)$|

以及所谓的”积木“
$$
S(k)=\frac{m-ip\!\!\!\backslash}{p^2+m^2-i\epsilon},\Delta^{\mu\nu}(k)=\frac1{k^2-i\epsilon}\left[g^{\mu\nu}-(1-\xi)\frac{k^\mu k^\nu}{k^2}\right]
$$


<!--more-->

### 光子自能项

光子自能图为
$$
\Pi^{\mu\nu}(k)=(-1)\int\frac{-i\mathrm d^4l}{(2\pi)^4}\ \mathrm{Tr}\left[S(l+k)ieC^\mu S(l)ieC^\nu\right]=e^2\int\frac{\mathrm d^4l}{(2\pi)^4}\mathrm{Tr}\left[\frac{m-i(l\!\!\backslash+k\!\!\!\backslash)}{(l+k)^2+m^2}C^\mu\frac{m-il\!\!\backslash}{l^2+m^2}C^\nu\right]
$$
求迹这种东西嘛，主要就是用$\{C^\mu,C^\nu\}=2g^{\mu\nu}\Rightarrow\mathrm{Tr}[C^\mu C^\nu]=4g^{\mu\nu}$
$$
\begin{aligned}
&\mathrm{Tr}[C^\rho C^\mu C^\sigma C^\nu]
=\mathrm{Tr}[C^\rho C^\mu(2g^{\sigma\nu}-C^\nu C^\sigma)]\\
=&8g^{\rho\mu}g^{\sigma\nu}-\mathrm{Tr}[C^\rho C^\mu C^\nu C^\sigma]=8g^{\rho\mu}g^{\sigma\nu}-\mathrm{Tr}[C^\rho(2g^{\mu\nu}-C^\nu C^\mu)C^\sigma]\\
=&8g^{\rho\mu}g^{\sigma\nu}-8g^{\mu\nu}g^{\rho\sigma}+\mathrm{Tr}[C^\rho C^\nu C^\mu C^\sigma]\\
=&8(g^{\rho\mu}g^{\sigma\nu}-g^{\mu\nu}g^{\rho\sigma}+g^{\nu\rho}g^{\mu\sigma})-\mathrm{Tr}[C^\nu C^\rho C^\mu C^\sigma]
\end{aligned}
$$
所以$\mathrm{Tr}[C^\rho C^\mu C^\sigma C^\nu]=4(g^{\rho\mu}g^{\sigma\nu}-g^{\mu\nu}g^{\rho\sigma}+g^{\nu\rho}g^{\mu\sigma})$，因此
$$
\Pi^{\mu\nu}(k)=4e^2\int\frac{-i\mathrm d^4l}{(2\pi)^4}\frac{[m^2+(l+k)_\rho l_\sigma g^{\rho\sigma}]g^{\mu\nu}-[(l+k)^\mu l^\nu+(l+k)^\nu l^\mu]g^{\mu\mu}g^{\nu\nu}}{[(l+k)^2+m^2][l^2+m^2]}
$$


做完Wick转动$l^4=il^0,k^4=ik^0$
$$
\Pi^{ij}(k_E)=4e^2\int\frac{\mathrm d^4l_E}{(2\pi)^4}\frac{[m^2+(l+k)\cdot l]\delta^{ij}-[(l+k)^\mu l^\nu+(l+k)^j l^i]}{[(l+k)^2+m^2][l^2+m^2]}
$$
做Feynman参数化
$$
\Pi^{ij}(k_E)=4e^2\int_0^1\mathrm dx\int\frac{\mathrm d^4l_E}{(2\pi)^4}\frac{[m^2+(l+k)\cdot l]\delta^{ij}-[(l+k)^il^j+(l+k)^jl^i]}{[(l+xk)^2+x(1-x)k^2+m^2]^2}
$$
设$q=l+xk,D=x(1-x)k^2+m^2$。略去一次项
$$
\Pi^{ij}(k_E)=4e^2\int_0^1\mathrm dx\int\frac{\mathrm d^4q}{(2\pi)^4}\frac{[m^2+q^2-x(1-x)k^2]\delta^{ij}-2q^iq^j+2x(1-x)k^ik^j}{[q^2+x(1-x)k^2+m^2]^2}
$$
利用$\int\mathrm d^4q\ q^iq^jf(q^2)=\frac14\delta^{ij}\int\mathrm d^4q\ q^2f(q^2)$得
$$
\begin{aligned}
\Pi^{ij}(k_E)
=&4e^2\int_0^1\mathrm dx\int_0^\infty\frac{2\pi^2 q^3\mathrm dq}{(2\pi)^4}\frac{[m^2+q^2-x(1-x)k^2]\delta^{ij}-\frac12\delta^{ij}q^2+2x(1-x)k^ik^j}{[q^2+D]^2}\\
=&\frac{e^2}{4\pi^2}\int_0^1\mathrm dx\int_0^\infty q^2\mathrm dq^2\ \frac{[m^2+q^2-x(1-x)k^2]\delta^{ij}-\frac12\delta^{ij}q^2+2x(1-x)k^ik^j}{[q^2+D]^2}\\
=&\frac{e^2}{4\pi^2}\int_0^1\mathrm dx\int_0^\infty \mathrm dt\ \frac{[m^2\delta^{ij}-x(1-x)(k^2\delta^{ij}-2k^ik^j)]t+\frac12\delta^{ij}t^2}{[t+D]^2}\\
\end{aligned}
$$
分别计算两项
$$
\int_0^\infty\mathrm dt\frac t{(t+D)^2}=\int_0^Q\frac{t}{(t+D)^2}\mathrm dt+\int_Q^\infty\frac{\mathrm dt}t=-\frac{Q}{D+Q}+\ln\frac{D+Q}D-\ln\frac{\infty}{Q}=-\ln D+c_1
$$

$$
\int_0^\infty\frac{t^2\mathrm dt}{(t+D)^2}=\left[\frac{Q(2D+Q)}{D+Q}+2D\ln\frac{D}{D+Q}\right]+\infty-Q-2D\ln\frac{\infty}{Q}=2D\ln D+c_2+c_3D
$$

所以
$$
\Pi^{ij}(k_E)=\frac{e^2}{4\pi^2}\int_0^1\mathrm dx\ \left\{[m^2\delta^{ij}-x(1-x)(k^2\delta^{ij}-2k^ik^j)](-\ln D+c_1)+\delta^{ij}(D\ln D+\frac12c_2+\frac12c_3D)\right\}
$$
整理得
$$
\Pi^{ij}(k_E)=\frac{e^2}{4\pi^2}\int_0^1\mathrm dx\ \left\{2x(1-x)\ln D[k^2\delta^{ij}-k^ik^j]+2b_1k^ik^j+2(b_2+b_3k^2)\delta^{ij}\right\}
$$
上式用到了$D=x(1-x)k^2+m^2$。变换回闵氏空间
$$
\Pi^{\mu\nu}(k)=\frac{e^2}{2\pi^2}\int_0^1\mathrm dx[x(1-x)\ln D (k^2g^{\mu\nu}-k^\mu k^\nu)+b_1k^\mu k^\nu+(b_2+b_3k^2)g^{\mu\nu}]
$$
On-shell 条件要求
$$
\left.\frac{\Pi^{ij}(k)}{k^2\delta^{ij}-k^ik^j}\right|_{k^2=0}=0\Rightarrow\Pi^{\mu\nu}(k)=\frac{e^2}{2\pi^2}(k^2g^{\mu\nu}-k^\mu k^\nu)\int_0^1x(1-x)\ln \frac{x(1-x)k^2+m^2}{m^2}\mathrm dx
$$
