# My-Linear-Algebra-Journey
大一学生，线性代数新手，在此过程中记录个人的一些心得.  



# 2026.04.08
今日闲来无事挑战了一道线性代数题目，它有关于老师上午刚讲的向量空间的准素分解.题干如下：

设 $V$ 是复数域 ℂ 上一个 $n$ 维向量空间， $\sigma$ 是 $V$ 的一个线性变换， $V$ 关于 $\sigma$ 的准素分解为 $V = V_1 \oplus V_2 \oplus \cdots \oplus V_k$. 令 $W$ 是 $V$ 的一个 $\sigma$ 不变子空间，证明

$$W = (W \cap V_1) \oplus (W \cap V_2) \oplus \cdots \oplus (W \cap V_k).$$

由于对知识不够熟悉，我并没有很快地找到思路. 我反而回想起了上学期期末的一道题目：  

## 问题1

$n$ 维向量空间 $V$ 有两个 $r$ 维子空间 $U_1$ 和 $U_2$，证明存在一个子空间 $W$，使得 $V$ = $U_1 \oplus W$ = $U_2 \oplus W$ . 

### 证明

$U_1 \cap U_2$ = {0} 时， $U_1$ 基： $\alpha_1 , \alpha_2 , \ldots , \alpha_r$ , $U_2$ 基： $\beta_1 , \beta_2 , \ldots , \beta_r$ . 

显然 $\alpha_1 , \ldots , \alpha_r , \beta_1 , \ldots , \beta_r$ 线性无关, 否则 $U_1 \cap U_2 \neq \{0\}$ .则 

$$\alpha_1 , \ldots , \alpha_r , \beta_1 , \ldots , \beta_r$$

可作为 $V$ 的一组基的一部分.扩充至 

$$\alpha_1 , \ldots , \alpha_r , \beta_1 , \ldots , \beta_r , \gamma_1 , \ldots , \gamma_{n-2r} . $$

取向量组 

$$\alpha_1 - \beta_1 , \alpha_2 - \beta_2 , \ldots , \alpha_r - \beta_r , \gamma_1 , \ldots, \gamma_{n-2r}$$ 

为 $W$ 的一组基。

任一向量都不属于 $U_1$ 且不属于 $U_2$ ，即 $U_1 \cap W = U_2 \cap W = {0} 且 V = U_1 + W = U_2 + W$ .

即存在子空间 $W$ ，使得 

$$V = U_1 \oplus W = U_2 \oplus W . $$

当 $U_1 \cap U_2 \neq${0} 时， $U_1$ 基： $\theta_1, \ldots, \theta_t, \alpha_1, \ldots, \alpha_{r-t}$ , $U_2$ 基： $\theta_1, \ldots, \theta_t, \beta_1, \ldots, \beta_{r-t}$ .

同样地， 

$$\theta_1, \ldots, \theta_t, \alpha_1, \ldots, \alpha_{r-t}, \beta_1, \ldots, \beta_{r-t}$$ 

线性无关.

扩充至

$$\theta_1, \ldots, \theta_t, \alpha_1, \ldots, \alpha_{r-t}, \beta_1, \ldots, \beta_{r-t}, \gamma_1, \ldots, \gamma_{n+t-2r} . $$

取向量组 

$$\alpha_1 - \beta_1, \alpha_2 - \beta_2, \ldots, \alpha_{r-t} - \beta_{r-t}, \gamma_1, \ldots, \gamma_{n+t-2r}$$

为 $W$ 的一组基.

显然 $U_1 \cap W = U_2 \cap W = {0} ， V = U_1 + W ， V = U_2 + W$ .

即存在子空间 $W$ ，使得 

$$V = U_1 \oplus W = U_2 \oplus W .      \square $$

### 反思

这道题考试时没做出来，因而印象深刻. 自那以后，我每次看到很多子空间直和起来的题目，都会不由自主地想到设基的方法. 但面对今天的题目时，却犯了想当然的错误，而且这个荒谬的错误从以前就犯过不止一次. 重新回顾一下今天的题干：

## 问题2

设 $V$ 是复数域 $\mathbb{C}$ 上一个 $n$ 维向量空间， $\sigma$ 是 $V$ 的一个线性变换， $V$ 关于 $\sigma$ 的准素分解为 $V = V_1 \oplus V_2 \oplus \cdots \oplus V_k$. 令 $W$ 是 $V$ 的一个 $\sigma$ 不变子空间，证明

$$W = (W \cap V_1) \oplus (W \cap V_2) \oplus \cdots \oplus (W \cap V_k).$$

### 错误证明

取 $V_1$ 的基 { $\alpha_{11}, \ldots, \alpha_{1r_1}$ }，取 $V_2$ 的基 { $\alpha_{21}, \ldots, \alpha_{2r_2}$ }， $\ldots$ ，取 $V_k$ 的基 { $\alpha_{k1}, \ldots, \alpha_{kr_k}$ } .

由于 $W \subseteq V$ ，取 $W$ 的基 $\beta_1, \beta_2, \ldots, \beta_t$ . ***显然***{ $\beta_1, \ldots, \beta_t$ } $\subset$ { $\alpha_{11}, \ldots, \alpha_{1r_1}, \ldots, \alpha_{k1}, \ldots, \alpha_{kr_k}$ }. 

### 注

这里并没有完整呈现我的错误证法，其实写到这里就不必往下写了. 我后面还设了那几个交集的基，进行了一系列奇怪的操作，完成了伪证. 值得注意，

