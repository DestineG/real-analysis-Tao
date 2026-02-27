### 2.1 皮亚诺公理体系 (The Peano Axioms)

**定义 2.1**：**自然数集**（记作 $\mathbb{N}$）是一个包含特殊元素 $0$ 且具备后继运算 $n \mapsto n\text{++}$ 的集合，该集合须完全满足以下五条公理：

---

* **公理 2.1 (存在性)**：$0$ 是一个自然数。
    $$0 \in \mathbb{N}$$
* **公理 2.2 (封闭性)**：若 $n$ 是自然数，则其后继 $n\text{++}$ 亦为自然数。
    $$n \in \mathbb{N} \implies n\text{++} \in \mathbb{N}$$
* **公理 2.3 (起点唯一性)**：$0$ 不是任何自然数的后继。
    $$\forall n \in \mathbb{N}, n\text{++} \neq 0$$
* **公理 2.4 (单射性)**：若两个自然数的后继相等，则这两个自然数相等。
    $$n\text{++} = m\text{++} \implies n = m$$
* **公理 2.5 (数学归纳法)**：设 $P(n)$ 是关于自然数 $n$ 的性质。若 $P(0)$ 为真，且在 $P(n)$ 为真时能推导出 $P(n\text{++})$ 为真，则对于所有自然数 $n$，$P(n)$ 均为真。

---

上述公理通过代数与拓扑性质确立了自然数的标准模型：

1.  **无环性 (Acyclicity)**：由**公理 2.3** 保证。它排除了序列回流至起点 $0$ 的可能性，确定了序列的单向起始。
2.  **良序性 (Well-ordering)**：由**公理 2.4** 保证。它规定了后继运算是一一映射（单射），确保了序列在延伸过程中不会发生合并或分叉。
3.  **最小性 (Minimality)**：由**公理 2.5** 保证。它限定了 $\mathbb{N}$ 仅包含从 $0$ 出发通过有限次后继运算可达的元素，排除了任何不属于该链条的“异质”元素。

**结论**：自然数系是满足皮亚诺公理的最小归纳集。

### 2.2 加法

**定义 2.2.1（自然数的加法）**：在自然数集 $\mathbb{N}$ 上定义加法运算 $+$ 如下：
1. **基例**：对于任意自然数 $m$，定义 $0 + m = m$。
2. **递归定义**：对于任意自然数 $m$ 和 $n$，定义 $(n\text{++}) + m = (n + m)\text{++}$。

**引理 2.2.2**：对于任意的自然数 $m$，恒有 $m + 0 = m$ 成立。

**证明**：
1. **基例**：当 $m = 0$ 时，$0 + 0 = 0$，结论成立。
2. **归纳假设**：假设对于某个自然数 $n$，$n + 0 = n$ 成立。
3. **归纳步骤**：
$$
\begin{aligned}
& \text{证明：} (n\text{++}) + 0 = n\text{++} \\
& \quad \text{加法的递归定义} \Rightarrow (n\text{++}) + 0 = (n + 0)\text{++} \\
& \quad \text{归纳假设} \Rightarrow (n + 0)\text{++} = n\text{++} \\
& \quad \text{所以，} (n\text{++}) + 0 = n\text{++}
\end{aligned}
$$

由数学归纳法，$m + 0 = m$ 对所有自然数 $m$ 都成立。

**引理 2.2.3**：对于任意的自然数 $m$ 和 $n$，恒有 $m + (n\text{++}) = (m + n)\text{++}$ 成立。

**证明**：
1. **基例**：当 $m = 0$ 时，$0 + (n\text{++}) = n\text{++}$，结论成立。
2. **归纳假设**：假设对于某个自然数 $m$，$m + (n\text{++}) = (m + n)\text{++}$ 成立。
3. **归纳步骤**：
$$
\begin{aligned}
& \text{证明：} (m\text{++}) + (n\text{++}) = ((m\text{++}) + n)\text{++} \\
& \quad \text{加法的递归定义} \Rightarrow (m\text{++}) + (n\text{++}) = (m + (n\text{++}))\text{++} \\
& \quad \text{归纳假设} \Rightarrow (m + (n\text{++}))\text{++} = ((m + n)\text{++})\text{++} \\
& \quad \text{加法的递归定义} \Rightarrow ((m + n)\text{++})\text{++} = ((m\text{++}) + n)\text{++} \\
& \quad \text{所以，} (m\text{++}) + (n\text{++}) = ((m\text{++}) + n)\text{++}
\end{aligned}
$$

