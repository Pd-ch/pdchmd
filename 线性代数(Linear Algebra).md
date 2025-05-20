##### **本文使用deepseek辅助编写**

### **一、线性方程组与矩阵**
#### **例题1：高斯消元法**
**题目**：解方程组  
$$
\begin{cases} 
x + 2y - z = 1 \\ 
2x + y + z = 8 \\ 
x - y + 2z = 5 
\end{cases}
$$
**解法**：  
1. 写出增广矩阵并化为行阶梯形：  
$$
\left[\begin{array}{ccc|c}
1 & 2 & -1 & 1 \\
2 & 1 & 1 & 8 \\
1 & -1 & 2 & 5
\end{array}\right]
\xrightarrow{R_2-2R_1, R_3-R_1}
\left[\begin{array}{ccc|c}
1 & 2 & -1 & 1 \\
0 & -3 & 3 & 6 \\
0 & -3 & 3 & 4
\end{array}\right]
$$
2. 发现第三行矛盾（$0=1$），故方程组无解。

---

### **二、行列式**
#### **例题2：行列式计算**
**题目**：计算行列式  
$$
\det(A) = \begin{vmatrix}
1 & 2 & 3 \\
0 & 4 & 5 \\
0 & 0 & 6
\end{vmatrix}
$$
**解法**：  
- 上三角矩阵的行列式等于对角元乘积：  
$$
\det(A) = 1 \times 4 \times 6 = 24.
$$

---

### **三、向量空间**
#### **例题3：线性相关性**
**题目**：判断向量组 $\mathbf{v}_1 = (1,2,3)$, $\mathbf{v}_2 = (4,5,6)$, $\mathbf{v}_3 = (7,8,9)$ 是否线性相关。  
**解法**：  
1. 构造矩阵 $A = [\mathbf{v}_1^T \ \mathbf{v}_2^T \ \mathbf{v}_3^T]$，求行列式：  
$$
\det(A) = \begin{vmatrix}
1 & 4 & 7 \\
2 & 5 & 8 \\
3 & 6 & 9
\end{vmatrix} = 1(45-48) - 4(18-24) + 7(12-15) = 0.
$$
2. 行列式为0，向量组线性相关。

---

### **四、线性变换**
#### **例题4：矩阵表示**
**题目**：线性变换 $T: \mathbb{R}^2 \to \mathbb{R}^2$ 满足 $T(1,0) = (2,3)$，$T(0,1) = (-1,4)$，求 $T$ 的标准矩阵。  
**解法**：  
- 标准矩阵的列为 $T$ 对基向量的作用结果：  
$$
A = \begin{bmatrix}
2 & -1 \\
3 & 4
\end{bmatrix}.
$$

---

### **五、特征值与特征向量**
#### **例题5：对角化**
**题目**：矩阵 $A = \begin{bmatrix} 4 & 1 \\ 2 & 3 \end{bmatrix}$ 是否可对角化？若可，求对角矩阵 $D$ 和可逆矩阵 $P$。  
**解法**：  
1. 求特征值：  
$$
\det(A-\lambda I) = \begin{vmatrix}
4-\lambda & 1 \\
2 & 3-\lambda
\end{vmatrix} = \lambda^2 -7\lambda +10 = 0 \Rightarrow \lambda = 2, 5.
$$
2. 求特征向量：  
   - $\lambda=2$：解 $(A-2I)\mathbf{v}=0$ 得 $\mathbf{v}_1 = (1,-2)^T$。  
   - $\lambda=5$：解 $(A-5I)\mathbf{v}=0$ 得 $\mathbf{v}_2 = (1,1)^T$。  
1. 构造 $P$ 和 $D$：  
$$
P = \begin{bmatrix}
1 & 1 \\
-2 & 1
\end{bmatrix}, \quad D = \begin{bmatrix}
2 & 0 \\
0 & 5
\end{bmatrix}.
$$

---

### **六、内积空间**
#### **例题6：施密特正交化**
**题目**：对向量组 $\mathbf{u}_1 = (1,1,0)$, $\mathbf{u}_2 = (1,0,1)$, $\mathbf{u}_3 = (0,1,1)$ 进行正交化。  
**解法**：  
1. $\mathbf{v}_1 = \mathbf{u}_1 = (1,1,0)$。  
2. $\mathbf{v}_2 = \mathbf{u}_2 - \frac{\langle \mathbf{u}_2, \mathbf{v}_1 \rangle}{\langle \mathbf{v}_1, \mathbf{v}_1 \rangle} \mathbf{v}_1 = (1,0,1) - \frac{1}{2}(1,1,0) = \left(\frac{1}{2}, -\frac{1}{2}, 1\right)$。  
3. $\mathbf{v}_3 = \mathbf{u}_3 - \frac{\langle \mathbf{u}_3, \mathbf{v}_1 \rangle}{\langle \mathbf{v}_1, \mathbf{v}_1 \rangle} \mathbf{v}_1 - \frac{\langle \mathbf{u}_3, \mathbf{v}_2 \rangle}{\langle \mathbf{v}_2, \mathbf{v}_2 \rangle} \mathbf{v}_2$（继续计算略）。

---

### **七、二次型**
#### **例题7：正定性判定**
**题目**：判断二次型 $Q(x,y,z) = 2x^2 + 3y^2 + z^2 - 4xy$ 是否正定。  
**解法**：  
1. 写出矩阵 $A = \begin{bmatrix} 2 & -2 & 0 \\ -2 & 3 & 0 \\ 0 & 0 & 1 \end{bmatrix}$。  
2. 检查顺序主子式：  
   - $D_1 = 2 > 0$，  
   - $D_2 = \begin{vmatrix} 2 & -2 \\ -2 & 3 \end{vmatrix} = 2 > 0$，  
   - $D_3 = \det(A) = 2 > 0$。  
1. 所有主子式为正，二次型正定。

---

### **八、数值应用**
#### **例题8：LU分解**
**题目**：对矩阵 $A = \begin{bmatrix} 2 & 4 & -2 \\ 4 & 9 & -3 \\ -2 & -3 & 7 \end{bmatrix}$ 进行LU分解。  
**解法**：  
1. 通过高斯消元得到：  
$$
L = \begin{bmatrix}
1 & 0 & 0 \\
2 & 1 & 0 \\
-1 & 1 & 1
\end{bmatrix}, \quad U = \begin{bmatrix}
2 & 4 & -2 \\
0 & 1 & 1 \\
0 & 0 & 4
\end{bmatrix}.
$$
2. 验证 $A = LU$。