$$由于 W \subseteq V ，取 W 的基 \beta_1, \beta_2, \ldots, \beta_t . **显然**{ \beta_1, \ldots, \beta_t } \subset { \alpha_{11}, \ldots, \alpha_{1r_1}, \ldots, \alpha_{k1}, \ldots, \alpha_{kr_k} }$$

当中，后半句明显是错误的命题，因为一组向量是 $V$ 的基，不仅要求线性无关性和线性张成性，还要求这组向量属于于 $V$ . 

因此，虽然 $\alpha_{11}, \ldots, \alpha_{1r_1}, \ldots, \alpha_{k1}, \ldots, \alpha_{kr_k}$ 中的每t个向量都线性无关，且存在t个向量张成 $W$ ，但这t个向量可能不属于 $W$ . 也就是说，我们无法确保在 $V$ 的一组基中取到 $W$ 的一组基. 

这事实上是一个非常明显的错误，但我已经**三次**犯了相同的错误了，每次都意识不到. 

这启示我在遇到相似类型的题目时，要多考虑 ***基的扩充*** ，也就是在一组更小的基的基础上扩充成一组更大的基，而不是从一组更大的基中选取一部分作为子空间的基. 

另外，这是一个线性变换的题目，本质是一个映射. 基与坐标是静态的，而线性变换是动态的，很难通过简单的基和坐标去刻画线性变换的过程. 

我甚至在证明中完全没有用到*准素分解*和*不变子空间*的条件，这意味着我的前提是残缺的，命题必然不充分. 

因此，证明命题时，更需注重***对本质的理解***以及***对结构的把控***，从直观理解入手. 如果从一开始就拼凑技巧、玩符号游戏，很有可能走入死胡同. 

下面给出命题的正确证明. 

### 证明

任取 $w \in W$ ，由 $W \subseteq V$ ，亦知 $w \in V$ .又由 $V = V_1 \oplus V_2 \oplus \cdots \oplus V_k$ ，存在唯一的 $v_1 \in V_1, v_2 \in V_2, \ldots, v_k \in V_k$ ，s.t. 

$$w = v_1 + v_2 + \cdots + v_k . $$

下证 $v_i \in W$ ， $i = 1, 2, \ldots, k . $

由于 $V$ 在数域 ℂ 上，记 $\sigma$ 的特征多项式 

$$f(x) = (x - \lambda_1)^{r_1}(x - \lambda_2)^{r_2} \cdots (x - \lambda_k)^{r_k} . $$

其中 $\lambda_1, \lambda_2, \ldots, \lambda_k$ 两两不等，且 $r_1 + r_2 + \cdots + r_k = n$ .

定义 $f_1(x) := (x - \lambda_1)^{r_1} , f_2(x) := (x - \lambda_2)^{r_2} , \cdots , f_k(x) := (x - \lambda_k)^{r_k}$ ，且 $f_1(x) , f_2(x) , \cdots , f_k(x)$ 两两互素.则 $f(x) = f_1(x)f_2(x) \cdots f_k(x)$ .

定义 

$$g_i(x) := \prod_{j \neq i} f_j(x) = f_1(x)f_2(x) \cdots f_{i-1}(x)f_{i+1}(x) \cdots f_k(x) . $$ 

$j \neq i$ 时，有

$$g_i(\sigma)(V_j) = \prod_{m \neq i} f_m(\sigma)(v_j) = \prod_{m \neq i,j} f_m(\sigma) · f_j(\sigma)(v_j) . $$

而 $v_j \in V_j = Ker(\sigma - \lambda_j I)^{r_j}$ ，则 $f_j(\sigma)(v_j) = 0$ ，则 $g_i(\sigma)(v_j) = \prod_{m \neq i,j} f_m(\sigma) · f_j(\sigma)(v_j) = 0$ .故 

$$g_i(\sigma)(w) = g_i(\sigma)(v_1 + v_2 + \cdots + v_k) = g_i(\sigma)(v_i) . $$

由于 $w \in W$ 且 $W$ 在 $\sigma$ 下不变且 $g_i(\sigma)(w) \in W$ ，则 $g_i(\sigma)(v_i) = g_i(\sigma)(w) \in W . $

显然 $g_i(x)$ 与 $f_i(x)$ 互素，则存在 $s(x), t(x) \in ℂ[x]$ ，s.t.

$$g_i(x)s(x) + f_i(x)t(x) = 1, \quad g_i(\sigma)s(\sigma) + f_i(\sigma)t(\sigma) = I$$

在右两边作用 $v_i$，得

$$g_i(\sigma)s(\sigma)(v_i) = v_i . $$

其中，由于 $W$ 是 $\sigma$ 下的不变子空间且 $g_i(\sigma)(v_i) \in W$ ，则 $v_i = s(\sigma)g_i(\sigma)(v_i) \in W$ .

这样就证得了 $v_i \in W$ ， $i = 1, 2, \ldots, k$ .

则 $v_i \in W \cap V_i$ ，则 $W = (W \cap V_1) + (W \cap V_2) + \cdots + (W \cap V_k)$ .

又由 $v_1, v_2, \ldots, v_k$ 的唯一性，有

$$W = (W \cap V_1) \oplus (W \cap V_2) \oplus \cdots \oplus (W \cap V_k) .   \square $$

### 反思

此前的错误证明中，既没有用到**准素分解**本身的性质，也没有用到$W$ 是 $\sigma$ -不变子空间这一条件，因此几乎不可能证得结论. 

究其本质，