由数学归纳法，$m + (n\text{++}) = (m + n)\text{++}$ 对所有自然数 $m$ 和 $n$ 都成立。

**命题 2.2.4 加法是可交换的**：对于任意的自然数 $m$ 和 $n$，恒有 $m + n = n + m$ 成立。

**证明**：
1. **基例**：当 $m = 0$ 时，$0 + n = n$ 和 $n + 0 = n$，结论成立。
2. **归纳假设**：假设对于某个自然数 $m$，$m + n = n + m$ 成立。
3. **归纳步骤**：
$$
\begin{aligned}
& \text{证明：} (m\text{++}) + n = n + (m\text{++}) \\
& \quad \text{加法的递归定义} \Rightarrow (m\text{++}) + n = (m + n)\text{++} \\
& \quad \text{归纳假设} \Rightarrow (m + n)\text{++} = (n + m)\text{++} \\
& \quad \text{加法的递归定义} \Rightarrow (n + m)\text{++} = n + (m\text{++}) \\
& \quad \text{所以，} (m\text{++}) + n = n + (m\text{++})
\end{aligned}
$$

由数学归纳法，$m + n = n + m$ 对所有自然数 $m$ 和 $n$ 都成立。

**命题 2.2.5 加法是结合的**：对于任意的自然数 $m$、$n$ 和 $p$，恒有 $(m + n) + p = m + (n + p)$ 成立。

**证明**：
1. **基例**：当 $m = 0$ 时，$(0 + n) + p = n + p$ 和 $0 + (n + p) = n + p$，结论成立。
2. **归纳假设**：假设对于某个自然数 $m$，$(m + n) + p = m + (n + p)$ 成立。
3. **归纳步骤**：
$$
\begin{aligned}
& \text{证明：} ((m\text{++}) + n) + p = (m\text{++}) + (n + p) \\
& \quad \text{加法的递归定义} \Rightarrow ((m\text{++}) + n) + p = ((m + n)\text{++}) + p \\
& \quad \text{加法的递归定义} \Rightarrow ((m + n)\text{++}) + p = ((m + n) + p)\text{++} \\
& \quad \text{归纳假设} \Rightarrow ((m + n) + p)\text{++} = (m + (n + p))\text{++} \\
& \quad \text{加法的递归定义} \Rightarrow (m + (n + p))\text{++} = (m\text{++}) + (n + p) \\
& \quad \text{所以，} ((m\text{++}) + n) + p = (m\text{++}) + (n + p)
\end{aligned}
$$

由数学归纳法，$(m + n) + p = m + (n + p)$ 对所有自然数 $m$、$n$ 和 $p$ 都成立。

**命题 2.2.6 加法的消去律**：对于任意的自然数 $m$、$n$ 和 $p$，如果 $m + n = m + p$，则 $n = p$。

**证明**：
1. **基例**：当 $m = 0$ 时，$0 + n = n$ 和 $0 + p = p$，所以 $n = p$。
2. **归纳假设**：假设对于某个自然数 $m$，若 $m + n = m + p$ 则 $n = p$。
3. **归纳步骤**：
$$
\begin{aligned}
& \text{证明：} (m\text{++}) + n = (m\text{++}) + p \implies n = p \\
& \quad \text{加法的递归定义} \Rightarrow (m\text{++}) + n = (m + n)\text{++} \\
& \quad \text{加法的递归定义} \Rightarrow (m\text{++}) + p = (m + p)\text{++} \\
& \quad \text{所以，} (m + n)\text{++} = (m + p)\text{++} \\
& \quad \text{单射性} \Rightarrow m + n = m + p \\
& \quad \text{归纳假设} \Rightarrow n = p
\end{aligned}
$$

由数学归纳法，若 $m + n = m + p$ 则 $n = p$ 对所有自然数 $m$、$n$ 和 $p$ 都成立。

