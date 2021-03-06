# Chapter 3. Linear Maps

在这章里，常常用到两个向量空间，一般记为 $V$ 与 $W$，它们都是基于数域 $\mathbb{F}$ 的。

## 3.A. The Vector Space of Linear Maps

### Definition and Examples of Linear Maps

如果函数 $T:V\rightarrow W$ 满足如下性质，我们称其为从 $V$ 到 $W$ 的**线性映射**：

* 加性（additivity）：对所有的 $u,v\in V$，都有 $T(u+v) = T(u) + T(v)$
* 齐性（homogeneity）：对于所有 $\lambda\in\mathbb{F}$ 与 $v\in V$，都有 $T(\lambda v) = \lambda T(v)$

（$T(v)$ 常常简写为 $Tv$）

从 $V$ 到 $W$ 的所有线性映射的集合记为 $\mathcal{L}(V,W)$。

线性映射的一些例子：

* 零函数

  ​	$0v=0$

  ​	左边的 $0$ 是零函数，右边的 $0$ 是加法单位元。

* 恒等

  ​	恒等函数记为 $I$，$I\in\mathcal{L}(V,V)$，定义为：

  ​	$Iv=v$

* 微分

  ​	$D\in\mathcal{L}(\mathcal{P}(\mathbb{R}),\mathcal{P}(\mathbb{R}))$，定义为：

  ​	$Dp=p'$

  ​	根据微分的一些基本运算法则的结论，有：$(f+g)'=f'+g'$ 以及 $(\lambda f)'=\lambda f'$

* 积分

  ​	$T\in\mathcal{L}(\mathcal{P}(\mathbb{R}),\mathbb{R})$，定义为：

  ​	$Tp=\int_0^1p(x)dx$

  ​	同样根据积分的基本运算法则的结论，可知积分函数满足加性与齐性，故而为线性映射。

* 乘以 $x^2$

  ​	$T\in\mathcal{L}(\mathcal{P}(\mathbb{R}),\mathcal{P}(\mathbb{R}))$，定义为：

  ​	$(Tp)(x)=x^2p(x)$，$x\in R$

  ​	思考题：对于任意的乘以 $x^n$，$n$ 为自然数，是否满足线性映射？

* 向后移位

  ​	$T\in\mathcal{L}(\mathbb{R}^{\infin},\mathbb{R}^{\infin})$ 定义为：

  ​	$T(x_1,x_2,x_3,...)=(x_2,x_3,...)$

* 从 $\mathbb{R}^3$ 到 $\mathbb{R}^2$ 的投影

  ​	$T\in\mathcal{L}(\mathbb{R}^3,\mathbb{R}^2)$ 定义为：

  ​	$T(x,y,z) = (2x-y+3z,7x+5y-6z)$

* 从 $\mathbb{F}^n$ 到  $\mathbb{F}^m$

  ​	构造对于每一个 $j=1,...,m$ 与 $k=1,...,n$ 都有的 $A_{j,k}\in \mathbb{F}$ ，定义 $T\in\mathcal{L}(\mathbb{F}^n,\mathbb{F}^m)$ 为：

  ​	$T(x_1,...,x_n)=(A_{1,1}x_1+...+A_{1,n}x_n,...,A_{m,1}x_1+...+A_{m,n}x_n)$。

  ​	实际上对于每一个从 $\mathbb{F}^n$ 到  $\mathbb{F}^m$ 的线性映射都可以表示为这种形式（也就是矩阵乘法的形式）。

 假设 $v_1,...,v_n$ 是 $V$ 的一组基，$w_1,...,w_n\in W$。那么存在唯一的线性映射 $T:V\rightarrow W$ 使得：$Tv_j=w_j$。

证明：

> First we show the existence of the linear map $T$ with the desired property.
>
> Define $T:V\rightarrow W$ by:
>
> $T(c_1v_1+...+c_nv_n)=c_1w_1+...+c_nw_n$ 
>
> As $v_1,.,,,v_n$ is a basis of $V$, each element in $V$ can be uniquely expressed as the linear combination of $v_1,...,v_n$, thus the function $T$ is indeed a function from $V$ to $W$.
>
> For each $j\in\{1,...,n\}$, we make $c_j=1$ and other $c$'s equal to $0$, then we have: $Tv_j=w_j$.
>
> Then we show this function is a linear map.
>
> If $u,v\in V$ with $u=a_1v_1+...+u_nv_n$ and $v=c_1v_1+...+c_nv_n$, then:
>
> $\begin{align}T(u+v)&=T((a_1+c_1)v_1+...+(a_n+c_n)v_n)\\&=(a_1+c_1)w_1+...+(a_n+c_n)v_n\\&=(a_1w_1+...+a_nw_n)+(c_1w_1+...+c_nw_n)\\&=T(a_1v_1+...+a_nv_n)+T(c_1v_1+...+c_nv_n)\\&=T(u)+T(v)\end{align}$
>
> if $\lambda\in\mathbb{F}$, then:
>
> $\begin{align}T(\lambda v)&=T(\lambda a_1v_1+...+\lambda a_nv_n)\\&=\lambda a_1w_1+...+\lambda a_nw_n\\&=\lambda(a_1w_1+...+a_nw_n)\\&=\lambda T(v)\end{align}$
>
> Thus $T$ is a linear map fron $V$ to $W$.
>
> 唯一性的证明暂时看不懂，先留着吧。

