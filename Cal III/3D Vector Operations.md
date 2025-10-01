
See [[Distance Formulas in 3D]]

**[[Dot Product]]**: 
$\vec{A} \cdot \vec{B} = AB\cos\theta = A_{x}B_{x} + A_{y}B_{y} + A_{z}B_{z}$ 

**[[Cross Product]]**: 

$|\vec{A} \times \vec{B}| = AB\sin\theta$ --> direction by right hand rule

$\vec{A} \times \vec{B} = (A_{y}-B_{z})i_{x} + (A_{z}-B_{x})i_{y} + (A_{x}-B_{y})i_{z}$ **// not actually true, the formula here is wrong**

$\vec{A} \times \vec{B} = \begin{bmatrix}  i_{x} & i_{y} & i_{z}\\  A_{x} & A_{y} & A_{z} \\  B_{x} & B_{y} & B_{z}\end{bmatrix}$

---

Verify that you did cross product right by taking the *dot product* of the output of your cross product which each of the original vectors $\vec{A}$ and $\vec{B}$. The dot product should be 0 because the new vector should be *perpendicular* to both.

---

Note that in problems asking for $\theta$ between 2 [[Vectors]] we can always use the dot product $\vec{A}\vec{B}\cos\theta$ formula to solve for $\theta$ before applying $\vec{A}\vec{B}\sin\theta$

---
You can use the magnitude of the *[[Cross Product]]* to find area within 2 3D [[Vectors]].

Example: Area of triangle $PQR$ at $P=(1, 0 , 0)$, $Q=(0, 2, 0)$, $R=(0, 0 , 3)$ is $\frac{1}{2}|\vec{PR} \times \vec{PQ}|$