**定义 2.2.7 正自然数**：一个自然数 $m$ 被称为**正自然数**(记作$\mathbb{N}^{+}$)，当且仅当自然数 $m$ 不等于 $0$，即 $m \neq 0$。

**命题 2.2.8**：一个正自然数 $n$ 与 一个自然数 $m$ 的和 $n + m$ 也是一个正自然数。

**证明**：
1. **基例**：当 $m = 0$ 时，$n + 0 = n$，由于 $n$ 是正自然数，所以 $n + 0$ 是正自然数。
2. **归纳假设**：假设对于某个自然数 $m$，$n + m$ 是正自然数。
3. **归纳步骤**：
$$
\begin{aligned}
& \text{证明：} n + (m\text{++}) \text{ 是正自然数} \\
& \quad \text{加法的递归定义} \Rightarrow n + (m\text{++}) = (n + m)\text{++} \\
& \quad \text{归纳假设} \Rightarrow n + m \text{ 是正自然数} \\
& \quad \text{由公理 2.3 可知，} n + m \text{ 是正自然数} \Rightarrow (n + m)\text{++} \text{ 是正自然数} \\
& \quad \text{所以，} n + (m\text{++}) \text{ 是正自然数}
\end{aligned}
$$

由数学归纳法，$n + m$ 是正自然数对所有正自然数 $n$ 和自然数 $m$ 都成立。

**推论 2.2.9**：对于自然数 $m$ 和 $n$，如果 $m + n = 0$，则 $m = 0$ 且 $n = 0$。

**证明**：反证法
$$
\begin{aligned}
& \text{假设存在自然数 } m \text{ 和 } n \text{ 使得 } m + n = 0 \text{ 且 } m \neq 0 \text{ 或 } n \neq 0 \\
& \text{如果 } m \neq 0 \text{，则 }m \text{ 是正自然数，根据 命题 2.2.8，} m + n \text{ 是正自然数} \\
& \text{这与 } m + n = 0 \text{ 矛盾} \\
& \text{如果 } n \neq 0 \text{，则 }n \text{ 是正自然数，根据 命题 2.2.4(加法的交换律) 和 命题 2.2.8，} m + n \text{ 是正自然数} \\
& \text{这与 } m + n = 0 \text{ 矛盾} \\
& \text{所以，} m = 0 \text{ 且 } n = 0
\end{aligned}
$$

由反证法，如果自然数 $m$ 和 $n$ 满足 $m + n = 0$，则必定 $m = 0$ 且 $n = 0$。

**引理 2.2.10**：对任意的正自然数 $m$，恰好存在一个自然数 $n$ 使得 $m = n\text{++}$。

**证明**：
1. **唯一性**：若存在 $n_1, n_2$ 使得 $n_1\text{++} = n_2\text{++} = m$，根据 **公理 2.4** 可知 $n_1 = n_2$。
2. **存在性**：对全体自然数 $m$ 施加归纳法。
   - **基例**：当 $m = 0\text{++}$ 时，取 $n = 0$，结论成立。
   - **归纳假设**：假设对于某个正自然数 $m$，存在自然数使得 $m = n\text{++}$。
   - **归纳步骤**：考虑 $m\text{++}$。
     我们需要找到一个自然数 $n$ 使得 $m\text{++} = n\text{++}$。
     显然，取 $n = m$ 即可满足 $m\text{++} = n\text{++}$。

由数学归纳法可知，除 $0$ 以外的每一个自然数都有唯一的前驱。

**定义 2.2.11 自然数的序**：对于自然数 $m$ 和 $n$，定义 $m$ **大于等于** $n$（记作 $m \ge n$）当且仅当存在一个自然数 $k$ 使得 $m = n + k$；定义 $m$ **大于** $n$（记作 $m > n$）当且仅当 $m \ge n$ 且 $m \neq n$。

**命题 2.2.12 自然数的序的基本性质**：令 $m$、$n$ 和 $p$ 是任意自然数，则以下性质成立：
1. **反身性**：$m \ge m$。
2. **反对称性**：如果 $m \ge n$ 且 $n \ge m$，则 $m = n$。
3. **传递性**：如果 $m \ge n$ 且 $n \ge p$，则 $m \ge p$。
4. **与加法的兼容性**：如果 $m \ge n$，则对于任意自然数 $p$，$m + p \ge n + p$。
5. **序的刻画**：$m < n \iff m\text{++} \le n \iff \exist p \in \mathbb{N}^{+} \text{ 使得 } m + p = n$

