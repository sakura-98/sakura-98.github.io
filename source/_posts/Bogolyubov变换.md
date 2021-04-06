---
title: Bogolyubov变换
tags: physics
categories: SST
mathjax: true
date: 2021-04-05
---

这只是一个小技巧啦，用于将 $\hat a^\dagger\hat b^\dagger,\hat a\hat b$ 形式对角化

<!--more-->

### 单态情形

简单起见先计算单态情况，根据哈密顿量厄米性和$[\hat a,\hat a^\dagger]=1$假设
$$
H=p\hat a^\dagger\hat a+q\left(\hat a^\dagger\hat a^\dagger+\hat a\hat a\right)\tag{1.1}
$$
1写为矩阵形式
$$
H=\left(\hat a,\hat a^\dagger\right)\left(\begin{array}{cc}0&q\\q&p\end{array}\right)\left(\begin{array}{c}\hat a^\dagger\\\hat a\end{array}\right)\equiv a^\dagger ha\tag{1.2}
$$
我们希望引入变换$U$使得$H=a^\dagger U^\dagger [(U^\dagger)^{-1}hU^{-1}]Ua$括号内为对角，并且$b=Ua$满足
$$
[\hat b,\hat b^\dagger]=[u_{21}\hat a^\dagger+u_{22}\hat a,u_{11}\hat a^\dagger+u_{12}\hat a]=u_{11}u_{22}-u_{21}u_{22}=1\tag{1.3}
$$
根据$\hat b,\hat b^\dagger$厄米共轭可知$u_{21}^*=u_{12},u_{22}^*=u_{11}$。所以可设
$$
U=\left(\begin{array}{cc}
e^{i\alpha}\cosh\theta & e^{i\beta}\sinh\theta\\
e^{-i\beta}\sinh\theta & e^{-i\alpha}\cosh\theta
\end{array}\right)\Rightarrow U^{-1}=\left(\begin{array}{cc}
e^{-i\alpha}\cosh\theta & -e^{i\beta}\sinh\theta \\
-e^{-i\beta}\sinh\theta & e^{i\alpha}\cosh\theta
\end{array}\right)\tag{1.4}
$$
所以代入(1.2)得$\alpha=\beta=0$时
$$
H=\frac12b^\dagger\left(\begin{array}{cc}
p\cosh2\theta-2q\sinh2\theta-p & 
2q\cosh2\theta-p\sinh2\theta \\
2q\cosh2\theta-p\sinh2\theta &
p\cosh2\theta-2q\sinh2\theta+p
\end{array}\right)b
$$
可选取$\tanh2\theta=\frac{2q}{p}$使得对角，并有
$$
\sinh2\theta=\frac{2q}{\sqrt{p^2-4q^2}},\cosh2\theta=\frac{p}{\sqrt{p^2-4q^2}}
$$
所以
$$
H=\frac12\hat b\left(\sqrt{p^2-4q^2}-p\right)\hat b^\dagger
+\frac12\hat b^\dagger\left(\sqrt{p^2-4q^2}+p\right)\hat b\tag{1.5}
$$
或者写为
$$
H=\sqrt{p^2-4q^2}\hat b^\dagger\hat b+E_0\tag{1.6}
$$
需要注意一个问题，$\tanh2\theta\in(-1,1)$，要求$|2q|\le|p|$，其物理意义尚不明确

### 双态情形

其实往往见到的是两套产生-湮灭，记为$\hat a,\hat b$。由厄米性可知，哈密顿量可写为
$$
H=p_1\hat a^\dagger\hat a+p_2\hat b^\dagger\hat b+q(\hat a^\dagger\hat b^\dagger+\hat a\hat b)+s(\hat a^\dagger\hat b+\hat a\hat b^\dagger)
\tag{2.1}
$$
$\hat a^\dagger\hat a^\dagger+\hat a\hat a,\hat b^\dagger\hat b^\dagger+\hat b\hat b$项可在单态情形中消去，因此不写出。$\hat a^\dagger\hat b+\hat a\hat b^\dagger$项可通过重新定义$a,b$消去，即
$$
\left(\hat a^\dagger,\hat b^\dagger\right)\left(\begin{array}{cc}p_1 & s\\s&p_2\end{array}\right)\left(\begin{array}{c}\hat a\\\hat b\end{array}\right)=\lambda_1\hat{\tilde a}^\dagger\hat{\tilde a}+\lambda_2\hat{\tilde b}^\dagger\hat{\tilde b}
$$
实对称矩阵可以通过正交矩阵对角化，所以变换后的$a,b$仍然满足标准的对易关系。因此(2.1)可设$s=0$
$$
H=\left(\hat a^\dagger,\hat b\right)\left(\begin{array}{cc}p_1 & q\\q&p_2\end{array}\right)\left(\begin{array}{c}\hat a\\\hat b^\dagger\end{array}\right)-p_2\tag{2.2}
$$
假设变换关系为
$$
\left(\begin{array}c\hat\alpha\\\hat \beta^\dagger\end{array}\right)=\left(\begin{array}{cc}u_{11} & u_{12}\\u_{21}&u_{22}\end{array}\right)\left(\begin{array}{c}\hat a\\\hat b^\dagger\end{array}\right)\tag{2.3}
$$
则显式得写出来
$$
\left\{\begin{aligned}
&\hat\alpha=u_{11}\hat a+u_{12}\hat b^\dagger\\
&\hat\beta^\dagger=u_{21}\hat a+u_{22}\hat b^\dagger\\
&\hat\alpha^\dagger=u_{11}^*\hat a^\dagger+u_{12}^*\hat b\\
&\hat\beta=u_{21}^*\hat a^\dagger+u_{22}^*\hat b\\
\end{aligned}\right.\Rightarrow
\left\{\begin{aligned}
&\left[\hat\alpha,\hat\alpha^\dagger\right]=|u_{11}|^2-|u_{12}|^2=1\\
&\left[\hat\beta,\hat\beta^\dagger\right]=|u_{22}|^2-|u_{21}|^2=1\\
&\left[\hat\alpha,\hat\beta\right]=u_{11}u_{21}^*-u_{12}u_{22}^*=0
\end{aligned}\right.\tag{2.4}
$$
当然还有其他对易关系，但是要么是显然的，要么包括在以上三个限制条件中了。

不妨设
$$
\left(\begin{array}c\hat\alpha\\\hat \beta^\dagger\end{array}\right)=\left(\begin{array}{cc}\cosh\theta & \sinh\theta\\\sinh\theta&\cosh\theta\end{array}\right)\left(\begin{array}{c}\hat a\\\hat b^\dagger\end{array}\right)
$$
回代(2.2)，和单态结果几乎完全一样嘛，得到
$$
\begin{aligned}
H&=\frac12\hat\alpha^\dagger\left(\sqrt{(p_1+p_2)^2-(q_1+q_2)^2}+(p_1-p_2)\right)\hat\alpha\\
&+\frac12\hat\beta\left(\sqrt{(p_1+p_2)^2-(q_1+q_2)^2}-(p_1-p_2)\right)\hat\beta^\dagger\\
&-p_2\\
&=\frac12\left(\sqrt{(p_1+p_2)^2-(q_1+q_2)^2}+(p_1-p_2)\right)\hat\alpha^\dagger\hat\alpha\\
&+\frac12\left(\sqrt{(p_1+p_2)^2-(q_1+q_2)^2}-(p_1-p_2)\right)\hat\beta^\dagger\hat\beta\\
&+\left(\sqrt{(p_1+p_2)^2-(q_1+q_2)^2}-p_1\right)
\end{aligned}
$$
