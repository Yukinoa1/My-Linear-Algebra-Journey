这个分支有关于自己常犯的一些错误，用于避免自己陷入惯性思维.

# 易犯错误1：直接从向量空间中取出子空间的基.
简介：本质上是忽视了“向量空间的基必须在向量空间中”这一事实,只关注了线性无关性和线性张成性.这个错误多次出现，已经成为惯性思维，需要进行改正.
最简单的例子，取二维空间的基向量 $[1,0]^T , [0,1]^T$ .直线 $y=x$ 是一个子空间，但显然这两个基向量都不在其中.

## 错例1（2026.3.30）
设 $\sigma$ 是复数域 ℂ 上 $n$ 维向量空间 $V$ 的一个线性变换，在基 $\alpha_1 , \alpha_2 , \cdots , \alpha_n$ 下的矩阵是

$$
\begin{bmatrix}
0 & & & & \\
1 & 0 & & & \\
 & 1 & 0 & & \\
 & & \ddots & \ddots & \\
 & & & 1 & 0\\
\end{bmatrix}.
$$

证明

&nbsp; (i)包含 $\alpha_1$ 的 $\sigma$ 不变子空间只有 $V$ 本身；

&nbsp; (ii) $\sigma$ 的每一非零的不变子空间都包含 $\alpha_n$ .

### 错误证明
(i)假设包含 $\alpha_i$ 的 $\sigma$ 不变子空间维数小于 $n$ .设该子空间为 $W$ ，不妨设 $dimW = n-1$ .

取 $W$ 的基为 $\alpha_1 , \alpha_2 , \cdots , \alpha_{i-1} , \alpha_{i+1} , \cdots , \alpha_n . i \in \mathbb{N}_{+} ， 2 \leq i \leq n$ .

这就是错误所在.后续的步骤大概就是取出 $W$ 中的一个向量并用这组基表示它，然后左右同时作用 $\sigma$ ，得到 $\sigma(\xi) \notin W$ ，进而通过 $W$ 的不变性得出矛盾.

但问题出现在很早的地方，一组向量是 $W$ 的基，不仅要求线性无关性和线性张成性，还要求这组向量属于 $W$ .此处无法确定 $\alpha_1 , \alpha_2 , \cdots , \alpha_{i-1} , \alpha_{i+1} , \cdots , \alpha_n$ 都在 $W$ 里，也就是说我们无法确保在 $V$ 的一组基中选取到 $W$ 的一组基.

(ii)记 $\sigma$ 的不变子空间为 $W$ .若 $W=V$ ，显然 $\alpha_n \in V = W$ .

若 $W \neq V$ ，假设 $\alpha_n \notin W$ .至少有某一 $\alpha_k \in W$ .则

$$\sigma(\alpha_k) = \alpha_{k+1} \in W , \sigma(\alpha_{k+1}) = \alpha_{k+2} \in W , \cdots , \sigma(\alpha_{n-1}) = \alpha_{n} \in W.$$

这与 $\alpha_n \notin W$ 矛盾.故 $\alpha_n \in W$ .即 $W$ 必包含 $\alpha_n$ .

事实上，这个证明过程在第二行就出现了问题，与第一问一样，想当然地认为一定能从 $V$ 的一组特定的基中选出 $W$ 的一组基.其实， $V$ 的这组基中的任一向量可能都不属于 $W$ .

正确的想法也并不复杂，这是一个平凡的简单题目，只要矫正了错误想法、多从内部出发而不是从外向内收缩，就容易证得命题.下面给出正确证明.

### 正确证明
(i)根据矩阵，容易看出

$$\sigma(\alpha_1) = \alpha_2 , \sigma(\alpha_2) = \alpha_3 , \cdots , \sigma(\alpha_{n-1}) = \alpha_n , \sigma(\alpha_n) = 0 . $$

任取一 $\sigma$ 不变子空间 $W$ 满足 $\alpha_1 \in W$ .则

$$\alpha_2 = \sigma(\alpha_1) \in W , \alpha_3 = \sigma(\alpha_2) \in W, \cdots , \alpha_n = \sigma(\alpha_{n-1}) \in W . $$

而 $V = \langle \alpha_1 , \alpha_2 , \cdots , \alpha_n \rangle \subseteq W$ 且 $W \subseteq V$ .则 $W=V$ .

故包含 $\alpha_1$ 的 $\sigma$ 不变子空间只有 $V$ 本身. $\square$

(ii)任取一 $\sigma$ 不变子空间 $W$ .若 $W=V$ ，则显然 $W$ 包含 $\alpha_n$ .

若 $W \neq V$ ， 取非零向量 $\beta \in W \subseteq V$ ，记

$$\beta = \sum_{i=1}^{n} k_i \alpha_i , 其中k_i不全为0 . $$

取最小的 $k_j \neq 0$ ，则 $\sigma^{(n-j-1)}(\beta) = k_j \alpha_n \in W$ . 于是 $\alpha_n \in W$ .

即 $\sigma$ 的每一非零的不变子空间都包含 $\alpha_n$ . $\square$

## 错例2（2026.04.09）
设 $V$ 是复数域 ℂ 上一个 $n$ 维向量空间， $\sigma$ 是 $V$ 的一个线性变换， $V$ 关于 $\sigma$ 的准素分解为 $V = V_1 \oplus V_2 \oplus \cdots \oplus V_k$. 令 $W$ 是 $V$ 的一个 $\sigma$ 不变子空间，证明

$$W = (W \cap V_1) \oplus (W \cap V_2) \oplus \cdots \oplus (W \cap V_k).$$

### 错误证明
取 $V_1$ 的基 { $\alpha_{11}, \ldots, \alpha_{1r_1}$ }，取 $V_2$ 的基 { $\alpha_{21}, \ldots, \alpha_{2r_2}$ }， $\ldots$ ，取 $V_k$ 的基 { $\alpha_{k1}, \ldots, \alpha_{kr_k}$ } .

由于 $W \subseteq V$ ，取 $W$ 的基 $\beta_1, \beta_2, \ldots, \beta_t$ . ***显然***{ $\beta_1, \ldots, \beta_t$ } $\subset$ { $\alpha_{11}, \ldots, \alpha_{1r_1}, \ldots, \alpha_{k1}, \ldots, \alpha_{kr_k}$ }.

值得注意，

$$由于 W \subseteq V ，取 W 的基 \beta_1, \beta_2, \ldots, \beta_t . **显然**{ \beta_1, \ldots, \beta_t } \subset { \alpha_{11}, \ldots, \alpha_{1r_1}, \ldots, \alpha_{k1}, \ldots, \alpha_{kr_k} }$$

当中，后半句明显是错误的命题，因为一组向量是 $V$ 的基，不仅要求线性无关性和线性张成性，还要求这组向量属于 $V$ . 

因此，虽然 $\alpha_{11}, \ldots, \alpha_{1r_1}, \ldots, \alpha_{k1}, \ldots, \alpha_{kr_k}$ 中的每t个向量都线性无关，且存在t个向量张成 $W$ ，但这t个向量可能不属于 $W$ . 也就是说，我们无法确保在 $V$ 的一组基中取到 $W$ 的一组基. 

### 注
正确证明见**main分支**中的文件**README.md**.