**命题 2.2.13 自然数的序的三歧性**：对于任意自然数 $m$ 和 $n$，恰有以下三种情况之一成立：$$m < n \quad \text{或} \quad m = n \quad \text{或} \quad m > n$$

**命题 2.2.14 强归纳法原理**：设 $P(n)$ 是关于自然数 $n$ 的性质。若对于任意自然数 $n$，在 $P(k)$ 对所有 $k < n$ 成立的前提下能推导出 $P(n)$ 为真，则对于所有自然数 $n$，$P(n)$ 均为真。

**证明**：反证法
$$\begin{aligned}
& \text{假设存在自然数 } n \text{ 使得 } P(n) \text{ 不成立} \\
& \text{根据命题 2.2.13 的三歧性，存在一个最小的自然数 } n_0 \text{ 使得 } P(n_0) \text{ 不成立} \\
& \text{由于 } n_0 \text{ 是最小的反例，} P(k) \text{ 对所有 } k < n_0 \text{ 成立} \\
& \text{根据强归纳法的假设，} P(n_0) \text{ 应该成立} \\
& \text{这与 } P(n_0) \text{ 不成立的假设矛盾} \\
& \text{所以，} P(n) \text{ 对所有自然数 } n \text{ 都成立}
\end{aligned}$$

**命题 2.2.15 加法的封闭性**：对于任意自然数 $m$ 和 $n$，$m + n$ 仍然是自然数。

**证明**：对 $m$ 施加归纳法。
1. **基例**：当 $m = 0$ 时，$0 + n = n$，结论成立。
2. **归纳假设**：假设对于某个自然数 $m$，$m + n$ 是自然数。
3. **归纳步骤**：
$$\begin{aligned}
& \text{证明：} (m\text{++}) + n \text{ 是自然数} \\
& \quad \text{加法的递归定义} \Rightarrow (m\text{++}) + n = (m + n)\text{++} \\
& \quad \text{归纳假设，公理 2.2} \Rightarrow (m + n)\text{++} \text{ 是自然数} \\
& \quad \text{所以，} (m\text{++}) + n \text{ 是自然数}
\end{aligned}$$

由数学归纳法，$m + n$ 是自然数对所有自然数 $m$ 和 $n$ 都成立。

### 2.3 乘法

**定义 2.3.1 自然数的乘法**：在自然数集 $\mathbb{N}$ 上定义乘法运算 $\cdot$ 如下：
1. **基例**：对于任意自然数 $m$，定义 $0 \cdot m = 0$。
2. **递归定义**：对于任意自然数 $m$ 和 $n$，定义 $(n\text{++}) \cdot m = (n \cdot m) + m$。

**引理 2.3.1.1**：对于任意的自然数 $m$，恒有 $m \cdot 0 = 0$ 成立。

**证明**：对 $m$ 施加归纳法。
1. **基例**：当 $m = 0$ 时，$0 \cdot 0 = 0$，结论成立。
2. **归纳假设**：假设对于某个自然数 $m$，$m \cdot 0 = 0$ 成立。
3. **归纳步骤**：
$$
\begin{aligned}
& \text{证明：} (m\text{++}) \cdot 0 = 0 \\
& \quad \text{乘法的递归定义} \Rightarrow (m\text{++}) \cdot 0 = (m \cdot 0) + 0 \\
& \quad \text{归纳假设} \Rightarrow (m \cdot 0) + 0 = 0 + 0 \\
& \quad \text{加法的交换律} \Rightarrow 0 + 0 = 0 \\
& \quad \text{所以，} (m\text{++}) \cdot 0 = 0
\end{aligned}
$$

由数学归纳法，$m \cdot 0 = 0$ 对所有自然数 $m$ 都成立。

**引理 2.3.1.2**：对于任意的自然数 $m$ 和 $n$，恒有 $m \cdot (n\text{++}) = m + m \cdot n$ 成立。

