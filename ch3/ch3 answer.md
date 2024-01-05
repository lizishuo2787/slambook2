#1. 正交矩阵定义
正交矩阵是一个方阵，其行向量和列向量是单位向量且两两正交的矩阵。具体而言，一个n阶方阵A是正交矩阵，如果满足以下条件：
1. A的每一行都是单位向量，即每一行的范数（向量长度）为1：\[ \|A_i\| = 1, \text{ 其中 } 1 \leq i \leq n \]
2. A的每一列也都是单位向量：\[ \|A^j\| = 1, \text{ 其中 } 1 \leq j \leq n \]
3. A的任意两行（或列）都是正交的，即它们的内积为0：\[ A_i \cdot A_k = 0, \text{ 当 } i \neq k \]
正交矩阵的重要性在于它保持向量的长度和夹角不变。如果矩阵A是正交矩阵，对于任意向量v，有\[ \|Av\| = \|v\| \]，并且对于任意两个向量v和w，它们的夹角保持不变：\[ (Av) \cdot (Aw) = v \cdot w \]。

#2. 罗德里格斯公式的推导
罗德里格斯旋转公式是用于表示绕轴旋转的公式，通常用于描述三维空间中的旋转。假设有一个单位向量 \( \mathbf{k} = [k_1, k_2, k_3] \)，表示旋转轴的方向，以及旋转角度 \( \theta \)，罗德里格斯旋转公式表示为：

\[ \mathbf{R} = \cos(\theta)\mathbf{I} + (1-\cos(\theta))\mathbf{k}\mathbf{k}^T + \sin(\theta)\mathbf{K} \]

其中：

- \( \mathbf{I} \) 是单位矩阵。
- \( \mathbf{k}\mathbf{k}^T \) 是外积矩阵，表示将 \( \mathbf{k} \) 视为列向量，然后与其转置相乘。
- \( \mathbf{K} \) 是反对称矩阵，定义为：

\[ \mathbf{K} = \begin{bmatrix} 0 & -k_3 & k_2 \\ k_3 & 0 & -k_1 \\ -k_2 & k_1 & 0 \end{bmatrix} \]

这个公式表示了一个绕单位向量 \( \mathbf{k} \) 旋转角度 \( \theta \) 的旋转矩阵 \( \mathbf{R} \)。