### $\mathcal{L}(V,W)$ 上的代数运算

先定义 $\mathcal{L}(V,W)$ 上的加法与数乘：

* $(S+T)(v)=Sv+Tv$
* $(\lambda T)(v)=\lambda(Tv)$

可以证明，经过加法与数乘的函数仍然在 $\mathcal{L}(V,W)$ 上。

证明：

> 

（3.7）定义了加法与数乘之后，$\mathcal{L}(V,W)$ 是一个向量空间。

证明：

> 

如果 $T\in\mathcal{L}(U,V)$ 且 $S\in\mathcal{L}(V,W)$，定义他们的**积** $ST\in\mathcal{L}(U,W)$ 为：

$(ST)(u)=S(Tu)$

$ST$ 其实就是函数复合 $S\circ T$，但是当两个函数都是线性的时候，数学家都喜欢写成 $ST$。╰(*°▽°*)╯

注意条件，只有当 $T$ 的值域等于 $S$ 的定义域时，线性映射的积才成立。（这里提出一个疑问，必须要等于而不能是属于吗？不过如果是属于的话，值域可以扩充到等于，毕竟映射不一定要是满射）

线性映射的积的性质：

* 分配律：$(T_1T_2)T_3=T_1(T_2T_3)$
* 恒等元 ：$TI=IT=T$，两个 $I$ 的定义域（等同于它的值域）不同，按 $T$ 的定义域与值域确定。
* 分配律：$(S_1+S_2)T=S_1T+S_2T$，$S(T_1+T_2)=ST_1+ST_2$，同样是要遵守基本法的。Θ..Θ

证明：

> 

线性映射的乘法不满足交换律，也是显然的。

（3.11）如果 $T$ 是一个从 $V$ 到 $W$ 的线性映射，那么 $T(0)=0$。

证明：

> $T(0)=T(0+0)=T(0)+T(0)$
>
> thus: $T(0)=0$

## 3.B Null Spaces and Ranges

### Null Space and Injectivity

对于 $T\in\mathcal{L}(V,W)$，$T$ 的**零空间**定义为包含所有被 $T$ 映射到 $0$ 的 $V$ 的子集，即：$null\ T=\{v\in V:Tv=0\}$

零空间是子空间。（3.14）

证明：

> As $T$ is a linear map and $T(0) = 0$, we know that $0$ is in $null\ T$.
>
> Suppose $u, v \in null\ T$, $\lambda\in\mathbb{F}$.
>
> $T(u+v) = Tu+Tv=0+0=0$
>
> $T(\lambda u)=\lambda Tu = \lambda 0 = 0$
>
> Thus $null\ T$ is a subspace.

对于函数 $T:V\rightarrow W$，如果 $Tu=Tv$ 意味着 $u=v$，那么称此函数是**单射的**。

 单射的线性映射等价于零空间为 $\{0\}$。（3.16）

证明：

> If linear map $T$ is injective:
>
> ​	Suppose $v\in null\ T$, then we have: $Tv=0=T0$, as $T$ is injective, we have $v=0$.
>
> If for linear map $T\in\mathcal{L}(V,W)$, $null\ T = \{0\}$:
>
> ​	Suppose for $u,v\in V$, $Tu=Tv$, so $Tu-Tv=0$, $T(u-v)=0$.
>
> ​	As $null\ T=\{0\}$, we have $u-v=0$, so $u=v$. Thus we know $T$ is injective.

### Range and Surjectivity

对于从 $V$ 到 $W$ 的函数 $T$，$T$ 的**值域**是 $W$ 的子集，包含所有的 $Tv$ （$v\in V$），即：$range\ T =\{Tv:v\in V\}$。

线性映射的值域是其到达域的子空间。（3.19）

证明：

> $T0=0$, so $0\in W$.
>
> As $T$ is a linear map, and $Tw\in W$ for any $w\in V$, easy to know that $range\ T$ is closed under addition and scalar multiplication.
>
> Thus $range\ T$ is a subspace of $W$.

如果一个函数的值域等于其到达域，那么称该函数为**满射的**。

### Fundamental Theorem of Linear Maps

线性映射基本定理：如果 $V$ 是一个有限维向量空间，$T\in\mathcal{L}(V,W)$，那么 $range\ T$ <u>是有限维的</u>，并且 $dim\ V=dim\ null\ T + dim\ range\ T$。（3.22）

证明：

> 

线性映射基本定理的一系列简单推论：

3.23 高维往低维的线性映射不是单射的。

3.24 低维往高维的线性映射不是满射的。

3.26 当变量多于方程时，齐次线性方程组必有非零解。

3.29 当方程多余变量时，必有一组常数解是的相应的非齐次线性方程组无解。