**证明**：对 $m$ 施加归纳法。
1. **基例**：当 $m = 0$ 时，$0 \cdot (n\text{++}) = 0$ 和 $0 \cdot n + 0 = 0 + 0 = 0$，结论成立。
2. **归纳假设**：假设对于某个自然数 $m$，$m \cdot (n\text{++}) = m + m \cdot n$ 成立。
3. **归纳步骤**：
$$
\begin{aligned}
& \text{证明：} (m\text{++}) \cdot (n\text{++}) = (m\text{++}) + (m\text{++}) \cdot n \\
& \quad \text{乘法的递归定义} \Rightarrow (m\text{++}) \cdot (n\text{++}) = (m \cdot (n\text{++})) + (n\text{++}) \\
& \quad \text{归纳假设} \Rightarrow (m \cdot (n\text{++})) + (n\text{++}) = (m + m \cdot n) + (n\text{++}) \\
& \quad \text{加法的结合律} \Rightarrow (m + m \cdot n) + (n\text{++}) = m + (m \cdot n + (n\text{++})) \\
& \quad \text{引理 2.2.3} \Rightarrow m \cdot n + (n\text{++}) = m \cdot n + (n\text{++}) \\
& \quad \text{加法的递归定义} \Rightarrow m \cdot n + (n\text{++}) = (m \cdot n)\text{++} \\
& \quad \text{加法的交换律} \Rightarrow m + ((m \cdot n)\text{++}) = ((m \cdot n)\text{++}) + m \\
& \quad \text{所以，} m + (n\text{++}) = n + (m\text{++}) \\
& \quad \text{加法的结合律} \Rightarrow m \cdot n + (n + (m\text{++})) = (m \cdot n + n) + (m\text{++}) \\
& \quad \text{乘法的递归定义} \Rightarrow (m \cdot n + n) + (m\text{++}) = (m\text{++}) \cdot n + (m\text{++}) \\
& \quad \text{加法的交换律} \Rightarrow (m\text{++}) \cdot n + (m\text{++}) = (m\text{++}) + (m\text{++}) \cdot n \\
& \quad \text{所以，} (m\text{++}) \cdot (n\text{++}) = (m\text{++}) + (m\text{++}) \cdot n
\end{aligned}
$$

由数学归纳法，$m \cdot (n\text{++}) = m + m \cdot n$ 对所有自然数 $m$ 和 $n$ 都成立。

**引理 2.3.2 乘法是可交换的**：对于任意的自然数 $m$ 和 $n$，恒有 $m \cdot n = n \cdot m$ 成立。

**证明**：对 $m$ 施加归纳法。
1. **基例**：当 $m = 0$ 时，$0 \cdot n = 0$ 和 $n \cdot 0 = 0$(**引理 2.3.1.1**)，结论成立。
2. **归纳假设**：假设对于某个自然数 $m$，$m \cdot n = n \cdot m$ 成立。
3. **归纳步骤**：
$$\begin{aligned}
& \text{证明：} (m\text{++}) \cdot n = n \cdot (m\text{++}) \\
& \quad \text{乘法的递归定义} \Rightarrow (m\text{++}) \cdot n = (m \cdot n) + n \\
& \quad \text{归纳假设} \Rightarrow (m \cdot n) + n = (n \cdot m) + n \\
& \quad \text{加法的交换律} \Rightarrow (n \cdot m) + n = n + (n \cdot m) \\
& \quad \text{引理 2.3.1.2} \Rightarrow n + (n \cdot m) = n \cdot (m\text{++}) \\
& \quad \text{所以，} (m\text{++}) \cdot n = n \cdot (m\text{++})
\end{aligned}$$

由数学归纳法，$m \cdot n = n \cdot m$ 对所有自然数 $m$ 和 $n$ 都成立。

**引理 2.3.3 正自然数没有零因子**：对于任意的自然数 $m$ 和 $n$，如果 $m = 0$ 或 $n = 0$，则 $m \cdot n = 0$。

**命题 2.3.4 乘法的分配律**：对于任意的自然数 $m$、$n$ 和 $p$，恒有 $m \cdot (n + p) = m \cdot n + m \cdot p$ 和 $(m + n) \cdot p = m \cdot p + n \cdot p$ 成立。

