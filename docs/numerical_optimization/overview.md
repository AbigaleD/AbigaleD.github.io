- ### gradient(梯度)


多个变量的函数 $( f(x_1, x_2, \dots, x_n) )$:

梯度是由该函数对每个变量的偏导数组成的向量：
$$
\nabla f = \left( \frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}, \dots, \frac{\partial f}{\partial x_n} \right)
$$


	•	梯度的方向：梯度指向函数增长最快的方向。
	•	梯度的大小：梯度的大小（向量的模）表示函数在该点沿着梯度方向变化得有多快。

矩阵梯度()

### 范数

###### L1 范数 (曼哈顿距离)

向量各分量的绝对值之和。
$$
\|x\|_1=\sum i=1^n\left|x_i\right|
$$


###### L2 范数 (欧几里得范数)

向量各分量平方和的平方根。它是最常用的范数之一。
$$
\|x\|_2=\sqrt{\sum i=1^n x_i^2}
$$

###### $L \infty$ 范数

向量各分量的绝对值中的最大值。
$$
\|x\|_{\infty}=\max _i\left|x_i\right|
$$

对于$m \times n$ 的矩阵

$L_\infty$ 范数在向量的情形下是向量各分量绝对值的最大值，对于矩阵也可以推广。对于一个 $m \times n$ 的矩阵 $A$，我们可以有多种方式来定义它的 $L_\infty$ 范数。



矩阵 $L_\infty$ 范数通常被定义为矩阵的行和范数，也就是说：



$$

|A|*\infty = \max*{1 \leq i \leq m} \sum_{j=1}^{n} |a_{ij}|

$$



这是每一行元素绝对值之和的最大值。具体来说，你可以按照以下步骤理解：



​	1.	对于矩阵 $A$ 的每一行，计算该行的所有元素的绝对值之和。

​	2.	找出这些行和中的最大值，这个最大值就是矩阵 $A$ 的 $L_\infty$ 范数。



**举例说明：**



假设有一个 $3 \times 3$ 的矩阵 $A$：


$$
A = \begin{pmatrix}

1 & -2 & 3 \\

-4 & 5 & -6 \\

7 & -8 & 9

\end{pmatrix}
$$




我们可以计算每一行元素的绝对值之和：



​	•	第一行的绝对值和：$|1| + |-2| + |3| = 1 + 2 + 3 = 6$

​	•	第二行的绝对值和：$|-4| + |5| + |-6| = 4 + 5 + 6 = 15$

​	•	第三行的绝对值和：$|7| + |-8| + |9| = 7 + 8 + 9 = 24$



因此，矩阵 $A$ 的 $L_\infty$ 范数为这三行和中的最大值：


$$
|A|_\infty = \max(6, 15, 24) = 24
$$




这就是矩阵 $L_\infty$ 范数的定义和计算方式。

###### Frobenius 范数 (Frobenius Norm)

Frobenius 范数是矩阵元素的平方和的平方根, 类似于向量的 L2 范数。它可以用于衡量矩阵整体的大小。

$$
\|A\| F=\sqrt{\sum i=1^m \sum_{j=1}^n\left|a_{i j}\right|^2}
$$


其中 $a_{i j}$ 是矩阵 $A$ 中第 $i$ 行第 $j$ 列的元素。
###### 谱范数 (Spectral Norm, L2 范数)

谱范数是矩阵的最大奇异值, 它反映了矩阵作为线性变换时, 对向量施加的最大拉伸效果。对于一个矩阵 $A$, 它的谱范数定义为:

$$
\|A\| 2=\sigma \max
$$


其中 $\sigma_{\max }$ 是矩阵的最大奇异值, 奇异值是通过奇异值分解 (SVD) 得到的。
###### 算子范数 (Operator Norm)

算子范数也称为 "诱导范数" (induced norm), 它衡量的是矩阵作为线性变换作用于向量时对向量的缩放程度。对于矩阵 $A$ 及其作用在任意非零向量 $x$ 上：

$$
\|A\| p=\sup x \neq 0 \frac{\|A x\|_p}{\|x\|_p}
$$

###### 半正定（semi-posititive definite)

$$
\forall x \space x^{T}Ax ≥0
$$

###### 正定（posititive definite)

$$
\forall x \space x^{T}Ax ≥0
$$

#### 可能有用的结论

gradient:

$$
\begin{aligned}
& \|A x-b\|_2^2=y^{\top} y \\
& \nabla\|A x-b\|=\frac{\partial\|A x-b\|_2^2}{\partial x}=\frac{\partial\left(y^{\top} y\right)}{\partial x}=2 y^{\top} \frac{\partial y}{\partial x} \\
& =2 y^{\top} A=2\left(A^{\top} y\right)=2\left(A^{\top}(A x-b)\right)^{\top} \\
& =2 A^{\top}(A x-b)
\end{aligned}
$$

hessian:

$$
\begin{aligned}
\nabla^2 f(x) & =\frac{\partial}{\partial x}(\nabla f(x))=\frac{\partial}{\partial x}\left[2 A^{\top}(A x-b)\right] \\
\nabla f(x) & =2 A^{\top} A x-2 A^{\top} b \\
\therefore \nabla^2 f(x) & =2 A^{\top} A
\end{aligned}
$$


Only when $A$ is full rank proof:
$\forall x$.

$$
x^{\top}\left(A^{\top} A\right) x=(x A)^{\top}(A x)=\|A x\|^2 \geqslant 0
$$

which means it is semi-definite but, def of positive definite requires $\|A x\|^2 \neq 0, A$ need to be full-rank

### 收敛

#### 序列收敛

序列{$x_k$}收敛到$x^{*}$:$\lim _{k \rightarrow \infty}\left\|x_k-x^*\right\|_2=0$

#### 收敛速度

###### Q-linear

###### Q-superlinear

###### Q-quadratic