证明：

> 

## 3.C Matrices

### 用矩阵来表示线性映射

矩阵的定义：一个 $m\times n$ 的矩阵是一个由 $\mathbb{F}$ 中的元素组成的 $m$ 行 $n$ 列的矩形阵列，形如：

$\left(\begin{matrix}A_{1,1}&\cdots&A_{1,n}\\ \vdots & \ddots&\vdots\\ A_{m,1}&\cdots&A_{m,n}\end{matrix}\right)$

线性映射的矩阵的定义：对于 $T\in\mathcal{L}(V,W)$，$v_1,...,v_n$ 是 $V$ 的一组基，$w_1,...,w_m$ 是 $W$ 的一组基，那么该线性映射的矩阵表示记为 $\mathcal{M}(T)$，定义为：$Tv_k=A_{1,k}w_1+...+A_{m,k}w_m$。如果基不是上下文自明的，那么记为 $\mathcal{M}(T,(v_1,...,v_n),(w_1,...,w_m))$。

### 矩阵的加法与数乘

定义略。

对于 $S,T\in\mathcal{L}(V,W)$，有 $\mathcal{M}(S+T)=\mathcal{M}(S)+\mathcal{M}(T)$。（3.36）

证明：

> 

对于 $\lambda\in\mathbb{F}$ 和 $T\in\mathcal{L}(V,W)$，有 $\mathcal{M}(\lambda T)=\lambda\mathcal{M}(T)$。（3.38）

证明：

> 

对于所有的元素来自 $\mathbb{F}$ 的 $m\times n$ 矩阵所构成的集合，记为 $\mathbb{F}^{m,n}$。

（3.40）定理：$dim\ F^{m,n}=mn$

证明：

> 

### 矩阵乘法

定义略。

对于 $T\in\mathcal{L}(U,V)$ 与 $S\in\mathcal{L}(V,W)$，有 $\mathcal{M}(ST) =\mathcal{M}(S)\mathcal{M}(S)$。（3.43）

证明：

> 

记号：

* $A_{j,\cdot}$ 表示矩阵 $A$ 的第 $j$ 行组成的矩阵
* $A_{\cdot,k}$ 表示矩阵 $A$ 的第 $k$ 列组成的矩阵

（3.47）矩阵积的元素等于列乘行：$(AC)_{j,k}=A_{j,\cdot}C_{\cdot,k}$

（3.49）矩阵积的列等于矩阵乘列：$(AC)_{\cdot,k}=AC_{\cdot,k}$

（3.52）$Ac$ 是矩阵 $A$ 的列的线性组合。

## 3.D Invertibility and Isomorphic Vector Spaces

### 可逆线性映射

定义：

* 对于 $T\in \mathcal{L}(V,W)$，如果存在 $S\in \mathcal{L}(W,V)$ 使得 $ST$ 与 $TS$ 为恒等映射（在不同的域上），那么称 $T$ **可逆**。
* 如果 $S\in \mathcal{L}(W,V)$ 满足 $ST=I$ 以及 $TS=I$，那么称 $S$ 是 $T$ 的**逆**，记作 $S=T^{-1}$。

（3.54）线性映射的逆是唯一的。

证明：

> For invertible T , suppose exist two inverse $S_1$ and $S_2$, we have:
>
> $S_1=S_1I=S_1(TS_2)=(S_1T)S_2=IS_2=S_2$

（3.56）线性映射可逆等价于单射与满射。

证明：

> 

### 同构的向量空间

定义：

* **同构**就是可逆的线性映射。
* 如果两个向量空间存在一个同构，那么称这两个向量空间是**同构的**。

（3.59）两个向量空间是同构的当且仅当他们有相同的维数。

证明：

> 

（3.60）当 $dim V = m$，$dim W = n$ 时，$\mathcal{L}(V,W)$ 与 $\mathbb{F}^{m,n}$ 同构。

证明：

> 

（3.61）$dim\ \mathcal{L}(V,W)=(dim\ V)(dim\ W)$

证明：

> This follows from 3.60, 3.59 and 3.40.

### 看作矩阵乘法的线性映射

定义：给定向量空间的一组基 $v_1,...,v_n$ 与该空间中的一个向量 $v$， 该向量的矩阵表示为：$\mathcal{M}(v)=\left(\begin{matrix}c_1\\\vdots\\c_n\end{matrix}\right)$，满足条件 $v=c_1v_1+...+c_nv_n$。

（3.64）$\mathcal{M}(T)_{\cdot,k}=\mathcal{M}(v_k)_{\cdot}$

证明：

> 

（3.65）线性映射就像矩阵乘法：$\mathcal{M}(Tv)=\mathcal{M}(T)\mathcal{M}(v)$

证明：

> 

### 算子

**算子**定义为定义域和到达域相同的线性映射，另外记 $\mathcal{L}(V,V)=\mathcal{L}(V)$。

（3.69）对于在有限维空间内的算子，以下三条性质等价：

* 可逆
* 单射
* 满射

证明：

> 