**证明**：对 $m$ 施加归纳法。
1. **基例**：当 $m = 0$ 时，$0 \cdot (n + p) = 0$ 和 $0 \cdot n + 0 \cdot p = 0 + 0 = 0$，结论成立。
2. **归纳假设**：假设对于某个自然数 $m$，$m \cdot (n + p) = m \cdot n + m \cdot p$ 成立。
3. **归纳步骤**：
$$\begin{aligned}
& \text{证明：} (m\text{++}) \cdot (n + p) = (m\text{++}) \cdot n + (m\text{++}) \cdot p \\
& \quad \text{乘法的递归定义} \Rightarrow (m\text{++}) \cdot (n + p) = (m \cdot (n + p)) + (n + p) \\
& \quad \text{归纳假设} \Rightarrow (m \cdot (n + p)) + (n + p) = (m \cdot n + m \cdot p) + (n + p) \\
& \quad \text{加法的交换律} \Rightarrow (m \cdot n + m \cdot p) + (n + p) = (m \cdot n + n) + (m \cdot p + p) \\
& \quad \text{乘法的递归定义} \Rightarrow (m \cdot n + n) + (m \cdot p + p) = (m\text{++}) \cdot n + (m\text{++}) \cdot p \\
& \quad \text{所以，} (m\text{++}) \cdot (n + p) = (m\text{++}) \cdot n + (m\text{++}) \cdot p
\end{aligned}$$

由数学归纳法，乘法的分配律对所有自然数 $m$、$n$ 和 $p$ 都成立。

**命题 2.3.5 乘法的结合律**：对于任意的自然数 $m$、$n$ 和 $p$，恒有 $(m \cdot n) \cdot p = m \cdot (n \cdot p)$ 成立。

