# Rotation
旋转相关的坐标变换内容

## 一、四元数

### 1. 轴角表示

任意一个旋转可以表示为绕某一转轴 $`\vec{k}`$（3维单位向量）转过某一角度 $`\theta`$（标量），这被称为特征旋转，表示两个姿态间的最短旋转

由此物理含义，四元数被定义为：

$$
q = [w \quad x \quad y \quad z]^T = [cos(\theta/2) \quad \vec{k} sin(\theta/2)]^T
$$

### 2. 复数表示

四元数同样具有在复数域内的含义，其中 $`w`$为实部，$`x \quad y \quad z`$为虚部

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
q_1 q_2 = [w_1 w_2 + x_1 x_2 + y_1 y_2 + z_1 z_2 \quad ]
q q^{-1} = 1
$$



