gradient(梯度)

多个变量的函数 $( f(x_1, x_2, \dots, x_n) )$:

梯度是由该函数对每个变量的偏导数组成的向量：
$$
\nabla f = \left( \frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}, \dots, \frac{\partial f}{\partial x_n} \right)
$$


	•	梯度的方向：梯度指向函数增长最快的方向。
	•	梯度的大小：梯度的大小（向量的模）表示函数在该点沿着梯度方向变化得有多快。

矩阵梯度()

//TODO:

范数：

- L1 范数 (曼哈顿距离)：向量各分量的绝对值之和。

$$
\|x\|_1=\sum i=1^n\left|x_i\right|
$$

- L2 范数 (欧几里得范数)：向量各分量平方和的平方根。它是最常用的范数之一。

$$
\|x\|_2=\sqrt{\sum i=1^n x_i^2}
$$

- $L \infty$ 范数：向量各分量的绝对值中的最大值。

$$
\|x\|_{\infty}=\max _i\left|x_i\right|
$$

1. Frobenius 范数 (Frobenius Norm)

Frobenius 范数是矩阵元素的平方和的平方根, 类似于向量的 L2 范数。它可以用于衡量矩阵整体的大小。

$$
\|A\| F=\sqrt{\sum i=1^m \sum_{j=1}^n\left|a_{i j}\right|^2}
$$


其中 $a_{i j}$ 是矩阵 $A$ 中第 $i$ 行第 $j$ 列的元素。
2. 1-范数 (列范数, L1 Norm)
1-范数是矩阵每列元素绝对值和的最大值, 适合用于衡量矩阵在列方向上的变化。

$$
\|A\| 1=\max _j \sum i=1^m\left|a_{i j}\right|
$$


即每列元素绝对值和的最大值。
3. $\infty$-范数 (行范数, L $\infty$ Norm)
$\infty$-范数是矩阵每行元素绝对值和的最大值, 适合衡量矩阵在行方向上的变化。

$$
\|A\| \infty=\max _i \sum j=1^n\left|a_{i j}\right|
$$

$\infty$-范数是矩阵每行元素绝对值和的最大值, 适合衡量矩阵在行方向上的变化。

$$
\|A\| \infty=\max _i \sum j=1^n\left|a_{i j}\right|
$$


即每行元素绝对值和的最大值。
4. 谱范数 (Spectral Norm, L2 范数)

谱范数是矩阵的最大奇异值, 它反映了矩阵作为线性变换时, 对向量施加的最大拉伸效果。对于一个矩阵 $A$, 它的谱范数定义为:

$$
\|A\| 2=\sigma \max
$$


其中 $\sigma_{\max }$ 是矩阵的最大奇异值, 奇异值是通过奇异值分解 (SVD) 得到的。
5. 算子范数 (Operator Norm)

算子范数也称为 "诱导范数" (induced norm), 它衡量的是矩阵作为线性变换作用于向量时对向量的缩放程度。对于矩阵 $A$ 及其作用在任意非零向量 $x$ 上：

$$
\|A\| p=\sup x \neq 0 \frac{\|A x\|_p}{\|x\|_p}
$$