假设旋转轴为 \( \mathbf{k} \)，旋转角度为 \( \theta \)。首先，我们定义一个旋转矩阵 \( \mathbf{R} \) ，它将初始向量 \( \mathbf{v} \) 旋转到终向量 \( \mathbf{v'} \)：

\[ \mathbf{v'} = \mathbf{R}\mathbf{v} \]

接下来，我们考虑旋转轴的方向，定义单位向量 \( \mathbf{u} \) 与旋转轴 \( \mathbf{k} \) 相等：

\[ \mathbf{u} = \mathbf{k} \]

现在，我们可以使用旋转矩阵 \( \mathbf{R} \) 来表示 \( \mathbf{u'} \)（即旋转后的旋转轴）：

\[ \mathbf{u'} = \mathbf{R}\mathbf{u} \]

由于 \( \mathbf{u} = \mathbf{k} \) 是旋转轴的方向，我们知道 \( \mathbf{u'} \) 也应该是旋转轴的方向，因此 \( \mathbf{u'} \) 也是单位向量。因此，我们可以将 \( \mathbf{u'} \) 表示为：

\[ \mathbf{u'} = \frac{\mathbf{R}\mathbf{u}}{\|\mathbf{R}\mathbf{u}\|} \]

现在，我们考虑旋转轴 \( \mathbf{u} \) 在旋转前后都不变，即 \( \mathbf{u} = \mathbf{u'} \)。这意味着：

\[ \mathbf{u} = \frac{\mathbf{R}\mathbf{u}}{\|\mathbf{R}\mathbf{u}\|} \]

解这个方程，我们可以得到旋转矩阵 \( \mathbf{R} \) 的形式。具体步骤如下：

1. 将旋转轴 \( \mathbf{u} \) 写成矩阵形式：\[ \mathbf{u} = \begin{bmatrix} k_1 \\ k_2 \\ k_3 \end{bmatrix} \]

2. 将旋转矩阵 \( \mathbf{R} \) 与旋转轴 \( \mathbf{u} \) 相乘：\[ \mathbf{R}\mathbf{u} = \begin{bmatrix} r_1 \\ r_2 \\ r_3 \end{bmatrix} \]

3. 计算 \( \|\mathbf{R}\mathbf{u}\| \)，即 \( \sqrt{r_1^2 + r_2^2 + r_3^2} \)。

4. 将 \( \mathbf{u} \) 代入方程：\[ \mathbf{u} = \frac{\mathbf{R}\mathbf{u}}{\|\mathbf{R}\mathbf{u}\|} \]

5. 解方程，得到旋转矩阵 \( \mathbf{R} \) 的形式。



#3. 四元数的旋转
四元数是一种用于表示三维空间旋转的数学工具。在四元数中，单位四元数通常用于表示旋转。如果你有一个单位四元数 \( q = a + bi + cj + dk \)，其中 \( a^2 + b^2 + c^2 + d^2 = 1 \)，它表示一个三维空间的旋转。

旋转一个向量 \( v = \begin{bmatrix} x \\ y \\ z \end{bmatrix} \) 使用四元数 \( q \) 的公式如下：

\[ v' = qvq^{-1} \]

其中 \( q^{-1} \) 是 \( q \) 的共轭四元数，对于单位四元数 \( q = a + bi + cj + dk \)，其共轭为 \( \bar{q} = a - bi - cj - dk \)。向量 \( v' \) 是旋转后的向量。

假设有一个单位四元数 \( q \) 表示一个绕轴 \( \langle b, c, d \rangle \) 旋转的情况，那么旋转后的向量 \( v' \) 的计算如下：

\[ v' = qv\bar{q} \]

#4. 旋转矩阵、轴角、欧拉角、四元数的转换关系
以下是旋转矩阵、轴角、欧拉角和四元数之间的转换关系。请注意，由于转换涉及到不同的旋转顺序（例如，绕X轴、Y轴和Z轴的顺序），可能有不同的约定和定义。下表中采用的是ZYZ顺序，即绕Z轴、Y轴和再次绕Z轴。

\[
\begin{array}{|c|c|c|c|}
\hline
\text{表示方式} & \text{表达式} & \text{转换关系} & \text{范围/单位} \\
\hline
\text{旋转矩阵} & R & \text{直接定义} & \text{正交矩阵} \\
\hline
\text{轴角} & (\mathbf{k}, \theta) & \begin{aligned} R &= \exp(\theta \mathbf{K}) \\ \text{其中 }\mathbf{K} &= \begin{bmatrix} 0 & -k_3 & k_2 \\ k_3 & 0 & -k_1 \\ -k_2 & k_1 & 0 \end{bmatrix} \end{aligned} & \begin{aligned} \mathbf{k} &\text{：单位向量} \\ \theta &\text{：旋转角度} \end{aligned} \\
\hline
\text{欧拉角} & (\phi, \theta, \psi) & \begin{aligned} R &= R_z(\psi)R_y(\theta)R_z(\phi) \\ &= \begin{bmatrix} \cos\theta\cos\psi & -\cos\phi\sin\psi + \sin\phi\sin\theta\cos\psi & \sin\phi\sin\psi + \cos\phi\sin\theta\cos\psi \\ \cos\theta\sin\psi & \cos\phi\cos\psi + \sin\phi\sin\theta\sin\psi & -\sin\phi\cos\psi + \cos\phi\sin\theta\sin\psi \\ -\sin\theta & \sin\phi\cos\theta & \cos\phi\cos\theta \end{bmatrix} \end{aligned} & \begin{aligned} \phi &\text{：绕Z轴旋转角度} \\ \theta &\text{：绕Y轴旋转角度} \\ \psi &\text{：绕Z轴旋转角度} \end{aligned} \\
\hline
\text{四元数} & q & \begin{aligned} R &= \begin{bmatrix} 1-2(q_2^2+q_3^2) & 2(q_1q_2-q_0q_3) & 2(q_1q_3+q_0q_2) \\ 2(q_1q_2+q_0q_3) & 1-2(q_1^2+q_3^2) & 2(q_2q_3-q_0q_1) \\ 2(q_1q_3-q_0q_2) & 2(q_2q_3+q_0q_1) & 1-2(q_1^2+q_2^2) \end{bmatrix} \end{aligned} & \begin{aligned} q &\text{：四元数} \\ &\text{（单位四元数：} q_0^2+q_1^2+q_2^2+q_3^2 = 1) \end{aligned} \\
\hline
\end{array}
\]

在上表中：

- \( \exp(\theta \mathbf{K}) \) 表示矩阵指数，即将矩阵 \(\theta \mathbf{K}\) 进行矩阵指数运算。
- \( R_x(\phi) \)、\( R_y(\theta) \) 和 \( R_z(\psi) \) 表示绕X轴、Y轴和Z轴的旋转矩阵。
- 欧拉角采用ZYZ顺序，分别表示绕Z轴、Y轴和再次绕Z轴的旋转。
- 四元数表示为 \( q = q_0 + q_1i + q_2j + q_3k \)，其中 \( q_0^2+q_1^2+q_2^2+q_3^2 = 1 \) 表示单位四元数。


#5. 
    Eigen::Matrix4d matrix;

    // 假设matrix已经被赋值

    // 提取左上角的3x3矩阵
    Eigen::Matrix3d submatrix = matrix.block<3, 3>(0, 0);

    // 赋值为单位矩阵
    submatrix.setIdentity();
