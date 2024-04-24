# Rotation
旋转相关的坐标变换内容

## 一、四元数

### 1. 轴角表示

任意一个旋转可以表示为绕某一转轴 $`\vec{k} \in \mathbb{R}^3`$ （单位向量）转过某一角度 $`\theta \in \mathbb{R}`$，这被称为特征旋转，表示两个姿态间的最短旋转

由此物理含义，四元数被定义为：

$$
q = [w \quad x \quad y \quad z]^T = [cos(\theta/2) \quad \vec{k} sin(\theta/2)]^T
$$

### 2. 复数表示

四元数同样具有在复数域内的含义，其中 $`w`$ 为实部，$`x \quad y \quad z`$ 为虚部

虚数单位满足 $`i^2 = j^2 = k^2 = -1`$，$`i j = k`$，$`j k = i`$，$`k i = j`$

$$
q = w + x i + y j + z k
$$

### 3. 基本运算

模：

$$
||q|| = \sqrt{w^2 + x^2 + y^2 + z^2} = \sqrt{cos(\theta/2)^2 + ||\vec{k}||^2 sin(\theta/2)^2} = 1
$$

共轭/逆：

$$
q^{-1} = [w \quad -x \quad -y \quad -z]^T
$$

乘法、加法：同复数运算法则

$$
q_1 + q_2 = [w_1 + w_2 \quad x_1 + x_2 \quad y_1 + y_2 \quad z_1 + z_2]^T
$$

$$
q_1 q_2 = [w_1 w_2 - x_1 x_2 - y_1 y_2 - z_1 z_2 \quad w_1 x_2 + x_1 w_2 + y_1 z_2 - z_1 y_2 \quad w_1 y_2 + y_1 w_2 + z_1 x_2 - x_1 z_2 \quad w_1 z_2 + z_1 w_2 + x_1 y_2 - y_1 x_2]^T
$$

因此有 $`q q^{-1} = 1`$

### 4. 姿态表示与旋转坐标变换

四元数可以表示旋转，对一个姿态 $`p`$ 进行一次旋转，运算上相当于乘上该旋转的四元数：$`p \rightarrow p q`$

一个坐标/一个向量 $`\vec{r}`$，若进行一次旋转，用四元数表示该坐标变换为：$`p(\vec{r}) \rightarrow q p(\vec{r}) q^{-1}`$

其中 $`p(\vec{r})`$ 指的是将三维坐标扩展实部0，变为 $`[0 \quad \vec{r}]^T`$ 的伪四元数

通常用world系向body系的旋转 $`q(q_{WB})`$ 表示姿态

！！！注意，“坐标”本身包含着“相对”的含义，因此对于world系和body系来说，分别理解 $`p(\vec{r}) \rightarrow q p(\vec{r}) q^{-1}`$ 的含义应该为：

world系和body系重合时，world系下有坐标 $`\vec{r}`$ →→→ 机体进行了旋转 →→→ 原坐标仍在world系下表示变为 $`p(\vec{r}) \rightarrow q p(\vec{r}) q^{-1}`$

world系和body系重合时，body系下有坐标 $`\vec{r}`$ →→→ 机体进行了旋转 →→→ 原坐标仍在body系下表示，相对关系未变，还是 $`\vec{r}`$ →→→ $`p(\vec{r}) \rightarrow q p(\vec{r}) q^{-1}`$ 表示body系下的坐标换到world系下表示





