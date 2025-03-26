###### 线性方程

迭代算法，先猜一个$x^{(0)}$,$x^{(k+1)}=\mathscr{M}\left(x^{(k)}\right)$利用迭代方法生成一个序列知道小于某个tolerance。

###### Jacobi迭代

$x^{(k+1)}=D^{-1} b-D^{-1}(L+U) x^{(k)}=M x^{(k)}+c$

$x_i^{(k+1)}=\frac{1}{a_{i i}}\left(b_i-\sum_{j \neq i} a_{i j} x_j^{(k+1)}\right)$

###### 非线性方程