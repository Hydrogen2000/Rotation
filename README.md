# Rotation
旋转相关的坐标变换内容

## 一、四元数

### 1. 轴角表示

任意一个旋转可以表示为绕某一转轴 $`\vec{k}`$（3维单位向量）转过某一角度 $`\theta`$（标量），这被称为特征旋转，表示两个姿态间的最短旋转。

由此物理含义，四元数被定义为：

$$
q = [q_w \quad q_x \quad q_y \quad q_z]^T = [cos(\theta/2) \quad \vec{k} sin(\theta/2)]^T
$$

### 2. 复数表示

四元数同样具有在复数域内的含义，其中$`q_w`$为实部，$`q_x \quad q_y \quad q_z`$为虚部

$$
q = q_w + q_x i + q_y j + q_z k
$$

### 3. 基本运算

模：

$$
||q|| = \sqrt{q_w^2 + q_x^2 + q_y^2 +q_z^2} = \sqrt{cos(\theta/2)^2 + ||\vec{k}||^2 sin(\theta/2)^2}
$$


