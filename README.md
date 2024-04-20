# Physics Informed Neural Networks

The objective of this repository is to use physics-informed neural networks (PINNs) (**Method 1**) and physics-informed regression using linear basis functions (**Method 2**) to solve a forward and inverse heat transfer via conduction in a plate. The problem is assumed to be non-dimensionalized and therefore, no unit is used.  The plate geometry is a square with length $L=1$. The plate is heated with a heat source $q(x_1,x_2)$ centered at $(x_1^{(0)},x_2^{(0)})$. The heat source distribution is approximated by:
$$q(x_1,x_2) = a \exp(-b (x_1-x_1^{(0)})^2-b (x_2-x_2^{(0)})^2), \qquad \text{(1)}$$
where $a$ and $b$ are constants. The plate boundaries are kept at a constant temperature of $T=T_b$.

The steady-state distribution of temperature is governed by
$$k(\frac{\partial^2{T}}{\partial x_1^2}+\frac{\partial^2{T}}{\partial x_2^2})+q(x_1,x_2)=0, \qquad \text{(2)}$$
where $T=T(x_1,x_2)$ is the temperature and $k$ is the plate conductivity. Let us assume we have some noisy temperature measurements at the boundary and at random interior points. Let us also assume that $a=250$, $b=20$, $x_1^{(0)}=\frac{1}{6}$, $x_2^{(0)}=\frac{1}{2}$, $T_b=0$ and $k=0.1$. In the following we adopt the generic notation of $y \leftarrow T$ and $x \leftarrow (x_1,x_2)$.