**证明**：对 $m$ 施加归纳法。
1. **基例**：当 $m = 0$ 时，$(0 \cdot n) \cdot p = 0 \cdot p = 0$ 和 $0 \cdot (n \cdot p) = 0$，结论成立。
2. **归纳假设**：假设对于某个自然数 $m$，$(m \cdot n) \cdot p = m \cdot (n \cdot p)$ 成立。
3. **归纳步骤**：
$$\begin{aligned}
& \text{证明：} ((m\text{++}) \cdot n) \cdot p = (m\text{++}) \cdot (n \cdot p) \\
& \quad \text{乘法的递归定义} \Rightarrow ((m\text{++}) \cdot n) \cdot p = ((m \cdot n + n) \cdot p \\
& \quad \text{加法的分配律} \Rightarrow ((m \cdot n + n) \cdot p = (m \cdot n) \cdot p + n \cdot p \\
& \quad \text{归纳假设} \Rightarrow (m \cdot n) \cdot p + n \cdot p = m \cdot (n \cdot p) + n \cdot p \\
& \quad \text{加法的递归定义} \Rightarrow m \cdot (n \cdot p) + n \cdot p = (m\text{++}) \cdot (n \cdot p) \\
& \quad \text{所以，} ((m\text{++}) \cdot n) \cdot p = (m\text{++}) \cdot (n \cdot p)
\end{aligned}$$

由数学归纳法，乘法的结合律对所有自然数 $m$、$n$ 和 $p$ 都成立。

**命题 2.3.6 乘法保序性**：对于任意的自然数 $m$、$n$ 和 $p$，如果 $m < n$，则 $m \cdot p < n \cdot p$（当 $p \neq 0$ 时）。

**证明**：对 $p$ 施加归纳法。
1. **基例**：当 $p = 0\text{++}$ 时，$m \cdot 0\text{++} = m$ 和 $n \cdot 0\text{++} = n$，由于 $m < n$，所以 $m \cdot 0\text{++} < n \cdot 0\text{++}$，结论成立。
2. **归纳假设**：假设对于某个自然数 $p$，如果 $m < n$，则 $m \cdot p < n \cdot p$ 成立。
3. **归纳步骤**：
$$\begin{aligned}
& \text{证明：} m \cdot (p\text{++}) < n \cdot (p\text{++}) \\
& \quad \text{乘法的递归定义} \Rightarrow m \cdot (p\text{++}) = m \cdot p + m \\
& \quad \text{乘法的递归定义} \Rightarrow n \cdot (p\text{++}) = n \cdot p + n \\
& \quad \text{归纳假设} \Rightarrow m \cdot p < n \cdot p \\
& \quad \text{因为 } m < n \text{，所以 } m \cdot p + m < n \cdot p + n \\
& \quad \text{所以，} m \cdot (p\text{++}) < n \cdot (p\text{++})
\end{aligned}$$

由数学归纳法，乘法保序性对所有自然数 $m$、$n$ 和 $p$ 都成立。

**推论 2.3.7 乘法的消去律**：对于任意的自然数 $m$、$n$ 和 $p$，如果 $m \cdot p = n \cdot p$ 且 $p \neq 0$，则 $m = n$。

**证明**：反证法(**命题 2.2.13 三歧性**)
$$\begin{aligned}
& \text{假设存在自然数 } m \text{ 和 } n \text{ 使得 } m \cdot p = n \cdot p \text{ 且 } m \neq n \\
& \text{如果 } m < n \text{，根据命题 2.3.6，} m \cdot p < n \cdot p \\
& \text{这与 } m \cdot p = n \cdot p \text{ 矛盾} \\
& \text{如果 }n < m \text{，根据命题 2.3.6，} n \cdot p < m \cdot p \\
& \text{这与 } m \cdot p = n \cdot p \text{ 矛盾} \\
& \text{所以，} m = n
\end{aligned}$$

由反证法，如果 $m \cdot p = n \cdot p$ 且 $p \neq 0$，则必定 $m = n$。

**命题 2.3.9 欧几里得算法**：对于任意的自然数 $a$ 和 $b$，存在唯一的自然数 $q$ 和 $r$，使得 $a = q \cdot b + r$ 且 $0 \leq r < b$。

**证明**：
1. **存在性**：对 $a$ 施加归纳法。
   - **基例**：当 $a = 0$ 时，取 $q = 0$ 和 $r = 0$，满足 $0 = 0 \cdot b + 0$ 和 $0 \leq 0 < b$，结论成立。
   - **归纳假设**：假设对于某个自然数 $a$，存在自然数 $q$ 和 $r$ 使得 $a = q \cdot b + r$ 且 $0 \leq r < b$。
   - **归纳步骤**：考虑 $a\text{++}$。
     - 如果 $r\text{++} < b$，则取 $q' = q$ 和 $r' = r\text{++}$，满足 $a\text{++} = q' \cdot b + r'$ 和 $0 \leq r' < b$。
     - 如果 $r\text{++} = b$，则取 $q' = q\text{++}$ 和 $r' = 0$，满足 $a\text{++} = q' \cdot b + r'$ 和 $0 \leq r' < b$。
     - 如果 $r\text{++} > b$，则取 $q' = q\text{++}$ 和 $r' = r\text{++} - b$，满足 $a\text{++} = q' \cdot b + r'$ 和 $0 \leq r' < b$。
2. **唯一性**：假设存在 $q_1, r_1$ 和 $q_2, r_2$ 满足 $a = q_1 \cdot b + r_1$ 和 $a = q_2 \cdot b + r_2$，且 $0 \leq r_1 < b$ 和 $0 \leq r_2 < b$。
$$\begin{aligned}
& \text{证明：} q_1 = q_2 \text{ 且 } r_1 = r_2 \\
& \quad \text{若 } q_1 \neq q_2 \text{，不失一般性假设 } q_1 < q_2 \text{，则 } q_2 = q_1 + k \text{ 对某个自然数 } k > 0 \\
& \quad \text{于是 } a = q_1 \cdot b + r_1 = (q_1 + k) \cdot b + r_2 = q_1 \cdot b + k \cdot b + r_2 \\
& \quad \text{所以 } r_1 = k \cdot b + r_2 \\
& \quad \text{由于 } 0 \leq r_1 < b \text{ 和 } 0 \leq r_2 < b，\text{ 这不可能成立，因为 } k > 0 \\
& \quad \text{因此，} q_1 = q_2 \\
& \quad \text{代入得 } r_1 = r_2
\end{aligned}$$

由数学归纳法和唯一性证明，欧几里得算法对所有自然数 $a$ 和 $b$ 都成立。

**定义 2.3.11 自然数的指数运算**：对于自然数 $m$ 和 $n$，定义 $m^0 = 1$，并定义 $m^{n\text{++}} = m^n \cdot m$。特别的，定义 $0^0 = 1$。

### 2.4 习题

**习题 2.4.4**：证明等式 $(a + b)^{2} = a^2 + 2ab + b^2$ 对任意自然数 $a$ 和 $b$ 成立。（注：$2x = x + x$）

**证明**：对 $a$ 施加归纳法。
1. **基例**：当 $a = 0$ 时，$(0 + b)^{2} = b^2$ 和 $0^2 + 2 \cdot 0 \cdot b + b^2 = b^2$，结论成立。
2. **归纳假设**：假设对于某个自然数 $a$，$(a + b)^{2} = a^2 + 2ab + b^2$ 成立。
3. **归纳步骤**：考虑 $a\text{++}$。
$$
\begin{aligned}
& \text{证明：}((a\text{++}) + b)^{2} = (a\text{++})^2 + 2(a\text{++})b + b^2 \\
& \quad \text{指数运算定义 2.3.11} \Rightarrow ((a\text{++}) + b)^{2} = ((a\text{++}) + b) \cdot ((a\text{++}) + b) \\
& \quad \text{加法递归定义} \Rightarrow ((a\text{++}) + b) \cdot ((a\text{++}) + b) = ((a + b)\text{++}) \cdot ((a + b)\text{++}) \\
& \quad \text{乘法的递归定义} \Rightarrow ((a + b)\text{++}) \cdot ((a + b)\text{++}) = ((a + b) \cdot ((a + b)\text{++})) + ((a + b)\text{++}) \\
& \quad \text{乘法的递归定义} \Rightarrow ((a + b) \cdot ((a + b)\text{++})) + ((a + b)\text{++}) = ((a + b) \cdot (a + b)) + (a + b) + ((a + b)\text{++}) \\
& \quad \text{归纳假设} \Rightarrow ((a + b) \cdot (a + b)) + (a + b) + ((a + b)\text{++}) = (a^2 + 2ab + b^2) + (a + b) + ((a + b)\text{++}) \\
& \quad \text{加法的递归定义} \Rightarrow (a^2 + 2ab + b^2) + (a + b) + ((a + b)\text{++}) = (a^2 + 2ab + b^2) + (a + b) + ((a\text{++}) + b) \\
& \quad \text{加法的交换律} \Rightarrow (a^2 + 2ab + b^2) + (a + b) + ((a\text{++}) + b) = (a^2 + a + (a\text{++})) + (2ab + b + b) + b^{2} \\
& \quad \text{乘法的递归定义} \Rightarrow (a^2 + a + (a\text{++})) + (2ab + b + b) + b^{2} = (a\text{++})^2 + (2ab + b + b) + b^2 \\
& \quad 2x = x + x \text{ ,加法的交换律} \Rightarrow (a\text{++})^2 + (2ab + b + b) + b^2 = (a\text{++})^2 + (ab + b + ab + b) + b^2 \\
& \quad \text{加法结合律} \Rightarrow (a\text{++})^2 + (ab + b + ab + b) + b^2 = (a\text{++})^2 + ((ab + b) + (ab + b)) + b^2 \\
& \quad \text{加法的递归定义} \Rightarrow (a\text{++})^2 + ((ab + b) + (ab + b)) + b^2 = (a\text{++})^2 + ((a\text{++})b + (a\text{++})b) + b^2 \\
& \quad 2x = x + x \Rightarrow (a\text{++})^2 + ((a\text{++})b + (a\text{++})b) + b^2 = (a\text{++})^2 + 2(a\text{++})b + b^2 \\
& \quad \text{所以，} ((a\text{++}) + b)^{2} = (a\text{++})^2 + 2(a\text{++})b + b^2
\end{aligned}
$$

因此，$(a\text{++} + b)^{2} = (a\text{++})^2 + 2(a\text{++})b + b^2$，结论成立。